# Chat History - ace-run (research.2i.cld)

- **TIMESTAMP:** 2026-09-24 15:04:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2i.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_142941.md`

## Prompt

%id(cld, clan=research.2i)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.2i.cdx`, `research.2i.mus`, `research.2i.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about moving
forward with the E3 and E4 epics described in the sase_tool_epic_roadmap.md file in the
research sidecar repo now that E2 (see the sase-17p epic bead) is almost complete. Can
you do some research with the goal of helping me determine if these epics are still
correct and appropriate? Should we make any changes to the epic? Flesh these epics out
enough that the epic landing criteria for both of these is crystal clear (the sase
agents that plan/implement/land these epics are likely to read this research). 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Reading the roadmap's sibling reports and the current state of E1/E2 before assessing E3/E4.

Now reviewing the later E1 research, guarded-recipes decisions, and the actual bead state for E1/E1.5/E2.

Now checking the later guarded-recipes research (2026-09-22) for any roadmap revisions it proposed for E3/E4.

Key finding so far: `check` fails ~76% of the time on the ledger (red master), which directly affects E4's pass-only receipts. Now inspecting the landed code and the live ledger to measure.

Now measuring the live athena ledger: failure rates, which stages fail, and how often an unchanged fingerprint repeats (E4's hit-rate evidence).

Pulling stage timelines for all ~640 recorded runs (read-only, parallel) to see which stages fail and how often.

Striking: 55% of failed `check` runs die at `lint (symvision)`, and the lint prefix (not the test stage) dominates runtime. Now measuring fingerprint repeats for E4.

Many `ci` beads (sase-zk, -10n, -150, -15c, -16m) track the same master-red lint items, and sase-180 already names "masked stages." Reading those beads.

Measuring current monitor `--next` prose lengths on athena (the E3 "structured continuation" target).

Measuring whether hand-offs fail fast at lint on athena (the E4 "cheap stages before hand-off" premise), and whether host completion consumes any verification proof.

Now reading the `lint_and_test` memory to see how agents are currently told to handle pre-existing failures (E3 must change that guidance).

Checking how often the scoped test stage actually executes inside `check` (masking impact).

Only 21% of `check` runs actually executed the scoped tests; 76% of agents' final `check` never ran them. Estimating the extra machine cost of a keep-going mode.

Testing feasibility of automatic owner-bead linking: do open beads mention the top recurring failure tokens?

Owner-linking by text match works but is noisy (hits closed phases/plans), so it must stay "suggested". Reading `cli_rules` so my proposed verbs conform.

I have the core evidence. Before writing, I'll file the discovered linked-repo identity bug as a task bead (required skill first).

No duplicate and no causal in-progress epic (the defect dates from E1/E1.5, both closed). Checking the `bug` task type's required fields.

Filed **sase-182** (bug, medium, ready). Now running a quick chronological backtest of the KNOWN-witness rule I plan to recommend, using only past evidence per run.

Checking whether the normal `/sase_final` path gates on verification at all (relevant to E4's re-scope).

Evidence gathering is complete. Writing the report now.

Fixing two small factual slips (the E1.5 close date in local time, and the 09-23 run count).

Now registering the report as a durable artifact.

Registered. Linking the report to the bead I filed, then finalizing the turn.

I wrote the report and registered it as `research:202609/sase_tool_e3_e4_readiness__cld.md` (artifact `file:explicit:22204af0937bf9499732111a`). It's based on athena's ToolRun ledger: 638 runs over 4.2 days, each run's stage timeline, fingerprints and logs. I didn't measure apollo or mac.

## E3 (failure triage): yes, start it now, with three changes

It's more valuable than the roadmap assumed, but its motivating workload has moved:

- **Target `check`, not `check-full`.** Since the check-full-is-explicit decision, athena recorded one `check-full` run in four days, against 488 `check` runs.
- **Add a way past failures that aren't the agent's.** 85% of sase `check` runs fail, and 55% of those stop at `lint (symvision)`. In 79% of those, every flagged symbol is in a file the run's own diff never touched. The same symbols fail for 23–28 different agents.
- **Why that matters:** `just check` stops at the first failing stage, so the scoped tests ran in only 21% of runs. 76% of agents finished on a run whose tests never executed, and only 11% finished on a passing run. Your bead `sase-180` describes the same problem. E3 should continue past a stage only when all its failures are KNOWN or FLAKY, and it must never turn a failure into exit 0.
- **Make precision a landing gate.** I replayed the ledger using only earlier evidence. 72% of failure items would be labelled KNOWN, 7% NEW and 21% UNKNOWN, and 47% of failed runs would get a "no NEW failures" verdict. A wrong KNOWN label tells an agent to ignore its own bug, so landing requires a hand-audited sample of at least 50 KNOWN labels with at least 95% correct.

I'd also drop `rerun` from E3 (it conflicts with E2's rule that a run id executes at most once), and drop the "shorter `--next` prose" exit metric (it no longer measures anything E3 changes).

## E4 (receipts and reuse): no, not as written

Its own go/no-go measurement is now possible, and it comes out negative:

- **Reuse:** zero of 518 fingerprinted runs re-ran a tree that had already passed, so pass receipts would have saved nothing.
- **Refusing to rerun an unchanged failure:** in sase-core it would have been wrong 9 times out of 11, because the tests are flaky.
- **"Cheap stages first":** false here. The lint stages take about 4.3 minutes; the scoped tests take 52 seconds.
- **Hand-offs:** the fastest failing one took 87 seconds, so there's no fast lint failure to catch before handing off.
- **`install` skip:** agents don't run `install` through `sase tool run`; one run was recorded in four days.
- **Fingerprints miss inputs** (ruff and mypy versions per `sase-vr`, plus bead-store state), so receipts wouldn't be safe yet.

What still holds up is the receipt as proof that an exact tree was verified, with host completion as the consumer. Prepared completion has committed nothing since E1 (6 uses, 0 commits), because it needs a green `check`. My recommendation is to re-scope E4 so host completion can commit on a "no NEW failures" verdict for the exact tree that was verified. Reuse would only be measured in shadow mode, becoming its own epic if it shows at least 2 hours a week of savings. E4 should be planned after E3, since it depends on E3's verdict. If you don't want host completion accepting "no NEW failures", defer E4 instead; nothing in E5–E8 depends on it.

The report defines each epic's phases and numbered landing criteria (11 for E3, 7 for E4), none of which require a green master.

## Filed

**`sase-182`** (bug, medium, ready): runs from the linked repos (sase-core, telegram, github, research-artifacts) are recorded under the sase project's identity. 51 runs on athena are mislabelled this way, because the project name comes from the agent's environment rather than the repo whose catalog ran. Both epics key their evidence on that identity, so this should be fixed before E3's classification phase.

## Decisions for you

1. **Continuation default:** continue automatically only past KNOWN failures (my recommendation), always continue (about 29% more `check` time), or make it opt-in only.
2. **Commit on "no NEW failures":** should host completion ever commit when only KNOWN failures remain? This decides between re-scoping E4 and deferring it.
3. **Decision record:** record "triage annotates; it never changes an exit code, and KNOWN needs an independent witness" now, or at E3 landing?
4. **Owner beads:** show them as suggestions only (my recommendation), or leave bead linking out of E3 v1?
5. **Roadmap update:** should the roadmap's E3 and E4 rows be amended to match?

The report and the bead are committed through the host.
