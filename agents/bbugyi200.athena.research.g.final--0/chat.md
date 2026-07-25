# Chat History - ace-run

- **TIMESTAMP:** 2026-07-17 10:07:54 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.g.final
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260717_094120.md`

## Prompt

%name:research.@.final %m:@research_lead %wait:research.g.cdx %wait:research.g.cld %g:research
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

Can you do some research on best-practices for top-level README.md files in GitHub projects with the goal of helping me improve this project's README.md file? End your analysis with a list of recommended changes I should make to this project's README.md file.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote (`research.@.cdx` -> `__a`, `research.@.cld`
   -> `__b`), then read both reports. Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory, create `<month-dir>/<name>/`, and
   move the two reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never overwrite: on any
   collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings from both reports and your own
   research, resolve conflicts, cut duplication, and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading the two researcher transcripts to identify their report files.

Both reports are present. Reading them now.

Done. The consolidated report is written and the final layout matches the spec:

```text
202607/github_readme_best_practices_consolidated/
├── github_readme_best_practices_consolidated__a.md   (research.g.cdx — moved via git mv)
├── github_readme_best_practices_consolidated__b.md   (research.g.cld — moved via git mv)
└── github_readme_best_practices_consolidated.md      (consolidated report)
```

## What the consolidation found

Both researchers independently landed on the same headline: **keep the 109-line landing-page shape from the recent rewrite; what's missing is facts, not sections.** The README never states Alpha status, never says POSIX-only, never expands "SASE," never links the completely orphaned `CONTRIBUTING.md`, has no CI badge or support route, and ships ~7 MB of media that renders broken on PyPI.

I resolved the three genuine disagreements between the reports with my own verification:

1. **Section ordering** — A wanted Quick start moved above the demo gallery; B argued the current demos-first "funnel order" is correct. Resolution: keep the order, shrink the gallery's mass — that fixes A's real complaint (Quick start buried 3–4 viewports deep) without giving up B's better-argued reader model.
2. **GIF handling** — A demanded removing all autoplaying GIFs on WCAG 2.2.2 grounds; B just wanted smaller variants. My follow-up found GitHub has had a platform-level autoplay-off accessibility setting since May 2022 (softening A's claim on GitHub), but PyPI has no such control — so the hybrid is: one animated hero using the existing 1.8 MB blog variant, the other two as stills linked to their `.mp4` twins. I also corrected B's claim that all blog variants exist: the `prs_pipeline` demo has no downsized variant and needs one generated.
3. **PyPI fix strategy** — A wanted a generated PyPI description; B wanted hard-coded absolute URLs. Resolution: `hatch-fancy-pypi-readme` (sase already builds with hatchling) does A's approach with B's simplicity — its documented substitution feature rewrites relative links to absolute at build time, one pyproject block, no second README.

I also kept B's evidence-hygiene corrections (Diátaxis says nothing about READMEs — A's framing was dropped; "good README → stars" causality is unproven per Gaughan 2025) and added one gap neither covered: the repo About description/topics/social-preview surface.

## The recommended changes (as ranked in the report)

High-confidence and cheap: **1)** link `CONTRIBUTING.md` (strongest evidence in the literature), **2)** state Alpha status, **3)** expand the acronym in the H1/lede, **4)** add platform (POSIX, no Windows) + `git`/editor prerequisites and a success statement to Quick start, **5)** fix PyPI rendering via hatch-fancy-pypi-readme before the next release, **6)** cut media from ~7 MB to ~2.5 MB using assets already in-repo, **7)** add a CI badge, **8)** add a GitHub Issues support route. Judgment calls: a diagram caption, the `just` prerequisite in Development, surfacing the blog + PDF handbook, a short "Why not sase?" limits note, and optionally compacting the all-"Supported" provider table. Explicitly not recommended: a manual TOC, reordering, manufactured social proof at Alpha, or restoring the pre-rewrite content.

The two moves are staged and the new report is untracked in the research sidecar (now at `origin/main`); I've left committing to the finalizer per the commit-workflow rules. No changes were made to the sase repo itself, so `just check` doesn't apply.

The uncommitted changes are mine from this session, so I'll commit them in the research repo using the commit skill.

Committed and pushed. The finalizer's two repository entries (`research` linked repo and the `sase-org/sase--research` sidecar) both point to the same checkout, so a single commit covered everything.

What I did:

- Ran the `/sase_git_commit` skill in `sase/repos/research`, staging exactly the three listed files with `-f`: the two moved reports (`github_readme_best_practices_consolidated__a.md` / `__b.md`, preserved as git renames) and the new consolidated report (`github_readme_best_practices_consolidated.md`).
- Commit message: `docs(research): consolidate GitHub README best-practices reports`, describing the merge and the resolved disagreements.
- `create_commit` completed successfully and `git status --short --branch` shows `main...origin/main` with a clean working tree — nothing dirty, nothing ahead.

The research deliverable itself is unchanged from my earlier summary: the consolidated report at `202607/github_readme_best_practices_consolidated/github_readme_best_practices_consolidated.md` ends with the ranked recommendation list (link CONTRIBUTING.md, state Alpha status, expand the SASE acronym, add platform/prereqs to Quick start, fix PyPI rendering via hatch-fancy-pypi-readme, cut media weight, add a CI badge, and add an Issues support route, plus the smaller judgment calls).
