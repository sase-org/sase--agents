# Chat History - ace-run (research.9.cld)

- **TIMESTAMP:** 2026-09-25 14:12:43 EDT
- **MODEL:** claude/opus
- **AGENT:** research.9.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_135331.md`

## Prompt

%id(cld, clan=research.9)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.9.cdx`, `research.9.mus`, `research.9.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to rename the `%proc` directive to
`%tool` and add some features to it to better support the `sase tool` command (see the
sase_tool_epic_roadmap.md file in the research sidecar repo for context).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? End your analysis with a recommended solution. 
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

I opened the research sidecar and found the `sase tool` roadmap files. Next I'll read the roadmap, then study how `%proc` is implemented today.

Reading `docs/tool.md` and the `%proc` implementation to compare the two execution paths.

Now looking at the `%proc` runtime and the tool hand-off code to see where they overlap.

Mapping the rename footprint across both repos (Rust core, Python, docs, tests).

Checking prompt history for real `%proc` usage, as evidence for how much a rename would disrupt.

Now reading the prior E3/E4 and guarded-recipes research for the current roadmap state.

Confirmed that a `%proc` body running `sase tool run` is already recorded as proc-owned. Checking how foreground runs under a proc owner handle timeouts.

Checking how `%proc` shows up in axe routines and the `%if` wait-outcome context, which bear on pipeline use cases.

Checking the bead store for any existing `%tool` proposals, plus the E3 epic status.

Sizing the rename: listing affected files in each repo.

Checking how ad-hoc ToolRun identity is computed, since that decides whether `%tool` code bodies would group in history.

Zero real `%proc` invocations anywhere. Last check: whether a `%proc` unit notifies anyone when it finishes.

Evidence gathering is done. Two quick checks (host name and when `%proc` landed), then I'll write the report.

I have what I need. Writing the report now.

Report written. Registering it as an artifact.

Artifact registered (`explicit:c4b9a08baa894c1174a5db97`). Now the final declaration.

The report is written, registered as an artifact, and the research repo commit has been declared.

**Verdict:** rename `%proc` to `%tool` only if the behavior changes too. If `%tool` did exactly what `%proc` does, it would be worse than no rename, because "tool" in SASE now means a recorded ToolRun (`sase tool`, the `tools:` catalog, the glossary).

**What I found:**
- **An xprompt `just check` is invisible today.** `%proc("just check")` records no ToolRun. The guarded-recipe check lets it through silently because a proc never sets `SASE_AGENT`. Nobody is notified when it finishes. That breaks the "every heavy run is a ToolRun" rule that later epics (E4 receipts, E6 forecasts, E7 capacity admission) rely on.
- **The execution work is mostly done.** E2's hand-off contract (reserve a run, the owning proc runs `sase tool _adopt`, settle from the proc's outcome, notify once) is exactly what a `%tool` unit needs.
- **The rename breaks nothing.** I found zero real `%proc` uses: none in about 1,600 chat transcripts from July to September, September's prompt history, your xprompt directories, or the proc store. It's still behind the beta `typed_launch_units` flag, due for a decision on 2026-11-20. That makes now the cheapest time to change the grammar and wire format.
- **Caveat: `%proc` has had no users in the 33 days since it landed.** A rename won't fix that on its own. `%tool` has to win on things only a multi-segment launch can do:
  - check what actually landed after an agent finishes;
  - scheduled checks on a fresh checkout, which also give E3 (failure triage) the clean-tree runs it lacks;
  - launch a fixer agent only if a check failed.

**What I recommend:**
- **Replace in one step.** `%proc` becomes a migration error, with no alias and no sunset flag, still behind `typed_launch_units`.
- **Name comes first.** `%tool:check` and `%tool(test, tests/x)` run catalog tools. Scripts need an explicit `bash=`, `python=`, or fenced body, and are recorded as ad-hoc ToolRuns keyed by the code's digest.
- **Every unit is a ToolRun owned by its proc**, through the E2 hand-off. The run is reserved after the workspace lease, and if reserving fails the command still runs wrapped, the way monitors handle it.
- **Fix `sase-11k` in the same epic.** Today a same-plan `%wait` on a proc resolves when the proc is submitted, not when it finishes. Also pass the ToolRun result to `%if::` through the existing, currently unused `outputs` field.
- **Defer the rest until there's usage:** capacity, receipts, remote dispatch, `%wait(tool=)`, and shorthand failure conditions.
- **Size and timing:** one epic of about five phases, after E3 (`sase-18j`) lands.
- **Name risk:** in a prompt, `%tool` can read as "give the agent a tool". Reserve another name, such as `%toolset`, for any future directive that controls agent tool access.

**Disclosure:** while counting `%proc` usage, a broad grep over chat transcripts printed one summary line from a peer researcher's transcript for this swarm. I didn't open those files or use that line. The report's Appendix B says so, so the lead can weigh my verdict on the "add `%tool` alongside `%proc`" option knowing I saw it.

Everything else is in the report: current-state evidence, a comparison of five options, risks, the grammar and execution design, a phase table, and six open questions.

- Report: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202609/proc_to_tool_directive__cld.md`
- Artifact: `explicit:c4b9a08baa894c1174a5db97`, label `research:202609/proc_to_tool_directive__cld.md`
