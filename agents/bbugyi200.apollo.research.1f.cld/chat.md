# Chat History - ace-run (research.1f.cld)

- **TIMESTAMP:** 2026-10-15 09:41:47 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1f.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_091655.md`

## Prompt

%id(cld, clan=research.1f)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.1f.cdx`, `research.1f.grk`, `research.1f.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

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
have been thinking that some of sase's memories should be migrated to documentation in
markdown files in the docs/ directory (the sase/memory/macros.md memory file, for
example), that I should consider making project documentation a first-class
representation of memory (we should manage it in a similar way, for example), and that I
should do a better job of structuring my documentation so its maintainance is more
intuitive and scriptable (via agents).

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
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Still mapping how SASE memory and the docs/ tree work today; after that I'll read prior research and outside sources, then write the report.

Reading SASE's decision records on memory design and checking whether memory tooling already knows about docs/.

Now measuring how memory notes and docs drift or co-change in git history.

Pulling per-note read counts from the memory audit log (paths and counts only).

Checking the existing "Documentation Workflow" guidance in docs/development.md, then moving to outside sources.

Now gathering outside sources (harness engineering, Diátaxis, llms.txt, AGENTS.md studies, docs-drift tooling) plus two earlier, unrelated research reports from the repo.

Repo evidence is in hand. Now running the outside-source searches in parallel.

Checking where memory resolution lives (Python vs. the Rust core) and whether a directive registry exists that could generate doc tables.

Measuring how often agents already read docs/ directly (unaudited), from recent Claude transcripts.

Spot-checking a few macros-memory facts against docs/macros.md for actual drift.

Found a real drift case; confirming it with the project-scoped resolver before citing it.

Evidence gathering is done. Confirming a couple of counts, then writing the report.

Writing the report now.

Fixing one table cell: `docs/macros.md` was renamed from `xprompt.md` 12 days ago, so its 30-day commit count needs both names.

Checking whether the snapshot captured the edited table cell, since the edit and registration ran together.

The snapshot matches the final report. Next I'll record the drift bug I found as a task bead, through the required skill.

No existing report of this drift. Sweeping last week's task beads for anything filed recently.

No duplicate in the weekly sweep. Checking in-progress epics for a causal link.

No active epic caused this. Checking the `bug` task type's required fields before creating the bead.

Now the final declaration.

I've written the report and registered it as an artifact. Short answer: yes in direction, but I'd change two of your three ideas before building anything. My recommended principle is **read docs like memory, write docs like code.**

- **Move memories to docs: only the descriptive ones, and the trigger has to come along.** `macros.md` is a hand-written 3.7k-token summary of `docs/macros.md`, which is about 61k tokens; the Directives section alone is about 26k. If agents are told to "read the docs" instead, each lookup costs roughly 7–16× more and they lose the one-line "read before…" prompt that tells them when to look. The duplication is causing real errors: the bulk xprompt→macro rename on 2026-10-03 put the wrong legacy directory names into the docs' discovery-order table, while the memory note kept the right names but has the order wrong. The heavily read notes (`lint_and_test` with 664 reads, `symvision`, `sase_flags`, `cli_rules`) are rules for agents and should stay in memory.
- **Manage docs like memory: share how they're read, not who may write them.**
  - **Share:** linkable sections, audited reads, `[[docs:…]]` links, validation.
  - **Don't share:** memory's rule that edits need your approval. 36% of the 1,493 commits touching `src/` in the last 30 days also updated docs, and that's what keeps them accurate.
  - **Approval-gate only:** a doc page's always-loaded trigger line, and any page that states rules for agents (`kind: policy`).
  - **Evidence:** in last week's Claude sessions, 44% of sase sessions grepped `docs/` directly with no audit. `docs/macros.md` was grepped 52 times in that week, versus 84 reads of the `macros.md` note in its whole life.
- **Structure docs so agents can maintain them: strongly yes, and it's the biggest win.**
  - Only 2 of 55 pages have frontmatter.
  - Nothing maps code to the pages that document it.
  - `ace.md` (about 185k tokens) and `configuration.md` (about 167k tokens) are each larger than many context windows, and took 466 commits between them in 30 days.
  - The `refresh_docs` gardener's prompt is just "refresh the docs." Because it may only touch docs, it writes known bugs into them as caveats (for example `docs/memory.md:257`: "that help text is stale").

**Requirement changes I made (R1–R7 in the report):**
- Docs become the one home for facts about how sase behaves; memory keeps rules, decisions, the glossary and private home notes.
- Who may edit depends on the kind of content, not the folder.
- The docs structure becomes a checked contract, not a tidy-up.
- The glossary and decisions get generated docs pages.
- The gardener files bugs instead of writing caveats.
- Pilot and measure before generalizing.
- Optionally, make this work for every SASE-managed project, with the resolver in sase-core.

**Recommended solution, in phases:**
1. **Quick fixes:** correct the discovery table, change the gardener prompts, turn on MkDocs anchor checking.
2. **Page frontmatter:** `description`, `kind`, `covers`, and an optional `memory:` trigger, checked in `just check`. Generate the directive rows, discovery order, glossary and decisions index from their sources, extending the pattern `tools/render_model_docs` already uses.
3. **Docs as memory targets:** `sase memory read docs:<page>#<anchor>` and `[[docs:…]]` links. Pilot with `macros.md` → `docs/macros_quick_reference.md` (keeping `macros.md` as an alias) and `dispatch.md`.
4. **Split and scope:** break up the two giant pages; add `sase docs affected`; have the gardener propose one agent per affected group of pages.

The report also lists what not to do: no wholesale move, no docs map in always-loaded instructions, no new "docs web" memory kind, and no LLM-written summaries at `sase memory init` time.

I filed the discovery-table bug as task bead **sase-1la** (bug, small, ready). One part is unverified: I didn't trace the actual first-wins ranking through every loader, so whoever fixes it should confirm the precedence before reordering the table.

The report is committed to the research repo at the end of this turn.

- Report: `sase/repos/research/202610/docs_as_first_class_memory__cld.md`
- Artifact: `file:explicit:697ef48e88cddbdb33f367b0`, label `research:202610/docs_as_first_class_memory__cld.md`
