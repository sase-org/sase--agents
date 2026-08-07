# Chat History - ace-run (research.00.cld)

- **TIMESTAMP:** 2026-08-07 13:56:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.00.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260807_134559.md`

## Prompt

%id(cld, clan=research.00) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I want to rename "ChangeSpec" to something better. Let's try to take inspiration from beads here, which are essentially lightweight issues/bugs ("ChangeSpec", on the other hand, are lightweight PRs). Can you do some research with the goal of helping me pick a good short name for this concept? End your analysis with a ranked list of recommended names I should consider. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this properly — the naming decision depends on how ChangeSpec actually behaves in the codebase, not just on the word.

Let me start by understanding the concept as it exists today.

3,741 references — this is a deeply embedded concept. Let me understand its actual semantics before proposing names.

Let me examine the actual data model and lifecycle.

Now let me check the CLI namespace and vocabulary collisions for candidate names.

I have what I need. Writing the research report.

Research written to `sase/repos/research/202608/changespec_rename.md`.

## What I did

Rather than brainstorming words in a vacuum, I first pinned down what's actually being named — reading the `ChangeSpec` dataclass, the format spec, and the lifecycle — then extracted *why* `bead` succeeds into a weighted rubric, surveyed prior art, and ran a full-repo collision sweep on every candidate.

**Four properties the name has to carry** (from the data model): it contains code (`COMMITS`/`DELTAS`), it gets reviewed (`MENTORS`/`COMMENTS`), it lands permanently (`Submitted` is terminal), and it stacks (`PARENT` is a ChangeSpec name, not a VCS ref).

## The ranking

1. **`weld`** (92) — a weld *is* the permanent joint where new material fuses into the existing structure. Same shape as `bead` (1 syllable, 4 letters), zero repo hits, natural verb, and weld *inspection* is a real discipline, so the review half of the concept comes free. `Welded` beats `Submitted` as a terminal status.
2. **`rivet`** (88) — the safest pick; everything `weld` offers minus the caveat below, costing one syllable.
3. **`splice`** (87), 4. **`graft`** (84), 5. **`stitch`** (84), 6. **`patch`** (83), 7. **`brick`** (79)

## Three findings worth flagging

- **The caveat on `weld`:** in welding jargon, a "bead" is the metal a weld pass deposits. Real overlap, and it's the one reason you might prefer `rivet`. I judge it minor — common usage of "weld" is just "join metal" — but it should be a deliberate choice.
- **`rung` is unavailable.** It has the best stacking image of any candidate, but SASE already uses it (`plan_show`'s five-rung ladder, clan rungs). Same for `seam`, which is used repo-wide as an architectural term.
- **`brick` fails on its past participle.** Best stacking metaphor available, but "bricked" means *destroyed* in every technical context — unusable for a lifecycle-bearing noun.

## On migration cost

3,741 references and 237 filename-level renames, but **the on-disk format is untouched** — `.sase` blocks use `NAME:`/`STATUS:`/`PARENT:`, and the literal string `ChangeSpec` never appears in stored data. It's a code-and-docs rename, not a data migration.

One thing I noticed while reading: the ACE tab is labeled **"PRs"** while the docs say **"ChangeSpec"** — two names for one concept, which is the exact mistake Phabricator made with Revision/Diff. A single good word fixes both at once.

I'll commit the research file. The finalizer lists the same repo twice (linked repo and SDD sidecar resolve to the same path), so one commit covers both.

The untracked file is the research report I wrote this session. Committing it with the commit skill.

Working directory is the research repo (commits match its `docs(research)` convention). Let me confirm the file content before writing the message.

Clean and in sync with `origin/main`. One thing to check — there's a similarly-named commit just before mine.

Committed. Verified clean and pushed.

## What I committed

`d294023 docs(research): evaluate replacement names for "ChangeSpec"` — adds `202608/changespec_rename.md` (341 lines) to the research repo. `git status --short --branch` shows `main...origin/main` with no ahead/behind markers and a clean tree.

The finalizer listed the repo twice (as linked repo and as SDD sidecar), but both entries resolve to the same path `sase/repos/research`, so the single commit covers both.

One non-blocking note from the commit output: the primary commit and push succeeded, but agent-hood publication was deferred because the agents sync lock was busy. It's queued to retry automatically — nothing was lost, and no action is needed from you.

## One thing you should know

There are now **two** research reports answering your question in that directory:

- `202608/changespec_rename.md` — mine, committed just now. Recommends **`weld`**, with `rivet` and `splice` as runners-up.
- `202608/changespec_rename_research.md` — 444 lines, committed separately as `e1bb406 docs: research names for ChangeSpec`. Recommends **`Change`**, with `Patch`, `Stitch`, and `Slice` following.

I did not write or commit the second one, and I only noticed it while verifying my own commit. The two reach genuinely different conclusions from different rubrics — mine weights metaphor fit and shape-match with `bead`; the other explicitly weights *familiarity*, citing Microsoft and Google naming guidance, which is what pushes it toward the plainer `Change`. That's a real disagreement about criteria, not just about words, and it's worth resolving deliberately.

I left the other file alone rather than reconciling or deleting it, since it isn't mine to overwrite. If you'd like, I can merge the two into a single report that states the familiarity-vs-metaphor tradeoff head-on and gives one ranking — that tension is arguably the actual decision you need to make.
