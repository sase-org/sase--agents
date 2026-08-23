# Chat History - ace-run (research.0y.cld)

- **TIMESTAMP:** 2026-08-23 09:38:16 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0y.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260823_120216.md`

## Prompt

%id(cld, clan=research.0y) %m:@research_b  #gh:gh_sase-org__sase I want to migrate the sase/memory/task_types.md memory file
to a finalizer that is only active for sase managed projects.

- This finalizer, like all finalizers, should be configurable via a Project Local sase
  config field, which should be added to sase-managed projects by the `sase init`
  command automatically (e.g. `use: builtin@tasks` will be added).
- The goal is to move all of this text out of agent instruction files (to keep
  short-term memory as focused as possible) and only prompt agents to think about
  whether they need to create task beads or not at the very end of the turn.
- I will soon migrate this text to a memory file, once I add a new memory file type.
  This is upcoming work I still need to research, but something you may want to keep in
  mind when thinking about this text.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current state of finalizers, the task_types memory file, and the config/init machinery.

I have what I need. Writing the research report.

The sase repo itself is untouched — only the research sidecar has the new file, so no `just check` is needed.

Research written to `sase/repos/research/202608/task_types_finalizer_migration.md`.

## What I found

**The substrate is more ready than I expected.** `sase-core` needs no change at all: `FinalizerTriggerKindWire::Always` already exists, and Rust only rejects `NotTriggered` + `submission_required` — so `always` + "must submit a payload" is legal today and simply has no producer. Every `builtin@commit` string in the Rust crate is inside test fixtures.

**The one genuinely missing primitive is an agent-facing instruction channel.** `sase final context` emits instance IDs, triggers, and a manifest template — no prose. The provider protocol *has* a `describe` operation, but `_execute_plugin_once` calls it after the turn ends, so its output can never reach the agent.

**Five gaps worth knowing before you design:**
- `finalizers.defaults` is *replaced* by the last config layer that sets it, while `instances.<id>.<field>` merges per field. So `sase init` writing `defaults: [commit, tasks]` would silently clobber a user-level `[commit, lint]` — it must write the effective list.
- Requirement digests feed the context digest, so `builtin@tasks` must **not** hash bead state, or every `/sase_new_task` call between `context` and `submit` invalidates the manifest. (Filing a bead is otherwise safe — the bead CLI auto-commits its own sidecar.)
- Two memory roots carry this note, not one: `sase/memory/task_types.md` (925 tokens, 21% of project `AGENTS.md`) and `~/sase/memory/task_types.md` (820 tokens, **52%** of `~/AGENTS.md`). Combined ≈29% of all always-loaded memory.
- `MemoryNoteType` is `Literal["short", "long"]`, enforced in two places — that's the seam your planned new type slots into.
- `sase init repo` is an exact precedent: it already gates on `is_sase_managed`, edits project `sase/sase.yml` with the comment-preserving `set_key`, and commits the result.

## Recommendation

A fourth builtin provider, `builtin@tasks`, activated by a project-local instance that a new `sase init finalizers` spec writes for SASE-managed repos only, with a host-side `instructions` field on the **context payload** (outside the signed wire, so no Rust change), and a **falsifiable payload** — a decision plus claimed bead IDs that the host verifies against the bead store rather than trusts. Instructions render from the live catalog and defer all mechanics to `/sase_new_task`, so they land well under 300 tokens instead of 925.

Two things I'd flag as real costs, not just details: with `trigger: always`, every non-handoff turn now requires a declaration (today clean turns submit nothing), so a forgotten `/sase_final` costs a full recovery turn — worth watching `sase_finalizer_recoveries_total` during a soak. And an end-of-turn nudge asks an agent to *recall* a flake rather than priming it to *notice* one. That's the core trade you're making; I think it's the right one, but the report says so plainly and suggests measuring task-bead creation rate per 100 turns across the change.

The `%final:!tasks` selector also lets you delete the awkward "unless your prompt forbids creating beads (epic phase workers…)" clause from the text entirely.
