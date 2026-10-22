# Chat History - ace-run (research.4q.grk)

- **TIMESTAMP:** 2026-10-17 16:10:28 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.4q.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_154710.md`

## Prompt

%id(grk, clan=research.4q)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 4-researcher swarm.
The other researchers, `research.4q.cdx`, `research.4q.cld`, `research.4q.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you reassess the solution proposed by the
merge_queue_fenced_master_and_exact_sha_releases.md file in the research sidecar repo,
make any changes to its requirements (in the new report your create) that you think are
warranted (but clearly call these out), and then recommend whether or not this work
should be a single epic or multiple epics with justification and indepent epic
verification steps if you think that multiple are warranted? 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll start by reading the research and artifact skills, then open the research sidecar so I can reassess the merge-queue proposal independently.

I'll open the research sidecar through `sase repo open` and pull the artifact, CI, and glossary notes this reassessment depends on.

The research sidecar is open. Next I’ll locate the source proposal, read it as an artifact, and inspect related CI and release code.

I'll read the research-repo instructions, then pull the source proposal through `sase artifact read` so the reassessment stays audited.

I have the proposal’s outline. Next I’ll read the rest of it, then check related prior research and the current CI/release code.

I have the proposal. Next I’ll independently verify workflows, the landing path, and live CI/release state against it.

I have independent measurements and a clear epic split. Next I’ll write the report under a new `__grk.md` name so it doesn’t overwrite the original.

Keep the proposed architecture (native merge queue, exact-SHA publish, trustworthy gate). Split the work into **three epics**. Do not ship it as one epic, and do not put “publish 0.18.0” in any of them.

Report: `research:202610/merge_queue_fenced_master_requirements_and_epic_split__grk.md`  
Snapshot: `file:explicit:4a38734b5048aa385aa13e8c`

The original proposal is still right about the hole: `master` has no protection, agents rebase-and-push without testing the combined tree, `publish.yml` builds whatever `master` is at job start, and Full CI is 0/30 in this sample. A GitHub merge queue with zero approvals is the fence. A host-side `just check` lane is not.

Independent checks from this checkout (`60718e5b1b`) and live GitHub/PyPI:

- Protection 404, rulesets `[]`, PyPI still `0.17.1` (49 days), PR #299 still open
- Master Gate last 97 completed runs: **9.3%** pass, p50 **12.5 min**, ~**53** landings/day, **42%** overlap
- Newest completed gate failed on a **single shard** with lint/docs/other shards green
- `allow_auto_merge` is **false** (the queue path needs it on)
- `visual-test` is a 45-minute Full CI job; Master Gate jobs are contract-capped at 20 minutes
- `ci.yml` `workflow_call` has **no `ref` input** and uses `ci-${{ github.ref }}` with `cancel-in-progress: true`

**Requirement changes** (called out in the report):

- Do not fold `visual-test` / 3.13 / 3.14 / perf-floors into the merge gate
- Do not include shipping 0.18.0 (`sase-1lh` already owns that)
- Qualification must be SHA-keyed; it must not share Full CI’s cancel group
- Defer tag rulesets until landings use a non-maintainer identity
- `ci-two-speed-split`’s reopen trigger is only partly met; replace the merge-queue *clause* because the rejected alternatives no longer apply
- Pilot merge limit **1**; 3% false-red is an **enforcement** gate, not a pilot gate
- Agent landings are `builtin@commit` push, not sase-github `gh pr merge`

**Three epics**

1. **Exact-SHA PyPI qualification** (S–M) — build, qualify, and publish one SHA. Unblocks honest releases while `master` is still red.
2. **Trustworthy Master Gate** (M) — one in-job rerun, expiring quarantine, `.python-version`, core-parity fail-fast. Parallel with epic 1.
3. **Merge-queue landing fence** (L) — scratch rehearsal, `merge_group` + `integration-ready`, flagged queue mode, sase-core landing records, empty-bypass cutover. Pilot can start in parallel; **enforcement** waits on epic 2’s flake SLO.

One epic would mix a publish-pipeline change, test-infra SLO work, and a distributed landing state machine, and it would collide with `sase-1lh`. Each epic has independent verification steps in the report (contract tests and a historical-SHA publish drill for epic 1; flake/quarantine fixtures for epic 2; scratch-repo then allowlisted pilot then enforcement for epic 3).
