# Chat History - ace-run (research.0g.cld)

- **TIMESTAMP:** 2026-10-07 17:09:46 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0g.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_163926.md`

## Prompt

%id(cld, clan=research.0g)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0g.cdx`, `research.0g.grk`, `research.0g.mus`, `research.0g.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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
would like to give sase plans (i.e. tales and epics) the ability to embed sase gate
options within their frontmatter somehow.

- This will be useful, for example, to start requiring that all memory file changes be
  planned in plan files with explicit human gates (that should default to on iff the
  user explicitly requested those memory changes).
- This will also be useful if, for example, a sase agent has a question for the user
  that effects the plan but the agent has enough information to write a good plan
  without an immediate answer (i.e. the coder agent can implement the plan based on what
  gate selections the user made).
- I have already done some research on this, which can be found in the
  plan_frontmatter_decisions.md file in the research sidecar repo. Review that research
  before performing your own. I agree with all of the recommendations made in that
  research file (though your judgement should take priority when it comes to UX
  decisions).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide what the best possible UX
looks like (across the TUI, Telegram, and the CLI) for this functionality? 
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

Read the prior Plan Decisions research. Next I'm surveying how the ACE TUI, Telegram, and CLI currently present plan gates, so the UX design starts from what exists.

I've finished surveying all three surfaces and the prior art. Now I'm checking two Telegram Bot API claims (button styles, rich messages) before drafting the design.

I'm building rendered mockups of the proposed TUI, Telegram, and CLI screens, using the same renderer ACE's snapshot tests use. They'll go alongside the report.

Both TUI mock states rendered. Checking them now, then I'll do the Telegram and CLI mocks.

Telegram mock done; rendering the CLI mock now. After that I'll write the report.

Changed the choice-decision glyph to ⋔ so it doesn't clash with the ◆ that `plan show` uses for epic phases. Re-rendered all the mocks; checking one now.

The mock images are in place in the research directory. Now I'm writing the report.

I've written and registered the report. Now I'm submitting the final declaration so the research repo gets committed.

I've written the report, rendered mock images of the proposed screens for the TUI, Telegram and the CLI, and registered the report as an artifact (`research:202610/plan_decisions_review_ux/plan_decisions_review_ux__cld.md`). The research repo will be committed when this turn ends.

**Report:** `sase/repos/research/202610/plan_decisions_review_ux/plan_decisions_review_ux__cld.md`

It keeps the model from `plan_frontmatter_decisions.md` and designs the review experience on top of it. The main recommendations:

- **Shared visual language everywhere:**
  - ★ marks the planner's default and a gold ● marks anything you changed (the same ● the Config pane already uses).
  - 🧠 marks a decision that authorizes memory edits, and ⋔ marks a multiple-choice decision.
  - Each decision's id is its only name, in every view and in `-D id=value`.
- **One summary sentence**, generated in sase-core and used by every surface, e.g. `→ coder + commit · 1 change · 🧠 tui.md`.
- **TUI:**
  - Decisions sit in the left column. Only the focused one expands to show its question, every option with its consequence, and the planner's reason.
  - The Tale/Reject/Feedback buttons become one compact row pinned to the bottom of that column. The current column is 42 cells wide with about 27 of its ~30 rows already used, so fully expanded decisions would push those buttons off screen.
  - Space, h/l or ←/→ change a value and `r` resets it. Enter still approves as shown.
  - Focusing a decision scrolls the plan to the part it controls, highlighting the chosen option's text and dimming the other.
- **Telegram:**
  - The message text is a fixed question sheet and the buttons hold the live answers.
  - Yes/no decisions flip in place. Multiple-choice decisions swap in a radio-button keyboard in place, then return.
  - The main button reads `✅ Tale · defaults` or `✅ Tale · 1 change`.
  - Once approved, the message is edited to show the answers. Plans that `%auto` approved with decisions get a silent receipt; today auto-approved plans send nothing at all.
- **CLI:**
  - `sase plan approve -D id=value` is strict: unknown values fail before anything happens and list the allowed ones.
  - Every approval prints a decision card; `--dry-run` prints it and stops.
  - `plan show` gains a DECISIONS section and `plan validate` gains decision checks. A failed `requested:` check shows the closest sentence you actually wrote.
- **Two additions to the plan format:**
  - An optional one-line `why:` explaining the default.
  - Obsidian-style branch markers in the plan body, `> [!decision] grouping = mode`. These are what make the highlighting, dimming and validation work.
- **One rollout change to the earlier design:** store decisions in the plan gate's host-only input schema, not as ordinary gate inputs. Otherwise existing generic screens would treat them as normal inputs. Telegram would send a separate message per decision, and the TUI and inbox would show duplicate input fields.

The images are mocks, not screenshots of real features. I built them with ACE's own syntax highlighter and PNG renderer from throwaway scripts that are not saved in the repo.

**Open questions for you:**
1. ⋔ instead of ◆ for multiple-choice decisions, since ◆ already marks epic phases.
2. Whether the branch markers are optional (my recommendation) or required.
3. Auto-approval receipts for every plan with decisions, or only those with memory decisions.
4. Compact Tale/Reject/Feedback buttons for every plan review, or only plans with decisions.
5. Whether to add `why:` now.
