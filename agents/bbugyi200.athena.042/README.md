# Agent: 042

[Agent Hoods](../../README.md) / [bbugyi200](../../users/bbugyi200/README.md) / [athena](../../users/bbugyi200/machines/athena/README.md) / [042](../../users/bbugyi200/machines/athena/hoods/042/README.md) / 042

**Global name:** `bbugyi200.athena.042` · **State:** active · **Source run:** `run-e98eb0cbf07f6f6da67e7f435680ad4e`

**Owner:** `bbugyi200.athena` · **Project:** sase · **Hood:** 042

## Summary

- Model: opus
- Provider: claude
- Timing: 2026-08-16T17:30:00.993151+00:00
- Commits: [2](#commits)
- Variables: [5](#variables)

## Files

[Prompt](prompt.md)

## Commits

| Repo | Commit | Subject | Committed |
|---|---|---|---|
| sase | [`84d8af5`](https://github.com/sase-org/sase/commit/84d8af51f6cfddcfcce499811285340ac554ecb4) | chore: Add SDD prompt and plan for clear\_agent\_tag\_meta\_revert | 2026-06-23 08:26:29 EDT |
| sase | [`4d60ba2`](https://github.com/sase-org/sase/commit/4d60ba2260c48a56b34ec3c5ea196aa2372a2b0d) | fix(tui): clear persisted agent meta tags on unset | 2026-06-23 08:39:49 EDT |

## Variables

| Variable | Value |
|---|---|
| `flag_cli_cannot_cite_a_local_note` | sase flag (phase sase-nb.7), its three doctor checks, and the FlagTriage gate text ship globally and run from any project, but sase/memory/sase\_flags.md will now exist only in the sase repo. Any user… |
| `formatting_is_now_manual` | Generated notes are auto-formatted by format\_generated\_memory\_markdown and validated at render time (description required, frontmatter applied by apply\_memory\_frontmatter). A hand-written sase/memory… |
| `glossary_and_docs_stay_where_they_are` | Do not over-apply the correction. (1) The glossary addition is already project-local: memory.glossary in this repo's sase/sase.yml renders sase/memory/glossary.md per project (init\_memory/glossary.py… |
| `tier1_pointer_is_the_same_bug` | The plan's always-loaded Feature Flags pointer is planned for src/sase/main/init\_memory/templates/memory-sase.template.md, which renders sase/memory/sase.md into EVERY sase project. That is the same… |
| `verification_shift` | Phase sase-nb.10's exit condition 'sase init -c reports no memory drift' stops covering sase\_flags.md, because drift checks compare generated files against their templates and a hand-written note has… |

Values are truncated for display; see [meta.json](meta.json) for the full values.

## Neighbors

| Agent | Relation | State |
|---|---|---|
| [042.f0](../bbugyi200.athena.042.f0/README.md) | descendant | active |
