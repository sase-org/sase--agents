# Chat History - ace-run (research.4v.cld)

- **TIMESTAMP:** 2026-10-19 07:43:51 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4v.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071316.md`

## Prompt

%id(cld, clan=research.4v)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4v.cdx`, `research.4v.grk`, `research.4v.mus`, `research.4v.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add pi (see the https://github.com/earendil-works/pi GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to pi that you should review if you
can find it. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I found the earlier pi research (`202610/sase_for_pi_users`). Next I'll read it through the audited artifact path, then look at the pi repo and sase's provider layer.

Prior research read. Now mapping sase's provider layer, starting with how the most recent providers (OpenCode, Qwen) were added.

Spawning a helper to inventory every touchpoint a new provider needs, while I read pi's integration docs and sase's provider interface myself.

I'm reading the Grok provider (the newest, most complete template) and the shared subprocess and stream helpers, to see exactly how a pi adapter would plug in.

Underscore skill names only warn; pi still loads them. Next I'm checking how pi reads a prompt from stdin, since large sase prompts can exceed Linux's 128 KiB argv limit.

Pi's bash tool has no default timeout, which suits sase's long foreground commands. Checking whether sase's mid-run interrupt plumbing has been revived since the earlier research.

No pi beads exist yet. Next I'll check whether pi ships a credential-free test model, so I can capture a real JSON event stream instead of relying only on docs.

Local Node is 22.14 and pi requires ≥22.19, so I won't install and run pi. I'll rely on its source and tests, which are authoritative for the event contract.

Pi's invoke result can only carry token counts, not dollar cost. Checking whether sase's usage artifacts have anywhere to put pi's priced cost, and how session resume works for other providers.

Pi aliases its own dependencies for extensions, so sase could ship a single `.ts` extension file as package data with no npm step. Checking the hook result types next.

I'm checking the remaining sase-side specifics: interactive tmux menu keys, and how `#fork`/`#resume` carry conversation history across providers.

Next I'll read the decision records my recommendation must respect (adapter normalization, single-turn, instruction delivery, helper rules) through the audited memory reader.

Pi ships a scripted `faux` model provider for its own tests. If an extension can register it, sase could record real JSON-mode fixtures without credentials. Checking that.

No native cross-turn provider resume exists in sase today; continuity is text injection, so native pi fork belongs in a later phase. Looking at how per-provider single-turn directives are registered.

I have enough on both sides. Checking the research repo's conventions before writing the report.

I have everything I need. Verifying the release dates I'll cite, then writing the report.

Research is complete. Writing the report to the research repo now.

Report written. Verifying the source line numbers I cited before registering it.

Two small fixes: the skills.ts line (329, not 323) and a more precise description of when an id triggers pi's y/N prompt.

Now registering the report as a durable artifact snapshot.

The report is registered. Now submitting the turn's final declaration.

I wrote the report and registered it as a durable artifact (`file:explicit:3a7d668f0a60e3fbef4d22ef`). The commit to the research repo is declared and will land when the turn ends. Pi isn't installed on athena, so I didn't run it; every pi claim is checked against its source and docs at the latest commit (1.3.0). The report's Phase 0 is a half-day live test to close that gap.

**Recommendation:** build pi as a built-in provider, modelled on the Grok and Qwen adapters, that runs `pi --mode json` once per sase invocation. That mode takes the prompt up front, streams events and exits, which fits sase's one-turn-per-run rule. No sase-core (Rust) changes are needed, because Rust has no hardcoded provider list.

**What the earlier pi research (`sase_for_pi_users`) gets wrong or misses:**
- **Instructions:** it said pi's own `AGENTS.md` loading was enough. On athena that loads the SASE contract twice, because pi reads both the project `AGENTS.md` and `~/AGENTS.md` and both contain it. Pi can switch that loading off (`-nc`) and take the instruction bundle as a file (`--append-system-prompt <file>`), so it should join Claude, Codex, Grok and Muse on explicit delivery.
- **Resuming sessions:** `--session <path>` reopens a session in the directory recorded inside it, not the current one. A follow-up turn in `sase_14` would run its tools against `sase_13`. Follow-up turns must use `--fork <path> --session-id <new>`.
- **Exit codes:** in JSON mode a failed, aborted or cut-off model response, or missing credentials, still exits 0. The adapter has to judge success from the event stream and report failure itself so sase's retries still work.
- **Skill names:** pi warns about underscores in skill names (every sase skill uses them) but still loads them.

**Other key design points:**
- **Keep the user's pi as it is:** add a `pi-default` model tier that omits `--model` so pi uses the user's own default. Keep their extensions, MCP servers and project-trust decisions, and re-add the two files the explicit flags would drop (`~/.pi/agent/AGENTS.md` and `APPEND_SYSTEM.md`).
- **Prompt and cost:** send the prompt on stdin to avoid the 128 KiB argument limit, and record pi's dollar cost and the model that actually answered in `run_metadata.json`.
- **Usage limits:** turn off sase's automatic provider disable for pi at first. It disables a whole provider at once, and one vendor's limit would block every pi route.
- **Phase 2, enforcement:** ship a small TypeScript pi extension inside the sase package. It would nudge the agent once if it ends without a final declaration and block `git commit`/`gh pr`. Pi also sets `PI_SESSION_ID` on every bash command, so sase can check that only the root agent declares. That meets the reopen condition of the `helpers-return-roots-declare` decision and would need a new decision record.
- **Deferred or rejected:** RPC mode waits for a later steering/live-control epic. I rejected an SDK bridge, print mode and a separate plugin repo, since a plugin would lose `models.yml` and the other built-in tables.

The report lists every file the provider touches, a risk table, and the full example command line.

**Questions for you:**
- **Default model:** should a pi run use the user's own pi default (`pi-default`, which I recommend) or a model sase picks? A sase-picked model fails for anyone without that vendor's credentials.
- **User extensions:** should sase runs load the user's pi extensions by default (my recommendation) or none?
- **OpenCode:** pi now covers OpenCode's multi-vendor role. Should we revisit OpenCode once pi has usage data?

Files are in `sase/repos/research/202610`:
- pi_llm_provider_implementation__cld.md
