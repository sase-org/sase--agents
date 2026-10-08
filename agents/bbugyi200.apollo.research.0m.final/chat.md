# Chat History - ace-run (research.0m.final)

- **TIMESTAMP:** 2026-10-08 12:46:07 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0m.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_120330.md`

## Prompt

%clan(research.0m, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
want to make the `%auto` directive much more configurable, intuitive, and more powerful
in general.

- I agree with all of the recommendations made by the auto_directive_autonomy_policy.md
  and auto_autonomy_profiles_ux.md files in the research sidecar repo, which you should
  review before performing your own research.
- I think that we would likely benefit from splitting this work up into multiple epics,
  but I would only want to do this if it is possible (without jumping through too many
  hoops) to do so in such a way that each epic could have distinct, verifiable results.

Can you do some research with the goal of helping me decide the best way to split this
work up into multiple epics? End your analysis with a recommended set of verifiable
epics (focus on the high-level plan, but epic phases MAY be recommended). If you think
that it is not necessary to split this work up into multiple epics, say so instead of
recommending a split (justify why).]]) %id:research.0m.final %m:@xlarge
%wait:research.0m.cdx %wait:research.0m.cld %wait:research.0m.grk %wait:research.0m.mus %wait:research.0m.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
want to make the `%auto` directive much more configurable, intuitive, and more powerful
in general.

- I agree with all of the recommendations made by the auto_directive_autonomy_policy.md
  and auto_autonomy_profiles_ux.md files in the research sidecar repo, which you should
  review before performing your own research.
- I think that we would likely benefit from splitting this work up into multiple epics,
  but I would only want to do this if it is possible (without jumping through too many
  hoops) to do so in such a way that each epic could have distinct, verifiable results.

Can you do some research with the goal of helping me decide the best way to split this
work up into multiple epics? End your analysis with a recommended set of verifiable
epics (focus on the high-level plan, but epic phases MAY be recommended). If you think
that it is not necessary to split this work up into multiple epics, say so instead of
recommending a split (justify why).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.0m.cdx`, `research.0m.cld`, `research.0m.grk`, `research.0m.mus`, `research.0m.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.0m.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0m.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

Reading the prior policy and UX reports first, then the five researcher reports.

Now the five researcher reports.

Verifying bead status and code claims (existing related beads, epic-size mechanics, tier-mismatch path).

Still verifying: checking how a tier-mismatch error surfaces at gate creation (determines whether the D7 stopgap is tale-sized).

Still checking epic-size data via the bead CLI (the store isn't cloned here).

`sase-1hg` already scopes Rust/LSP parity. Checking the in-flight beads cld flagged as file collisions.

Telegram-touching epics nested 52% of the time in my count (11/21; cld got 39%). The sample is small, but the direction agrees. Checking grk's "legend" concept and how epics chain.

Checking the e2e test seams cdx cited, since the per-epic acceptance gates would reuse them.

Research is done. Now moving the five reports into a new topic directory in my research checkout and writing the consolidated report.

Before writing, one quick check: the baseline maps `%auto:plan` to bare `standard`, but the epic adapter's allowed set excludes `plan`.

Writing the consolidated report now.

Report written. Registering it as a durable artifact for the linker.

Layout is correct. Now the final declaration.

My recommendation is to split the work: ship a few small safety fixes as standalone tasks now, then run three committed epics. A fourth epic is optional, and a fifth waits until there's demand. Each epic ends in one result you can demonstrate and the land agent can check with tests, and no temporary feature flag carries over from one epic to the next.

**Why split instead of one epic.** The whole program is about 20 phases across sase, sase-core and sase-telegram. I recounted this repo's own epic history (it roughly matches the cld researcher's figures):

| Closed epics, Aug–Sep | Median time to close | Needed a "Finish…" child epic |
|---|---|---|
| 5–6 phases | 4.9 h | 11.6% |
| 9+ phases | 22.5 h | 55.6% |

The closest precedent, Plan Decisions (9 phases), needed a 6-phase repair epic. A plan can also carry at most five Plan Decisions, and the two accepted reports leave about ten open. Some of those defaults should be chosen from real usage data, and an epic can't pause midway to collect it.

**The extra overhead from splitting is small:**
- one "sunset" flag that keeps the old `%auto` state readers working while running agents drain;
- one Rust-first phase per epic (the sase-core revision pin updates automatically when a turn commits both repos);
- `%auto(...)` is rejected at first and gets a meaning later;
- epic workers emit `%auto:tale` at first, and that later moves into config roles with the same behavior;
- one table-driven test suite of expected `%auto` behavior that every epic extends.

**Recommended set:**

| # | Unit | Result you can check | Phases |
|---|---|---|---|
| P0 | Safety tasks: `sase-1hg`, `sase-1hh`, `sase-15s`, plus two new ones (epic workers park nested epics; question guidance) | No `%auto` spelling grants more than it says, turning auto off really turns it off, and epic workers stop auto-launching nested epics | 5 tasks |
| E1 | One autonomy record | One Rust evaluator decides every automatic gate from one live session record. `sase autonomy explain` predicts each decision exactly, every decision is logged, and the state survives every follow-up turn. No other behavior change | 6 medium |
| E2 | See it, stop it | Every surface names the agent's profile in the same words, epic launches ring with Manual and Pause buttons, and a host-wide Pause makes every future gate wait | 5 |
| E3 | Named profiles | Choose `attended`, `overnight` or your own profile, found through `%auto` completion and the `,a` picker. Generated workers run under config roles, and prompts can narrow autonomy but never grant it | 6 |
| E4 | Steer from anywhere (optional) | Change a live agent's profile from the TUI, CLI or Telegram, with conflicting edits refused | 3 |
| E5 | Bounded delegation (deferred) | Config-armed child launches with a budget that retries and fan-out can't exceed | ~4 |

Order: P0 → E1 → E2 → E3, then E4 and E5 only if their triggers fire. E2 and E3 each depend only on E1, so they can run in parallel if you want profiles sooner. I'd do E2 first and plan E3 after about a week of E1's decision log, since E3 asks you to pick defaults.

**Points where I overruled or corrected the researchers:**
- **Safety fixes as tasks, not an epic.** Three are already filed and ready, and the nested-epic fix shouldn't wait for a plan review. Bringing auto state through gate and pipe follow-ups goes into E1 so the state isn't migrated twice. Only the `%auto` half of `sase-11g` moves; its `%queue` half stays on that bead.
- **The new record and its TUI/Telegram visibility are separate epics.** Combined they come to about 10 phases, the size bucket that most often needs a repair epic. The brake goes in E2 because it needs no profiles and the Pause button depends on it.
- **The worker fix is bigger than it looks.** `%auto:tale` on an epic plan currently makes `sase plan propose` exit 1. So making epic workers emit `%auto:tale` only works together with turning that tier mismatch into "ask" at three call sites.
- **`%auto:plan` doesn't behave like bare `%auto`.** Today it acts like `%auto:tale`, but the policy report maps it to `standard`, which would let it launch epics. I recommend mapping it to `tale`; recent usage of it is zero.
- **The parse fix needs Rust too.** The Rust launch parser also ignores keywords inside `%auto(...)`, so the mus researcher's "Python-only" claim was wrong.
- **Most auto-launched epics now come from your own prompts.** In October, 21 of 26 came from top-level agents and workflow workers, not epic workers. "Should bare `%auto` keep auto-launching top-level epics?" therefore becomes an E3 decision best answered from E1's log.
- **Rejected:** the gem researcher's split by surface. It ships profiles with no completion or picker, and its brake design and profile names contradict the reports you accepted.

**Delivered.** The five researcher reports, plus the grk researcher's infographic (moved so its image link still resolves), now live in `202610/auto_autonomy_epic_roadmap/` as `auto_autonomy_epic_roadmap__{cdx,cld,grk,mus,gem}.md`. The consolidated report is `auto_autonomy_epic_roadmap__final.md` in the same directory. It is registered for the linker as `research:202610/auto_autonomy_epic_roadmap/auto_autonomy_epic_roadmap__final.md` (`file:explicit:c7a0485c8feb58537300a8d7`). The research repo commit is declared, and the host makes it after this turn ends.
