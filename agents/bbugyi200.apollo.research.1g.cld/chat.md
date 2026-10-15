# Chat History - ace-run (research.1g.cld)

- **TIMESTAMP:** 2026-10-15 09:44:22 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1g.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_091709.md`

## Prompt

%id(cld, clan=research.1g)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.1g.cdx`, `research.1g.grk`, `research.1g.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

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

Can you do some research with the goal of finding some articles/papers that will help
inspire me on this front? End your analysis with a ranked list of articles/papers that
you think I should consider reading. 
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

Now I'm checking all ~40 candidates against Bryan's reference library in one batch.

I have enough sources. Before writing, I'm checking whether sase already generates any of its reference docs (CLI, configuration) from code, since that bears on the single-source recommendation.

Writing the report now.

Report written. Now registering it as an artifact.

The artifact registered successfully. Submitting the final declaration.

I've written the report and registered it as a durable artifact (`research:202610/docs_as_first_class_memory_reading_list__cld.md`). The host will commit it after this turn.

**Report:** `sase/repos/research/202610/docs_as_first_class_memory_reading_list__cld.md`

**Main conclusions:**
- **Keep the macros digest, but bind it to the doc.** `sase/memory/macros.md` (167 lines) is a hand-written summary of `docs/macros.md` (4,082 lines). Write the Docs' "accept some repetition" principle and Mintlify's generated `skill.md` both defend keeping an agent-facing summary. The change worth making is to tie the note to the doc sections it summarizes, so a check flags it when those sections change. Its "agents never commit" paragraph already lives in the always-loaded instructions and the `decisions` web, so it can come out.
- **Docs become first-class memory by using memory's machinery.** Memory notes have typed frontmatter, trigger-style descriptions, authored links, audited reads and a drift check. Only 2 of the 65 top-level docs pages have any frontmatter. Adding `type`, `description`, `owner`, `reviewed` and the code paths a page covers is the core move. So is letting `sase memory read` open `docs:<page>#<anchor>` with the same audit.
- **Routing matters more than placement.** Gao & Chen found that agents rarely read ordinary docs (10.6% of documentation interactions) and never checked docs against code. Docs only work as memory if memory notes link into them. Inlining a docs catalog into the always-loaded file would add cost without much benefit.
- **For scriptable upkeep, use mechanical checks feeding small fixes.** Today the `refresh_docs` job asks an agent to "Refresh the documentation" as a whole. Cheaper checks would catch most drift:
  - CLI commands and config keys in the docs that no longer exist in the parser or `sase.schema.json`
  - broken links and anchors
  - stale review dates
  - commits that change covered code without touching the page

  Each finding would become one small fix, which is also how Diátaxis says to migrate: one page at a time, not a big restructure.

**Read first:**
1. Karpathy, *LLM Wiki* gist (2026-04)
2. Gao & Chen, *From Agent Behaviour to Agent-Friendly Documentation* (2026-08)
3. *Software Engineering at Google*, chapter 10, plus Google's docguide best practices
4. Diátaxis: the compass and "Diátaxis as a guide to work"
5. Cochran's preregistered ablation on an LLM-maintained 709-page wiki (2026-07)
6. Tan, Wagner & Treude on outdated code references in docs

The report has 24 ranked items in three tiers, a worked example of the macros migration, a 10-item idea list, and `bob ref create` lines you can run to capture the top picks.

**Caveats:**
- Most of the evidence is observational or comes from single-author studies and experience reports.
- Medium blocked the Yegge Beads post, so those quotes come from secondary summaries.
- The GitLab metadata details come from archived mirrors of GitLab's docs.
- The Diátaxis "complex hierarchies" page returned 404, so nothing relies on it.

Library check: 9 of 42 candidates already in your library (1 finished).
