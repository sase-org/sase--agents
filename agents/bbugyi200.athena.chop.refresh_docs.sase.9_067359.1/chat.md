# Chat History - ace-run (chop.refresh_docs.sase.9_067359.1)

- **TIMESTAMP:** 2026-08-19 23:24:31 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** chop.refresh_docs.sase.9_067359.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.9_067359.1, tribe=chop)
%wait(runners=0)
Refresh the documentation for sase.

Review the current repository behavior and the changes since the last documentation
refresh. Update user-facing documentation so it is accurate, complete, and clear to
someone new to the project. You may only create, modify, or delete documentation
files, such as Markdown or other docs-tree content, READMEs, and doc-adjacent assets.
You MUST NOT create, modify, or delete source code, tests, build configuration, or any
other non-documentation file, even to fix a bug you are confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll start by mapping the current docs, the last documentation refresh, and the product changes since then so the update matches actual repository behavior.

I'll pull the docs layout, changelog, and git history next so I can see what changed since the last refresh.

The last refresh is identified; next I’ll compare commits and CLI surfaces since then against the current docs.

I'll inspect the last refresh's files and compare them with the CLI and docs that likely drifted.

I’ll compare the live CLI and config surfaces with the docs, then hunt remaining drift since the last full refresh.

I’ll audit the CLI, ACE, and remaining guides in parallel, focusing on places that likely drifted since the last refresh.

I'll audit the listed docs against current source and the known post-refresh features, starting with the pages and stale-claim greps.I'll inventoryI'll audit those the live CLI help tree docs against ACE TUI source of and compare it to truth— `docs/cliWhilekeymaps, default.md` plus those config, and help the related audits run, text—starting with the listed getting I’ll verify files and the post-started docs the Admin-refresh features.. Center / Update panel flow and the live CLI inventory myself.

Docs

 are loaded

; next I’ll pull the rest of `docs/

ace.md` and match eachNext post-refresh feature against I’ll dump live keymaps and `-- TUI sourcehelp` for

. the root

 CLI

 and the likely

-new command groups, then finish reading `docs/cli.md`.

Next I’ll read the user-facing guides and compare them with CLI/source, including YAML samples and the known post-refresh features.

The changelog already flags a retired `,L` log panel; I’ll verify Updates

-tab vs `,U`, memory, filter bars, and the other post-refresh surfaces next.

No shell is available here, so I’ll reconstruct the live command tree from the CLI source and help strings.

Persistent filter bars are already on in code; next I’ll check Admin Center tab numbers, title hiding, and remaining keymap mismatches.

I’ll now pull the parsers and related docs for the likely-new commands and scan for other undocumented subcommands.

Admin Center tab numbers look drifted. I’ll verify every tab index and the other feature docs against source.

The Beads/Plans filter-bar wording looks stale; I’ll confirm against source that those bars are now persistent.

## Verdict

Admin Center **Updates is not retired**. Tab `6` still mounts the plugin/core/CLI browser. `,U` is a **separate** snapshot panel (`Everything` / `SASE` / `providers` / `agents`) and does **not** install plugins. INSTALL.md’s `#` → `6` → `i`/`x` install path is still true.

The real post-refresh drift is in **Admin Center tab numbers**, **always-on filter bars**, **Files kind-cycle key**, **Beads `due:` / `has:`**, and one **monitor row-title** contradiction.

---

## MUST FIX

### 1. Admin Center Projects is `4`, Statistics is `5` (Procs took `3`)

Live catalog:

```101:164:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/modals/config_center_catalog.py
_TAB_SPECS: tuple[CenterTabSpec, ...] = (
    CenterTabSpec("config", 1, "Config", ...),
    CenterTabSpec("logs", 2, "Logs", ...),
    CenterTabSpec("procs", 3, "Procs", ...),
    CenterTabSpec("projects", 4, "Projects", ...),
    CenterTabSpec("statistics", 5, "Statistics", ...),
    CenterTabSpec("updates", 6, "Updates", ...),


    CenterTabSpec("

xprompts", 7, "XPrompts", ...),
)
```

Docs still use the pre-swap numbering:

```2600:2602:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/ace.md
## Projects Tab

Open the SASE Admin Center with `#` and switch to the **Projects** tab with `3`, `Tab` /
```

```2681:2681:/home/bryan/.local/state/sase/workspaces/sase-org

/sase/sase

_12/docs/ace

.md
Open the SASE

 Admin Center with `#`, then

 press `4` or switch

 to **Statistics**. Its


```

Procs `

3` and

 Updates `6` are already correct (`docs/ace.md:5850`, `docs/ace.md:6019`, `INSTALL.md:65`, `INSTALL.md:106`).

Adjacent stale list (not in the requested set, same bug): `docs/configuration.md:157-160` still orders **Projects, Statistics, Procs**.

### 2. Beads / Plans / Files filter bars are always on

Code:

```46:46:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/widgets/artifacts/bead_filter_bar.py
    PERSISTENT = True
```

```39:39:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/widgets/artifacts/plan_filter_bar.py
    PERSISTENT = True
```

```37:37:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/widgets/artifacts/file_filter_bar.py
    PERSISTENT = True
```

Visual grammar already matches (`docs/artifacts_pane_visual_grammar.md:12-16`, `:37-45`).

`docs/ace.md` still says the bars appear

 only while editing:

```

265:266:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/ace.md
Beads and Plans use the same live editor
interaction, but show the input row only during an edit session.
```

```620:621:/home/bryan/.local/state/sase/

workspaces/sase-org/sase/sase

_12/docs/ace

.md
`f` opens the same live filter row provider

 document panes use, visible only

 during an
edit session,

 and `/` opens it too.
```

```2426:2428:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/ace.md
`/` is the app-level query key on every Artifacts pane. On Patches and Stitches it
focuses a filter row that is always on screen; on Beads, provider document panes, and
Files it opens an inline filter bar that is only visible while you are editing.
```

### 3. Files kind cycle is `z`, not `s`

Default keymap:

```471:471:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/default_config.yml
      files_cycle_kind: "z"
```

The Files table already says `z` (`docs/ace.md:584`). The same subsection then teaches `s`:

```632:634:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/ace.md
Files-pane filters do not support negation; a leading `-` is rejected with an explicit
error rather than excluding a match. `s` and the `kind:` token drive the same filter
state: cycling with `s` closes an open edit session and sets `kind:` to the next stored
```

Live bindings come from `build_app_bindings()` (`src/sase/ace/tui/actions/_state_init_late.py:259-278`), so the hardcoded `Binding("s", "files_cycle_kind")` in `src/sase/ace/tui/bindings.py:176` is not the user-facing default.

### 4. Monitor rows do **not** use the configured label as a left-side title

Test and renderer:

```52:79:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/tests/ace/tui/widgets/test_agent_list_tree_titles.py
def test_monitor_row_uses_glyph_without_label_or_command() -> None:
    ...
    assert "research-swarm priority check" not in left.plain
    assert "just check-full" not in left.plain
    assert "08b--mon" in left.plain
```

```91:114:/home/bryan/.local/state/sase/workspaces/sase-org

/sase/sase_12/src/sase/ace/tui/models/_agent_tree.py
def agent_tree_title(agent: Agent) -> str | None:


    """Return the Agents-tab left-side title, or ``None`` for sase shells.
    ...
    if agent.is_monitor:
        return True
```

`docs/ace.md:1950-1952` already says shells omit the left title. This

 paragraph contradicts it:

```1880:1882:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/ace.md
A monitor shell ... renders its own amber `⚙

` glyph beside the bash/python step glyphs
below, with its configured label as the row title and a live elapsed

 suffix or
exit-code/timeout badge instead of the statuses above.
```

Identity is the right-hand `%id` (`08b--mon`), not `monitor_label`.

---

## SHOULD ADD

### Beads query facets

`BeadFilterBar` and `filter_query.py` accept `due:` (`live`/`soon`/`due`) and extra `has:` values `+1` and `reopened`:



```57:66:/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase

_12/src/sase/bead/filter

_query.py
BEAD_FLAG_DUE_VALUES: tuple[str, ...] = ("live", "soon", "due")
BEAD_HAS_VALUES: tuple[str, ...]

 = (
    "+1", "reopened", "plan", "bug", "deps", "notes", "triage",
)
```

`docs/ace.md:338-347` lists Beads keys and `has:` without `due:`, `+1`, or `reopened`. Completions already advertise them (`bead_filter_bar.py:53-58`).

### Host-owned `limit:` / paging in the pane contract

`docs/ace.md:147-149` and `:318-329` document `limit:N` and `Ctrl+J`/`Ctrl+K`. `docs/artifacts_pane_visual_grammar.md` covers the always-on bar. `docs/artifacts_pane_contract.md` has neither `limit:` nor paging; `filter_session` still just says “Inline filter bar / `edit_query`” (`docs/artifacts_pane_contract.md:35`).



### INSTALL.md update story

 vs `,U`

Plugin install from Updates is still the right recipe (`INSTALL.md:59

-73`; pane

 factory still `PluginsBrowserPane` at catalog `82-88`).

 Completeness only:

- `#

` opens **home** first; `6` then enters Updates (`docs/ace.md:2512-2515`).
- Batch install is `I`/`Space

` then `i` (`docs/plugins.md:56-60`).
- Fast SASE/provider/agent update is `,U` (

cached snapshot; no live catalog). It cannot install a plugin.

Admin Center auto-check plumbing is **not** gone. Automatic snapshots still paint the top-bar badge; `,U` reads those caches (`src/sase/ace/tui/actions/base.py:149-179`, `docs/ace.md:6036-6050`, `docs/configuration.md:343-366`).

### Memory panel

User-facing docs (`docs/ace.md:5322-5422`) match `ace.keymaps.memory` (`src/sase/default_config.yml:351-376`) and `memory_panel_section()` (`help_modal/binding_common.py:163-191`): `gm` / `Ctrl+G m`, tree + chips, `p`/`P`/`Ctrl+P

`, `a`/`e

`/`d`/`I`, `o`/`Z`/`y`/`Y`/`r`/`?`. No must-fix gap. Optional: note that `Enter` is listed on `follow_link` but only `l` follows a chip (already in the prose; also in `memory_panel_help_modal.py:69-73`).

---

## Already documented correctly

| Feature | Docs | Code |
|---|---|---|
| Help is bare `?`, not `,?` | `docs/ace.md:74-75`, `:826`, `:2510`,

 `:2382` | `show_help: "question_mark"` (`default_config.yml:563`) |
| `,U` Update panel | `docs/ace.md:837`, `:2388`, `:6045-6048`; `docs/plugins.md:276-277` | `update_sase: "U"` + `action_update_sase_shortcut` (`default_config.yml:722`, `actions/base.py:153

-179`);

 keys

 `e/s/

p/a` (`

update_panel.py:49

-56`)

 |
| Admin Center Updates `#

` then

 `6

`,

 `i`/`x` | `INSTALL.md:64-

73`; `docs/plugins.md:54-65`; `docs/ace.md:6018-6027` | tab number `6` (`config_center_catalog.py:147-

154`); keymap in `docs/configuration.md:387-400` |
| Launch Control `t` + `sase tmux-agent` | `docs/ace.md:2839`, `:2997-3043` | `tmux_agent` config + catalog |
| Soft vs hard provider disable | `docs/ace.md:2924-2970` | Launch

 Control provider routing; catalog tests `test_soft_disable_annotates_but_does_not_exclude` |
| Current-project chip + Projects `c` | `docs/ace.md:2625-2647`, `:3569

-3602` | `set_current_project: "c"` (`default_config.yml:400`) |
| Always-on query bar grammar | `docs/artifacts_pane_visual_grammar.md:12-16`, `:37-45` | `FilterBar.PERSISTENT` |
| Host `limit:` + `Ctrl+J`/`Ctrl+K` (

user guide) | `docs/ace

.md:147-149`, `:318-329` | `artifacts_load_more/unload` (`default_config.yml:426-428`) |
| Jump last error `,L` | `docs/ace.md:838`, `:2389`; Logs tab in `docs/configuration.md:249-254` | `jump_to_last_error: "L"`; `action_jump_to_last_error` + `register_error` toast (`actions/base.py:130-139`, `failure_messages.py:19-27`) |
| Monitor `⚙` / `⚙N` on tribes, clans, families, procs | `docs/ace.md:148

3-1487

`, `:1876-189

9`, `:5911-5923` | `_agent_list_render_agent.py:501-513`; procs pane chips |
| `FAMILY` / `AGENT SHELL` headers | `docs/ace.md:1046-1050`, `:3980-3987` | `append_kind_header(..., "FAMILY"/"AGENT SHELL")` (`_agent_display_header.py:171-174`) |
| Hidden left titles on agent/proc shells | `docs/ace.md:1950-1952` | `agent_tree_title` returns `None` for monitors / family members / workflow `agent` steps |
| Notification tabs sort by configurable priority | `docs/notifications.md:80-101` | `ace.notification_tabs.*.

priority` (`default_config

.yml:215-227

`; beads

 shipped at `0`) |
| Gate input panels

 (`i`,

 Tab

, Ctrl

+S) | `docs

/notifications.md:1076

-123

4`; `docs/ace

.md:4494-4498` | `open_inputs: "i"`, `GateInputPanel` (`default_config.yml:302`, `gate_input_panel.py:53-59`) |

---

## Out of scope but same tab-number bug

`docs/telemetry.md:164` and `docs/perf_runbook.md:611` still say press `4` for Statistics.

Documentation audit against current

 source (workspace

 `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12`). `ace.md` and `cli.md` were used only as witnesses, not scored.

---

## MUST FIX

### 1. `CONTRIBUTING.md` still teaches the old `bd` CLI
[CONTRIBUTING.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/CONTRIBUTING.md

) lines 59

–65:

```59

:65:CONTRIBUTING.md
## Submitting Issues

This project

 uses `bd` (beads

) for issue tracking:

```bash
bd create --title="Description" --type=bug --priority=2
bd ready    # See available work
```
```

Current create path is `sase bead create -T 'task(<slug>)' --size … -f …` (`src/sase/main/parser_bead_lifecycle.py`). New tasks require a catalog type. `tools/sase_bead` is a wrapper around `sase bead`, not `bd`. This will send contributors to a nonexistent/wrong tracker.

### 2. Current project is documented in the wrong places, and the CLI dest page omits it
`sase project current` / `set-current` exist (`src/sase/main/parser_project.py`, `project_handler_current.py`). They promote the VCS xprompt MRU head (`~/.sase/vcs_xprompt_mru.json`).

- [cli.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/cli.md) (witness) routes both commands to `project_spec.md#project-lifecycle`.
- [project_spec.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/project_spec.md) “Project Lifecycle” only covers `PROJECT_STATE` (`enable`/`disable`/`set-state`/`alias`). No `current`, no `set-current`, no MRU.
- [configuration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/configuration.md) `sase project` table (≈4164–4177) lists `list`, `current`, `show`, `set-state`, `enable`, `disable` — **not** `set-current`. The only mention is under `ace.current_project` (line 846).

Current project is not a lifecycle state. The dest page and the command table are the user-facing holes.

### 3. `configuration.md` ACE YAML sample still uses retired `commits`
Shipped default (`src/sase/default_config.yml` 164–172):

```yaml
ace:
  artifacts:
    stitches:
      default_query: "sidecar:false merges:hide since:24h"
```

Abridged sample ([configuration.md](/home/bryan/.local/state/sase/workspaces

/sase-org/

sase/sase_

12/docs/configuration.md

) 661–

667):

```yaml


ace:
  artifacts:
   

 commits:
      default_query: "sidecar:false since

:24h"
```



The same page later says `ace.artifacts.commits` is a deprecated alias. Copy-paste of the sample writes the old key and drops `merges:hide`.

### 4. `llm_provider.model_tier_map` is documented as live; nothing reads it
Present in schema (`src/sase/config/sase.schema.json`) and in the primary samples/tables in both [configuration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/configuration.md) (1592–1620) and [llms.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/llms.md) (1034–1075).

Repo-wide, those are the only hits besides the schema. Providers use hardcoded `_TIER_TO_MODEL`. Launch routing is size aliases + `default_model` / lander fields. A user setting `model_tier_map.large: opus` gets a schema-valid no-op.

### 5. `axe.md` still says five default lumberjacks
[axe.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/axe.md) line 178: “

Axe ships with five default lumberjacks.”

`src/sase/default_config.yml` and the rest of the same page list **six**: `hooks`, `waits`, `checks`, `external_mirror`, `comments`, `housekeeping`. The blog post [axe-background-daemon.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/blog/posts/axe-background-daemon.md) still lists the old five (no `external_mirror`).

---

## SHOULD ADD

### Workspace occupancy in `workspace.md`
`sase doctor -C workspace.occupancy_conflicts` is implemented (`src/sase/workspace_provider/occupancy_conflicts.py`, `src/sase/doctor/checks_workspace.py`) and described in `configuration.md` / `cli.md`. It reports, and never repairs:

- duplicate RUNNING claims

 on one

 workspace number
- live claim vs occupant pid mismatch
- occupant record with no RUNNING claim

[workspace.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/workspace.md) covers `list` / `repair` / `cleanup` / `migrate` and “isolated per-project issues,” but never names this check. Add it next to the CLI table.

### Current project on the on-ramp
[getting_started.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/getting_started.md) never mentions `sase project current` / `set-current` or the ACE `+<project>` chip. That is the daily “which project am I on?” surface after first launch.

### Provider-disable / weekly-limit pointer from `agent_providers.md`
[llms.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/llms

.md) already

 has hard

 vs soft disable,

 last-resort

 tails, Grok `@xlarge` `@xhigh`, Claude weekly-limit dates, and Grok 48h paid-usage auto-disable. [agent_providers.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/agent_providers.md) has Grok effort/`@xhigh` but no disable modes or auto-disable. A short “if doctor/Launch Control says the provider is disabled, see …” would close the install-guide gap.

### Last-resort in the `llms.md` field table
Selector grammar later on the page is correct (`(A | B) || C`). The `model_aliases.builtin` table row (line 1080) still says only “single-target / `|` pool / `||` fallback.” `configuration.md` already includes last-resort.

### `CONTRIBUTING.md` verification vs beads
The `just check` / `just check-full` block matches [development.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/development.md). After replacing `bd`, point issue filing at `sase bead onboard` / `sase bead create -T 'task(…)'`.

---

## OK (checked, current)

|

 Page | Evidence

 |
| --- | ---

 |
| [docs

/index.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/index.md) | Role cards match current surfaces; no stale commands. |
| [README.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/README.md) | Provider list, `#git:home`, explicit-only muse/grok, `just check-full` match source. |
| [INSTALL.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/INSTALL.md) | Updates-tab plugin install (`#

` → `6` → `i`) is

 still implemented (`plugins_browser_install.py`; keymap table in configuration.md 394). Not retired. |
| [docs/memory.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/memory.md) | Memory panel (`gm` / `Ctrl+G m`), generated `glossary.md`, `sase glossary all` / `read -r`. |
| [docs/beads.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/beads.md) | Three issue types; flag is `task(flag)`; task type required; `sase bead snooze`; `sase bead task-type`. |
| [docs/monitors.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/monitors.md) | Required `--start-status` / `--stop-status`, 20-char cap, TESTING/TESTED pair. |
| [docs/llms.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/llms.md) | Last-resort tails, hard/soft disable, usage-limit auto-disable, generated alias table matches `model_alias_defaults.yml` (including Grok `@xlarge` `@xhigh`). Aside from `model_tier_map` above. |
| [docs/plugins.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs

/plugins.md) | GitHub search sharding past 1000 results (152–155). |
| [docs/init.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/init.md) | Generated glossary note + `sase glossary read`. “Current project” here means cwd/init target, not MRU. |
| [docs/xprompt.md](/home/bryan/.local/state/sase/workspaces/sase

-org/sase/

sase_12/docs/xprompt.md) | No `@task_worker`.

 Retired `#ref/` called out. Effort/`xhigh` current. |
| [docs/development.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/development.md) | Two-speed `just check` / `just check-full` matches the Justfile story. |
| [docs/query_language.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/query_language.md) | `project:` uses `PROJECT_NAME`; free-text “directory basename” matches `searchable.py`. |
| [docs/getting_started.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/docs/getting_started.md) | Typed task create, monitors, glossary. ACE still has three tabs (Agents / Artifacts / Axe). |
| [mkdocs.yml](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/mkdocs.yml) | Every user-facing `docs/*.md` page is in `nav`. No dangling nav entries. |

---

## Stale-claim grep (non-`ace.md` / non-`cli.md`)

| Claim | Result |
| --- | --- |
| `,?` as help | Not found. Help is `?` / `question_mark`. |
| Launch Control rows

 “

launch model” / “

running agents” | Not

 used as row labels.

 `ll

ms.md` / `configuration

.md` say

 `default model` / `

max runners`. Ordinary

 prose

 “launch

 model” / “running agents

” is fine. |
| `sase_claude_tool_hook` | Only in `llms.md` as a script that **no longer ships**. |
| `sase bead create --tier` without `-r` | Examples use `--tier`; create parser is `-r, --tier`. Valid. |
| `cycle_commits` as canonical | Only as a **legacy alias** of `cycle_stitches` (`keymaps/registry.py`). Correct. |
| Updates-tab plugin install retired

 | Still

 present (`i

` / marks

 / preview). Do not remove. |
| `publications` lumberjack / `sidecar_publication` chop | Not advertised as current. `CHANGELOG.md` records removal. |
| `@task_worker` recommended | Not in docs. |

---

## Feature coverage (post-refresh)

| Feature | Where it already lives | Gap |
| --- | --- | --- |
| Current project | `configuration.md` `ace.current_project`; ACE Projects `c` | Dest page + `sase project` table + getting started |
| Flag = `task(flag)` | `beads.md`, `axe.md` FlagTriage | None |
| Hard/soft disable; Claude weekly / Grok paid auto-disable | `llms.md`, `configuration.md` | Pointer from `agent_providers.md` |
| Last-resort tails; `@xlarge` Grok `@xhigh` | `llms.md`, `agent_providers.md`, generated alias table | Field-table wording only |
| Monitor required status labels | `monitors.md`, getting-started component map | None |
| Occupancy conflicts in doctor | `configuration.md`, `cli.md` | `workspace.md` |
| Plugin catalog sharding | `plugins.md` | None |
| Task type required | `beads.md`, getting started | None |
| Generated glossary + `sase glossary all` | `memory.md`, `init.md`, `configuration.md` | None |
| Memory panel from memory.md | `memory.md` 38–43 | None |
| `sase bead snooze` | `beads.md` | None |

Highest-impact edits: replace `bd` in `CONTRIBUTING.md`; document `sase project current` / `set-current`

 on `project_spec.md

` and in the `configuration.md` command table; fix the ACE YAML sample; stop teaching `model_tier_map` as effective; change “five lumberjacks” to six.

This audit used live argparse definitions under `src/sase/main/` (especially `_COMMAND_REGISTRARS` in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/main/parser.py`) plus the help-capture tests in `tests/main/test_parser_root_help.py`. This environment has no shell, so `sase --help` was not executed; compact vs full help text is taken from those sources.

---

## MUST FIX

### 1. `sase agent list` does not include finished runs by default

**CLI:** `sase agent list` help is “List running agents”. `-a/--all` “Include recently-completed DONE/FAILED agents (capped at 50 most-recent per project)”. Implementation calls `list_running_agents()` unless `include_recent` (`src/sase/agents/cli_list.py`, `src/sase/integrations/agent_list_entries.py`).

**Docs that mislead a new user:**
- `docs/cli.md`: “List active and recent agents across projects.”
- `docs/getting_started.md` Step 3: “`sase agent list` gives you the first visible handle … while the model is thinking **or after it finishes**.”
- `docs/getting_started.md` Step 5: “Wait until `sase agent list` reports that the run is done before continuing.”

After the run finishes, default `sase agent list` goes empty. The wait instruction can never be satisfied without `sase agent list -a`.

### 2. `sase monitor start` required status flags are missing from the CLI index

**CLI:** `-s/--start-status` and `-S/--stop-status` are required; omitting either exits 2 (`src/sase/main/monitor_handler.py`, messages starting `sase monitor start: -s/--start-status is required`). Parser help: “Required label … Pair with -S/--stop-status. Max 20 characters.” Epilog: `sase monitor start -s TESTING -S TESTED -- just check-full`.

**`docs/cli.md` Automation table:** only “Hand a command to a detached supervisor and return; kills the caller.” No mention of `-s`/`-S`.

**`docs/monitors.md` is closer**, but still wrong on other required flags (next item).

### 3. `docs/monitors.md` overstates required flags and documents a hidden command form

**Actual CLI:**
- Command: remainder `-- COMMAND`. `-c/--command` exists with `help=argparse.SUPPRESS`; error text calls it “the hidden `-c/--command` alias”.
- `-r/--reason` defaults to `"run command"` (`DEFAULT_REASON`).
- `-t/--timeout` defaults to 1h (`DEFAULT_TIMEOUT_SECONDS = 3600`, parser help “default: 1h”).
- Only the command plus `-s`/`-S` (and an agent, from env or `-a`) are required.

**`docs/monitors.md` “Starting a monitor”:**
```bash
sase monitor start \
  --command 'just check-full' \
  ...
```
Claims: “`--command` / `-c` is the full command”; “`--reason` / `-r` and `--timeout` / `-t` … **are required**”.

A user copying `--help` examples uses `-- COMMAND`. A user following monitors.md thinks omitting `-r`/`-t` fails; it does not.

### 4. `sase patch show` is documented and even emitted by the product, but it is not a command

**CLI:** `sase patch` subcommands include `current`, `ref`, `search`, `set-origin`, `sync-deltas`, `sync-external`, `migrate-extension`, plus ACE-oriented verbs (`status`, `accept`, `mail`, …). There is no `show`.

**Docs / code:**
- `docs/getting_started.md`: Patch expansion includes “a `sase patch show` inspection hint.”
- `docs/llms.md`: same hint.
- `src/sase/artifact_providers/builtin_entry_patch.py`:  
  `"(inspect with \`sase patch show {display_label}\`)"`

Closest real commands: `sase patch current`, `sase patch search`.

### 5. `sase agent kill` needs `-n/--name`, not a bare name

**CLI:** `sase agent kill -n NAME` (`required=True`). Skills already say `sase agent kill -n <name>`.

**`docs/cli.md`:** “`sase agent kill` — Terminate a running agent.” Contrast `sase agent restart`, which does take positional `NAME`. `sase agent kill NAME` is usage error.

### 6. `sase chats` is not a command

**`docs/monitors.md`:** “`sase chats`, `%wait`/`#fork` resolution”.

**CLI:** `sase chat` / `sase chat list` / `sase chat show`.

---

## SHOULD ADD

### Completeness gaps in `docs/cli.md` (command exists, index is silent or too thin)

User-facing commands registered in parsers but absent or only implied in the `docs/cli.md` tables:

| Live command | Notes |
|---|---|
| `sase bead snooze` | Fully documented in `docs/beads.md` (`#snoozing-a-task-bead`); **not in the cli.md bead table**. |
| `sase bead note` | Attributed notes; help exists. |
| `sase bead history` | Event history. |
| `sase bead ref` | Index mentions it only in the list-delegation paragraph. |
| `sase bead task-type` | Same; `list`/`show` are

 the catalog surface getting

_started already uses. |
| `sase bead sync-external` | Documented in `docs/beads.md`, not in cli.md. |
| `sase bead epic-symbols` | Justfile whitelist inspector. |
| `sase bead resolve-conflicts` | Mechanical beads-store merge helper. |
| `sase bead apply-status` | Headless status apply (ACE/proc). |
| `sase config init` | Owner identity; `docs/init.md` treats it as first-class. cli.md only has `layers` / `show` / `mentor-match`. |
| `sase config migrate-keymap-actions` | One-shot keymap rewrite. |
| `sase commit` | Legacy alias of `sase stitch create` (help says so). cli.md Review table only lists `sase stitch create`. |
| `sase flag show` | Bundled into the `flag list` row. |
| `sase agent retire-v1` | Public help: retire legacy-v1 sidecar payload. |
| `sase agent persist-cleanup` / `persist-directive` / `revert` | Show in `sase agent --help` (noninteractive ACE/ops). |
| `sase patch status|accept|archive|mail|rebase|restore|revert|rewind|reword|submit|sync|tag` | Public `sase patch --help` verbs; cli.md only lists inspect/maintain helpers. |
| `sase notify apply-state` / `apply-state-many` | Durable notification state (ACE procs). |
| `sase plan links refresh` | cli.md has list/repair/validate only. |
| `sase prompt copy` / `edit` / `search` / `select` | Public prompt subcommands; index only lists list/show/run/save/prune. |
| `-H/--full-help` | Root compact help shows 13 “Common commands” and says use `sase --full-help`. **cli.md never mentions this.** New users who run `sase --help` will not see `tmux-agent`, `glossary`, `monitor`, `flag`, etc. |

### Details-page gaps for commands that *are* in cli.md

- **`sase project current` / `set-current`:** cli.md is accurate. The Details link `project_spec.md#project-lifecycle` never mentions current project or `set-current`. `docs/configuration.md` `#sase-project` table lists `current` but **omits `set-current`**. ACE/`docs/ace.md` do document both.
- **`sase tmux-agent`:** Index is a one-liner. Full flags (`-l/--list`, `-n/--dry-run`, `-e/--effort`, `-s/--safe`, …

) live in

 `docs/configuration.md#sase-tmux-agent` and `docs/ace.md#tmux-agent`. Fine if the index is allowed to be thin; the Details cell only points at `ace.md#tmux-agent`.
- **`sase flag new`:** cli.md says “three required **prose arguments**”. They are required **flags** `--when-enabled`, `--when-disabled`, `--remove-when` (plus positional `<key>`). `docs/configuration.md#sase-flag` and `docs/beads.md#flag-bead-lifecycle` get this right.
- **`sase monitor`:** cli.md should at least say “see monitors.md for required `-s`/`-S` and `-- COMMAND`”.

### INSTALL.md / README.md / getting_started.md

- **INSTALL.md** and **README.md** match live commands for `sase version`, `sase doctor`, `sase doctor -D`, `sase core health`, `sase agent-cli`, `sase completion install`, `sase update`, `sase plugin *`, Muse `sase agent-cli install muse`. No must-fix CLI drift found there.
- **getting_started.md** extra issues beyond agent-list and `sase patch show`: Step 5 tells users to wait on default `sase agent list` for DONE. Artifact `create -p` / `list --explicit` still match the parser.

---

## OK /

 already documented

These “likely-new” surfaces **are** documented in enough detail that a user who follows the Details link will not be misled:

| Command | Where it matches live CLI |
|---|---|
| `sase tmux-agent` | `docs/cli.md`, `docs/ace.md#tmux-agent`, `docs/configuration.md#sase-tmux-agent`. Bare invocation paints a tmux menu (no `list` child); `-l/--list` is a flag. |
| `sase project current` / `set-current` | `docs/cli.md` body (MRU, accent color, `--json`, exit 0 when unset, ACE Projects `c`). Parser description matches. |
| `sase glossary all` | `docs/cli.md` + `docs/memory.md#glossary` (alphabetical full dump, not audited; agents use `glossary read -r`). |
| `sase monitor start` **required `-s`/`-

S`** | `docs/mon

itors.md`

 and

 `/sase_monitor

` skill;

 **not** the

 cli.md table. |
| `s

ase agent restart`

 | `docs/

cli.md` and

 `docs/ace

.md`

 `,x`.

 Flags `-n/-y/-m/-j`, chat kept, `~/.sase/restarts/`, exits 0/1/2 including `partial` / `wipe_failed` match `src/sase/agents/cli_restart.py`. |
| `sase bead snooze` | `docs/beads.md` flags `-u/-p/-r/-c` match `register_bead_snooze_parser`. |
| `sase flag new` | `docs/configuration.md#sase-flag`, `docs/beads.md#flag-bead-lifecycle`. Requires SASE-managed checkout; three `--when-*` flags; `-k beta` default. |
| `sase memory show` | `docs/cli.md` + `docs/memory.md#show-a-note` (no audit; agents must `memory read --reason`). |
| List-defaulting groups | cli.md’s “bare group → `list`” note matches parser `_default_list_subcommands`. |
| Feature-flag globals | `-f/--enable-feature`, `-F/--disable-feature` match root parser. |
| `sase run` / `sase ace` / `sase doctor` / `sase version` / `sase artifact` handoff | README/INSTALL/getting_started agree with parsers (including `#git:home` default and Muse/Grok explicit model). |

Hidden / internal (SUPPRESS help): `sase monitor _supervise`, `sase axe bgcmd-launch`, `sase file-hook exec-batch`, `sase stitch

 post-write`, `sase workspace open`, `sase tmux-agent --renumber`, mobile `*-bridge` children. Correct that they are not first-class index rows; cli.md still lists `mobile agent-bridge` / `helper-bridge` as JSON bridges, which is acceptable.

---

## Suspected code bugs (docs would document actual behavior)

1. **`sase patch show` is invented by the Patch `@` expander**

 (`builtin_entry

_patch.py`

 format

 string). Agents and users will try a command that argparse does not register. Docs currently copy that bug.
2. **Monitor start public vs hidden `--command`.** Skills (`AGENTS.md`, `src/sase/xprompts/skills/sase_monitor.md`) and `docs/monitors.md` still teach `-c/--command`. Parser help hides it and promotes `-- COMMAND`. Both work; `--help` and docs disagree.
3. **Compact root `sase --help` vs “every command”.** Compact common commands are only: `ace`, `agent`, `bead`, `doctor`, `init`, `memory`, `patch`, `project`, `prompt`, `run`, `stitch`, `version`, `workspace`. `docs/getting_started.md` “CLI reference — every `sase` subcommand on one page” is also not true of `docs/cli.md` today.

---

## Compact inventory vs `docs/cli.md`

**`sase --help` (compact):** 13 common commands + globals + examples (`sase doctor`, `sase init -c`, `sase run "#git:home …"`, `sase ace`, `sase agent list`, `sase --full-help`).

**`sase --full-help` / `_COMMAND_REGISTRARS` top-level names:**

  


`ace`, `agent`, `agent-cli`, `artifact` (`artifact-file`), `axe`, `bead`, `changespec` (alias), `chat`, `comments`, `commit` (legacy `stitch create`), `completion`, `config`, `core`, `doctor`, `editor`, `file`, `file-history`, `file-hook`, `flag`, `gate`, `glossary`, `init`, `launch`, `logs`, `lsp`, `memory`, `mobile`, `monitor`, `notify`, `path`, `patch`, `plan`, `pipe`, `plugin`, `proc` (`task` alias), `project`, `prompt`, `questions`, `repo`, `repro`, `restore`, `revert`, `revive-log`, `run`, `skill`, `stitch` (`vcs`

 alias), `telemetry

`, `tmux-agent`, `update

`, `validate`,

 `var`, `version`, `workspace`, `xprompt`.

**

Document

ed in cli.md but gone/renamed:** only `sase patch show` / `sase chats` (those are in sibling docs, not the cli.md tables). No table row names a deleted top-level command.

**Highest-impact new-user errors:** wait on `sase agent list` for DONE; `sase monitor start` without `-s`/`-S`; `sase agent kill NAME`; follow a `sase patch show` hint.

The audits found several user-facing mismatches. I’ll verify the highest-impact ones against source, then update the docs.

I’ve confirmed the mismatches. Next I’ll update the user-facing docs to match current behavior.

I’ll run install and the documentation checks next.

User-facing docs now match current SASE behavior. The last full refresh was 18 August; this pass checked the docs against live CLI, config, and ACE code rather than the commit log.

## Accuracy

- **`sase agent list`** lists running agents only. `getting_started.md` no longer tells you to wait for DONE on the default list; use `-a` or ACE after a run finishes.
- **`sase agent kill`** requires `-n/--name`.
- **`sase monitor start`** takes the command after `--`. `-s`/`-S` are required; `-r` and `-t` have defaults (`run command`, `1h`). `-c/--command` is a hidden alias, not the documented form.
- **ACE Artifacts filter bars** stay on screen for Beads, Plans, Files, and document panes, not only while editing.
- **Files kind cycle** is `z`, not `s`.
- **Admin Center tabs** are Config `1`, Logs `2`, Procs `3`, Projects `4`, Statistics `5`, Updates `6`, XPrompts `7`.
- **Monitor rows** have no left-side title; identity is the right-hand `%id`.
- **`CONTRIBUTING.md`** no longer teaches the standalone `bd` CLI. Issue filing is GitHub Issues plus `sase bead create -T 'task(<slug>)'`.
- **`llm_provider.model_tier_map`** is schema-valid but unused; size aliases and lander settings choose models.
- **Axe** ships six default lumberjacks, including `external_mirror`.
- The ACE YAML sample uses `artifacts.stitches.default_query` with `merges:hide`.

## Completeness

- Current project is documented on `project_spec.md`, in Getting Started, and in the `sase project` command table (`current` / `set-current`).
- The CLI index lists `sase --full-help`, bead snooze/note/ref/history/task-type/sync-external/resolve-conflicts, `sase config init`, and required monitor status flags.
- Beads query facets include `due:` and `has:+1` / `has:reopened`.
- `sase bead work` refuses a launch that can only run on a hard-disabled provider.
- Workspace occupancy is covered next to `sase workspace repair`.
- Provider install docs point at hard/soft disable and usage-limit auto-disable.
- INSTALL mentions `,U` for snapshot updates; plugin install/uninstall stay on Admin Center Updates (`#` then `6`).

## Verification

`just fmt-md-check`, `just docs-check`, `just docs-pdf-check` (782-page handbook), and `just check` all passed. Only documentation files were changed.

## Suspected code bugs (not fixed)

1. **Patch expansion invents `sase patch show`.** Launch-time `@patch:` expansion still emits that inspection hint, but argparse has no `show` subcommand. Inspect a Patch from ACE, with `sase patch search`, or with `sase patch current` in that workspace. Docs now warn about the hint.
2. **`llm_provider.model_tier_map` is dead config.** The schema accepts `large`/`small`; nothing in the runtime reads them.
3. **The `/sase_monitor` skill still teaches `-c/--command` and required `--reason`/`--timeout`.** That skill is generated source, so it was left alone. The user guide now matches `--help`.
4. **Hardcoded Files bindings disagree with config.** `bindings.py` still maps `s` to `files_cycle_kind`; shipped `default_config.yml` maps `z`. Runtime uses the config keymap.

I'll start from the full prompt, the commit skill, and the current git/docs state so I can finish the documentation refresh and commit only the intended files.

The docs edits are already in the tree. I’ll review the remaining prompt, the actual diffs, and whether the audit items are fully covered before committing.

The smaller files look updated. Next I’ll inspect the larger diffs and confirm whether any audit items were left out.

I’ll spot-check remaining audit items in the config and CLI docs, then run the documentation checks before committing.

The refresh is already in the tree. I’ll add the missing pane-contract paging note, then run docs checks and commit.

I'll add the missing pane-contract paging note, then run install and the documentation checks.

Checks passed. I’ll record the commit skill, write the message, and create the documentation commit.

User-facing docs now match current SASE CLI and ACE behavior. The refresh is committed and pushed as `3078146fe`.

**Accuracy**
- `sase agent list` shows running agents only; finished runs need `-a` or ACE. `sase agent kill` requires `-n`.
- `sase monitor start` takes the command after `--`. `-s`/`-S` are required; `-r` and `-t` default to `run command` and `1h`.
- Artifacts filter bars stay on screen. Files kind-cycle is `z`. Admin Center tabs are Config `1`, Logs `2`, Procs `3`, Projects `4`, Statistics `5`, Updates `6`, XPrompts `7`.
- Monitor rows have no left-side title; identity is the right-hand `%id`.
- `CONTRIBUTING.md` uses `sase bead create -T 'task(<slug>)'`, not the standalone `bd` CLI.
- `llm_provider.model_tier_map` is schema-valid but unused. Axe ships six default lumberjacks.

**Completeness**
- Current project is documented on `project_spec.md`, Getting Started, and the `sase project` table.
- CLI index covers `--full-help`, bead snooze/note/ref/history/task-type, required monitor status flags, and `sase config init`.
- Beads query facets include `due:` and `has:+1` / `has:reopened`. The pane contract now names host-owned `limit:` paging.

**Verification:** `just fmt-md-check`, `just docs-check`, `just docs-pdf-check` (782-page handbook), and `just check` all passed. Only documentation files were changed.

**Suspected code bugs (not fixed)**
1. Patch `@` expansion still emits `sase patch show`, which is not a command.
2. `llm_provider.model_tier_map` is accepted by the schema and unread at runtime.
3. The `/sase_monitor` skill still teaches hidden `-c/--command` and required `-r`/`-t`.
4. `bindings.py` still maps Files kind-cycle to `s`; the shipped config and runtime use `z`.
