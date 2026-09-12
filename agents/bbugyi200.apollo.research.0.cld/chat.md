# Chat History - ace-run (research.0.cld)

- **TIMESTAMP:** 2026-09-03 16:10:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260903_155244.md`

## Prompt

%id(cld, clan=research.0) %m:@research_b  #gh:gh_sase-org__sase I want to start allowing users to invoke the `sase init`
command from the TUI (in a visually appealing way), from the "Projects" tab on the "SASE
Admin Center" panel. Users should be able to initialize individual projects or all
projects (using the `-a|--all` CLI option).

Can you do some research with the goal of helping me decide the best way to implement
this? In particular think hard about the best UX for this functionality. End your
analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the `sase init` command and the Admin Center Projects tab.

Now I'll write the research document.

Research written to `sase/repos/research/202609/init_from_projects_tab.md`.

## What the investigation turned up

Three findings drove the design, and each kills an obvious approach:

1. **Init planning reads `Path.cwd()` process-globally**, and `--all` scopes projects by `os.chdir`-ing the whole process (`init_onboarding.py:430`). A Textual app can't do that — so the TUI must shell out, never call the planners in-process.

2. **Parts of init are deliberately non-bypassable-interactive.** `--yes` cannot authorize creating a missing provider sidecar; that path hard-requires `stdin.isatty()` (`_repo_init_sidecars.py:138`), as does owner-identity setup. `docs/init.md` states this is intentional. A TUI-only flow can never be complete.

3. **I measured the cost: ~8.4 s of work per project check, and ~92 % of it is project-independent** (config ≈ 0.8 s, memory ≈ 2.1 s, repo ≈ 0.55 s, skills ≈ 6.9 s). Config and skills are host-scoped, not project-scoped. So no eager drift column is possible, and running `--all` as N procs would redo ~7.7 s of identical work N times *and* race N chezmoi deploys that the coordinator currently batches into one.

## The recommendation

`i` initializes the marked set or selected project (reusing the existing `_target_records()` mark semantics that enable/disable/delete already use); `I` maps to `--all`. Both plan off-thread, then open an **`InitPlanModal`** built on the Updates tab's `PluginActionConfirmModal` — showing the exact argv and four planner rows, where *the confirmation is the dry run*. Confirm submits **exactly one** tracked proc streaming live into the Procs tab via `reporter.run()`. A TTY-only blocker adds a "Run in terminal" button that `app.suspend()`s into the real interactive `sase init` — the honest valve rather than pretending `--yes` is complete. An `INIT` column shows only cached, user-requested results with an age.

Two small CLI additions make it clean and are useful on their own: **`-p/--project`** (so nothing has to chdir, and `sase init -p foo` becomes possible from anywhere) and **`-j/--json`** on `--check` (the serializer already exists unnamed in `doctor/checks_config_init.py:111`). Notably, the design contains zero re-implemented init logic in the TUI — the CLI stays the shared API.

The doc also flags an orthogonal CLI win worth its own bead: hoisting the two host-scoped planners out of `--all`'s per-project loop would cut an N-project run by roughly `(N−1) × 7.7 s`.
