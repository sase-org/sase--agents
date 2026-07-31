# Chat History - ace-run (chop.refresh_docs.sase.2_860680.1)

- **TIMESTAMP:** 2026-07-31 18:44:47 EDT
- **MODEL:** claude/sonnet
- **AGENT:** chop.refresh_docs.sase.2_860680.1

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.2_860680.1, tribe=chop)
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

I'll start by surveying the repository structure and existing documentation to understand what needs refreshing.

Now launching five parallel research agents to map source changes since the last docs refresh (commit `e93ab3db0`, 2026-07-30) to documentation gaps.

Five research agents are now running in parallel to map source changes since the last docs refresh onto documentation gaps. I'll wait for them to complete before making edits.

Now let me look at the full diffs in more detail, particularly the ones that matter for docs.

Baseline `just docs-check` build is running in the background too. I'll wait for the research agents and the build check to complete before making any edits.

That tool is only for `/loop` sessions — not needed here. I'll simply wait for the background notifications to arrive.

That axe.md reference is unrelated (description grammar analogy). Now let's check docs/agents_sidecar.md and docs/development.md for relevant content.

Baseline confirmed clean (exit 0, no warnings). Now waiting on the five research agents.

I'll stop polling and just wait — task notifications will arrive automatically when each research agent finishes.

This matches docs/commit_workflows.md's description closely. Now let's confirm behavior in `workflow.py` for where the gate runs (still first stage, before bead association?), and check the `_log_commit_failed` reason string, plus check current `default_config.yml` and `sase.schema.json` for allowed_types list (in case changed later).

There's a `.venv`. Let me try running via it, and also read the fe397e363 full diff via the saved file.

Research agents are still running in the background — I'll continue once they report back.

Good, this confirms the docs are accurate here — subject gate is the first real check after payload-shape validation, before `apply_bead_commit_tag`. Now let's check the default_config.yml and schema.json current state for allowed_types, and check the sase_git_commit.md skill file fully as currently rendered.

This skill source file is already up to date (this is the actual sase_git_commit skill md, not docs/ — but it's the source that the doc commit updated). Now let's check `docs/configuration.md` current full commit.message section, and check anchors referenced (`configuration.md#commitmessage`).

Now let's read the current docs files in full.

Good — this example config block is already accurate (already dropped `research` per e023e68a9). Now let's view configuration.md lines 605-650 for the tribes table.

All source data matches the current docs. Now let's check `registry.py` / `alias_view.py` for the fakey-hiding behavior and `model_completion.py` to confirm docs about `%model` completion behavior are accurate, plus check `config.py` for `provider` enumeration and `_registered_provider_names()`.

Good, everything checks out and is consistent with docs. Now let me verify the `sase artifact` / model completion source referenced in docs, and double-check the `docs/llms.md` "Source" line for registry references still points to correct modules given the split (32c47e0d6).

Confirmed the glyph mapping matches docs (plan `▸`, phase `↳`, task `◆`). Now let's verify the `sase bead create` attribution behavior precisely, and check current `cli_crud.py` for the exact logic to document accurately.

Now let's confirm the identity resolution source order for `acting_agent_name`, checking `discover_agent_identity`.

That confirms it's an external Rust binding dependency (sase-core-rs), not vendored in this repo. Good — no need to verify further since it's out of scope; the tests in tests/workflows/test_commit_message_validation.py already validate the exempt-prefix behavior. Let's check those tests for confirmation and check the exempt list precisely.

Good, matches configuration.md description (though the doc says "squash!" and "amend!" too — let's verify those match too, but they're at least consistent with the doc's claim). This all checks out. Now let's look at `docs/beads.md`, `docs/init.md`, and other doc mentions to see if there's outdated conventional-tag lists (the old `_ALLOWED_TAGS` in commit_message.py).

Good, doctor checks aren't centrally enumerated elsewhere, so no additional gap there. Now let's confirm the exact current wording of the notification gate docs table and double check whether `task_triage` and generic_form gate debug entry point paragraph mentions it fully (line 551).

This is fine, no doc gaps here. Now let's double check `docs/configuration.md`'s "12 types above" — count the listed types: build, chore, ci, deps, docs, feat, fix, perf, refactor, revert, style, test = 12. Correct, matches default_config.yml. Now let's check the sase.schema.json defaults too, in case they differ, plus double check CONTRIBUTING.md for old commit conventions.

No mentions there — no gap. Now let's double check the "Bead association" note in the docs about "invalid_message" reason and confirm the exact string used in code for `_log_commit_failed`.

Good, that matches doc claim exactly (`commit_failed` run-log event with `reason="invalid_message"`). Now let's check whether `docs/commit_workflows.md`'s CLI arguments table or other sections reference the old (pre-gate) behavior anywhere else I might have missed. Let's also check `docs/getting_started.md` and `docs/development.md` for any mention of raw commit examples.

Good, table is complete and matches directory (16 rows for 16 files minus SKILL.frame.template.md). No gap there. Now let's check the `tests/main/test_init_skills_handler.py` reference change from 642b4f490, and check docs/init.md for any residual mention of sase_beads as a skill source.

Confirmed. Now let's verify the `alias_view.py` "lazy import" comment about `registry` importing `config` at import time, to make sure the `Source:` line at 805 (`registry.py`, `_invoke.py`) is still the right citation, and check if `model_alias_config.py`/`model_alias_policy.py` should be cited near the "Implicit role aliases" section instead.

Good — confirms `ref add`/`rm` go through `resolve_cli_issue_ids` at the Rust CLI level too. This confirms the docs' blanket claim ("Every `sase bead` command argument that names an existing bead accepts either the full ID or its shorthand suffix...") is accurate. I now have enough to write the final report.

No specific gap there. Now let's check `docs/agents_sidecar.md` link `commit_workflows.md#cli-inputs-and-internal-payload` to verify it's still a valid anchor (unaffected, since that section heading didn't change).

I now have all the source verification needed. Let me compile the final structured report.

Good, anchors unaffected. Now let's confirm the `RunResult` / exit codes table doesn't need updates (FAILED covers invalid_message case, already correct — `RunResult.FAILED` with exit code 1, matches skill doc "1: Commit failed with a printed reason"). That's accurate already.

Let's also double check whether `docs/beads.md` mentions commit message conventions that might reference the old unenforced advisory tone.

No stale references remain. Now let's check the `config.py` doc-facing `_registered_provider_names` for accuracy and confirm the `sase doctor` cross-references in agent_providers.md/fakey.md are still accurate, plus verify the `sase skill init -p` provider list.

No override key exists — consistent with docs. Now let's check the doctor check for the memory README stats consistency, and double check the current `sase/memory/README.md` content fully for consistency.

Only one instance — confirmed. Now let's double-check the exact current text block once more for precision, and verify line numbers for the table row.

Now I have everything needed. Let me do one final check — confirm the `AdminCenterFooter`'s exact placement/behavior text and the config key binding help description, to make sure my proposed replacement text for docs/ace.md is fully accurate.

I now have all the evidence needed. Here is the structured audit report.

None of these touch the commit.message section. Good — confirms current docs state (as read) reflects only up through 2f565d0be plus unrelated later edits. This confirms my finding set is complete and current. Now let's compile the final report.

Good, confirmed at `src/sase/llm_provider/alias_view.py:444-456`. I now have everything needed to write a complete, grounded report.

Confirmed (the `792080e51` refactor moved `_append_stale_prefix_diagnostic` from `project.py` into `_project_queries.py`, unconditionally run by plain `sase bead doctor`). I have everything needed for the report.

---

# Documentation Gap Report: `docs/beads.md` (and `docs/cli.md`)

## Scope note

`docs/cli.md` was read in full. It is a high-level command index that links out to `beads.md` for detail (e.g. `sase bead update` / `open` / `close` / `rm` → "Mutate issue metadata or lifecycle state", `sase bead show` → "Show one issue"). None of its bead-related rows make a syntax claim that any of the audited commits invalidated (no claim of single-ID-only, no claim about compact-row shape, etc.). **No gaps found in `docs/cli.md`.** All gaps below are in `docs/beads.md`.

Also note: commits `7765a07c9`, `50988fe7f`, `7d4afb394`, `01ace663f`, and `22e78f792` already updated `docs/beads.md` in the same commit, and I verified those updates against current source — they are accurate (shorthand-ID resolution semantics, glyph-only compact rows, type glyph table, multi-ID `update`, `--fix-issue-prefix` repair flag). `792080e51`, `02e8d914c`, `3a98c68df`, `9d6b40c6c`(unrelated sdd feature), `c82eff9a0`, `889ddca89`, `6e96deaf8` are internal refactors/unrelated features with no doc-facing surface. The real gaps are all in commits that changed behavior but did **not** touch `docs/beads.md`: `578e4f5c6`, `b2b1e73d9`, `3b087669e` (creator-attribution feature), plus one doc completeness gap in `22e78f792`'s own doctor-checks bullet list.

---

## Gap 1 — Creator-attribution *policy* is undocumented (only the rendering is documented)

**Doc location:** `docs/beads.md`, `### sase bead create` section (~line 507-525), and/or a new subsection under "Data Model".

**What's wrong/missing:** `docs/beads.md` documents how a bead's creator is *displayed* (`CREATED BY` block added by commit `2c1525785`, at lines 774-777 and 787-788) but never documents how a bead's creator is *determined*. That resolution logic was added by `578e4f5c6` (`src/sase/bead/attribution.py`) and wired into bead creation by `b2b1e73d9` and `4fd54a967`, and none of those three commits touched `docs/beads.md`. A reader of the `### sase bead create` section (lines 507-525) has no idea what `created_by` will be set to, or why two beads created the same way sometimes show an agent name and sometimes show an email.

**Verified current behavior** (`src/sase/bead/attribution.py:63-83`, `src/sase/bead/cli_crud.py:117-125`, `sase-core` `crates/sase_core/src/bead/mutation.rs:186-205`):

- **Phase beads**: `resolve_bead_creator()` always returns `None` for `issue_type == "phase"`; Rust core then inherits `created_by` from the parent bead (`mutation.rs:196-204`) — a phase is never independently attributed.
- **Plan beads** (`plan(...)`/epic/tale): prefers the plan file's `proposed_by` frontmatter value (`plan_proposed_by()`, read directly from frontmatter, not via full plan validation). `proposed_by` is auto-stamped onto the plan file by `sase plan propose` (`src/sase/main/plan_propose_handler.py:136-139`, added by `b2b1e73d9`) from the *acting agent at propose time* — it is not something a user types. If no `proposed_by` is present, falls through to the acting agent.
- **Everything else** (`task`, and plan beads with no `proposed_by`): attributed to `acting_agent_name()` — the running agent's durable global name, resolved from `SASE_AGENT_NAME` or `agent_meta.json` under `SASE_ARTIFACTS_DIR` (never the bare `SASE_AGENT=1` launcher flag).
- **Fallback**: if no agent identity can be resolved at all (e.g. a human typing `sase bead create` at a shell), `resolve_bead_creator()` returns `None` and Rust core defaults `created_by` to the store `owner` (git `user.email`) — this is why some beads show `owner@example.com` and others show an agent name.
- This path only works for `sase bead create` because `4fd54a967` had to force `create` off the Rust *fast path* (`src/sase/main/bead_fast_path.py:27-33`) specifically because the fast path could not resolve the acting agent — worth calling out since a reader might otherwise assume every `sase bead` mutation attributes identically.

**Suggested replacement content** — add a new paragraph to `### sase bead create` (after the existing "ChangeSpec metadata is valid only on plan beads..." paragraph, line 525):

> New beads are attributed to the acting SASE agent (from `SASE_AGENT_NAME` or `agent_meta.json`), falling back to the store owner when no agent identity resolves. A `phase` bead always inherits its creator from its parent epic instead of being attributed independently. A `plan` bead prefers the `proposed_by` value `sase plan propose` stamps onto the plan file at proposal time, and falls back to the acting agent when the plan carries none. See [`sase bead show`](#sase-bead-show-id) for how the resolved creator is displayed.

---

## Gap 2 — Bead *pages* rendering of the creator is undocumented

**Doc location:** `docs/beads.md`, `## Bead Pages` section (~line 416-450).

**What's wrong/missing:** Commit `3b087669e` (`feat(bead-pages): render bead creators`) added a `**Created by:**` fact to every generated bead page's identity block (`src/sase/bead_pages/rendering_identity.py:127-149`), but that commit made **no** `docs/beads.md` change. The "Bead Pages" section currently says only:

> "Pages are generated projections, not hand-maintained state. They are rebuilt from the canonical bead event store plus the primary repository's commit history, and they link to the bead's plan, artifact references, parent and child beads, dependencies, associated agents, and commits."

This never mentions that the page's ownership line now also renders the creator, with a link to the hosted agent page when resolvable.

**Verified current behavior** (`src/sase/bead_pages/rendering_identity.py:127-149`, golden fixtures `tests/test_bead/golden/bead_pages/root.txt` / `descendant.txt`):

- The ownership line is `**Owner:** \`<owner>\` · **Created by:** <value> · **Assignee:** \`<assignee>\` · **Size:** <size>` — `Created by` sits between `Owner` and `Assignee`, and is omitted entirely when `issue.created_by` is empty.
- `<value>` renders as a hyperlink `[<name>](<url>)` when the resolver can produce an agent URL (an `_AgentLinkResolver`/hosted agents-sidecar page); otherwise it renders as inline code `` `<name>` `` with no link.
- Concrete example (from `tests/test_bead/golden/bead_pages/root.txt`):
  ```
  **Owner:** `owner@example.com` · **Created by:** [alice.athena.sase-ai.plan](https://github.com/sase-org/sase--agents/blob/main/agents/alice.athena.sase-ai.plan/README.md) · **Assignee:** `alice.athena.sase-ai.land`
  ```

**Suggested replacement content** — extend the "Bead Pages" paragraph (line 427-431) that currently ends "...they link to the bead's plan, artifact references, parent and child beads, dependencies, associated agents, and commits." to add:

> Each page's identity block also renders the bead's creator as `**Created by:** <name>`, between `**Owner:**` and `**Assignee:**`. It links to the creator's hosted agents-sidecar page when one resolves and otherwise renders as inline code with no link; a bead with no recorded creator omits the fact entirely.

---

## Gap 3 — `sase bead show`'s `CREATED BY` documentation doesn't note it never links from `list --format full` / `search --format full`

**Doc location:** `docs/beads.md`, `### sase bead show <id>` (~line 772-788) and `### sase bead list` (~line 668-707).

**What's wrong/missing:** The doc's `CREATED BY` description (added by `2c1525785`) is written entirely under `sase bead show` and correctly describes `show`'s link-resolving behavior. But `render_issue_detail()` (the same renderer) is also used by `sase bead list --format full` (`src/sase/bead/cli_query.py:265-281`) and `sase bead search --format full` (`src/sase/bead/cli_query.py:395-420`) — and in **both** of those call sites, `creator_url` is never passed (it defaults to `None`), so those two surfaces print the `CREATED BY` label and name but **never** the `→ <url>` link line, unlike `sase bead show`. Nothing in `docs/beads.md` states this asymmetry, so a reader could reasonably (and incorrectly) assume `sase bead list --format full` behaves identically to `sase bead show`.

**Verified current behavior:**
- `cli_query.py:274-279` (`_render_list_full`) and `cli_query.py:411-417` (`_render_search_full`) call `render_issue_detail(...)` without `creator_url=`.
- `cli_query.py:137-141` and `cli_query.py:274` in `handle_bead_show` (both `full` and `json` branches) explicitly resolve `resolve_bead_creator_url(issue.created_by)` and pass it through.
- Golden fixture `tests/test_bead/golden/cli/list_full.stdout` confirms: entries show
  ```
  CREATED BY
    owner@example.com
  ```
  with no `→` link line, even where a link would resolve for `show`.
- Also note: `sase bead list`'s **compact** row (the default) never shows the creator at all — only `--format full`/`json` do, and only `sase bead show`'s `json`/`full` resolve the link.

**Suggested replacement content** — append to the `sase bead show <id>` paragraph (end of line 777, "...A human-created bead shows the creator's email without a link."):

> `sase bead list --format full` and `sase bead search --format full` share the same `CREATED BY` block but never resolve or print the hosted-agent link — only `sase bead show` does. Compact `sase bead list`/`sase bead search` rows never show the creator at all.

---

## Gap 4 — `sase bead doctor`'s "Checks for:" bullet list omits the new leaked-prefix diagnostic

**Doc location:** `docs/beads.md`, `### sase bead doctor` (~line 601-616).

**What's wrong/missing:** Commit `22e78f792` added an *unconditional* doctor diagnostic — `_append_stale_prefix_diagnostic()` (now in `src/sase/bead/_project_queries.py:169-183`, called from both `doctor()` and `doctor_report()` with no flag gate) — that warns whenever a store's `issue_prefix` matches the raw ProjectSpec directory key instead of the project's `PROJECT_NAME`. The commit *did* update docs for the `--fix-issue-prefix` repair flag (lines 626-636), but it never added the corresponding bullet to the plain "Run health checks on the beads database. Checks for:" list at lines 605-615, so a plain `sase bead doctor` run (no flags) can print a warning that the docs never told the reader to expect.

**Verified current behavior** (`src/sase/bead/_project_queries.py:169-183`, `src/sase/bead/cli_admin.py:40-76`):
```python
def _append_stale_prefix_diagnostic(messages: list[str], beads_dir: Path) -> list[str]:
    """Warn when a store's issue prefix leaked a ProjectSpec key."""
    ...
    messages.append(
        f"WARNING: bead issue prefix '{stored}' is a ProjectSpec key; "
        f"project name is '{corrected}' "
        "(repair with: sase bead doctor --fix-issue-prefix)"
    )
```
This runs on **every** `sase bead doctor` invocation (with or without `--fix-issue-prefix`), reported-only unless `-I/--fix-issue-prefix` is also passed.

**Suggested replacement content** — add a bullet to the list at line 605-615, right after "Legacy or unresolved `design` plan references" (line 611):

> - Issue prefix leaked as the project's ProjectSpec directory key instead of its `PROJECT_NAME` (reported only; repair with `sase bead doctor --fix-issue-prefix`)

---

## Gap 5 — New-store issue-prefix default derivation is undocumented outside the repair flag

**Doc location:** `docs/beads.md`, `### sase bead init` (~line 662-666), or the "Directory Structure" subsection (~line 341-354).

**What's wrong/missing:** `22e78f792` changed how **new** bead stores pick their default `issue_prefix` (`src/sase/bead/prefix_policy.py:39-68`, wired through `src/sase/bead/config.py:54-56`), but this default-creation-time behavior is described nowhere in `docs/beads.md` except implicitly, via the `--fix-issue-prefix` *repair* paragraph (which only covers fixing already-leaked stores). A user creating bead stores for multiple projects (e.g. projects that got auto-suffixed keys like `gh_org__repo`, `foo_1`) has no doc explaining why their new bead IDs now use the human-readable `PROJECT_NAME` (e.g. `bob-cli-1`) rather than the internal ProjectSpec key (e.g. `gh_bobs-org__bob-cli-1`).

**Verified current behavior** (`src/sase/bead/prefix_policy.py:39-68`):
1. Infer the current ProjectSpec key from cwd (`infer_project_name_from_cwd()`).
2. If a key is found, resolve its display name via `project_display_name_for(key)` (this is `PROJECT_NAME`, or the key itself if no display name is configured) and use it **if** it is a "safe" bead prefix (no whitespace, no `.`/`/`\`, no `--`, no trailing `-` — see `_is_safe_bead_prefix`, since `--` is the reserved agent-family separator and prefixes feed straight into bead-work agent names).
3. If the display name is unsafe, fall back to the raw key if *it* is safe.
4. If no key resolves at all, fall back to `git remote get-url origin`'s repo name, then finally the root directory's name.

**Suggested replacement content** — add to `### sase bead init` (line 662-666):

> A newly initialized store's default `issue_prefix` is the project's `PROJECT_NAME` display name (falling back to the internal ProjectSpec key, then the git remote's repo name, then the directory name) rather than the raw ProjectSpec key. Use `sase bead doctor --fix-issue-prefix` to forward-repair a store created before this change that already leaked the key (see [`sase bead doctor`](#sase-bead-doctor)).

---

## Summary of what did **not** need changes (verified accurate, no action needed)

- "Bead ID Arguments" section (lines 76-84): matches `sase-core` `resolve_issue_id_in_issues` (`crates/sase_core/src/bead/read.rs:651-682`) exactly — shorthand = suffix after final `-`, full IDs (containing `-`) pass through unresolved, ambiguous suffixes reject with candidate list.
- `sase bead update <id> [<id2> ...]` section (lines 808-835): matches current `cli_crud.py` (`update_many`, `✓ Updated`/`· Unchanged`/`○ Reopened ancestor` rows, single joined commit) exactly.
- Compact list/show row grammar and type-glyph table (lines 674-694): matches current `cli_query.py:246-262` and `bead_type_presentation.py` exactly (glyph-only cells, `▸`/`↳`/`◆`).
- `--fix-issue-prefix` repair paragraph and flag table (lines 626-636): matches `cli_admin.py:168-224` and `prefix_policy.py` exactly.
- `docs/cli.md`: no stale claims found; it correctly defers all bead detail to `beads.md`.

# Documentation Audit: ACE/TUI changes since e93ab3db0

## Summary of what I verified

Of the 9 commits/areas listed, **6 already updated their own docs correctly in the same commit** (143666ba5, df5054c40, 0002a0590 → docs/configuration.md, ba611aa48, e023e68a9, 6e5b36028). Two gaps come from **later commits invalidating earlier doc updates without touching the docs themselves**, and one commit's docs never existed to begin with. Full detail below.

---

### Gap 1 — docs/ace.md:1051–1055 (Tribe `TRIBE` header description row)

**Commit chain:** `ba611aa48` (added inline description) → `146982d14` (moved to a labeled `Description:` block, updated docs) → **`574b7761f` removed the `Description:` label from the widget code but did not touch docs/ace.md or docs/configuration.md.**

**Current (wrong) text, `docs/ace.md:1051-1055`:**
> "A selected tribe panel's `TRIBE` header always ends with a labeled `Description: ` row, set off from the field stack (`Name`, `Status`, `Composition`, `Runtime`, `Fold`) by a blank line and wrapped with a hanging indent at a fixed 80-cell measure. It shows the tribe's configured [`description`](configuration.md#acetribes) when set. Otherwise it shows `not set · add ace.tribes.<name>.description`, so the fix is visible at the point of use — including for unconfigured ad-hoc tribes (for example epic-bead tribes with no `ace.tribes` entry)."

**Ground truth, `src/sase/ace/tui/widgets/prompt_panel/_agent_display_tribe_header.py:88-110`:** `_append_description` no longer emits a `"Description: "` label at all (removed in 574b7761f). It appends a blank line, then either the description text wrapped at the full `PROMPT_PANEL_LINE_CELL_LIMIT` (80 cells, **no hanging indent** — there is no label to indent past), or `"not set · add ace.tribes.<name>.description"` (also unlabeled).

**Correct replacement:**
> "A selected tribe panel's `TRIBE` header always ends with an unlabeled description row, set off from the field stack (`Name`, `Status`, `Composition`, `Runtime`, `Fold`) by a blank line and wrapped at a fixed 80-cell measure (no hanging indent — there is no label to indent past). It shows the tribe's configured [`description`](configuration.md#acetribes) when set. Otherwise it shows `not set · add ace.tribes.<name>.description`, so the fix is visible at the point of use — including for unconfigured ad-hoc tribes (for example epic-bead tribes with no `ace.tribes` entry)."

---

### Gap 2 — docs/configuration.md:632 (`ace.tribes.<name>.description` field table row)

**Current (wrong) text:**
> `| `description`        | str  | _required_ | One-line explanation of the tribe, 1-160 characters. Shown in the labeled `Description:` row beneath the header fields when that tribe's Agents-tab panel is selected. |`

Same root cause as Gap 1 (574b7761f never updated this table).

**Correct replacement:**
> `| `description`        | str  | _required_ | One-line explanation of the tribe, 1-160 characters. Shown as an unlabeled row beneath the header fields (`Name`/`Status`/`Composition`/`Runtime`/`Fold`) when that tribe's Agents-tab panel is selected. |`

---

### Gap 3 — docs/ace.md:1777–1802 ("Global Keybindings" `#` row and explanatory paragraphs)

**Commit:** `0002a0590` (add alternate-section jump to Admin Center opener key). This commit correctly rewrote the equivalent description in `docs/configuration.md`'s "SASE Admin Center (interactive editor)" section (lines 133-154), but **left the duplicate/older description in `docs/ace.md`'s "Global Keybindings" section completely untouched.** That section is now both incomplete and factually wrong.

**Current text, `docs/ace.md:1780`:**
> `| `#`                 | Open SASE Admin Center home; repeat on home to resume the last section used in this ACE process |`

**Current text, `docs/ace.md:1792-1802`:**
> "The generic **Open SASE Admin Center** action and the first `#` always open a lightweight landing page without mounting a working pane. Press `#` again while home is visible to resume the last section that was successfully active in this ACE process. ... Only the section identity is remembered, and only in memory: a new ACE process has no resume target, while filters, selection, scroll position, loaded data, and pane instances end with the modal."

**What's wrong:**
1. **Missing the new in-tab alternate-jump meaning entirely.** Per `src/sase/ace/tui/modals/config_center_modal.py:446-457` (`check_action`) and `action_alternate_center_tab` (line 509-517), inside a working section the *same* opener key now jumps to the previously visited section and toggles between exactly those two on repeated presses (two-slot alternate, see `config_center_history.py`'s `AdminCenterTabHistory`). A color-coded, clickable footer (`config_center_footer.py`, `AdminCenterFooter`) names the jump target, or shows a dimmed "no earlier section yet" placeholder.
2. **"Only in memory... a new ACE process has no resume target" is factually wrong.** Per `src/sase/ace/tui/modals/config_center_state.py` (`load_admin_center_tab_history` / `save_admin_center_tab_history`), both the resume target *and* the alternate are persisted machine-locally to `~/.sase/ace_admin_center_last_tab.txt` and survive across ACE process restarts. `docs/configuration.md:152-154` already states this correctly — `docs/ace.md` directly contradicts it.

**Correct replacement (table row):**
> `| `#`                 | Open SASE Admin Center home (repeat on home to resume the last section); inside a working section, jump to the alternate section (repeat to toggle back) |`

**Correct replacement (paragraph, replacing 1792-1802):**
> "The generic **Open SASE Admin Center** action and the first `#` always open a lightweight landing page without mounting a working pane. Press `#` again while home is visible to resume the last section that was successfully active. With no prior visit, the repeated key stays on home and loads nothing. Inside a working section, the same key takes on a second meaning: it jumps to the section you were in immediately before the current one, and pressing it again toggles back — exactly two sections remembered, like a two-slot alternate. A color-coded, clickable footer along the bottom of the working section names the jump target (or explains that none exists yet). The numbered strip remains clickable, `Tab` enters Config, and `Shift+Tab` enters XPrompts. Each working pane and its data are loaded only on first entry, then cached while the modal remains open. Command-palette actions such as **Open logs panel**, **Open tasks panel**, and **Open statistics**, plus update shortcuts and indicators, enter their requested pane directly and make a successful entry the next resume target. Closing from home does not clear an older target.
>
> Both the resume target and the alternate are persisted machine-locally and survive across ACE process restarts; filters, selection, scroll position, loaded data, and pane instances still end with the modal. If `ace.keymaps.app.open_config_center` is rebound, repeat that configured key instead; the footer and landing page display the effective binding and destination."

(See `docs/configuration.md:133-154` for the now-correct sibling text this should be aligned with.)

---

### Gap 4 (minor/optional) — docs/ace.md: no coverage of epic clan summary "Counts:" row (9d6b40c6c)

`src/sase/scripts/sase_clan_summary_epic.py:210` always calls `render_plan_document(..., include_counts=True)`, so every epic clan's rendered plan summary (Title/Goal/**Counts**/Path, per `src/sase/sdd/_plan_display_rendering.py:94-118`) now includes a `Counts: N phase(s) · N wave(s)` row (or `unavailable` / `waves unavailable` degraded states). This text is what populates the ACE Agents-tab epic clan panel's clan-summary body (confirmed via `tests/ace/tui/visual/test_ace_png_snapshots_agents_clan_panel.py`, which asserts `"Counts:"`, `"phases"`, `"waves"` appear in the rendered panel).

This is **not a regression** introduced by this refresh — `docs/ace.md` never documented the Title/Goal/Path fields of an epic clan summary at all (`grep` for `"Title:"`/`"Goal:"`/`"Path:"` in docs/ace.md returns nothing), so there's no existing paragraph to correct. Flagging as a pre-existing gap that's now slightly larger: if the next docs pass adds epic-clan-summary field documentation to `docs/ace.md`, it should mention the `Counts: N phase(s) · N wave(s)` row and its `unavailable`/`waves unavailable` degraded states (`src/sase/sdd/_plan_display_rendering.py:147-158`).

---

## Areas confirmed already up to date (no action needed)

- **docs/notifications.md** — fully current. `143666ba5` (sent-time line), `df5054c40` (bulk mark actions), and `6e5b36028` (adapter-derived gate capabilities) each updated `docs/notifications.md` in the same commit, and no later commit in the audited set touches notification behavior. Verified keybinding table, "Marks and Bulk Actions" section, "Mute and Snooze" section, and the gate-kind table all match current source (`notification_modal_actions.py`, `notification_modal_sent_at.py`, `notification_gates/adapters.py`).
- **docs/configuration.md `#### ace.tribes`** (lines 622-651) — accurate for `ba611aa48`/`e023e68a9`/`0002a0590` (required description, dropped bundled `research` entry, doctor check) **except** for the stale `Description:` label wording at line 632 (Gap 2 above).
- **docs/configuration.md `## SASE Admin Center`** (lines 133-154) — fully accurate for `0002a0590`'s alternate-jump and persistence behavior; this is the correct reference text that `docs/ace.md` (Gap 3) should be reconciled with.

First research report is in (bead CLI docs gaps). Marking that task complete and continuing to wait for the remaining four.

ACE/TUI research report is in as well. Marking that complete and continuing to wait for the remaining three.

Still waiting on the commit-workflow, LLM/provider, and memory/tribe research agents.

## Audit Report: Commit-Workflow Docs vs. Current Behavior

### Summary of what changed since e93ab3db0 (investigated each commit)

| Commit | What it did | Doc-relevant? |
|---|---|---|
| `748b617c0` feat(commit): add commit subject validation policy | Adds `src/sase/core/commit_subject_facade.py` (Rust-backed `parse_commit_subject`/`default_commit_subject_types`), `src/sase/workflows/commit/message_validation.py` (`CommitMessagePolicy`, `check_commit_message`, `load_commit_message_policy`), and the `commit.message` config schema/defaults (`require_conventional_subject: true`, `allowed_types: [build, chore, ci, deps, docs, feat, fix, perf, refactor, revert, style, test]`). Not yet wired into the workflow or docs. | Superseded by later commits |
| `84721922e` feat(commit)!: reject invalid conventional subjects (BREAKING) | Wires the gate into `CommitWorkflow.run()` (`src/sase/workflows/commit/workflow.py:117-123`): loads the policy, calls `check_commit_message`, and on rejection calls `print_status(rejection, "error")`, logs `commit_failed` with `reason="invalid_message"`, and returns `RunResult.FAILED`. | Superseded by later docs commit |
| `ae3c0109a` fix(commit): write agent commit messages under .sase/ instead of repo root | Changes the `sase_git_commit` skill's prescribed `-M` path from `commit_message.md` to `.sase/commit_message.md` (git-ignored dir), updates `docs/commit_workflows.md` lines 63-74, and extends `_agent_deltas.py` bookkeeping-path filter to recognize both old and new paths. | Already documented (partially — see gap below) |
| `9a6b20390` fix(commit): apply conventional subject gate updates | **53 files changed, 0 insertions/deletions** — purely binary PNG visual-snapshot regoldens (ACE TUI screenshots). No source or doc content changed. Confirmed via `git show --stat`. | No doc impact |
| `2f565d0be` docs(commit): document the conventional subject gate | Adds the "Subject gate" stage to the `CommitWorkflow` diagram in `docs/commit_workflows.md`, a full `#### commit.message` subsection in `docs/configuration.md`, and skill-file wording in `sase_git_commit.md` making the tag "mandatory, not advisory." Also privatizes `CommitSubject`→`_CommitSubject` and `CommitMessagePolicy`→`_CommitMessagePolicy` (no doc impact — internal names weren't documented). | This is the last docs update; it landed **after** `ae3c0109a`, so it did not go stale itself, but it did not catch a pre-existing gap left by `ae3c0109a` (below). |

### Verified current behavior (source-grounded)

1. **What makes a subject invalid / rejection behavior** — `src/sase/workflows/commit/message_validation.py:60-131` and `src/sase/core/commit_subject_facade.py`. Grammar: `<type>[(<scope>)][!]: <description>`, type must be lowercase and in `policy.allowed_types` (default 12 types, config `allowed_types` **replaces**, not extends). Exempt subjects (verified via `tests/workflows/test_commit_message_validation.py:76-84`): `Merge `, `Revert "`, `fixup!` (doc also claims `squash!`/`amend!` exempt — plausible per Rust grammar, not directly re-verified but consistent with doc's own prior-verified claims). Empty message always rejected. It is a **hard block**: `CommitWorkflow.run()` returns `RunResult.FAILED` (exit code 1) before any bead/plan/hook side effect runs (`src/sase/workflows/commit/workflow.py:117-127`), the rejection reason text is printed via `print_status(..., "error")`, and `commit_failed` is logged with `reason="invalid_message"` (`src/sase/workflows/commit/workflow_support.py:58-63`). No env-var or per-invocation bypass exists — `SASE_DISABLE_COMMIT_STOP_HOOK` only disables the unrelated commit *finalizer*, not this gate (confirmed by grep — the gate check has no env-var read at all).

2. **Where agent commit messages are written** — `src/sase/xprompts/skills/sase_git_commit.md:58-70` mandates `.sase/commit_message.md` (git-ignored, so it can't trip the post-completion finalizer's dirty check or be swept into `git add -A`). `docs/commit_workflows.md` lines 63-74 already document this correctly.

### Doc gaps found

**1. `docs/commit_workflows.md:181` — stale example path, inconsistent with the `.sase/` convention established 100+ lines earlier in the same file**

Current text (in the `## CLI Inputs and Internal Payload` section, "Typical commit or proposal" example):
```
sase commit -M commit_message.md -f src/auth.py -f src/login.py -t commit
```
This is the one place in the file that `ae3c0109a` missed when it rewrote the skill-wrapper example (`docs/commit_workflows.md:66,72`) to `.sase/commit_message.md`. It directly contradicts the file's own earlier guidance ("The skill writes the message file under `.sase/` because that directory is git-ignored... so the temporary file can never trip the commit finalizer's dirty check," line 69-70) and re-creates exactly the bug `ae3c0109a`'s commit message describes (a leftover `commit_message.md` at repo root tripping the finalizer / getting swept into `git add -A`).

Recommended replacement:
```
sase commit -M .sase/commit_message.md -f src/auth.py -f src/login.py -t commit
```

Note: the adjacent PR example on line 187 (`sase commit -M pr_description.md -n feature_branch -B 12345 -s ready -t pr`) uses a different filename; there is no dedicated skill wrapper for PR description files distinct from `sase_git_commit.md` (grep confirms `pr_description.md` appears nowhere in `src/sase/xprompts/skills/`), so for full consistency it should likely also become `.sase/pr_description.md`, but this is a secondary/optional fix — the `ae3c0109a` fix and its docs update were specifically scoped to `commit_message.md`, so recommend flagging this one for the editing agent's judgment rather than asserting it's strictly "wrong."

### Things checked and confirmed NOT stale (no action needed)

- `docs/commit_workflows.md:66,72,113-166` (Subject gate diagram entry, stage description, `reason="invalid_message"`, `-M` file preservation, `use_project_pr_prefix` interaction) — all match `src/sase/workflows/commit/workflow.py` and `message_validation.py` exactly.
- `docs/configuration.md` `#### commit.message` subsection (lines 1124-1152) — table, YAML example, grammar description, exempt-prefix list, "no bypass" claim, and `Source:` file list all verified against current source; fully accurate.
- `src/sase/xprompts/skills/sase_git_commit.md` (the actual generated skill source, distinct from docs/) — fully current, already reflects both the `.sase/` path and the mandatory-gate wording.
- `docs/agents_sidecar.md` — no conventional-commit-gate or `.sase/commit_message.md` content; its commit-provenance/lane-tag material is unrelated to this feature and unaffected.
- `docs/development.md` — no conventional-commit-gate content (`just lint` mention only).
- `CONTRIBUTING.md` — mentions `feat:`/`fix:` conventions generically and consistently with (not contradicted by) the new hard-enforcement gate; no factual error, could optionally note enforcement is now hard-blocked rather than just a release-please convention, but not a required fix.
- `docs/beads.md`, `docs/vcs.md`, `docs/init.md`, `docs/change_spec.md`, `docs/axe.md`, `docs/acknowledgements.md` — grepped for "commit message"/"conventional commit"; no stale content found (axe.md's "commit message" hit is an unrelated grammar analogy for lumberjack/chop descriptions).
- `docs/blog/posts/commit-workflows-plugins.md` — draft-status blog post (dated 2026-05-18, `draft: true`) whose pre-dispatch pipeline description predates the subject gate and does not mention it. Out of the explicitly-requested scope (blog posts are point-in-time narrative content, not living reference docs, and the prior refresh commit `e93ab3db0` did not treat blog posts as requiring lockstep updates). Flagging for awareness only — not recommending an edit unless the requester wants blog content kept current too.

### Bottom line for the editing agent

Exactly one concrete, in-scope fix is needed:

- **File:** `docs/commit_workflows.md`
- **Line:** 181
- **Change:** `sase commit -M commit_message.md -f src/auth.py -f src/login.py -t commit` → `sase commit -M .sase/commit_message.md -f src/auth.py -f src/login.py -t commit`
- **Grounding:** `src/sase/xprompts/skills/sase_git_commit.md:58-70` and `docs/commit_workflows.md:66-70` (the file's own already-corrected convention, from `ae3c0109a`).
- **Optional secondary consideration:** line 187's `pr_description.md` example, for the same consistency reason (no strong behavioral evidence it's "wrong," but stylistically orphaned from the `.sase/` convention).

Commit-workflow research is done too — small, well-scoped gap found. Marking complete and continuing to wait for the last two.

Waiting on the LLM/model-provider and memory/tribe research agents to finish.

Confirmed `-C/--check` is the correct flag. Now let me check a couple remaining edge cases around the ACE display of tribe descriptions in agent_families.md vs ace.md placement, and double-check the `sase agent tribe` CLI doesn't need a description-related update.

# LLM Provider Documentation Audit — Findings

## Commit-by-commit verification (baseline: e93ab3db0, 2026-07-30)

I read each commit and cross-checked its current-state source files against `docs/llms.md`, `docs/configuration.md`, `docs/agent_providers.md`, `docs/fakey.md`.

| Commit | What it did | Doc status now |
|---|---|---|
| `bc359cca6` | Added `ZHIPU_API_KEY` to `OpenCodeProvider.llm_auth_evidence()` (`src/sase/llm_provider/opencode.py:148`) | **Already documented correctly** — the same commit updated `docs/agent_providers.md:66`, which now reads `ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `OPENROUTER_API_KEY`, `ZHIPU_API_KEY`, and other `*_API_KEY` variables (additive to the pre-existing example list, not a full canonical enumeration). No gap. |
| `f55ce07d1` | Moved shipped implicit-alias defaults into `src/sase/llm_provider/model_alias_defaults.yml` (new file) as the single source of truth; `model_alias_policy.py` became a validating YAML loader. Added `tests/llm_provider/test_model_alias_defaults_docs_sync.py`, which asserts every YAML target string appears verbatim in `docs/llms.md` and `docs/configuration.md`. | Ran the sync test — **it passes today**, so the quoted default values (`smartest: claude/claude-fable-5 \|\| codex/gpt-5.6-sol`, `cheap: claude/opus@medium \| codex/gpt-5.5`, `cheaper: claude/sonnet \| codex/gpt-5.3-codex-spark`, `cheapest: claude/haiku \|\| codex/gpt-5.3-codex-spark`) are accurate in both docs. **Gap found**: neither doc's Source Layout/citation lines mention the new `model_alias_defaults.yml` (see Finding 1 below). |
| `e5361f4de` | Added `llm_hidden_from_model_pickers()` hook; `fakey.py` opts in (`src/sase/llm_provider/fakey.py:149-151`). Filters fakey out of (a) the ACE model-picker rows (`model_picker_rows.py`) and (b) the `%model` completion catalog (`xprompt/model_completion.py`). **Also** filters the implicit `@fakey_coder` alias out of `build_alias_views()` (`src/sase/llm_provider/alias_view.py:444-456`), which feeds the ACE **Models panel** (`,m`, `src/sase/ace/tui/modals/models_panel.py`) — a third, distinct surface. | Docs (`docs/agent_providers.md:111-113`, `docs/fakey.md:25-28`, `docs/llms.md:798-801`) correctly describe surfaces (a) and (b). **Gap found**: surface (c), the Models panel's `@fakey_coder` hiding, is undocumented anywhere (see Finding 2 below). |
| `e0d2476f1` | Dropped `claude-opus-5`/`claude-sonnet-5` from Claude's known models/short-aliases (`claude.py:79-88`); added `gpt-5.3-codex-spark` to Codex (`codex.py:223-247`). | Same commit rewrote `docs/llms.md`'s catalog/shorthand tables. Verified current `claude.py`/`codex.py` against current `docs/llms.md:789-822` — **fully in sync**, no stale `claude-opus-5`/`claude-sonnet-5` references remain anywhere in the 4 audited docs. |
| `fe397e363` | Renamed all Antigravity models from display-name strings (`"Gemini 3.5 Flash (High)"`) to stable slugs (`"gemini-3.6-flash-high"`) in `agy.py:274-296`; bumped the large/small tier defaults to the 3.6 generation. | Same commit rewrote `docs/llms.md` (Antigravity section + catalog/shorthand tables) and `docs/xprompt.md`. Verified against current `agy.py` — **fully in sync**. No stale `Gemini 3.5 Flash (High)`-style names remain in the 4 audited docs. |
| `9562e5366` | Added a `display_name` metadata field so `%model` completion shows a human label (e.g. "Codex") instead of the raw lowercase `llm_provider_name()` value. | No doc text described the literal completion-label format before or after, so nothing is now wrong. No gap. |
| `32c47e0d6` | Pure refactor: split `registry.py` into `_registry_metadata.py` + `_registry_plugins.py`. Confirmed the public API (`get_llm_metadata_payload`, `resolve_model_provider`, etc.) is unchanged — same names still exported from `registry.py`. | No behavior change, so no doc *correctness* issue, but the new files are undocumented (folds into Finding 1). |
| `6e5b36028` | Gate-adapter capability derivation; only touches `docs/notifications.md` (out of scope) and notification-gate source. | No changes needed in the 4 audited docs. |

---

## Finding 1 — `docs/llms.md`: Source Layout table omits the files these commits introduced

**Location:** `docs/llms.md:52-77` (`### Source Layout` table), and no `Source:` citation follows the "Implicit role aliases" table at `docs/llms.md:686-709` (compare with the `Source:` line pattern used at `docs/llms.md:250`, `805`, `825`, `891`, `1348`, `1378`, `1413`).

**What's wrong:** The table lists `registry.py` but not the two new modules it now delegates to, and lists no module at all for model-alias-default resolution:

```
| `src/sase/llm_provider/registry.py`           | Provider registration and lookup                       |
```

It's missing rows for `_registry_metadata.py` and `_registry_plugins.py` (both added by `32c47e0d6`, confirmed still doing real work — `_provider_metadata()`/`llm_metadata_cache_policy()` live in `_registry_metadata.py`; `build_llm_plugin_manager()`/`create_provider()` live in `_registry_plugins.py`), and for `model_alias_defaults.yml` / `model_alias_policy.py` / `model_alias_config.py` / `model_alias_resolution.py` / `alias_view.py` — the module chain that `f55ce07d1` explicitly made the single edit point for every default quoted in the "Implicit role aliases" table and in `docs/configuration.md`.

**Correct replacement:** Add rows to the Source Layout table (after the `registry.py` row) and a `Source:` line after the Implicit role aliases table:

```
| `src/sase/llm_provider/_registry_metadata.py` | Provider metadata normalization and cache fingerprints |
| `src/sase/llm_provider/_registry_plugins.py`  | Plugin discovery/construction via `sase_llm` entry points |
| `src/sase/llm_provider/model_alias_defaults.yml` | Single bundled source of truth for shipped implicit-alias targets/fallbacks/descriptions |
| `src/sase/llm_provider/model_alias_policy.py` | Validating loader for `model_alias_defaults.yml` |
| `src/sase/llm_provider/model_alias_config.py` | Model-alias name constants, config parsing, presentation metadata |
| `src/sase/llm_provider/model_alias_resolution.py` | Alias/target/effort resolution logic |
| `src/sase/llm_provider/alias_view.py`         | ACE Models-panel alias-view construction (`build_alias_views()`) |
```

and, right after the Implicit role aliases table (before `#### Launch-scoped alias overrides` at line 740):

```
Source: `src/sase/llm_provider/model_alias_defaults.yml` (shipped defaults — the single edit point), `src/sase/llm_provider/model_alias_policy.py`
```

Grounded in: `src/sase/llm_provider/model_alias_defaults.yml:1-11` ("This file is the single edit point..."), `src/sase/llm_provider/model_alias_policy.py:1-8` (module docstring), `src/sase/llm_provider/_registry_metadata.py:1`, `src/sase/llm_provider/_registry_plugins.py:1`.

---

## Finding 2 — `docs/fakey.md`: missing the ACE Models-panel hiding of `@fakey_coder`

**Location:** `docs/fakey.md:25-28` (the paragraph added by `e5361f4de`).

**Current text:**
```
Fakey models are not offered in the ACE model picker or the `%model` completion menu — it exists only for testing, so it
is hidden from user-facing model selection surfaces. It remains fully registered and routable: the explicit spellings
above (`%model:fakey-large`, `sase run -m fakey-large`) and `%model:fakey/fakey-large` all still work, and the picker's
`Custom...` entry accepts them by hand.
```

**What's wrong:** This only documents two of the three surfaces the `e5361f4de` change actually hides fakey from. `src/sase/llm_provider/alias_view.py:444-456` also filters the implicit `@fakey_coder` role alias out of `build_alias_views()` (unless a user has explicitly configured a `fakey_coder` custom alias), and `build_alias_views()` is what powers the ACE **Models panel** (`,m`), per `src/sase/ace/tui/modals/models_panel.py`. A reader checking "does fakey show up anywhere in the Models panel" would not find this documented, and `tests/llm_provider/test_alias_view.py::test_fakey_coder_alias_hidden_by_default` / `test_configured_fakey_coder_alias_still_surfaces` pin exactly this behavior.

**Correct replacement:** Append a sentence to the same paragraph (or a new one):

```
The implicit `@fakey_coder` role alias is likewise hidden from the ACE Models panel (`,m`) unless you explicitly
configure `model_aliases.custom.fakey_coder` — once configured, it appears and is editable like any other alias.
```

Grounded in: `src/sase/llm_provider/alias_view.py:444-456`, `tests/llm_provider/test_alias_view.py` (`test_fakey_coder_alias_hidden_by_default`, `test_configured_fakey_coder_alias_still_surfaces`).

---

## Finding 3 (lower priority, pre-existing — not caused by the 8 audited commits, but internally inconsistent)

**Location:** `docs/llms.md:552` vs. `docs/configuration.md:959`, and each vs. its own Config Fields table (`docs/llms.md:588`, `docs/configuration.md:988`).

**Current text:**
```
docs/llms.md:552:            provider: claude # or "qwen", "opencode", "agy", "fakey" (default: auto-detect)
docs/configuration.md:959:   provider: claude # or "qwen", "opencode", "agy" (default: auto-detect)
```

**What's wrong:** Both omit `codex` from the enumerated example even though `codex` is the second-highest autodetect priority (`src/sase/llm_provider/codex.py:261`, `return 10`), and each doc's own field-description row two lines below explicitly states the full order `claude → codex → qwen → opencode → agy` (`docs/llms.md:588`, `docs/configuration.md:988`). `docs/configuration.md` additionally omits `fakey`, while `docs/llms.md` includes it. This predates the audited commits (present identically in `e93ab3db0`), but it is a real, current inconsistency within each file.

**Correct replacement:**
```
provider: claude # or "codex", "qwen", "opencode", "agy", "fakey" (default: auto-detect)
```
in both files, to match each file's own Config Fields description of the full auto-detect order.

---

## Summary of what is already correct (no action needed)

- Claude/Codex/Antigravity/Qwen/OpenCode/fakey known-model lists and short-alias tables in `docs/llms.md:789-823` exactly match current `claude.py`, `codex.py`, `agy.py`, `qwen.py`, `opencode.py`, `fakey.py`.
- All four implicit-alias default target strings (`smartest`, `cheap`, `cheaper`, `cheapest`) in `docs/llms.md` and `docs/configuration.md` match `src/sase/llm_provider/model_alias_defaults.yml:52-70` verbatim (confirmed by running `tests/llm_provider/test_model_alias_defaults_docs_sync.py`, which passed).
- `docs/agent_providers.md`'s OpenCode auth env-var list and Fakey section, and `docs/fakey.md`'s picker/completion-hiding paragraph, are accurate as of `bc359cca6` and `e5361f4de`.
- Entry-point table (`docs/llms.md:112-120`) and autodetect priority list (`docs/llms.md:138-141`, `claude=0, codex=10, qwen=15, opencode=18, agy=30`) match `pyproject.toml:149-155` and each provider's `llm_autodetect_priority()`.
- `32c47e0d6` and `6e5b36028` require no doc corrections beyond Finding 1 (registry file split) — both are confirmed behavior-neutral / out of scope for these 4 docs respectively.

LLM/model provider research is in. Marking complete and waiting on the final memory/tribe report.

Waiting on the last research agent (memory/tribe config).

This confirms current source exactly matches the docs claim — no launch happens, it's a plain `sase bead update --status` call. Everything checks out. Let me do a final targeted check on the `docs/configuration.md` tribes section rendering fully to be safe, and look once more at potential stale cross-references in `docs/agent_families.md`'s epic-bead-work example section relative to `ba611aa48`/`e023e68a9`.

Good — confirms no `tier2_entries` placeholder, matching docs. Let me do one final check on the `sase.memory.paths` module to make sure `memory_write_root` behaves as documented, and verify the `AGENTS.md`/`CLAUDE.md` root files here (this repo itself) correctly show the Tier 2 bead note reference, confirming end-to-end consistency.

Now I have a complete picture. Let me compile the final audit report.

## Documentation Audit Report

**Bottom line: I could not find a genuine stale/wrong/incomplete passage in `docs/memory.md`, `docs/beads.md`, `docs/configuration.md` (tribes sections), or `docs/agent_families.md` relative to the 7 commits under review.** Each of these commits either shipped its own doc update, or was later corrected by that same commit chain (33c63112c → f0e1a25e6), and I traced every claim in those docs back to current source to confirm it. Below is the evidence trail per commit so you can verify my conclusion rather than take it on faith. I did **not** fabricate findings to fill a quota — where the docs are accurate, I say so with the source citation that proves it.

---

### 1. `642b4f490` — retire bundled `sase_beads` skill
**Doc location:** `docs/xprompt.md` "Bundled Skills" table (~L889–908)
**Status: accurate.** The `sase_beads` row was removed and the table now exactly matches `src/sase/xprompts/skills/*.md` (16 files, 16 rows). No file in `docs/`, including `docs/beads.md`, references a `/sase_beads` skill or the deleted `src/sase/xprompts/skills/sase_beads.md`. **No gap.**

### 2 & 3. `d6a2cce1f` (generate Tier 2 bead note) and `f0e1a25e6` (scope to project repos only)
**Doc locations:** `docs/memory.md` L16–19, `docs/init.md` L169–207, `docs/configuration.md` L389–393 (template variable table), `sase/memory/README.md` L16–18

**What actually determines "project repo" vs not** (verified in source, not assumed):
- `sase/memory/sase_beads.md` is generated only when **both**: (a) `is_project_dir` is true (`src/sase/main/init_memory_handler.py:99`) **and** (b) the project opts in with `is_sase_managed: true` in its own `sase/sase.yml` (`manage_memory=inputs.is_sase_managed`, `src/sase/main/init_memory_handler.py:275,430,462`).
- `include_bead_memory=True` is passed only on the project-root plan (`src/sase/main/init_memory_handler.py:280,435`); the home-root plan (live home or chezmoi-home — same code path, `_home_root_path()`, `src/sase/main/init_memory_handler.py:63-67`) never sets it.
- If `manage_memory` is false, `memory_root_context()` short-circuits before `include_bead_memory` is even consulted (`src/sase/main/init_memory/root_planning.py:426-433`), so a project directory that exists but hasn't opted into `is_sase_managed: true` gets nothing.
- Retirement of a stale copy: `_retired_note_paths()` (`src/sase/main/init_memory/root_planning.py:172-195`) deletes a previously-generated `sase/memory/sase_beads.md` only if `include_bead_memory` is false **and** the on-disk content is byte-identical to the freshly rendered template — a human-edited copy is left untouched. This exactly matches `docs/init.md` L200-202: *"A root that no longer manages the note ... deletes an unmodified copy on the next `sase memory init` pass; a copy a human has since edited is left alone..."*

Every doc sentence describing this (`docs/memory.md` L18-19, `docs/init.md` L172-174/198-203, `docs/configuration.md`'s `amd_agents_minimal_template` row now listing only `title, tier1_sections` matching `src/sase/amd/_template.py:13`) is currently correct. `sase/memory/README.md` and this repo's own generated `AGENTS.md`/`CLAUDE.md`/etc. (this repo is itself a SASE-managed project) confirm the described behavior end-to-end. **No gap.**

One consequence worth flagging to you even though it isn't a "wrong doc" (every doc sentence about it is honestly scoped): retiring the globally-bundled `sase_beads` skill in favor of a project-repo-gated Tier 2 note means agents working in a non-`is_sase_managed` project, or in the home context, now get **zero** bundled bead-workflow guidance (previously the skill was available everywhere). The docs never claim otherwise, so this isn't a documentation error — just noting the functional narrowing in case it's not what you intended.

### 4. `33c63112c` — document bulk bead update semantics (the "is it complete / did f0e1a25e6 make it stale again" question)
**What it touched:** only `sase/memory/README.md`, `sase/memory/sase_beads.md`, and `src/sase/main/init_memory/templates/memory-sase-beads.template.md` — it did **not** touch `docs/beads.md`.
**Why that's fine:** `docs/beads.md` already documented the exact same bulk semantics via the *earlier* commit `50988fe7f` (`docs/beads.md` L808-835, "`sase bead update <id> [<id2> ...]`" section) — that commit's own message says "Docs and the `sase_beads` skill source are updated to describe the bulk contract." So 33c63112c's scope (generated note + its template + README stats) was the only thing left out of sync at that point, and it closed that gap completely.
**Was it made stale by `f0e1a25e6`?** No — verified with `cmp sase/memory/sase_beads.md src/sase/main/init_memory/templates/memory-sase-beads.template.md` → **identical**, and `f0e1a25e6`'s diff never touches the content of either file, only the *generation-condition* plumbing (`include_bead_memory`). The bulk-update paragraph (lines 60-62 of the generated note) survived untouched. **No gap.**

### 5. `ba611aa48` — require description for configured agent tribes
**Doc location:** `docs/configuration.md` `#acetribes` (~L622-646), `docs/ace.md` (out of your requested-file scope, but cross-checked since it's the same feature)
Verified against source:
- Schema requires `description` (1-160 chars): `src/sase/config/sase.schema.json:480,499-503` — matches docs table exactly.
- `sase doctor -C config.tribes` is a real, correctly-named check: `src/sase/doctor/checks_config_tribes.py:10,47` — matches.
- "ACE Config Center refuses to write *any* change while [a missing-description error] is present" — confirmed in `src/sase/ace/tui/modals/config_transaction_preview.py:57-59`: `is_valid` is `False` if **any** diagnostic in the whole plan has `severity == "error"`, not just the touched field. Matches doc claim precisely.
- Note: the header-row rendering detail in `docs/ace.md`/`docs/configuration.md` was further refined by a *later*, non-audited commit `146982d14` ("render tribe description as a labeled block below the header"), and both docs reflect that latest layout correctly — so nothing here is stale either. **No gap.**

### 6. `e023e68a9` — drop bundled `research` tribe display config
**Doc location:** `docs/configuration.md` `#acetribes` (~L641-643)
`src/sase/default_config.yml:105-124` bundles exactly `default, epic, chop, pinned, review` — no `research` entry — matching the doc's explicit list. Grepped all of `docs/agent_families.md`, `docs/ace.md`, `docs/configuration.md` for stray `research`-tribe references (as opposed to the unrelated `research` document/sidecar role, which is a different concept using the same word) — found none. **No gap.**

### 7. `76e9ab408` — correct task bead workflow guidance (the "don't reintroduce the same error" check)
**Doc location:** `docs/beads.md`, "Standalone Task Workflow" (L205-276) and "Task Bead Surfaces" (L1041-1052)
What it fixed (for your reference, so future edits don't regress it):
- Previously implied the ACE Plans-pane `s` action could launch a worker as it cycled to `in_progress`; corrected to "only changes status ... does not launch a worker." **Verified current**: `action_plans_cycle_status` (`src/sase/ace/tui/actions/artifacts_plans.py:110-123`) only calls `_submit_plans_bead_update(fields={"status": ...})` — never a launch. The exact cycle `open→ready→in_progress→closed→open` (`claimed→ready`) matches `_next_plans_bead_status` (`src/sase/ace/tui/actions/artifacts_plans.py:446-464`) byte-for-byte.
- Previously implied ACE/mobile show a task's reverse "blockers" list; corrected to say ACE's task detail does **not** show one. **Verified current**: `src/sase/ace/tui/widgets/artifacts/plans_detail.py` has no blocker/reverse-dependency rendering for tasks, only forward `dependencies`.
- Previously oversimplified the `TaskTriage` gate cancel/regenerate rule and the dispatch-failure recovery split (checkpoint/no-runner vs. partial-dispatch). **Verified current**: `bead_task_triage` chop is registered under the 5-minute `checks` lumberjack (`src/sase/default_config.yml:638-656`), matching the doc's "five-minute scan" framing in both places it's described.
- Previously conflated the `small` display fallback with actual task launch routing. **Verified current**: `task_model_directive_value()` (`src/sase/bead/work.py:314-324`) only consults `size` for routing, independent of the CLI display fallback, and `render_task_prompt()` (`src/sase/bead/work.py:327-353`) never emits `#plan` (unlike `phase_requires_plan()` used for epic phases) — matching L274-276's "task size currently selects the model route only."

All of it checks out against current HEAD. **No gap, and nothing has regressed.**

---

### Summary table

| Commit | Doc(s) | Verdict |
|---|---|---|
| 642b4f490 | docs/xprompt.md | Accurate — skill row removed cleanly, no dangling refs |
| d6a2cce1f + f0e1a25e6 | docs/memory.md, docs/init.md, docs/configuration.md | Accurate — "project repo" scoping matches `include_bead_memory` gating exactly |
| 33c63112c | sase/memory/README.md, generated note + template | Complete; not made stale by f0e1a25e6 (content untouched, byte-identical to template) |
| ba611aa48 | docs/configuration.md `#acetribes` | Accurate — schema, doctor check, and Config Center block-on-error behavior all verified |
| e023e68a9 | docs/configuration.md `#acetribes` | Accurate — bundled tribe set exactly matches `default_config.yml` |
| 76e9ab408 | docs/beads.md | Accurate — all 4 corrected claims (s-action, blockers, gate regeneration, size-routing) still hold against current source |

If you had a specific passage in mind that you suspected was wrong, point me at it and I'll re-verify that one spot specifically — but a full-file read plus source cross-check of all four requested docs turned up no discrepancies to report.

All five research reports are in — a clear, well-verified set of gaps. Marking research complete and moving to the edit phase.

Now applying the edits. Starting with `docs/beads.md`.

Now let's look at the `sase bead create`, `sase bead show`, `sase bead doctor`, and `sase bead init` sections for the remaining beads.md edits.

Now I'll add the creator-attribution policy paragraph after the ChangeSpec paragraph.

Now let's view the `sase bead show` CREATED BY section, the `sase bead doctor` section, and the `sase bead init` section.

Now let's add the missing doctor bullet and the init-time default prefix behavior.

I made a typo — let me fix "sitecar" back to "sidecar".

Now let's handle the `sase bead show` CREATED BY asymmetry note.

beads.md edits are done. Now `docs/commit_workflows.md`.

Both examples should follow the same `.sase/`-relative convention documented earlier in the file.

Now `docs/ace.md` — the tribe description labeled-block gap and the `#` keybinding / alternate-jump gap.

Now the Global Keybindings `#` row and its explanatory paragraphs.

Now `docs/configuration.md` — the `description` field row wording and the provider auto-detect example.

Now `docs/llms.md` — the provider example line and the Source Layout table gap.

Now let's find the "Implicit role aliases" table to add the `Source:` citation line, matching the pattern used elsewhere in the file.

I'll add the `Source:` line right before `#### Launch-scoped alias overrides`, after the YAML example block.

Now `docs/fakey.md` — add the ACE Models panel hiding note.

Let me verify the anchor slugs I referenced match mkdocs' actual generated IDs, by checking existing cross-reference patterns in the file.

All edits are in place. Now running `just docs-check` again to confirm the strict build still passes.

Docs build passes cleanly, same as baseline. Now let's run the model-alias docs-sync test to make sure my `docs/llms.md` edits didn't break the verbatim-string check.

That test still passes. Let's mark tasks complete and do a final diff review.

Only documentation files were touched, as required. Let me do one last visual check of the full diff to catch anything off.

Let me clean up the line wrapping for readability — the codespan splits awkwardly across lines.

Let me rewrap this whole paragraph cleanly to match the file's ~120-column style.

Build is clean. All tasks are complete.

## Summary

Refreshed sase's documentation to match repository behavior as of `HEAD` (`f0e1a25e6`), covering everything since the last broad refresh (`e93ab3db0`, 2026-07-30). Used 5 parallel research agents to audit each area against source, then applied all edits directly. Only `docs/*.md` files were touched (verified via `git status`); `just docs-check` passes clean before and after.

**Changes:**
- **`docs/beads.md`** — documented creator-attribution policy (`sase bead create`), bead-page `Created by:` rendering, the `sase bead show` vs `list/search --format full` link asymmetry, the new leaked-issue-prefix doctor diagnostic, and the `PROJECT_NAME`-based default prefix for new stores.
- **`docs/ace.md`** — fixed the stale "labeled `Description:` row" claim (the label was removed) and rewrote the `#` keybinding docs to cover the new alternate-section jump/toggle behavior and corrected a wrong claim that resume state was memory-only (it's now persisted across ACE restarts).
- **`docs/configuration.md`** — matched the tribe `description` field row to the unlabeled rendering, and added `codex` to the provider auto-detect example.
- **`docs/llms.md`** — added the new `model_alias_defaults.yml`/registry-split source files to the layout table, added a `Source:` citation, added `codex` to the same provider example.
- **`docs/fakey.md`** — documented that `@fakey_coder` is also hidden from the ACE Models panel unless explicitly configured.
- **`docs/commit_workflows.md`** — fixed two example commands still using the pre-`.sase/`-relocation message-file paths.

**Suspected code bug for follow-up (not fixed, per instructions):** the memory/tribe research agent noted that retiring the globally-bundled `sase_beads` skill in favor of a project-repo-gated Tier 2 memory note (`642b4f490`, `d6a2cce1f`, `f0e1a25e6`) means agents working in a non-`is_sase_managed` project, or in the home context, now get **zero** bundled bead-workflow guidance — previously the skill was available everywhere. This may be intended narrowing rather than a bug, but it's worth a human decision; docs are already scoped accurately to current behavior, so no doc fix was needed for it.

I made these documentation changes this session, so I'll commit them now using the sase_git_commit skill.

Now writing the commit message file and running the commit.

A leftover message file exists from a prior commit. I'll read it, then overwrite it with this session's message.

This is stale content from an already-completed prior commit (`f0e1a25e6`). Now overwriting with this session's message.

Commit succeeded. Now verifying the tree is clean and pushed.

Working tree is clean and in sync with `origin/master` — nothing left to push.

## Summary

Committed the documentation refresh (docs/ace.md, docs/beads.md, docs/commit_workflows.md, docs/configuration.md, docs/fakey.md, docs/llms.md) via `sase_git_commit`. The commit succeeded and the branch is clean and up to date with `origin/master`. No further action needed.
