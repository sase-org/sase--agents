# Chat History - ace-run (research.2u.final)

- **TIMESTAMP:** 2026-09-27 18:14:48 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2u.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_173702.md`

## Prompt

%clan(research.2u, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm not sure what memory file
updates (if any) I should make once all sase goal epics are complete (none have been
planned yet). See the sase_goals_epic_roadmap.md file in the research sidecar repo for
context. Can you do some research with the goal of helping me decide? End your analysis
with a recommended set of memory file updates and/or additions you think I should
consider making.]]) %id:research.2u.final %m:@xlarge
%wait:research.2u.cdx %wait:research.2u.cld %wait:research.2u.grk %wait:research.2u.mus %wait:research.2u.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm not sure what memory file
updates (if any) I should make once all sase goal epics are complete (none have been
planned yet). See the sase_goals_epic_roadmap.md file in the research sidecar repo for
context. Can you do some research with the goal of helping me decide? End your analysis
with a recommended set of memory file updates and/or additions you think I should
consider making.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.2u.cdx`, `research.2u.cld`, `research.2u.grk`, `research.2u.mus`, `research.2u.gem` dependencies, matching by `wait_name` and the canonical research
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
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

I've read three of the five reports; now reading the two longer ones (cld, gem) before starting my own research.

Now reading the roadmap itself, then verifying the key disputed facts against the tree.

Roadmap read. Now verifying the disputed facts myself — first loading the memory-read procedure.

tui_perf.md already covers G5's budgets generically, and sase_flags.md already covers per-epic scaffolding flags. Checking the design for planned docs and whether sase-core has its own memory.

Verification done; I have enough to resolve the disagreements. Now setting up the output directory and moving the five reports.

Writing the consolidated report now.

Quick verification of two claims I carried from cld (memory-audit stale proposals; the late-recorded decision) before finalizing.

All carried claims check out. Now the final declaration.

Yes, you should make memory updates for Goals, but only a small set. Most of them should also land inside the epic that makes each one true, not all at once after G6. By the end they add about **+320 always-loaded tokens (~7.6%)**, almost all of it decision-roster lines. I haven't changed any memory file: this research prompt doesn't authorize memory writes.

**Why not wait until the end.** Goals makes some current memory *wrong*, not just incomplete. The notes list artifact kinds, ref kinds, directives, typed gate kinds and TUI tabs as closed sets, and agents working on G2–G6 would read them as complete. Also, a phase agent can't change memory unless the approved plan names the change. When a plan leaves it out, it turns into a follow-up memory bead. That happened today: `sase-1b1` shipped deck views with no glossary term, and its land agent filed `sase-1bg`. The cheap fix is to paste each epic's memory list into its plan prompt.

**Recommended set**

1. **Before G1 is planned:** add the decision record `decisions/goals-host-binds` ("host binds, agents claim, users settle"), keeping it to those rules only. Also decide first whether routine jobs get standing goals or an exemption, because that changes the "every LLM turn" wording.
2. **During the epics, three more decision records:**
   - `goal-ledger` (G1): goals reuse the beads *repo*, not the beads *model*.
   - `goal-fails-open` (G3): a goal problem never fails an agent turn.
   - `claims-replace-success-pings` (G6): written with the measured before/after notification volume.
3. **Two glossary strands:** `goal` and `goal-claim`. Both words already mean something else here: a plan's `goal:` field, a bead's `claimed` status, a workspace claim, and every decision record's "Claim." heading.
4. **One new reference note, `sase_goals.md`:** about 40–60 lines, sase repo only, built up from G2 through G6. It's a warning list for agents changing launch paths, finalizers, notification routing or the goal ledger, not a copy of the design.
5. **About a dozen small edits to lists that would become wrong:**
   - glossary strands for artifact, artifact reference, gate, nav item and nav section, and agent jump targets (plus routines, only if standing goals ship);
   - the `%goal` directive and the new required finalizer in `xprompts.md`;
   - `dispatch.md`, where the existing `%tab` bullet should be rewritten to cover `%goal` too;
   - the generated templates behind `sase_artifacts.md` and `sase_beads.md` ("closing a bead never settles a goal").
6. **Once all epics are complete:** one cleanup pass. Check every item against the landed code, delete wording that only made sense mid-rollout, close any leftover memory beads, and record missed decisions as new records that supersede old ones rather than editing them. Only if G1–G6 finish with at most one remediation child epic, also add a record on how to split epics.
7. **Don't touch:** core memory (`sase.md`, `gotchas.md`, `rust_core_backend_boundary.md`), `tui`/`tui_perf`, `cli_rules`, `sase_flags`, `generated_skills`, the task types, or `host-owned-completion`. Agents already get the per-turn rules from the injected goal line, `/sase_final` and `/sase_goal`, and a core copy would cost every turn in every project.

**Where the five reports disagreed:**
- **Decision records:** from one (mus) to five (cld). I kept fail-open as its own record because `record-before-admit` was partly superseded twice, once specifically for a bundled fail-open clause.
- **Glossary strands:** from one to eight. Gem's eight add terms that don't clash with anything.
- **Who the new note is for:** grk wanted it generated into every project. I chose sase-only, since the rules agents need in other projects already reach them through the edited templates and skills.
- **Core memory:** grk and gem wanted a sentence added to the Final Declaration section. I rejected it as a duplicate of what's already injected.

I checked each disputed fact against the current tree and corrected several claims from individual reports.

**One addition of mine:** the G3 plan should include a test that checks the `/sase_final` examples against the finalizer's schema. That schema rejects unknown fields and the goal finalizer fails open, so if the examples drift, agents' claims would silently become "keep open".

The report ends with six open questions for you, including whether to write the first decision record now; I'd say yes. I've moved the five researcher reports in next to it, fixing the relative links in grk's so they still resolve, and the research-repo commit has been submitted.

Files are in `sase/repos/research/202609/sase_goals_memory_end_state/`:
- sase_goals_memory_end_state.md
- sase_goals_memory_end_state__cdx.md
- sase_goals_memory_end_state__cld.md
- sase_goals_memory_end_state__grk.md
- sase_goals_memory_end_state__mus.md
- sase_goals_memory_end_state__gem.md
