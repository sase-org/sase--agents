# Chat History - ace-run (research.02.cld)

- **TIMESTAMP:** 2026-08-08 10:46:47 EDT
- **MODEL:** claude/opus
- **AGENT:** research.02.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260808_103139.md`

## Prompt

%id(cld, clan=research.02) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I recently migrated xprompt skills to the sase/skills/
directory and allow users to invoke them via xprompt invokations that have the
`#skills/` prefix. Work is also in-progress to migrate sase memories to xprompts that
use the `#memory/` prefix when invoked (see the sase-hf epic bead for context). I would
like to also start making artifact references (ex: `@commit` or `@research`) defined by
xprompts as well. These should allow the user to customize what text gets substituted
for these artifact references (we should consider supporting other useful customizations
too--spend some time thinking about this) when rendered while providing builtin
functionality that is useful for all artifacts (e.g. artifact reference usage tracking,
artifact linking, etc...). Can you do some research with the goal of helping me decide
the best way to implement this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current state of xprompts, skills, memory migration, and artifact references in the codebase.

I have what I need. Writing the research report now.

Research written to `sase/repos/research/202608/xprompt_artifact_references.md` (459 lines, untracked in the research sidecar).

## What I found

**The customization target is smaller than it looks.** Grammar, scanning, canonicalization, and resolution are ~2,300 lines of Rust in `sase-core`. The entire "what text replaces `@commit:sase@abc`" decision is **43 lines of Python** — `_artifact_ref_replacement()` at `src/sase/artifact_ref_prompt.py:201`. That function *is* the ask.

**The builtin functionality you want to preserve is already template-independent.** The consumption ledger, prompt-artifact staging, and prompt-archive linkification all key off the *resolution result*, not the rendered text — and the file-reference dedupe keys on `resolved_path`, not the emitted string. The seam is already cut in the right place.

**Precedent is ready-made.** `sase-hb` (skills) and `sase-hf` (memories) have already paid the cost of discovering what a "special xprompt type" needs: reserved namespace, canonical source dirs, Rust-owned reference naming, two-way placement diagnostics, additive catalog field.

## Recommendation

A reserved `artifacts/` xprompt namespace — `sase/artifacts/<kind>.md` declaring `artifact: <kind>`, body = Jinja2 substitution template, frontmatter = the per-kind policy currently hardcoded. **Ship the six builtin renderings as packaged templates** so customizing `@commit` is just shadowing a file, and the default path and custom path are the same code from day one. Rust keeps the registry and resolver; Python renders (Jinja lives in Python — same split skills already have).

Four phases: rendering → policy metadata (`label`, `role`, `link`, `fragments`, `on_missing`) → links and declarative new kinds → surfaces. Phase 1 alone delivers the stated ask.

I recommend **against** letting templates define resolvers (bash/python at launch time) — that's arbitrary code per reference on the launch path, no possible native parity for editor completion, and it crosses the Rust-core boundary rule.

## The hazard worth your attention

Declaring a kind silently reinterprets existing prose. The `@path` regex excludes `:` from its capture (`file_references.py:31`), and unknown kinds are skipped outright — so today `@notes:todo` is left *completely alone*. The moment `notes` is a declared kind, that same text becomes a hard `sys.exit(1)` launch failure everywhere it appears. Mitigation is a per-kind `on_missing:` policy plus a doctor check that counts existing occurrences before you enable a kind.

Four open questions are listed at the end — the namespace name (`artifacts/` vs `refs/`) is the one that's expensive to reverse, since it becomes reserved. I did not file any beads.

I'll commit the research file I wrote this session.

Committed.

**Commit:** `12ad006` — `docs(research): evaluate xprompt-defined artifact references` in the research sidecar (`sase/repos/research`), containing only `202608/xprompt_artifact_references.md` (459 lines). Working tree is clean and the branch is level with `origin/main`, so the push landed.

One thing worth flagging: the commit immediately before mine, `2d7b53d docs: research xprompt-backed artifact references`, adds `202608/xprompt_backed_artifact_references.md` (616 lines) — a separate report on the same question, from a different agent. Two overlapping research files now sit side by side in `202608/`. I left both in place rather than reconciling them, since consolidating someone else's report is your call; if you'd like, I can read the other one and merge them into a single report.

The research itself — recommending a reserved `artifacts/` xprompt namespace with Jinja2 bodies, frontmatter policy, the current builtin renderings shipped as packaged templates, and Rust keeping the registry/resolver while Python renders — is unchanged from what I described before the commit pass.
