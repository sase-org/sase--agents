# Chat History - ace-run

- **TIMESTAMP:** 2026-07-16 18:05:05 EDT
- **MODEL:** claude/opus
- **AGENT:** research.f.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260716_175250.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research #gh:gh_sase-org__sase I would like to add support for running multiple agent children in the same family in parallel so I can support a few different use cases:
1. Running all phase agents and the agent that lands the epic in the same agent family
2. Doing the same thing for the research_swarm_kiss that lives in my chezmoi repo.

This will have several benefits, including saving space on the agents tab and allowing the user to see all of the agent metadata for all of the agents related to a particular Epic on a single panel. The root agent entry that contains all of the Epic agents should consolidate the metadata from all of them.

Can you do some research to help me understand how feasible this is and what other design decisions need to be made before we can start implementing this? End your analysis with a recommended solution Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding how agent families and the Agents tab currently work.

Research directory exists. Let me explore the relevant code in parallel.

I'll research agent families in this codebase, starting with the `--` parsing logic.

The repo has a glossary entry for this. Let me read it and find the core source.

I'll research the Agents tab of the `sase ace` TUI thoroughly. Let me start by locating the relevant code.

There's a dedicated `src/sase/agent/names/` package. Let me explore it along with the family_attach modules.

I'll start by exploring the repo structure and searching for Epic-related code.

Let me explore the ace TUI structure.

I'll research both topics in parallel.

`src/sase/plan_chain.py` is the core module. Let me read it fully.

Let me search the source tree specifically.

While those run, let me check the research directory conventions and open the chezmoi repo to look at `research_swarm_kiss`.

`models/agent_groups` looks central. Let me explore that and the widgets.

Found the core files. Let me read the epic modules.

There's substantial prior research on agent families here. Let me read the most relevant prior art.

Now let me examine the name allocation, validation, and the launch/spawn paths in parallel.

Now let me dig into the core tree/row building files.

The launch entrypoint is `sase bead work <plan> --yes`. Let me read the epic creation and work modules.

Let me look at the sequential chain execution (axe phases) and the validation module.

Now let me examine the Agent model and the child/parent relationship fields.

This is major prior art — a consolidated report on nearly this exact topic, dated today. Let me read the related design docs.

Now let me find the agent naming (Rust binding) and xprompt resolution.

Found the child linkage model. Now let me trace the fold filter and the `h`/`l` keymaps.

Let me read the plan chain execution flow — how the plan → code handoff happens.

Now let me open the chezmoi repo to inspect `research_swarm_kiss`.

The Rust lives in a linked repo. Let me find the epic work plan naming logic there.

Let me find the actual `h`/`l` binding definitions and their action handlers.

Now the dynamic family-attach path (the newer, non-chain way to add family members) and the template allocator.

Found it: `l` = `expand_or_layout`, `h` = `hooks_or_collapse`. Let me read the folding actions.

This is the key naming code. Let me read it exactly.

Let me check the family-attach directive parsing and the TUI grouping/ordering logic.

Let me read the core folding logic in detail.

`research_swarm_kiss` doesn't exist by that name — there's `research_swarm.md` and `old_research_swarm.md`. Let me read them.

Critical finding: phase/land agent names are raw bead IDs. Let me check the naming conventions and the launch handler.

Now the TUI grouping/ordering side, and how `agent_family` metadata is set.

Now the key question: rollup/aggregation. Let me examine the status family and rendering.

Now let me examine the family/hood conventions and the orchestration handler.

`research_swarm.md` uses **hoods** (`research.@.cdx`) plus a `%g:research` directive. Let me investigate `%g` and check for `kiss` elsewhere.

Let me read the grouping/linkage core: `is_family_child`, `agent_family_name`, and the `find_agent_family` lookup.

Key question: does each family member point at the root or at its predecessor? Let me check `create_followup_artifacts`.

There's already a `%group` directive (alias `%g`). This is highly relevant — let me dig in.

Now the launch mechanics and name expectations.

The info panel is a status strip. Let me find the actual metadata panel that shows per-entry details.

Let me check the name validation rules and bead ID format.

Let me verify the parent linkage in the family-attach launch path and the Agent model fields.

Found the metadata panel header builder. Let me read it.

Key finding: `%group`/`%g` maps to an existing **agent tag** concept (`agent_tags.json`) with its own ACE grouping UI. Let me understand how tag grouping differs from family rollup.

There's an `_agent_ordering.py`. Let me read it plus the Agent model's family properties.

Now let me check the `%w` wait directive semantics (parallel vs sequential) and the epic xprompts.

Let me read the ordering block and check the `%wait` dependency mechanism between family members.

Let me examine the runtime rollup and family metadata copying — this is key for question 3.

Let me trace the `%w` (wait) directive to determine parallel vs sequential execution.

Let me check the history of `research_swarm` in chezmoi for the "kiss" naming.

Let me read how `%wait` on a family base name resolves — the closest thing to a family dependency.

Let me find where `runtime_children` is populated and how intervals merge.

This is the rollup core. Let me read the status apply (parent-from-child derivation) and runtime interval merging.

This is the parallel-vs-sequential crux. Let me inspect `has_wait` in the multi-prompt launcher.

Let me confirm the name-building helper and the root `--0` suffix logic.

Let me confirm how the wait gate actually blocks at runtime.

Now let me check row rendering (root vs child) and the detail panel selection.

One last check: what happens when the family-attach parent is still running.

`ordered_row_providers` is another rollup. Let me read the fold annotation and child row rendering.

Found the epic phase mechanism. Let me read it.

Now let me check the Epic definition in the bead model and the plan schema.

Let me check the detail panel dispatch and tools panel source aggregation.

This is the exact use case #1. Let me read `bead/work.py` where phase agents + the land agent are composed.

Now the plan-side Epic schema (frontmatter) and the approval → launch path.

Let me check the `--epic` plan-chain agent and the Rust epic plan schema.

Let me find where epic phase agent names are generated (likely Rust core).

Let me do a final check for any token/cost aggregation anywhere in the agents tab.

Let me confirm the Rust epic plan schema (frontmatter phases) location.

Let me confirm the role model aliases.

Epic phase agents are named by bead ID (`sase-6e.4`) and the land agent by epic ID (`sase-6e`) — meaning they already form a **hood**. Let me check how hoods render.

Now let me examine how family root rows currently consolidate metadata from children — the core of the user's ask.

I have a complete picture. Here are my findings.

## 1. Where the family name is parsed from an agent name

**`src/sase/plan_chain.py` is the single source of truth.**

- **`plan_chain.py:9`** — `AGENT_FAMILY_SEPARATOR = "--"`
- **`plan_chain.py:308-323`** — `_split_agent_family_name()`, the actual splitter:
  ```python
  separators = [AGENT_FAMILY_SEPARATOR, "."]
  if include_legacy_dash:
      separators.append("-")
  for separator in separators:
      head, sep, tail = name.rpartition(separator)
      if not sep or not head or not tail:
          continue
      suffix = canonical_plan_chain_suffix(f"{sep}{tail}")
      if suffix is not None:
          return head, suffix
  ```
- **`plan_chain.py:326-329`** — `agent_family_base()` (public accessor, returns `split[0]`)
- **`plan_chain.py:351-356`** — `is_agent_family_member()`

**Important nuance:** the split is *not* a naive "split on `--`". It only succeeds if `canonical_plan_chain_suffix()` (**`plan_chain.py:139-149`**) recognizes the tail. Arbitrary suffixes like `foo--reviewer` work only because of the catch-all **`plan_chain.py:22`** `_ROOT_TOKEN_SUFFIX_RE = re.compile(r"^--([A-Za-z0-9_]+)$")`. Legacy `.plan`/`-plan` spellings map to canonical `--plan` via **`plan_chain.py:31-45`**.

**Second nuance:** it uses `rpartition` (last separator), so `foo--a--b` yields base `foo--a`, not `foo` — contrary to the "prefix" phrasing in the glossary. This is safe only because validation (see §5) forbids user-created `--` names and multi-`--` suffixes.

Other parse sites, which all prefer stored metadata over string parsing:
- **`src/sase/ace/tui/models/_agent_status_family.py:168-180`** — `agent_family_name()`: returns `agent.agent_family` metadata first, falls back to `agent_family_base(agent.agent_name)`.
- **`src/sase/agent/names/_lookup.py:153-168`** — `_family_base_from_meta()`: `agent_family` field → `workflow_name` → name parsing.
- **`src/sase/agent/_family_attach_candidates.py:130-136`** — `family_base()`.

## 2. How families are created today — two distinct paths

**Path A: the sequential plan chain (axe run loop).** This is the classic `foo--plan` → `foo--plan-0` → `foo--code` flow, and it *is* strictly sequential — an in-process loop where one phase finishes before the next artifacts dir is created.

- **`src/sase/axe/run_agent_exec_plan_accept.py:481`** — plan approved → coder:
  ```python
  state.current_role_suffix = PLAN_CHAIN_CODER_SUFFIX
  ```
  then `create_followup_artifacts(...)` at **:494-517**.
- **`src/sase/axe/run_agent_exec_plan.py:170-220`** — plan feedback → next planner round; allocates `--plan-@` at **:182-190**.
- The loop state lives in `state.current_role_suffix` (**`run_agent_exec_types.py:60`**), initialized to `""` at **`run_agent_exec.py:189`**.
- Suffix constants: **`plan_chain.py:10-14`** (`--plan`, `--q`, `--code`, `--epic`, `--commit`).

**Path B: dynamic family attach `%n(parent, suffix)`.** This is *not* sequential and is the newer mechanism.

- **`src/sase/agent/_family_attach_directives.py:14-45`** — `parse_name_directive_args()`; two positional args = family attach.
- **`src/sase/agent/_family_attach_resolution.py:19-130`** — `resolve_family_attach_plan()`; builds `agent_name = f"{parent_base}{role_suffix}"` at **:85**.
- Public API: **`src/sase/agent/family_attach.py:33-47`**.

Critically, Path B can attach to a **still-running** parent (**`_family_attach_resolution.py:122`**, `parent_is_running=kind == "running"`), which triggers workspace deferral (**`_family_attach_launch.py:64-73`**) and an auto-injected `%wait` on the parent (**`src/sase/axe/run_agent_directives.py:180-190`**).

## 3. Ordering / dependency — the family is a flat star, not a linear chain

This is the most important finding for your purposes. **The data model has no chain and no dependency edges.**

- **Every member points at the root, not at its predecessor.** Despite the parameter being named `prev_artifacts_timestamp` (**`run_agent_helpers_artifacts.py:101`**, assigned at **:159-161**), both call sites pass the *root* run's timestamp, which is constant for the whole axe run:
  ```python
  # run_agent_exec_plan.py:208 and run_agent_exec_plan_accept.py:498
  convert_timestamp_to_artifacts_format(ctx.timestamp)
  ```
- Grouping is purely `parent_timestamp == root.raw_suffix` — **`_agent_status_family.py:195-200`**:
  ```python
  def is_family_child(agent: Agent, parent: Agent) -> bool:
      if not parent.raw_suffix or agent.parent_timestamp != parent.raw_suffix:
          return False
  ```
- **`src/sase/agent/names/_lookup.py:193-231`** — `find_agent_family()` defines a "generation" as root + everything whose `parent_timestamp == root.timestamp`. Flat.
- **Display order is chronological, not structural** — **`src/sase/ace/tui/models/_agent_ordering.py:44-46`**:
  ```python
  # Sort follow-ups chronologically (oldest first) so the display reads
  # plan -> feedback -> coder in natural order.
  for followups in followups_by_parent.values():
      followups.sort(key=lambda a: a.start_time or "")
  ```
  The plan→feedback→coder reading order is an *emergent artifact of launch timestamps*, not a declared sequence.
- **Family completion is set semantics, not "last member wins"** — **`_lookup.py:234-241`**, `is_agent_family_complete()` requires `all(member.outcome == _SUCCESS_OUTCOME for member in family.members)`.

The only real dependency mechanism is the orthogonal `%wait` system in **`src/sase/core/wait_dependency_resolution/`**, and `%wait:<base>` resolves against the whole family via `resolve_wait_dependency()` (**`_lookup.py:279-286`**).

## 4. How the next family member's name is decided

Chain: `allocate_agent_family_child_suffix` → `_allocate_agent_family_child_name` → `allocate_agent_name_template` (lowest free token).

- **`plan_chain.py:448-462`** — `allocate_agent_family_child_suffix()` (returns only the suffix portion).
- **`plan_chain.py:426-445`** — `_allocate_agent_family_child_name()`; requires `@` in the template.
- **`plan_chain.py:409-423`** — `_reserved_agent_family_names()`; seeds reserved with the registry plus `base`, `base--plan`, and `base--0`.
- **`src/sase/agent/names/_templates.py:177-206`** — `allocate_agent_name_template()`; iterates tokens in sequence order and returns the first available candidate.
- **`_family_attach_resolution.py:151-173`** — `_resolve_role_suffix()`: `@` → allocate next free; anything else → `normalize_family_suffix_arg()` (explicit).
- **`_agent_status_family.py:627-660`** — `assign_bare_family_root_zero_suffix()`: a plain-named root `foo` that gains an attached sibling renders as `foo--0` *in memory only*; the registry name stays `foo`.

## 5. Where names are validated / constrained

- **`src/sase/agent/launch_validation.py:84-91`** — the core rule: user-supplied names may not contain `--`:
  ```python
  def validate_user_agent_name(name: str) -> None:
      if AGENT_FAMILY_SEPARATOR in name:
          raise AgentNameSyntaxError(name)
  ```
  Error text at **:69-77**: *"double dash is reserved for agent-family phases."*
- **`launch_validation.py:122-186`** — `validate_launch_name_requests()`, under the global allocation lock; also checks collisions.
- **Bypass for trusted internal launchers**: **`launch_validation.py:24`** `INTERNAL_AGENT_NAME_BYPASS_ENV = "SASE_INTERNAL_AGENT_NAME_BYPASS"`, checked at **:94-100**, threaded via `allow_reserved_family_separator_names` (**`launch_executor.py:65`**, **`multi_prompt_launcher.py:129`**, and ~8 call sites in **`launch_cwd_agents.py`**).
- **Suffix arg validation**: **`_family_attach_directives.py:142-155`** — `normalize_family_suffix_arg()`; `_SUFFIX_TOKEN_RE = ^[A-Za-z0-9_]+$` (**:11**); rejects leading `.`/`-` and any embedded `--`.
- **Collision check**: **`_family_attach_resolution.py:188-207`** — `_ensure_family_name_available()`.
- **Reserved registry**: **`src/sase/agent/names/_registry.py:57`** — `get_reserved_agent_names()`.

## Summary for a design change

If you're considering making families support explicit ordering/dependencies, the relevant gap is: **the persisted model is a flat star keyed on the root's `parent_timestamp`, with zero ordering metadata.** Linear-chain appearance comes only from (a) the axe loop being sequential in-process, and (b) chronological sort in `_agent_ordering.py:44-46`. `role_suffix` / `agent_family_role` carry semantic role but no sequence position. Any real dependency today has to go through the separate `%wait` system, which family-attach already leverages for running parents (`run_agent_directives.py:180-190`) — that's the natural extension point.

Excellent — the family data model is already a **flat star** (all members point at the root), not a chain. Let me check the info panel while the other agents finish.

Findings below.

## 1. Agent hoods

**Core parsing — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/models/agent_hoods.py`** (192 lines, the only hood implementation):

- `agent_name_key()` (L13-21) — case-folds the name, rejects any name with an empty dotted segment (`.bar`, `foo.`, `foo..bar`).
- `agent_hood()` (L37-57) — the actual hood parse. It is `rpartition(".")`: everything up to the *last* dot.
  ```python
  hood, sep, last = name.rpartition(".")
  if not sep or not hood or not last:
      return None
  return hood
  ```
  So `foo.bar` → hood `foo`; `foo.bar.baz` → hood `foo.bar` (the *immediate* namespace, not the root prefix).
- `is_agent_descendant()` (L24-34) — prefix test `candidate.startswith(f"{parent}.")`.
- `AgentNeighborIndex.from_visible_rows()` (L80-157) — buckets visible rows by hood (`members_by_hood`), plus separate ancestor/descendant maps. `_prefix_range()` (L188-192) does a bisect over sorted names using `prefix + chr(0x10FFFF)` as the upper bound.

**Notable divergence from the spec.** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/memory/glossary.md:15-17` says "The agent `foo`, if it exists, is also considered part of the `foo` agent hood." The code says the opposite (agent_hoods.py L46-49): dotless names have *no* hood in V1 and don't participate in hood-neighbor navigation. Also, the glossary implies `foo.bar` and `foo.bar.1` share the `foo` hood; the code puts `foo.bar.1` in hood `foo.bar`, not `foo`. The `foo`-agent case is partially compensated for by the separate *ancestor* map (L139-149), which walks every dotted prefix and does find a visible `foo` row — but that is a different relation than hood membership.

**Hoods vs families (`--`)** — different concepts, no shared code:

- Family separator: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/plan_chain.py:9` — `AGENT_FAMILY_SEPARATOR = "--"`, with `agent_family_base()` (L326) and `is_agent_family_member()` (L351).
- Families carry real metadata + lifecycle: `AGENT_FAMILY_FIELD`, `find_agent_family()` at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/names/_lookup.py:193`, family roles/status overrides in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/models/_agent_status_family.py`.
- Hoods carry no metadata at all — they are computed on the fly from the display name, only for TUI rows.
- Rendered names may not contain `--`: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/names/_indexed.py:63-65` rejects `AGENT_FAMILY_SEPARATOR` in a rendered template name.
- Docs state the split explicitly: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/docs/agent_families.md:7-8` ("Dot-separated names such as `foo.bar` are a separate ACE concept... They do not create plan-chain family membership") and `docs/xprompt.md:896`.

**Are hoods rendered in the Agents tab? No — not as structure.** Families group under a shared root entry; hoods produce no rows, no panels, no grouping level. `GroupingMode` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/models/agent_groups/_buckets.py:37-49`) has only `STANDARD`/`BY_DATE`/`BY_STATUS` — no hood mode. Panel keys come from tags/workflow parents (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/models/agent_panels.py:37-42`), not names. Hoods surface in exactly two places:

- A count badge: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/widgets/agent_info_panel.py:289-296` — `text.append("neighbors: ", style="dim")`, fed from `_selected_agent_neighbor_count()` at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agents/_display_detail.py:487-500`.
- The `~` jump modal: `action_start_sibling_mode` at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/navigation/_tree.py:41-52` delegates to `AgentNeighborMixin` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agents/_neighbors.py`, index cached at L46-77, rows built at L109-146, modal pushed at L222-229) rendering `"Neighbors - {hood} hood"` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/modals/agent_neighbor_modal.py:223`).

## 2. Xprompt swarms

**Fan-out — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/xprompt_swarm.py`** (653 lines).

- Detection: `xprompt_has_segment_separators()` in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/xprompt/segment_separators.py:13-18` — regex `^---\s*$` (MULTILINE) run *after* `protect_fenced_blocks`, so `---` inside code fences is not a separator.
- Public entry: `expand_xprompt_swarms_with_metadata()` at xprompt_swarm.py:490; the real work is `_expand_xprompt_swarms_with_metadata()` at L537-642. Fast path at L547 (`if not any("#" in seg ...)`). Swarm set built at L555-557. Sole-reference fan-out at L560-590: render body with the call's args, split on `---` (`_render_xprompt_swarm`, L382-393, which calls `substituted` with `preserve_segment_separators=True` then `split_segments_protecting_fences`), inherit the call-site VCS ref onto every follow-up (L577-579), attach the call site's leading directives to segment 0 only (L580-581), then recurse with `max_depth - 1` (L582-589; cap raises `_XpromptSwarmDepthError`, default `max_depth=8`).
- Embedded variants: `_expand_embedded_xprompt_swarm_reference` (L396) and `_expand_multiple_embedded_xprompt_swarm_references` (L437).
- Legacy alias shim: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/multi_agent_xprompt.py` (15 lines).

**Dispatch sites** (3, matching docs/xprompt.md:1881):
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_cwd_agents.py:89,118,129` (`sase run` / cwd launcher)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_request.py:610,620` (`_build_preview_plan`)

**Naming.** Each segment names itself via its own `%name:` directive (`%name:plan`, `%name:code`, `%name:review` — docs/xprompt.md:1858-1870). The swarm layer contributes only a *template group* tag so that `@`-style name templates from one invocation share one index token:

- `_next_template_group()` at xprompt_swarm.py:645-646 — `f"xprompt:{name}:{next(group_counter)}"` (e.g. `xprompt:swarm:0`, confirmed in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/tests/test_multi_prompt_launcher_xprompt_groups.py:199-203`). The group is assigned once per invocation at L568 and propagated to every sub-segment, including recursively.
- Carried through as `segment_template_groups` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_cwd_agents.py:103,125-134,202`) into `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/multi_prompt_launcher.py:398-418`, which calls `name_allocator.planned_names_for_template_group(...)` with `segment_template_group or f"fanout:{i}"`.
- Allocation: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/multi_prompt_reference_allocator.py:112-194` — one shared token rendered across all templates in the group (`_template_candidates`, L620-632), so a swarm's `foo@`/`bar@` templates get the *same* number. Non-grouped slots fall back to `planned_name_for_prompt` (multi_prompt_launcher.py:424-431). The chosen name is injected as `SASE_AGENT_PLANNED_NAME` (L435-449).
- Two invocations of the same swarm get distinct groups via a shared `group_counter` (`itertools.count()`), deliberately threaded through the per-segment path at launch_cwd_agents.py:113-127.

**Do swarm agents form a family? No, not by default.** The swarm layer never emits `--` names and sets no family metadata. A swarm becomes a family only if its segments say so — either an explicit `%n(parent, suffix)` directive, or a later segment attaching to an earlier segment's static name via `_explicit_static_name_for_pending_family_parent()` (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_executor.py:147-155, 162-169`) feeding `pending_family_parents`.

**Are they launched in parallel? No — spawned sequentially, then run concurrently.** Both loops are plain `for`:
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/multi_prompt_launcher.py:251` — `for i, segment in enumerate(segments):`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_executor.py:101` — `for slot in plan.slots:`

Concurrency comes from the spawn itself: `spawn_agent_subprocess()` at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/launch_spawn.py:117` — "Spawn a detached background agent process" (L124). So the segments start back-to-back and then run at once, unless `%wait` chains them (docs/xprompt.md:1877: "The `%wait` directives chain them sequentially; without `%wait` they would run in parallel").

## 3. Parallel agent launches elsewhere

There is **no place that concurrently spawns sase agents**, and one place that explicitly refuses to:

- **Deliberate sequentialization** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/axe/lumberjack.py:216-227`. Script chops go through `ThreadPoolExecutor`; agent chops are run inline in the main thread. The comment is the load-bearing rationale:
  ```python
  # Run script chops concurrently. Agent launches are sequentialized below
  # because launch preparation allocates workspaces before the eventual
  # RUNNING-field claim, so same-tick launches can race on one workspace.
  ```
  This is the constraint any "launch agents in parallel" work would have to solve first. The workspace claim is at launch_spawn.py:165-170 (`claim_workspace` / `transfer_workspace_claim`), and `WorkspaceClaimError` failure kills the process before raising (launch_spawn.py:141-144).

- **Parallel workflow steps (in-process, not spawned agents)** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/xprompt/workflow_executor_parallel.py:212-223`, `_execute_parallel_step`, `ThreadPoolExecutor(max_workers=len(nested_steps))` with `copy.deepcopy(self.context)` per step; join/fail-fast at L223+. The loop equivalent is `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/xprompt/workflow_executor_loops.py:488-499` (parallel nested steps per loop iteration). These run agent *steps* concurrently in threads; they do not use `execute_launch_plan` and get no agent names from the allocator.

- **Other threads are not launches**: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/axe/orchestrator.py:89` streams a child's stdout; `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/actions/agent_workflow/_workflow_exec.py:268` runs one workflow off the UI thread; `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/ace/tui/models/_loaders/_json_cache.py:80-92` is a JSON read pool.

**Summary of name assignment across all fan-out paths:** every launch, parallel or not, routes names through `_PlannedNameAllocator` in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/agent/multi_prompt_reference_allocator.py`, under a process-wide `agent_name_allocation_lock()` (L135) with reservations against `get_reserved_agent_names()`. Grouped templates (swarm invocation, or `fanout:{i}` for a multi-model fan-out) share one token; everything else allocates per-slot. Names are committed post-spawn via `mark_template_reservation_committed` (multi_prompt_launcher.py:487).

I have a complete picture. Here are my findings.

## Critical framing: there are TWO nesting hierarchies

The Agents tab has two independent tree structures that are easy to conflate:

1. **Group banners** (project → ChangeSpec → name-root → name-prefix) — built in `models/agent_groups/_tree.py`, folded via a `GroupFoldRegistry`.
2. **Agent rows** (root agent/workflow → child entries) — a flat list where children are interleaved after their parent, folded via a separate `FoldStateManager`.

Your questions are about #2, but `h`/`l` drive **both** (see Q4). Note also: `is_workflow_child` is a **misleading historical alias** — it returns true for *any* child row, not just workflow steps (`models/agent.py:280-287`).

---

## 1. Where rows are built

**Tree assembly** — `models/agent_groups/_tree.py:171-393` `build_agent_tree()`. Emits `TreeEntry(kind="group"|"agent")` (`_tree.py:43-49`). Note this builds only *banner* structure; agent rows are emitted flat at `_tree.py:391` (`entries.append(TreeEntry(kind="agent", agent_idx=i))`) — root and child agents are indistinguishable at this layer.

**Ordering / parent-child interleave** — `models/_agent_ordering.py:17-148` `sort_and_reorder()`. This is where children get physically placed under parents: workflow steps at `:140`, family follow-ups at `:141`, other steps at `:142`.

**Row → Option rendering** — `widgets/_agent_list_build.py:196-403` `build_list()`. Calls `build_agent_tree` at `:237`, pre-formats agent rows at `:254-302`, walks the tree emitting Options at `:322-389`.

**Per-row visuals** — `widgets/_agent_list_render_agent.py:118-127`, where the child indent is applied:
```python
if agent.is_child_row:
    text.append(_CHILD_INDENT, style="dim #808080")
```

---

## 2. Root vs child distinction

Computed in **`models/agent.py:251-262`**:
```python
@property
def child_linkage(self) -> AgentChildLinkage:
    if self.parent_workflow is not None:
        return AgentChildLinkage.WORKFLOW_STEP
    if self.parent_timestamp is not None:
        return AgentChildLinkage.FAMILY_MEMBER
    return AgentChildLinkage.ROOT
```
Enum at `models/agent_types.py:14-19`. Derived properties at `agent.py:264-287` (`is_child_row`, `is_workflow_step_child`, `is_family_member_child`, `is_workflow_child`).

The **linkage key is `parent_timestamp` → parent's `raw_suffix`**. Parent lookup is rebuilt in several places:
- `_tree.py:201-203` and `_tree.py:101-105` — `parent_lookup: dict[str, Agent]`
- `_agent_status_apply.py:92-95` — `parent_by_suffix`
- `_agent_ordering.py:170-173` — `_attach_runtime_children`
- `_fold_filter.py:27-29` — `present_parent_keys`

---

## 3. Rollup today — partial, and there is no token/cost anywhere

**There is no `tokens` or `cost` field on `Agent` at all.** I verified `models/_agent_state.py` (the full field list) has none. Tokens exist only per-tool-call, parsed from artifact JSON summaries — `tui/tools/_entry.py:181` and `widgets/_tools_panel_details.py:239` read `total_tokens` from a tool-response summary. So a token/cost rollup would need the underlying field to be introduced first.

What rollup **does** exist, by field:

| Field | Rollup? | Location |
|---|---|---|
| **Elapsed time** | Yes — real recursive sum | `models/agent_time.py:332-359` `_aggregate_runtime()` |
| **Status** | Yes — mirror, not aggregate | `_agent_status_apply.py:44-48` `_mirror_root_from_child()` |
| **Model / provider / workspace** | Yes — backfill only | `_agent_status_family.py:518-530` |
| **Provider badges** | Yes — ordered union | `widgets/_agent_list_helpers.py:29-52` |
| **Tool-call sources** | Yes — per-child sources | `tui/tools/sources.py:47-56`, `:151-195` |
| **Timestamps** | Yes — union | `_agent_status_apply.py:106-120` |
| **Tokens / cost** | **No — field doesn't exist** | — |

The elapsed-time rollup is the model to copy — `agent_time.py:332-359` sums children:
```python
for child in children:
    interval = _runtime_interval(child, now, seen)
    ...
    elapsed_seconds += interval.elapsed_seconds
    active = active or interval.active
```
Note it's cycle-guarded via a `seen: set[int]` of `id()`s, and `_runtime_interval` (`:363-381`) prefers aggregate over leaf — a parent with children **ignores its own leaf interval entirely**.

The plumbing that makes this work: `runtime_children` (`_agent_state.py:270`, load-time only, explicitly excluded from serialization at `agent_bundle.py:21`), populated in `_agent_ordering.py:164-186` and cleared each rebuild at `:151-161`.

Status is a **mirror, not an aggregate** (`_agent_status_apply.py:44-48`: `parent.status = child.status`) — the root shows the newest child's status verbatim.

Group banners have a separate, unrelated rollup — `_tree.py:396-424` `compute_banner_summary()` counts running/failed/awaiting, and **explicitly skips child rows** (`:413-414`). Rendered at `_agent_list_render_banner.py:78-79`.

---

## 4. `h` / `l` keymaps

**Bindings** — `tui/bindings.py:139` (`l` → `expand_or_layout`), `tui/bindings.py:26` (`h` → `hooks_or_collapse`). Uppercase variants at `:140` / `:27`. Note `h` is also `agent_home` in *leader* mode (`keymaps/types.py:507`) — different mode, no conflict.

**Action entry points** — `actions/agents/_folding.py:569-591`. Both first route to the tools-detail level (`_route_tools_detail_level`), and only then fall through to the tab dispatch — so `h`/`l` do *not* fold rows when the tools panel has focus.

**Core logic** — `_folding.py:191-232` `_expand_fold()` and `_folding.py:281-343` `_collapse_fold()`. The dispatch is priority-ordered:
- `l`: banner focused → expand group (`:203-214`); else agent focused → `self._fold_manager.expand(wf_key)` (`:219-221`).
- `h`: **per-workflow fold takes priority** (`:297-315`); then banner collapse w/ parent escalation (`:318-331`); then collapse enclosing group (`:333-343`).

**Fold state** — `models/fold_state.py:28-145` `FoldStateManager`, keyed by parent `raw_suffix`, three-level `FoldLevel` (`fold_state.py:6-11`): `COLLAPSED → EXPANDED → FULLY_EXPANDED`. The middle level hides `is_hidden_step` children.

**Where hiding actually happens** — `models/_fold_filter.py:52-72`:
```python
level = fold_manager.get(parent_key)
if level == FoldLevel.COLLAPSED:
    continue
if level == FoldLevel.EXPANDED and agent.is_hidden_step:
    continue
```
Default is `COLLAPSED` (`fold_state.py:47`) — **children are hidden until the user presses `l`**, which is the core constraint for a rollup feature: the root row is what users see by default.

Fold counts `(non_hidden, hidden)` are returned from `_fold_filter.py:41-44` and rendered as the `×N −M` annotation via `_agent_list_helpers.py:71-122` `compute_fold_annotation()`.

---

## 5. Panel on root vs child — they are the same panel

**There is no root-specific panel.** `actions/agents/_display_detail.py:124-138` calls `_get_selected_agent()` and passes that single `Agent` to `agent_detail.update_display(...)`. Selection resolution is `_selection.py:17-25` — a plain `self._agents[self.current_idx]` lookup.

The panel body is `widgets/prompt_panel/_agent_display_header.py:149-569` `build_header_text()`, which reads **only `agent.*` fields**. Root vs child differences are just conditional rows:
- `:231-233` — child shows `Step:`; root shows `ChangeSpec:`/`Project:`
- `:285-288` — `Model:` (root value may be backfilled from a child per Q3)
- `:207-220` — retry-chain breadcrumb

**Collapsed banner selection does not aggregate** — `_agent_list_build.py:132-163` `resolve_row()`:
```python
if banner is not None:
    first = banner.agent_indices[0] if banner.agent_indices else 0
    return (first, None, banner.group_key)
```
Selecting a collapsed banner shows the **first agent's** metadata, not a group summary.

---

## Implications for a root-entry rollup

- **Tokens/cost cannot be rolled up today** — no `Agent` field exists; it must be added to `_agent_state.py` and threaded through `agent_loader.py` first. Elapsed time is the only numeric with real aggregation.
- **`_aggregate_runtime` (`agent_time.py:332-359`) is the pattern to follow** — it already solves cycle-guarding and the aggregate-over-leaf precedence.
- **`runtime_children` is the right traversal edge**, but note it holds only *direct* children and only `step_type == "agent"` main steps + follow-ups (`_agent_ordering.py:177-184`) — hidden/bash/python steps are excluded, so a "total cost" rollup over it would silently undercount.
- **Watch the render cache** — `_agent_list_render_cache.py:104` and `tools/cache.py:120` already key on `runtime_children`; a new rolled-up field must participate in cache invalidation or roots will show stale totals.
- **The metadata panel needs a new branch** to render aggregate rows, since `build_header_text` is strictly single-agent today.

I have a complete picture. Here are my findings.

## 1. What is an Epic?

An Epic is **two things bound together**: a *bead* (tracked work item) and an *SDD plan file* (the spec).

**Bead side** — `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/src/sase/bead/model.py:15-22`

```python
class IssueType(Enum):
    PLAN = "plan"
    PHASE = "phase"

class BeadTier(Enum):
    PLAN = "plan"
    EPIC = "epic"
```

An epic is `issue_type=PLAN` **and** `tier=EPIC`. Both are required — enforced in Rust at `sase/repos/linked/sase-core/crates/sase_core/src/bead/work.rs:51-60`. Its **phases** are child beads (`issue_type=PHASE`, `parent_id=<epic_id>`), and phase ordering comes from bead `Dependency` edges.

**Plan side** — plan tiers are `("tale", "epic")` at `src/sase/sdd/plan_tiers.py:10`. The epic frontmatter schema is defined in Rust at `sase/repos/linked/sase-core/crates/sase_core/src/plan/validate.rs:21-23`:

```rust
const EPIC_FIELDS: &[&str] = &["phases", "changespec", "bug_id"];
// phase fields:
    &["id", "title", "depends_on", "description", "model"];
```

So: **a tale is a single-agent plan; an epic is a plan with a `phases:` DAG**. The bridge from plan → beads is `src/sase/bead/epic_from_plan.py:84-129` — it creates the epic bead, writes `bead_id` back into the plan frontmatter, then creates one PHASE child per `phases:` entry and adds `depends_on` edges.

## 2. How phase agents are launched

**There is no per-phase launch loop.** All phase agents plus the land agent are launched in **one single multi-prompt call**, then self-sequence at runtime via wait gates.

The DAG → wave computation is in **Rust**: `sase/repos/linked/sase-core/crates/sase_core/src/bead/work.rs:125-153` (Kahn-style layering; wave 0 = phases with no open in-epic blockers). Python calls it via `build_epic_work_plan_from_beads_dir` at `src/sase/bead/work.py:114-119`.

Rendering to a `---`-separated multi-prompt: `src/sase/bead/work.py:247-282`. Each phase segment becomes:

```python
lines.append(f"%name:!{assignment.agent_name}")
lines.append(_group_directive(plan.launch_tag_id))   # %group:<epic_id>
lines.append("%auto:tale")
if assignment.waits_on:
    lines.append(f"%w:{','.join(assignment.waits_on)}")
lines.append(f"#{work_phase_xprompt.name}:{assignment.bead_id}")
```

**Parallel or sequential?** Both, in a specific sense — this is the key design:

- **Spawn: all at once (parallel).** `src/sase/bead/cli_work_handler.py:353-362` makes a *single* `launch_bead_work_agents` call with the whole multi-prompt. That routes to `launch_planned_bead_work_agents` (`src/sase/agent/launch_cwd_bead_work.py:29`), which spawns every segment.
- **Execution: wave-ordered (sequential across waves, parallel within a wave).** `%w:` marks a segment as deferred (`has_deferred_start_directive`, `src/sase/xprompt/_directive_scan.py:51-59`). Each spawned agent then **blocks inside its own process** in `wait_for_dependencies` (`src/sase/axe/run_agent_wait.py:303`), writing `waiting.json` and polling for `ready.json` until its named upstream agents finish. Deferred agents also defer workspace assignment (`multi_prompt_launcher.py:366`, `deferred_workspace=has_wait`).

Phases in the same wave run concurrently; a wave-*k* phase waits on its specific blockers, not on the whole prior wave (`work.rs:164-169` — `waits_on` is per-phase deps, not the full wave).

## 3. The agent that lands the epic

The **land agent**. Every epic gets exactly one, appended as the final segment: `src/sase/bead/work.py:267-280`.

```python
land_lines.append(f"%name:!{plan.land_agent_name}")
...
land_lines.append(f"%w:{','.join(plan.land_waits_on)}")   # every phase agent
land_lines.append(f"#{land_epic_xprompt.name}:{plan.epic_id}")
```

`land_waits_on` = every phase agent in the epic (`work.rs:182-187`), so it starts only after all phases finish.

Its prompt is the **`bd/land_epic` xprompt**, `src/sase/default_config.yml:502-524`, tagged `land_epic`. Three steps: **Verify** (re-read children beads + actual source/commits to confirm reported work is real), **Integrate** (merge with changes that landed since the epic started), **Land** (`sase bead close`, run `just symvision`, set `status: done` in the plan frontmatter). If it finds remaining work it plans it via `/sase_plan` rather than landing.

Resolution: `resolve_land_epic_xprompt` at `src/sase/bead/xprompts.py:42-44` → `XPromptTag.land_epic` (`src/sase/xprompt/tags.py:28`). Users can override by tagging their own xprompt.

## 4. How the agents are named — **neither convention**

This is probably the most important finding for your purposes. Phase and land agents are named **the raw bead ID, verbatim**:

`sase/repos/linked/sase-core/crates/sase_core/src/bead/work.rs:199-205`

```rust
fn phase_agent_name(bead_id: &str) -> String {
    bead_id.to_string()
}

fn land_agent_name(epic_id: &str) -> String {
    epic_id.to_string()
}
```

So an epic `sase-02k` with phases `sase-03v`, `sase-03w` produces agents literally named `sase-03v`, `sase-03w`, and `sase-02k`. **No `--` family suffix, no `.` hood nesting.** The land agent shares its name with the epic bead ID; there is no `--land` or `.land`.

Notable related details:

- **Legacy used the hood convention.** `src/sase/bead/cli_work_plan.py:17-32`: `_legacy_land_agent_name` = `f"{plan.epic_id}.land"`, kept only as an extra wipe target. So the land agent *moved off* dotted naming to the bare epic ID.
- **The `--` family convention exists but is for plan-chain agents, not phase agents.** `src/sase/plan_chain.py:9-15` defines `AGENT_FAMILY_SEPARATOR = "--"` with suffixes `--plan`, `--q`, `--code`, `--epic`, `--commit`. `--epic` is the *planner* that authors the epic plan — a different agent from the phase workers.
- **The `.` hood convention exists but is TUI-only.** `src/sase/ace/tui/models/agent_hoods.py:37-57` — dotted names form navigation "hoods" (`foo.bar` lives in hood `foo`). Bead-ID names are dotless, so **phase agents do not participate in hood navigation at all** (`agent_hoods.py:54-56` returns `None` for dotless names).
- Bead IDs are `prefix + "-" + base36` (e.g. `sase-03v`, `src/sase/bead/ids.py:44`). Because they contain a hyphen, launches set `SASE_INTERNAL_AGENT_NAME_BYPASS=1` (`src/sase/agent/launch_validation.py:24`, set in `work.py:355`) to pass `allow_reserved_family_separator_names` (`launch_cwd_bead_work.py:113,160`).
- Grouping is by `%group:<epic_id>` (`work.py:341-342`), and models default to role aliases `phase_worker` / `epic_lander` (`src/sase/llm_provider/config.py:57,60`).

## 5. Where orchestration lives

**Python + Rust + xprompt — no workflow YAML.** Layered:

| Layer | Location | Role |
|---|---|---|
| CLI entry | `src/sase/bead/cli_work_handler.py:79` `handle_bead_work` | `sase bead work <target>`; routes plan-file vs bead-ID |
| **Main orchestrator** | `src/sase/bead/cli_work_handler.py:217` `launch_epic_bead_work` | The spine: xprompt lookup → work-plan build → VCS context → render → confirm → force-reuse wipe → mark ready → pre-claim → launch → commit, with rollback |
| DAG/waves | `sase-core/crates/sase_core/src/bead/work.rs:32-197` (Rust) | Wave partitioning, cycle + cross-epic-blocker detection, agent naming |
| Prompt render | `src/sase/bead/work.py:212-282` | Wave plan → `---`-separated multi-prompt with `%name`/`%group`/`%model`/`%w`/`#xprompt` |
| Launch adapter | `src/sase/agent/launch_cwd_bead_work.py:29` | Preplanned one-slot fan-out; skips generic discovery |
| Runtime gating | `src/sase/axe/run_agent_wait.py:303` `wait_for_dependencies` | Per-agent blocking on upstream completion |
| Agent instructions | `src/sase/default_config.yml:502` (`bd/land_epic`), `:558` (`bd/work_phase_bead`) | The actual prompts, tag-resolved so users can override |
| Plan→epic bridge | `src/sase/bead/epic_from_plan.py:33` | Deterministic epic DAG creation w/ full rollback |
| Approval→launch | `src/sase/plan_approval_actions.py:133-201`, `src/sase/bead/epic_launch.py` | Host-side launch: `detached` (default) / `foreground` / `skip` |

**Full end-to-end flow:**

```
planner agent (--epic) authors plan w/ phases: DAG
  → sase plan propose → approval (choice == "epic")
  → epic_launch.py: spawn_detached_epic_launch → ["sase","bead","work",<plan>,"--yes"]
  → cli_work_from_plan → epic_from_plan.create_and_launch_epic_from_plan
      → creates epic bead + PHASE children + dependency edges
  → cli_work_handler.launch_epic_bead_work
      → Rust build_epic_work_plan → waves
      → render_multi_prompt → N phase segments + 1 land segment
      → ONE launch call → all N+1 agents spawned
  → each agent self-gates on %w until its blockers finish
  → land agent (named <epic_id>) verifies, integrates, closes
```

Two safety notes worth flagging: `preclaim_epic_work` (`cli_work_handler.py:334`) claims phase beads *before* spawning, with `rollback_work_launch` on failure; and `epic_from_plan.py:143-147` deliberately **refuses to roll back** when `BeadWorkError.agents_launched` is true, since deleting beads out from under live agents would orphan them.

Two more agents reported. Let me verify a critical detail: whether epic phase agents share a ChangeSpec and workspace today.

All four agents reported. Let me verify one detail I need to get right — whether phase bead IDs contain dots (which would make them hoods).

Confirmed — child bead IDs are `{parent_id}.{n}` (e.g. `sase-6e.4`). Let me verify epic phases use this dotted form.

One more critical check — whether `sase-6e.4` already parses as a family *feedback-round* suffix of `sase-6e`.

Let me test this empirically rather than reason about it.

While that installs, let me check the docs on families to ground the recommendation.

Confirmed a significant finding. Let me verify the load-bearing claims myself before writing.

All claims verified. Now let me write the research report.

The sase repo is untouched (the report lives in the research sidecar), so no `just check` is needed.

**Research written to `sase/repos/research/202607/parallel_family_children.md`.**

## The headline

**Parallelism isn't the blocker — both your use cases already run in parallel in production.** `sase bead work` spawns every phase agent plus the land agent in one multi-prompt call, and they self-gate at runtime via `%wait`. `research_swarm` does the same. Nothing needs a new scheduler.

The actual problem is that SASE has **three uncoordinated grouping mechanisms**, and both use cases picked the two that don't produce a root row:

- **Family** (`foo--code`) → root row + folded children, with rollup
- **Hood** (`foo.bar`) → navigation index only
- **Tag** (`%g:foo`) → a whole side panel per tag

Both use cases use tag + hood. Tags make your space complaint *worse*: `%group:<epic_id>` gives every epic its own panel containing N+1 rows.

## The best find

I executed the parser rather than reasoning about it, and **epic phase agents already classify as family members of the land agent**:

```
'sase-6e.4'  member=True  base='sase-6e'  suffix='--4'  role='feedback'
```

Child bead IDs are `{parent}.{n}`, and the feedback-suffix regex accepts a dot. So `agent_family_base('sase-6e.4')` returns exactly the land agent's name — the naming needs no migration at all. Two caveats: the role is wrong (`feedback`, meant for replan rounds), and the *name* says family while the *linkage* (`parent_timestamp`) says root, so they currently disagree. Whether that disagreement is inert or already causing misbehavior is my top open question.

Also good news: the family data model is already a **flat star**, not a chain — the plan→code reading order is just a chronological sort. Parallel members are representable today.

## What will actually cost you

Three things, and the "it's just metadata" pitch is false for all of them:

1. **Root status is a mirror, not an aggregate** — literally `parent.status = child.status`. With 8 parallel phases there's no correct "winning child," and `_agent_status_family.py` is 664 lines of recency-as-supersession heuristics that all assume sequence.
2. **Tokens and cost don't exist as fields at all.** I checked the full `Agent` field list — nothing. "Consolidated cost for an epic" is a new metric subsystem crossing the Rust wire, not a rollup. This is the easiest thing to under-scope.
3. **Family children are slot-exempt**, so granting membership would make an 8-phase epic bypass `max_running_agents` entirely. That's a live capacity bug that membership would *activate*.

## Recommendation

Grant membership via metadata to agents that already run in parallel; make the root a real aggregate; **don't touch `%n`, the axe loop, or the scheduler**. Staged: fix slot accounting → aggregate status → cascade kill → epic membership → consolidated panel → `research_swarm` last (it's the harder one: unlike the epic, no agent is named `research.3`, so it forces the synthetic-root decision the epic lets you dodge).

Notably, the first three phases are worth doing even if you drop the grouping feature — a good sign about the sequencing.

Two things worth your attention: **`research_swarm_kiss` doesn't exist** — there's only `research_swarm.md` and `old_research_swarm.md` in chezmoi, and I assumed you meant the former. And there's substantial prior art here — a consolidated report on nearly this exact question dated *today*. I built on it rather than relitigating it, and flagged where I think it understates the good news for these two specific workloads.

I made these changes — the report is mine from this session. Let me commit it.

Single untracked file, and both listed repos resolve to the same directory — so one commit covers both. Invoking the commit skill.

I'll record the skill use, then commit.

Let me check what tag convention this research repo's history uses.

The convention is clear: `docs(research):`. Writing the message.

Committed and pushed. Working tree is clean and `main` is in sync with `origin/main`.

## What I did

Committed the research report I wrote this session as `3cc12e6 docs(research): analyze parallel agent family children`. The finalizer listed two repositories, but both the `research` linked repo and the `sase-org/sase--research` sidecar resolve to the same directory (`sase/repos/research`), so the single commit covers both. No `just check` was needed — the sase workspace checkout itself is untouched, since the report lives entirely in the research sidecar.

I followed the repo's existing `docs(research):` tag convention, and the commit message describes only this report, cross-referencing the prior agent-family unification research (`2ca7d90`) that I built on rather than restating it.

## The report's conclusion, in brief

Parallelism isn't the blocker — both of your use cases already run their members in parallel via a single multi-prompt spawn plus runtime `%wait` gates. The real problem is that SASE has three uncoordinated grouping mechanisms, and both use cases picked the two that don't produce a root row.

The most useful find: epic phase agents **already** parse as family members of the land agent, because child bead IDs are `{parent}.{n}` and the feedback-suffix regex accepts a dot. So `agent_family_base('sase-6e.4')` returns `sase-6e` with no migration at all — though the derived role is wrong, and the name and linkage currently disagree.

The recommendation is to grant membership via metadata and make the root a real aggregate, without touching `%n`, the axe loop, or the scheduler. Worth re-flagging two things from my analysis: **`research_swarm_kiss` doesn't exist** — I assumed you meant `research_swarm.md` — and the three things that resist the "it's just metadata" framing are that root status is a mirror rather than an aggregate, tokens/cost don't exist as `Agent` fields at all, and family children are slot-exempt (so membership would let an epic bypass `max_running_agents`).
