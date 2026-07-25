# Chat History - ace-run

- **TIMESTAMP:** 2026-07-11 19:03:45 EDT
- **MODEL:** claude/opus
- **AGENT:** research.8.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260711_185728.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research #gh:gh_sase-org__sase This codebase contains a lot of backward compatibility logic that no longer serves any use because there are no projects that still need that logic. We need agents to always introduce backward compatibility logic because we don't want once this project becomes popular but we need a process or policy to govern how/when we should deprecate this logic. And most importantly we need a way to track and ensure that this logic always gets removed. Can you do some research to help me think about the different ways that we could implement this? End your analysis with a recommended solution. Once you're done writing your research file express your answer by setting a few sase variables. Write this research to a new markdown file under the $(sase sdd path research)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding the existing conventions in the research directory and the SASE tooling that could support such a policy.

Let me understand the research file conventions and the SASE tooling that could support such a policy.

This gives me the format and depth expected. Now let me survey the actual SASE tooling that could enforce such a policy, and how backcompat/deprecation logic currently appears in the codebase.

The problem is clear: 235 files carry ad-hoc backcompat/legacy markers with no structured metadata, no removal date, no owner, and wildly inconsistent styles. Now let me understand the enforcement/tracking tooling SASE already has. Let me read the relevant long-term memory and survey the lint/CI/beads machinery in parallel.

Let me read the pyvision memory properly and locate the lint/CI machinery.

Excellent — pyvision already has an `--epic-symbol <bead_id>(<symbol>)` mechanism that's *self-cleaning* (it forces you to drop the entry when the bead closes). That's a direct in-house precedent. Let me read the Justfile lint invocation and understand beads + existing audit workflows.

The architecture is coming into focus. `pyvision` runs with `BD_COMMAND=tools/sase_bead`, meaning the linter already queries the bead store to validate its self-cleaning `--epic-symbol` whitelist. That's the exact pattern the user needs. Let me confirm bead metadata capabilities and the audit-workflow precedent.

I have enough grounding. The key finding: SASE already has the exact primitive the user needs — pyvision's `--epic-symbol <bead_id>(<symbol>)` is a self-cleaning, bead-keyed whitelist enforced in `just check`, run with `BD_COMMAND=tools/sase_bead` so the linter queries bead status directly. That's the pattern to generalize. Let me write the research doc.

The research file is written. Now let me express the answer by setting SASE output variables.

All six output variables were set (the `set` succeeded — it echoed `keys: core_mechanism, options_considered, recommendation, recommended_option, research_file, status`; the only error was my `sase var list` readback, which isn't a subcommand). No `just check` needed — the only change is a new markdown file under `sdd/research/`, which is exempt.

## Summary

I researched how to govern the lifecycle of backward-compatibility logic and wrote it to:

`.sase/sdd/research/202607/backcompat_lifecycle_governance_20260711.md`

**What I found grounding the problem:** `deprecat|backcompat|legacy` markers touch **235 files** in `src/`, in ~a dozen mutually-inconsistent styles, none machine-parseable and none carrying a removal trigger, owner, or introduction version. That's exactly why nothing ever gets removed — the death condition lives nowhere.

**The key insight:** SASE already has the primitive you need. `pyvision --epic-symbol <bead_id>(<symbol>)` is a *self-cleaning, bead-keyed allowlist* enforced in `just check`, run with `BD_COMMAND=tools/sase_bead` — so a linter in this repo already queries the bead store to decide whether temporary code is still legitimate, and forces you to drop the entry when the bead closes. The recommendation generalizes that proven loop to backcompat.

**Six options evaluated** (policy-only, in-code markers+linter, registry file, bead-backed, version-windows, scheduled agentic sweep), scored on removal-guarantee, friction, state-location, whether they govern *introduction*, and agent-execution.

**Recommended solution — a layered system** where each layer is teeth / clock / work-item / driver / rule:
1. **Policy** — two rules: only add a shim when a real consumer exists (a declared *compatibility baseline*), and *no shim merges without a removal trigger + tracking id* (a "birth certificate").
2. **One structured marker** — `# BACKCOMPAT[bd-1234]: since=v0.4.0 remove_by=v0.6.0 reason="…"` (+ a decorator form), replacing all 235 ad-hoc styles.
3. **A `_lint-backcompat` stage in `just check`** (the teeth) — hard-fails on malformed/untracked/expired markers, bidirectionally cross-checked against bead status, exactly like `--epic-symbol`.
4. **Beads** as the schedulable, agent-executable removal work item (`sase bead work`), with a note that a *lightweight removal bead type* is the one net-new build cost since today's beads are plan-shaped.
5. **Version anchor** (semver N-2) to make `remove_by` mechanical once releases exist.
6. **A scheduled sweep agent** that works removals proactively so the CI time-bomb never lands on an unrelated author's PR.

Plus **immediate backlog remediation**: since no current consumer needs the existing logic, declare the baseline at today's version and delete the dead shims now rather than aging them out.

The doc also covers risks/mitigations (time-bomb blast radius, agent compliance via a `#backcompat` skill, bead-model fit, over-deletion).

**Variables set:** `research_file`, `recommendation`, `core_mechanism`, `options_considered`, `recommended_option`, `status=ok`.
