# Chat History - ace-run (research.4u.mus)

- **TIMESTAMP:** 2026-11-15 17:02:26 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.4u.mus
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261115_164459.md`

## Prompt

%id(mus, clan=research.4u)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.4u.cdx`, `research.4u.cld`, `research.4u.grk`, `research.4u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

It doesn't seem like agent hijacks are working correctly. See the
~/tmp/screenshots/20261115_164112.png screenshot, which was taken on the apollo machine,
for context. Agent hijacks should work on as many types of sase turns (in as many
states) as possible. I would like to fix this issue and make agent hijacks much more
resiliant / dependable in general.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Research complete. Report written and registered:

- [agent_hijack_resilience_coverage__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202611/agent_hijack_resilience_coverage__mus.md) — registered as artifact `explicit:5a508d1ceed47b8b1d9cd986` (`research:202611/agent_hijack_resilience_coverage__mus.md`). Final declaration accepted; host will commit the research repo.

Top finding: the screenshot toast is a symptom of two deeper defects. **P0, verified live:** the runner's `runner_capabilities: ["hijack"]` stamp (written early in `_write_bootstrap_agent_meta`) is wiped milliseconds later when `extract_directives_and_write_meta` publishes a fresh `build_agent_meta` dict via complete-replacement `write_agent_meta_atomic` — `preserved_agent_metadata` doesn't carry the key. All ~30 live `agent_meta.json` files on apollo have `runner_capabilities: null`, and hand-walking the Rust `agent_hijack_eligibility` over the live `tailnet-t.10--6` facts (RUNNING, ws 10, live pid, not gate/monitor) ends at `missing_capability` ("launched before hijack support; use x") — for a turn launched minutes ago. Unit tests mask it by hand-injecting the capability. Second, the TUI toast names no reason: `agent_can_offer_hijack` and the Rust precheck are two divergent policies, so the UI can't distinguish a container-row misclick from a transient STARTING state from a real policy refusal.

Verdict and recommendation: hijack is the right feature and the fix-not-revert call stands, but I argue against blanket "hijack every turn type in every state" — gate/monitor turns, local hijack of remote rows, home `#0`, procs, and bulk should stay out (each with a named alternative), while workflow-typed LLM rows, STARTING transients, and WAITING/QUEUED waiters (via wait-cancel-with-snapshot) should be widened. The report gives a full coverage matrix, stop/recovery resilience gaps (`stop_failed` has no retry, `resolving` has no watchdog, remote rows have no tracked referral), five explicit requirement adjustments, and a phased plan: Phase 0 unbreaks the happy path (preserve the capability + real-bootstrap regression test), Phase 1 unifies eligibility and makes refusals carry `code` + next action, Phase 2 widens where safe, Phase 3 explicitly not built.
