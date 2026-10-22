# Chat History - ace-run (research.2u.cld)

- **TIMESTAMP:** 2026-09-27 17:55:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2u.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_173702.md`

## Prompt

%id(cld, clan=research.2u)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2u.cdx`, `research.2u.grk`, `research.2u.mus`, `research.2u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure what memory file
updates (if any) I should make once all sase goal epics are complete (none have been
planned yet). See the sase_goals_epic_roadmap.md file in the research sidecar repo for
context. Can you do some research with the goal of helping me decide? End your analysis
with a recommended set of memory file updates and/or additions you think I should
consider making. 
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

Reading the Goals epic roadmap first, then the current memory files, to work out which memory updates would make sense once the epics land.

I've read the roadmap and the design. Now I'm going through the existing memory notes, decision records, and glossary to see which ones Goals would affect.

I'm checking which memory notes are generated from templates (and so update themselves) versus hand-written (and would go stale).

Found evidence that decision records often lag behind shipped epics. Next I'm checking whether the epic land prompt asks agents to update memory.

Confirmed that plan frontmatter already has a `goal` field, which would clash with the new Goal artifact. Now checking how the planner skill describes that field.

That's the evidence I needed: an epic shipped today, its glossary term was left out, and the term was filed as a follow-up memory task (`sase-1bg`). Now writing the report.

Report written. Registering it as an artifact snapshot.

Registration succeeded. Now the final declaration.

I wrote the report and registered it as an artifact. The host will commit it to the research repo.

- **Report:** `sase/repos/research/202609/sase_goals_post_epic_memory_updates__cld.md`
- **Artifact:** `file:explicit:776b710720dba5b2fb5a22c4`, label `research:202609/sase_goals_post_epic_memory_updates__cld.md`

**Main finding: most of the memory changes can't wait until after the epics.** A phase agent may only edit memory if the approved plan names the change. When the plan doesn't, the change becomes a follow-up memory task bead after the epic lands. That happened again today: `sase-1b1` shipped deck views without a glossary term, and its land agent filed `sase-1bg` to add it. Neither the land-epic prompt, the `/sase_plan` skill, nor the roadmap's cross-epic rules mention memory. So the key step is to paste each epic's memory list into the prompt you use to plan it.

**Goals will make some memory wrong, not just incomplete.** Eight places state a closed list that Goals extends: artifact kinds, prompt-ref kinds, the directives table, typed gate kinds, the tab lists in the glossary's nav-item and nav-section entries, and the required-finalizer rule. Each should be fixed in the epic that ships the change.

**Recommended set:**
- **Now, before G1:** a decision record for the core rule that the host binds every turn to a goal, agents only claim, and you settle. Keep it to that rule. The `sase tool` program's up-front decision was partly superseded twice in 9 days because it bundled mechanism details.
- **During the epics:**
  - **Three more decision records:**
    - the goal ledger (reuse the beads repo but not the beads model), in G1;
    - a goal problem never fails an agent turn, in G3;
    - claims replace success pings, in G6.
  - **Two glossary terms:**
    - *Goal*, which must be told apart from a plan's `goal:` field, from task beads, and from agent status.
    - *Goal Claim*, because "claim" already means a bead's `claimed` status, a workspace claim, and every decision record's opening "Claim."
  - **One new reference note, `goals.md` (about 40 lines):** warnings for agents changing launch paths, finalizers, notifications, or the goal ledger.
  - **About 11 edits to existing notes:** the glossary artifact entries, the `sase_artifacts.md` and `sase_beads.md` templates, `xprompts.md`, `dispatch.md`, the gate and navigation glossary entries.
- **After G6:** one cleanup pass. Audit everything Goals touched against the shipped code, record any decisions the plans left unwritten, and mark older records superseded rather than editing them. Optionally add a process decision on splitting large features into small epics, but only if G1–G6 actually validate it.
- **Leave alone:** all core memory. Goals already injects a goal line on every turn, and `/sase_final` covers claiming. The additions cost about 300 always-loaded tokens per turn (~7%), several times Goals' own ~40-token goal line, so keep them tight.

Two points aren't in the roadmap or the design. Once success pings are silenced in G6, a goal finalizer that fails quietly leaves the quiet Idle notice as the only backstop. And neither the design nor the roadmap says what happens when an agent is dispatched to a remote machine that hasn't fetched its goal, or whose goal is still an unpublished draft; `dispatch.md` will need that rule once G2 or G4 decides it.

The report ends with six decisions for you, the first being whether to record the core decision now.
