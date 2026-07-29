# Chat History - ace-run (research.p.cld)

- **TIMESTAMP:** 2026-07-29 07:08:05 EDT
- **MODEL:** claude/opus
- **AGENT:** research.p.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260729_065513.md`

## Prompt

%id(cld, clan=research.@) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I'm looking for new and improved ways that users can view, copy, and reference sase artifacts (for example, from the `Artifacts` panel in the TUI). Can you do some research to help me decide the best path forward? End your analysis with a ranked list of recommended improvements. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding how artifacts currently work in SASE.

I have a complete picture. Writing the report now.

Report written to `sase/repos/research/202607/artifact_view_copy_reference_20260729.md`.

## What I found

The core insight: **the panel doesn't need more features so much as one shared noun.** Six artifact kinds sit behind six unrelated models, six keymaps, and two disjoint UI surfaces that share no verb — and two universal primitives for fixing that already exist in the tree, each used for exactly one thing.

**Two concrete defects, verified:**

1. **Copy mode (`%`) and marks (`m`) are hard-gated off on 4 of 5 sub-tabs.** They're missing from the `NON_PRS_ARTIFACT_ACTIONS` allow-list (`src/sase/ace/tui/actions/artifacts.py:39`), which `check_action` treats as deny-by-default (`app.py:371`). Even `%s` — the tmux snapshot copy unrelated to ChangeSpecs — doesn't respond on Commits/Plans/Chats/Bugs. The dispatcher underneath never learned about sub-tabs either, and the Artifacts tab's internal id is literally `"changespecs"`, so lifting the gate alone would make `%n` on Chats copy the selected PR's name.

2. **The two "artifact" concepts never meet.** `ArtifactFile` has a rich viewer (kitty icat, mpv, markdown→PDF paging, tmux pane), marks, and copy contents/path — reachable only from the Agents tab. The panel *named* Artifacts has none of it. 3,984 artifact files / 619 MB are reachable only by first finding the producing agent among 5,072 runs.

**The two dormant primitives:**

- `ArtifactEntryTarget` — already computed for every row as `("commit", repo, sha)`, `("chat", path)`, `("bug", project, n)` — consumed by exactly one caller, to restore scroll position.
- `plans:` refs in the Rust core — drift-tolerant, ordered-root resolution — locked to a single kind by an explicit error.

**Ranked recommendations** (full rationale in the doc): 1. restore copy mode + marks per sub-tab (small, immediate, fixes a live defect) · 2. promote `ArtifactEntryTarget` into a `sase_core::artifact_ref` grammar — the keystone · 3. make `PreviewPanelModal` a real reader (it currently has *only* scroll and close) · 4. `sase artifact` read CLI · 5. reach the rich viewer from the panel · 6. marks/bulk actions · 7. surface `research` in Plans (two lines) · 8–10 vocabulary normalization, prompt-bar refs, Jump All.

Two notes: the field is clear — 73 commits since May touched the panel, but only one bead is open. And `research` docs are invisible in the Plans sub-tab (`kinds=("tale", "epic")` is hardcoded), so this report won't show up there until #7 lands. Three open questions are listed at the end — ref syntax being the one that most affects #2's shape.

I made that file, so I'll commit it.

Committed.

- **Repo:** `sase/repos/research` (the linked repo and SDD sidecar entries in the finalizer point at the same directory, so one commit covers both).
- **Commit:** `55d9f37 docs(research): survey artifact view, copy, and reference paths` — one file, `202607/artifact_view_copy_reference_20260729.md` (324 lines).
- **State:** `git status --short --branch` shows `## main...origin/main` with no dirty files and no ahead marker — clean and pushed. The rebase during commit also brought in an upstream commit (`5a5baad`).

No source files in the workspace checkout were changed, so `just check` doesn't apply — this was a research-doc-only change.
