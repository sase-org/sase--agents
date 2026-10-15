# Chat History - ace-run (research.1f.final)

- **TIMESTAMP:** 2026-10-15 10:03:11 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1f.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261015_091655.md`

## Prompt

%clan(research.1f, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
have been thinking that some of sase's memories should be migrated to documentation in
markdown files in the docs/ directory (the sase/memory/macros.md memory file, for
example), that I should consider making project documentation a first-class
representation of memory (we should manage it in a similar way, for example), and that I
should do a better job of structuring my documentation so its maintainance is more
intuitive and scriptable (via agents).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.1f.final %m:@xlarge
%wait:research.1f.cdx %wait:research.1f.cld %wait:research.1f.grk %wait:research.1f.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 4 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, gem, belonging to this
   dispatch's `research.1f.cdx`, `research.1f.cld`, `research.1f.grk`, `research.1f.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.1f.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1f.linker`, can find it:

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
├── <name>__gem.md
└── <name>__final.md
```

## Response

Opened the research repo; now reading the four researcher reports.

Read all four reports. Now checking the points where they disagree or make factual claims, directly against the sase checkout.

Confirmed two key facts so far: the macro discovery-order drift (both copies wrong, differently) and an unlisted docs page. Checking memory-read usage stats and how agents actually reach docs today.

Read counts confirm the pattern (rules notes are read heavily; descriptive digests rarely). Now sampling recent agent transcripts to check how often agents open `docs/` directly.

Transcript sampling shows agents do grep `docs/` often, but the Claude sample is mostly research agents, which weakens one report's headline number. Refining that count to sase's own docs pages only.

Codex sessions in sase workspaces: 24/64 shelled into a sase docs page, 56/64 ran `sase memory read`. Now checking the generator/lock-test precedents and where the directive registry lives.

Enough evidence gathered. Setting up the consolidated layout in the research checkout.

Reports moved. Checking a prior consolidated report's header format so this one matches the repo's conventions.

No local `site/` build to confirm against, so the report will state the image-prompt orphan-page point as MkDocs default behavior rather than an observed result. Writing the consolidated report now.

Report written. Checking one claim before registering: whether any docs page links to the image-prompt `.md` files, which would make the proposed `exclude_docs` setting produce warnings.

No docs page links to those files, so excluding them is safe. Removing an unsupported time estimate and tightening one count's wording.

No formatting convention in the research repo (prior finals aren't Prettier-clean either), so the report stays as written. Registering the consolidated report as a durable artifact.

Registered as `file:explicit:84a38d447e7a97e81024acdd`. Verifying the final layout and the state of both checkouts.

The layout is correct: the primary sase checkout is clean, and the research checkout has the four renames plus the new final report. Submitting the final declaration.

I've merged the four reports and my own checks into one consolidated report. It's written, registered for the linker, and the host will commit the research repo when this turn ends.

**Verdict:** the direction is right, but the problem isn't where memory lives. Three things are actually wrong:
- **The same facts are hand-maintained in two places, and both copies are drifting.** I ran the macro resolver: `docs/macros.md` and the `macros.md` memory note are both wrong about discovery order, in different ways. The docs list directories the resolver never reads. The memory note also leaves out the `%if` directive entirely.
- **Several docs pages are too big for agents to work with.** Six pages are over 30k tokens; `ace.md` alone is about 160k.
- **Agents already read `docs/` constantly, with no audit trail.** 24 of 64 recent Codex sessions in sase workspaces grepped a sase docs page.

**On your three ideas:**
1. **Migrate memories to docs:** only for descriptive facts, and the memory trigger has to stay. Most memory is rules that agents read heavily (`lint_and_test.md`: 665 reads). Only `macros.md` and `dispatch.md` summarize docs content, and they're rarely read. Deleting them and saying "read the docs" would make each triggered read cost 15–20× more.
2. **Docs as first-class memory:** yes for reads (audited, routable, addressable), no for writes. 36% of `src/` commits in the last 30 days also edited docs, and that co-editing is what keeps docs accurate. Putting it behind memory's write authorization would make drift worse.
3. **Structure docs for agent maintenance:** this is the biggest win and should come first.

**The researchers disagreed in three places; here's how I resolved them:**
- **What to do with `macros.md`:** two said keep it, two said migrate it. I recommend splitting it by content. Generate the directive and discovery-order tables from the code that owns them. Drop its copy of the "agents never commit" rule, which is already in core memory. Give the invocation grammar one home in a dense docs reference page that the existing memory trigger points to.
- **How agents reach docs:** proposals ranged from a new `sase doc` command to a docs map in agent instructions. I recommend letting an existing reference-memory note take its body from a docs page or a section with an explicit id. That needs one resolver in sase-core, because today `sase memory read` (Python) and `#memory/` expansion (Rust) resolve notes separately. Vercel's eval supports some kind of index (an always-loaded list of doc paths beat 53%-pass skills), but SASE's reference list already plays that role.
- **Page size budget:** a token-based warning above 15k. Line counts mislead (`cli.md` is 1,026 lines but about 26k tokens), and a 400-line cap would split 33 of 57 pages.

**Other gaps I found:**
- With zero PRs in the last 30 days, the strict MkDocs build first runs after a change has already landed. `just check` only covers the generated model tables. Broken `#anchor` links and pages missing from the nav aren't caught at all.
- The docs gardener's prompt sends code bugs to its final response, where they're lost. Two stale-help-text notes it wrote on 2026-08-30 are still in the docs, and the underlying `sase -h` bug is still live.
- Git co-change history already picks the right docs page for each code area. That can seed the code-to-docs mapping a scoped gardener needs. It also shows `configuration.md` as the #2 page for every area, which makes it the best target for generating from `sase.schema.json`.

**Recommended path:**
- **Phase 0 (hygiene):** fix the drift, send gardener defects to beads, turn on MkDocs anchor and nav validation, and run the strict build before changes land.
- **Phase 1:** generate the tables from code.
- **Phase 2:** add a small docs frontmatter contract and split `docs/macros.md`.
- **Phase 3:** docs-backed memory entries, piloted on `macros.md` and `dispatch.md`.

Phases 0–2 are worth doing even if you never build Phase 3. Whether Phase 3 is worth a cross-repo feature for two pilot notes is your call; I lean yes, because agents are already reading docs in a large share of sessions.

**Memory edits need your sign-off.** Fixing the discovery order corrects a false claim, so it would be approved by default in an implementation plan. Adding `%if` and turning the pilot notes into docs-backed entries count as new content, so they need you to ask for them explicitly.

Everything is in `202610/docs_backed_memory_and_agent_maintained_docs/` in the research repo:
- `docs_backed_memory_and_agent_maintained_docs__final.md` (registered as `file:explicit:84a38d447e7a97e81024acdd`)
- `docs_backed_memory_and_agent_maintained_docs__cdx.md`
- `docs_backed_memory_and_agent_maintained_docs__cld.md`
- `docs_backed_memory_and_agent_maintained_docs__grk.md`
- `docs_backed_memory_and_agent_maintained_docs__gem.md`
