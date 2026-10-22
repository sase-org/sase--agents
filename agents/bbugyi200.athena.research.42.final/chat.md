# Chat History - ace-run (research.42.final)

- **TIMESTAMP:** 2026-10-08 17:17:05 EDT
- **MODEL:** claude/opus
- **AGENT:** research.42.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_163448.md`

## Prompt

%clan(research.42, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I
need a way to reliably install sase from PyPI (i.e. prod) and from a dev/editable
install (which needs to include the appropriate sase-core checkout for that dev version)
using the `just` command.

- The `just install` command and other related `just install-*` commands are already
  used to install sase into a local virtual environment.
- These commands are necessary but their names are not intuitive. Can we rename them to
  `just install-venv` / `just install-venv-*`? This will likely require updating some
  memory files.
- This will allow us to add new `just install` and `just install-dev` commands to serve
  these roles.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.42.final %m:@xlarge
%wait:research.42.cdx %wait:research.42.cld %wait:research.42.grk %wait:research.42.mus %wait:research.42.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I
need a way to reliably install sase from PyPI (i.e. prod) and from a dev/editable
install (which needs to include the appropriate sase-core checkout for that dev version)
using the `just` command.

- The `just install` command and other related `just install-*` commands are already
  used to install sase into a local virtual environment.
- These commands are necessary but their names are not intuitive. Can we rename them to
  `just install-venv` / `just install-venv-*`? This will likely require updating some
  memory files.
- This will allow us to add new `just install` and `just install-dev` commands to serve
  these roles.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.42.cdx`, `research.42.cld`, `research.42.grk`, `research.42.mus`, `research.42.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.42.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.42.linker`, can find it:

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
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

Exactly one report per suffix is present. Now reading each through its canonical research reference.

I've read all five reports. Now I'm checking the points where they conflict against the actual Justfile, CI, and update code.

Verifying the agent guard mechanism and the cold-start refusal next. After that I'll write the consolidated report.

I've checked the CI just pin (1.50.0, so `[arg(flag)]` isn't available). Now I'm prototyping the `just --list` layout to compare grk's dispatcher with flat recipe names.

I've verified enough to settle the disagreements. Next I'll set up the research directory, move the five reports in, and write the consolidated report.

Now writing the consolidated report.

Confirmed: `sase update` skips detached checkouts (`_plan_roots.py:163-164`). I'll add that citation to the report.

The consolidated report is registered. Last step is the final declaration.

The consolidated report is written and registered as `research:202610/just_install_pypi_dev_venv_split/just_install_pypi_dev_venv_split__final.md` (ref `file:explicit:cb9576f930ad90a93f22375e`). All five reports matched their `research.42.*` dependencies one per suffix, and I moved them into `202610/just_install_pypi_dev_venv_split/`. The research repo commit is declared; the host makes it after this turn.

## Verdict

**It's a good idea, and you should keep your names (`install`, `install-dev`, `install-venv*`). But don't land it as a plain rename.** `just install` currently means "repair the `.venv`" in 47 files here. That includes the CI action's default recipe, doctor messages, memory, a generated skill, and Rust error messages in sase-core. If the meaning flips quietly, an agent following an old hint would replace your global editable `sase` with PyPI wheels and downgrade sase-core-rs from 0.37 to 0.35.

## What I found beyond the five reports

These reverse some of their recommendations:

1. **The dev install must leave an editable core.** `update_routing.py:90-100` treats a wheel-installed core under an editable host as broken, and the next `sase update` rebuilds it. Two reports' approaches (cld, grk) produce exactly that state.
   - Building with `rust-dev-install-uv-tool`, as `sase update` already does, avoids it.
   - `sase update --to dev` itself can produce the broken state today, because it uses the other build recipe.
2. **Never pass `--python` to an existing install.** Your tool environment runs Python 3.14.7. In an isolated uv probe, adding `--python` rebuilt the environment on the older version. Three reports (cld, gem, mus) proposed `--python 3.12`.
3. **`uv tool install --force --reinstall` deletes files uv doesn't own.** The core build, the LSP binary and the source-identity file must be re-installed after every swap. Your live environment has no source-identity file at all, so "verify the core pairing" can't work until that's fixed.
4. **Your global `sase` loads its Rust core from inside `~/projects/github/sase-org/sase-core`.** The compiled extension there changed at 16:50 today, after the 15:16 install. So the check that refuses temporary agent workspaces must cover the core path too, not just the sase checkout.

## Recommended design

- **One standalone installer.** Both new recipes call a single standard-library-only script, `tools/sase_install`, which never imports `sase`.
- **Agents can't run it.** It exits 2 when `SASE_AGENT` is set, unless an explicit bypass variable is set.
- **It asks before big changes.** It previews and asks for confirmation on a mode switch, a downgrade, or plugin changes.
- **It refuses temporary sources.** `install-dev` won't install from a SASE agent workspace.
- **It picks the core the way `sase update` does.** The core checkout must contain the commit pinned in `sase-core-revision.txt`. It never quietly falls back to a published core.
- **It leaves exactly the install `sase update` expects.** It finishes by checking that `sase update -n -j` sees nothing to repair.
- **Rollout in three phases:**
  1. Rename the venv recipes; `just install` becomes a placeholder that exits 2 and prints the new names.
  2. Add the two installers.
  3. Update the sase-core messages and the plugin repos, and replace the chezmoi `acei`/`aceii` scripts with `just install-dev --sync`.

## Changes to your requirements

The report calls out ten adjustments explicitly. The main ones:

- "Install" means your `uv tool` environment, not `.venv`, pip or pipx.
- The two global installers are human-only.
- `install-dev` installs this checkout as it is on disk, and only from a permanent location.
- The plugin set is preserved, and the dev/PyPI mode applies to the whole set.
- Doctor and runtime error messages choose the right command based on how `sase` is installed.

## Decisions for you

1. Should `install-dev` switch plugins that have a local checkout to editable (my recommendation), or leave each plugin's source as it is?
2. Do you want an exact-pin core mode in v1? I'd defer it.
3. Should a fresh `just install` also add this project's required plugins? I'd only print a suggestion.
4. Later, should the global core become an immutable wheel so that `.venv` builds can't change it? That's a separate decision, because it changes how `sase update` works.

I didn't file task beads for the discovered gaps (the missing source-identity file and the inconsistent `--to dev` build). They're listed in the report as follow-ups for the implementation plan.
