# Chat History - ace-run (research.1p.cld)

- **TIMESTAMP:** 2026-09-09 08:23:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1p.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260909_080224.md`

## Prompt

%id(cld, clan=research.1p) %m:@opus_or_grok 
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1p.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I think that I have the Apollo machine set up correctly to
work with sase's new remote dispatch feature (see the sase-xe epic bead for context).
I'm not seeing any agents on the Fleet tab, however, even though there are several done
agents showing on the Apollo machine. There are a few open beads still associated with
this epic that are in progress now but I do not think any of them address this issue
directly.

Can you do some research with the goal of helping me understand what's causing this
issue, whether or not we can expect these issues to be fixed by the agents working the
corresponding open beads, and what action we should take otherwise? End your analysis
with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll start by understanding the sase-xe epic and the remote dispatch feature.

Research complete and registered.

**Report:** `sase/repos/research/202609/fleet_tab_shows_no_apollo_agents__b.md`
**Artifact:** `file:explicit:b9ae70a15789da7c18cbf16c` (label `research:202609/fleet_tab_shows_no_apollo_agents__b.md`)

## What's actually wrong

Your Apollo setup is fine. I pulled **100 live Apollo rows** (152 matching, 48 DONE) over the tailnet during this session. The gateway, Serve, credentials, and the federation worker all work. The rows are even sitting in `~/.sase/fleet/worker_cache.json`.

The Fleet tab is empty because the Python code that turns federation responses into TUI rows was written against a wire shape **no Rust code has ever produced**:

1. **`_FLEET_CATALOG_LIMIT = 250`** but `sase-core` caps a page at 100 → every TUI catalog read comes back `invalid_request`, `payload: None`.
2. **`summary_payloads()` never opens the `payload` envelope.** The worker returns `hosts[i].payload.page.rows`; the Python looks for `summaries`/`agents`/`rows` directly on the host. I fed it a *fully successful* 100-row response — it projected **0 rows**.
3. **`include_terminal` appears nowhere in the sase Python codebase**, so the gateway filters out all done/failed rows. Even with 1 and 2 fixed you'd see 2 rows, not your done agents.
4. **The failure is silent** — per-host `status`/`error` are never read, so you got `"1 machine · 0 results"` instead of the real error. The parent plan explicitly forbids this ("never an empty 'successful' catalog").
5. The Rust counts binding gets the same wrong shape, raises, and is swallowed by a bare `except`.
6. Patching 1–3 in-process yields 100 rows — but every agent is named `attempt-0` with `provider: None`, because the row adapter also mis-models `ResolvedAgentSummaryWire` (treats `content` metadata as an agent-info blob, `lifecycle`/`liveness` strings as mappings, ignores `labels`).

Two things make this unambiguous rather than judgement: `_attention_entries_from_host()` in the *same module* reads `host["payload"]` correctly, and `ops/commands/machine.py:141` descends `payload.page.rows` and sends `limit: 100`. The CLI path works; the TUI path never did.

**Why tests are green:** `tests/ace/tui/fleet_fixture.py` (the `sase-xe.16.7` "offline fixture") invents the host shape, and `test_dispatch_federation.py` mocks the worker with the same fiction. No contract test binds the projection to the real wire.

## Will the open beads fix it?

**No.** Grepping the whole `sase-xe.16.11` plan for `payload`/`catalog`/`rows`/`projection` turns up nothing. `.3` and `.4` don't touch it. `.5` (live acceptance) is the only phase that *must* hit it — but it's last in the dependency chain, and the plan's own constraints ("record outside-scope findings as `PROPOSED FOLLOW-UP:`", "leave work open on failure") steer a worker toward a blocker note, not a repair.

## Recommendation

Land a dedicated fix phase in `sase-xe.16.11` **before** `live-apollo-acceptance`, not a standalone task bead. Normalize the host envelope in `sase-core` (the CLI duplicates that traversal today, so it's shared backend behavior per `rust_core_backend_boundary`), fix the row adapter against `ResolvedAgentSummaryWire`, derive the limit from `FLEET_READ_MAX_PAGE_ROWS`, set `include_terminal: true`, surface per-host errors — and regenerate the fixture from real worker output. **The contract test is the real deliverable**; the six defects are cheap to fix and were only expensive to find.

Two loose ends in the report: `sase machine agent`/`attention` also can't target done remote agents (same `include_terminal` gap), and athena's `/tmp` is a 32 GB tmpfs at 100% full from stale per-workspace cargo target dirs — it broke tool output mid-session and will bite other agents.
