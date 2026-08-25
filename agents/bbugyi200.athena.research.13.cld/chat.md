# Chat History - ace-run (research.13.cld)

- **TIMESTAMP:** 2026-08-25 07:15:04 EDT
- **MODEL:** claude/opus
- **AGENT:** research.13.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260825_070100.md`

## Prompt

%id(cld, clan=research.13) %m:@research_b  #gh:gh_sase-org__sase Sase seems to have support for three different installation
modes for plug-ins:

1. the published version of the python package
2. the dev version, which uses an editable local install
3. a "from git" option

I don't understand why the third option ("from git") is necessary since we can always
use the second option (dev/editable install) instead, right? The bugyi-chops plugin
which is installed on this machine, for example, uses a "from git" installation and I
would like to migrate this installation to use a dev/editable install instead.

Can you do some research with the goal of helping me understand what it would take to
remove support for "from git" sase plugin installations? End your analysis with a
recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by exploring how plugin installation modes work in the sase codebase.

The user asked for research, so I'll do this exploration directly. Let me read the plugin subsystem.

Let me read the required reference memory for flags and CLI rules before forming a recommendation.

This research directory is a sidecar repo, so I need to open it properly before writing.

Now let me correct the line references in the report.

The sase repo itself is unchanged, so no verification gates apply. Let me close out the turn.

Research written to `sase/repos/research/202608/plugin_install_sources.md`.

## What I found

**Your premise is half right, and the half that's wrong changes the answer.** There is no third "dev install" mode for plugins. `sase plugin install` has exactly two sources — index and git — and *no* flag produces an editable plugin. Editable plugins exist only as a whole-environment property set by `sase update --to dev`, which converts every package at once. Worse, `sase plugin install /some/path` looks like a dev install but isn't: `Requirement.from_spec` emits `--with <path>`, not `--with-editable`, so uv builds a frozen wheel that silently drifts from your checkout.

So "just use option 2 instead" isn't something a user can currently do for one plugin.

**`--git` isn't why `bugyi-chops` is on git.** Its one PyPI release attempt (v0.3.1, 2026-07-27) failed in 19 seconds with `invalid-publisher` — the trusted publisher was never configured on PyPI. The repo has a complete `publish.yml`, a working build backend, and its only dependency is on PyPI. The git install is a workaround for a five-minute settings gap.

**You can't remove git support, only demote it.** `uv-receipt.toml` is written by `uv`, not SASE, and every SASE mutation path reconstructs the entire `--with` set from it. Drop git understanding and any receipt containing a git row — including yours right now — gets silently corrupted. Only the `-g` catalog shortcut is removable, and even that's cosmetic: `git+` URLs already pass through verbatim.

Three defects surfaced along the way, all pre-existing:
- `_source_for_entry` short-circuits on `install_type == "wheel"` before checking PEP 610 metadata, so `sase-research-artifacts` — a git install — is being version-compared against PyPI right now.
- Git installs get no freshness signal at all (`error="non-index install"`), despite SASE already having the machinery it would need.
- After a dev switch, `_index_requirement_for` discards the git source, so `sase update --to pypi` would try to install `bugyi-chops` from PyPI, fail, and take the whole environment's switch down with it.

## Recommendation

Fix the PyPI trusted publisher **first**, then `sase update --to dev` (verify with `--dry-run` — both checkouts already exist at the right paths, so it should read `reuse`). Note it converts `sase-research-artifacts` too; there's no per-package granularity.

In `sase`: add `sase plugin install -e|--editable`, fix the classification bug, then retire `-g` behind a `sunset` flag via `sase flag new` — and never touch receipt-level git tolerance.

One caveat on the ordering: migrating `bugyi-chops` to editable before publishing it makes `--to pypi` a one-way door on this machine. Recoverable via the mode-switch backup, but worth doing in the order above.
