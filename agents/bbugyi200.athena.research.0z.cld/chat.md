# Chat History - ace-run (research.0z.cld)

- **TIMESTAMP:** 2026-08-24 07:21:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0z.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260824_070932.md`

## Prompt

%id(cld, clan=research.0z) %m:@research_b  #gh:gh_sase-org__sase I've been toying around with a way to generalize sase's
glossary into a new type of sase memory and I think I've got it.

- To start, some naming changes. We should make sure to update all relevant references:
  - short-term memory will now be called "core memory".
  - long-term memory will now be called "structured memory".
- We will add two new types of memory that are not represented as tiers (i.e. we will
  stick with using just the "Tier 1" and "Tier 2" H2 sections in agent instruction
  files):
  1. "memory strands": These are small memory notes inspired by zettel in a
     zettelkasten. These notes will be stored in files of the form
     `sase/memory/webs/<web>/<name>.md`, where `<web>` is the name of the web that the
     strand lives in and `<name>` is the name of the strand.
  2. "memory webs": These are inspired by hub notes in a zettelkasten. They should be
     defined in files of the form `sase/memory/webs/<web>.md` that correspond with an
     existing `sase/memory/webs/<web>/` directory.
- Memory webs should be configured by users by adding the appropriate sase/memory/ files
  to the machine's home directory or to project directories. This project and the
  bob-cli project should have their sase/sase.yml glossary configurations migrated to
  use this structure (i.e. create a new "glossary" web that is presented as a core
  memory--see the next bullet).
- A memory web should be presented to agents in agent instruction files as either core
  memories or strucured memories (one per memory web). Users should be able to configure
  whether a web is rendered as a core memory (like the glossary web should be) or a
  structured memory via the frontmatter of the `sase/memory/webs/<web>.md` file
  corresponding with that web.
- The `sase glossary` command would be migrated to the
  `sase memory read <web>:<keyword> [<web>:<keyword> [...]]` command where `<web>` is
  the name of a web and `<keyword>` is a repeatable argument that takes keywords
  specified by memory strand files (for example, we currently call these "terms" in the
  case of the glossary).
- If the `sase memory read <web>` command is used without providing any `<keyword>`,
  then all of the strands in that web should be displayed.
- As far as other use cases go, besides the glossary, I was thinking that architecture
  decision records (ADRs) might be a good 2nd use-case (using a
  sase/memory/webs/decisions/ web).

Can you do some research with the goal of critiquing this idea and, if you think I
should proceed, helping me decide the best way to implement this? Flesh out any open
questions that remain, but do your best to answer them on your own. End your analysis
with a recommended solution and, if you like the idea, some additional potential use
cases (i.e. What other memory web notes might I or someone else create in the future?). Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding the current glossary and memory implementation.

I have the full picture. Writing the report now.

Report written to `sase/repos/research/202608/memory_webs_and_strands.md` (661 lines).

## Verdict: proceed — but not in the order you proposed

**The strongest argument for the idea isn't Zettelkasten, it's that you've already built this three times.** `glossary.md`, `task_types.md`, and `artifact_relations.md` are all the same shape: a generated roster in core memory + a per-item on-demand read command + a detail store that isn't a memory note. Three generators, three snapshot formats, three collision blockers. A memory web is the extraction of that pattern. Lead with that framing — it's much harder to argue with than an analogy.

Supporting evidence: the glossary note has moved between Tier 1 and Tier 2 **four times** (`abc8a9ea8` → `445afde7c` → `eaafcbe72` → `fee21a898`). That's not indecision; it's a missing knob. Per-web tier config is the direct fix.

## The five things I'd change

1. **Build `decisions` first, migrate the glossary last.** Your instinct is glossary-first because it's the motivating case. It's also the riskiest: 5,866 src LOC, 10,934 test LOC, 124 modules, a `sase-core` wire change, and it's core memory in three projects. A broken ADR web costs nothing. Prove the machinery where failure is free.

2. **The closure semantics don't generalize.** `resolve_glossary_closure` works because "Patch" literally appears inside the definition of "Stitch." ADR titles don't appear in each other's prose, so a `decisions` web gets an empty closure and every "batched reads are cheaper" claim becomes false for it. Fix: support explicit links always, keyword-phrase closure only for strands that declare keywords. Both in every web; content decides which fires. Bonus — `supersedes`/`superseded-by` is *already* in your artifact relation registry, so ADR supersession is free.

3. **`core` yes, `structured` no.** "Structured" is the S in SASE — it describes all of it and doesn't contrast with "core." Your Tier 2 intro already says "detailed **reference** material." `core`/`reference` costs zero explanation. (Recommendation, not a blocker — it's your vocabulary.)

4. **One invariant, stated loudly: a core web inlines the *web note's* body, never strand bodies.** The glossary's 34 definitions are 1,831 words against a 2,323-word total core budget today.

5. **Config→files trades one enforced invariant for seven unenforced ones.** YAML key uniqueness is structural; 34 files aren't. Keyword collisions, filename↔keyword drift, orphan strands, empty webs, case collisions. All solvable, all must be *written*, and the validator is a first-class deliverable, not polish. (`validate_glossary_entries` in Rust is reusable verbatim — only discovery changes.)

## Two findings you may not have expected

- **bob-cli's four terms aren't bob-cli's.** `Pomodoro`, `Task Link`, `Work Log`, `Schedule Log` are your Obsidian vocabulary, stranded in one project's `sase.yml` because config glossaries have no home scope. As home-scope strands they'd serve every project. This argues for **per-strand merge** (project wins on collision), not the flat-note first-wins-by-stem shadowing.
- **File-backed strands unlock `sase memory write` → `sase memory review` for glossary terms.** Today an agent that finds a missing definition has no sanctioned path to propose one — editing `sase.yml` is a config edit. That capability doesn't exist at any price right now.

## Worth flagging

Your repo has removed three memory features (`dynamic memory`, `episodes`, `keyword metadata`). The common failure was mechanism-before-corpus. Phase 2 dodges it only if the `decisions` web ships with ~10 real ADRs written from actual history — the Rust core boundary, the two-speed verification split, the episodes removal. Those decisions exist and are currently only recoverable from commit messages.

Also: reintroducing `keywords:` on strands looks like a relapse against `21e1640ee`. It isn't — that was a *runtime trigger*, this is an *addressing alias* — but say so in the README or someone files a bead in six months.

Report covers 12 answered open questions, a 6-phase plan (§4.5), 10 candidate webs with §5.3 on what should *not* be a web, and a "generated webs" extension seam so `task_types`/`artifact_relations` can converge later.
