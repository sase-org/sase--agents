# Chat History - ace-run (research.0m.cld)

- **TIMESTAMP:** 2026-10-08 12:25:57 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0m.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_120330.md`

## Prompt

%id(cld, clan=research.0m)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0m.cdx`, `research.0m.grk`, `research.0m.mus`, `research.0m.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

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

I've read the autonomy-policy report and I'm now reading the profiles-UX report. After that I'll check current source state before drafting the epic split.

I've read both baseline reports. Now I'm reading SASE memory on beads, epics, flags, and macros, so the epic split fits how epics actually work.

I'm pulling bead-store data to see how often epics land cleanly versus spawning nested "Finish…" child epics. That base rate will tell us how much to split.

I'm reading how epic land agents decide an epic is done, since that's what "verifiable" has to mean in practice.

Now registering the report as a durable artifact.

Registration succeeded. Now submitting the final declaration.

Yes, split it: four core epics plus one optional one. Each epic ends in one user-visible claim that its land agent can check with a test suite or a single command, and no feature flag has to outlive the epic that adds it.

The report is at `sase/repos/research/202610/auto_autonomy_epic_split__cld.md` and is registered as `research:202610/auto_autonomy_epic_split__cld.md` (artifact `file:explicit:549ccfc0f0757dbbd95f70f5`). The host commits it to the research repo after this turn.

| # | Epic | Verifiable result | Phases |
|---|---|---|---|
| E1 | Truthful `%auto` | Every `%auto` spelling either does what the docs say or fails at launch. `A` off really turns it off. Auto state survives gate, pipe and in-process handoffs. Generated epic workers stop auto-approving nested epics. Absorbs `sase-1hg`, `sase-1hh`, `sase-15s`, `sase-11g`. | 5 |
| E2 | One autonomy record | One Rust evaluator decides every gate outcome from one stored record, every automatic decision is logged, and `sase autonomy explain` shows what will happen. Behavior stays the same. | 5 |
| E3 | See it, stop it | Context-card history, epic-launch alerts on the TUI and Telegram, and a host-wide Pause brake that makes every gate wait. | 5 |
| E4 | Named profiles | Config profiles that prompts can only narrow, never widen; role profiles for generated workers; completion and a picker. | 6 |
| E5 | Steer from anywhere (optional) | Change a running agent's profile from the TUI, CLI or Telegram. Only worth building if profiles actually get used. | 3 |

Run them in the order E1 → E2 → {E3, E4} → E5. E3 and E4 each depend only on E2, so either can go first. Two things in the report go beyond the two baselines:
- **Earlier shared pieces.** I moved the shared display format and the "change an agent's autonomy" function into E2. That is what lets E3 and E4 run in either order.
- **Pause moved up.** The Pause brake is in E3 instead of with profiles, because it doesn't need them.

**Why split** (from this repo's own epic history):
- **Big epics leave work behind.** Since July, epics with 7 or more phases spawned a "Finish…" child epic 29% of the time; epics with 5–6 phases did so 10–13% of the time. Closed epics with 9+ phases took a median 22.5 hours and 44% nested; 5–6 phases took 4.9 hours and 12%.
- **Cross-repo work makes it worse.** Epics touching sase-core nested 21.5% of the time versus 12.9%. Epics touching Telegram nested 39% of the time versus 17%.
- **Large phases are the risk.** They spawned their own epic 11.4% of the time; medium phases did so once in 2,355.
- **Plan Decisions is the closest precedent.** It had 9 phases across core, gate, TUI, Telegram and CLI, and needed a 6-phase repair epic (`sase-1hi.10`) within hours.
- **Some choices need real usage first.** Several decisions in the baselines wait on data, an epic lands in about 5 hours, and a plan can carry at most five decisions against the ten left open.
- **E1 protects the rest.** Epic phase and land workers still hard-code `%auto`, which auto-launched 5 nested epics in October alone. Shipping E1 first protects every later epic in this program.

**What I found at the current code:**
- **Nothing has shipped yet.** None of the baselines' urgent fixes is in yet, and I re-ran their parser test: `%auto(epic=ask)` still grants full automation.
- **Beads the baselines missed:** `sase-15s` (the `A` toggle), `sase-11g` (gate and pipe handoffs), and `sase-1i1` (memory-consent policy under `%auto`).

**Don't use `%auto` on the planners** for these epics. Approve each epic plan yourself: under `%auto` its Plan Decisions just take their defaults, and memory edits get skipped. The report includes a prompt that chains E1 → E2 → E3 with `%wait`, so each epic is planned only after the previous one lands. Launch E4 by hand once you've read about a week of E2's decision log.

**Before E1 starts:**
- The Plan Decisions repair epic (`sase-1hi`) should finish landing.
- `sase-18i`, `sase-11t` and `sase-1ab.10` touch the same files, so land or retire them first.
