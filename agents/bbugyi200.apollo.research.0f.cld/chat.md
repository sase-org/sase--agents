# Chat History - ace-run (research.0f.cld)

- **TIMESTAMP:** 2026-10-07 15:32:23 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0f.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_151324.md`

## Prompt

%id(cld, clan=research.0f)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0f.cdx`, `research.0f.grk`, `research.0f.mus`, `research.0f.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

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
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

I'm mapping the current plan schema and the gate system. Next I'll look at how plan approval gates are built.

I've read the plan gate and approval code. Now I'm sending parallel searches to cover the coder prompt, the epic phase launch, the TUI inputs, and the memory-write path.

Three survey reports are in. Next I'm checking the finalizer path (for a memory-diff backstop), the memory-write skill text, and the Rust validator.

The Rust validator rejects unknown frontmatter keys, so any new field needs a schema change in sase-core first. Next I'm checking existing beads, the flag rules, and the TUI review modal.

I'm now checking your local gate history (296 plan/epic gates, 6 question gates) to see how often feedback is really an answer to a choice or about memory.

The planner's prompt is in the artifacts directory (`raw_prompt.md`), so a "requested" quote can be checked when the plan is proposed. Next I'm confirming the key line numbers I'll cite.

I have enough evidence. Writing the report now.

Now registering the report as an artifact.

The report is registered. Submitting the final declaration.

I wrote the report and registered it as an artifact (`research:202610/plan_embedded_gate_decisions__cld.md`, id `explicit:c6a3737a4653106f89261baa`). The final declaration was accepted, so the host will commit it after this turn.

My verdict: this is a good idea. Today, a planner that needs your answer first must open a `/sase_questions` gate, which costs a whole extra agent turn. The one memory-consent question on this host shows exactly that ("the follow-up agent will finalize the plan and run sase plan propose"). Putting the question inside the plan review you already do removes that turn and keeps your answer in the archived plan.

**Adjustments I'm recommending to your requirements (each is called out in §3):**
- **Gate *inputs*, not gate *options*.** In SASE an option is a command-backed branch of the gate. The plan gate's branches are fixed by validation, and its follow-ups are keyed by which options were selected. Adding toggles as options would multiply those keys, allow nonsense submissions like "memory only", and support only yes/no. Instead, each choice becomes a typed parameter on the existing approve option. You'd still see ☑️/⬜ toggles in the same review screen.
- **Every decision needs a default.** About 75% of plan approvals here never reach a human: 143 of 197 tales and 75 of 92 epics were resolved by `%auto`. Leaving a value out means "use the default", which covers Enter, `%auto`, and Telegram/mobile until they can show decisions. If the planner can't name a default it would defend, it should ask now with `/sase_questions` instead.
- **"Default on only if you asked" gets checked mechanically.** A memory decision may default to on only with a `requested:` quote of your words. SASE checks that quote against your prompt, feedback and answers, both when the plan is proposed and again when the review is built. If the quote can't be found, the default is forced off. Right now this rule exists only in skill text; nothing in code checks memory changes.
- **"All memory changes must be planned" is narrowed.** I'd keep the direct path when your current prompt explicitly asks for a memory edit, since that prompt is already your approval and forcing a plan turns one turn into three. If you want no exceptions, that's a later switch.
- **Epic phases can be conditional (`when:`).** A phase tied to a declined decision is never created, so nothing depends on phase agents reading your answer and choosing to skip.
- **Decisions are fixed for the life of one review**, and capped at five per plan with two to five choices each. Edits inside the review can change wording but not the decisions themselves (send feedback for that).

**Recommended solution:**
- **In the plan:** an optional `decisions:` map in the frontmatter. Each entry has an `ask`, a required `default`, and either nothing more (a toggle) or `choices` (a pick-one). Memory decisions add `memory:` note paths and, to default on, the `requested:` quote. Epic phases can add `when:`.
- **Validation:** done in the Rust core (`sase-core`), since it currently rejects any frontmatter key it doesn't know.
- **In the review:** a new "Decisions" section in the Plan Review screen, above the existing approve/reject/feedback controls (renamed "Verdict"). Enter still approves with the shown values in one keystroke.
- **After approval:** your answers are written back into the archived plan as `answer:`, keeping one file as the only handoff. The coder gets a short "Reviewer decisions" block in its prompt, and `sase bead read` shows the decisions to every phase agent.
- **Later, behind a beta flag:** a check at commit time that blocks memory changes not covered by an accepted memory decision.

The report sketches this as a six-phase epic, with the skill and policy changes landing last. It also covers alternatives I rejected, naming (I chose `decisions:` over `questions:`), mock-ups of the review screen and archived frontmatter, file-level touch points, and five open questions for you.

Files are in `sase/repos/research/202610`:
- plan_embedded_gate_decisions__cld.md
