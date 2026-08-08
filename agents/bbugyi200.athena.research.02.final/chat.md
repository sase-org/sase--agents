# Chat History - ace-run (research.02.final)

- **TIMESTAMP:** 2026-08-08 10:59:01 EDT
- **MODEL:** claude/opus
- **AGENT:** research.02.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260808_103139.md`

## Prompt

%id(final, clan=research.02) %wait(priority=20) %m:@research_lead
%wait:research.02.cdx %wait:research.02.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I recently migrated xprompt skills to the sase/skills/
directory and allow users to invoke them via xprompt invokations that have the
`#skills/` prefix. Work is also in-progress to migrate sase memories to xprompts that
use the `#memory/` prefix when invoked (see the sase-hf epic bead for context). I would
like to also start making artifact references (ex: `@commit` or `@research`) defined by
xprompts as well. These should allow the user to customize what text gets substituted
for these artifact references (we should consider supporting other useful customizations
too--spend some time thinking about this) when rendered while providing builtin
functionality that is useful for all artifacts (e.g. artifact reference usage tracking,
artifact linking, etc...). Can you do some research with the goal of helping me decide
the best way to implement this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.02.cdx` -> `__a`, `research.02.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading both researcher transcripts to identify which report each wrote.

Mapping confirmed: `cdx` → `xprompt_backed_artifact_references.md` (`__a`), `cld` → `xprompt_artifact_references.md` (`__b`). Reading both reports now.

Both reports read. Now verifying key claims and probing the disagreements between them.

All claims verified. Creating the consolidated directory and moving both reports.

Consolidated report written. Layout is as specified — both source reports preserved via `git mv` (rename-tracked), plus the merged report.

`research:202608/artifact_reference_rendering/artifact_reference_rendering.md`

## What the two researchers agreed on (and I verified)

The seam is already cut in the right place. `_artifact_ref_replacement()` (`src/sase/artifact_ref_prompt.py:201`, ~50 lines) returns `tuple[str, Path | None]` — and **only the `Path` reaches tracking**. Dedupe keys on `resolved_path`, the ledger on the canonical ref, archive links on the staged record. So making rendering a template endangers none of the builtin machinery. Both rejected programmable resolvers and `@kind` → early-`#` sugar, for the same verified reasons.

## Conflicts I resolved

**Directory name** — `__a`'s `sase/artifact_refs/` wins. `__b`'s own §6.6 argues against `__b`'s pick: "artifacts" already means three things (`~/.sase/artifacts/`, `.sase/artifacts/` staging, `SASE_ARTIFACTS_DIR`). The file describes how `@commit:` *renders*, not an artifact.

**Mandatory `{{ artifact.pointer }}`** — `__a`'s constraint rejected. The invariants it protects are already structural, and it would forbid several high-value renderings *both* reports name. Kept as a doctor lint instead, with a `ref.default` context field so the safe case stays a one-liner.

**Jinja hazard** — both were wrong. `is_jinja2_template()` is a **whole-prompt** regex (`_jinja.py:42`), so a template emitting `{{` flips the *entire* prompt into `StrictUndefined` rendering — it breaks other people's text, not its own. `__b`'s "escape it" underestimates this; `__a`'s pipeline reorder silently changes two unrelated behaviors. Recommended a ~10-line span-protection between late steps 4 and 5 using existing machinery.

## What I added

- **Registry ownership is Python, not Rust** — both reports got this backwards. `known_kinds` is a Python property unioning Rust builtins with Python-discovered document roots. Smaller job than they scoped.
- **Rendering isn't pure today** — `_materialize_vcs_file_reference()` (`:209`) writes a file from inside the render step. Neither caught it; it blocks `__b`'s purity invariant.
- **`__b`'s §6.3 blast radius is narrower than claimed** — plans and follow-up prompts use the *early* phase only. And a corpus scan of `sase/memory/`, `src/sase/skills/`, `src/sase/xprompts/`, `docs/` finds only `@file` (already builtin). Zero current exposure — reframes it from blocker to doctor check, which is why I set `on_missing: error` as the universal default rather than `__b`'s `warn`.
- Confirmed live that `sase xprompt expand 'see @file:foo'` already exits 1 — so `sase xprompt expand` is in the blast radius too.
- `sase artifact show --render` instead of a new `render` subcommand; provenance on the staging manifest, not the ledger; `ref.occurrence_index` for repeat-reference bloat.

**Sequencing:** start after `sase-hf` lands — phases `.3`/`.5` are IN_PROGRESS and its `CONTENT_LAYOUT_SCHEMA_VERSION` 2→3 breakage is unresolved on the same wire this work touches.

The consolidated report is untracked in the research sidecar; I did not commit it.

Committed. The research sidecar is clean and in sync with `origin/main`.

**Commit** `e80d2a8` — `docs(research): consolidate artifact reference rendering research`

```text
202608/artifact_reference_rendering/
├── artifact_reference_rendering__a.md   (from xprompt_backed_artifact_references.md, cdx)
├── artifact_reference_rendering__b.md   (from xprompt_artifact_references.md, cld)
└── artifact_reference_rendering.md      (505 lines, new)
```

Both source reports moved as rename-tracked (0 content change); the consolidated report is the only new content.

One snag worth noting: the first commit attempt failed because I passed `-f` for the two *pre-rename* paths the finalizer listed, and `git add` can't take a pathspec for a file that no longer exists on disk. Re-ran with only the three real paths — `vcs_create_commit` runs an unrestricted `git commit` after staging (`_git_commit_dispatch.py:353`), so the already-staged rename deletions were included regardless. `git show --stat` confirms both renames landed.
