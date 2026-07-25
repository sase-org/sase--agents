# Chat History - ace-run (sase-6n.w1--plan)

- **TIMESTAMP:** 2026-07-18 06:08:23 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-6n.w1--plan

**Plan:** /home/bryan/.sase/plans/202607/big_epic_lander.md


## Prompt

#gh:gh_sase-org__sase Can you help me add a new built-in `@big_epic_lander` model alias that is used for the epic lander agent when an epic plan file has `<N>` or more phases? `<N>` should default to `5`, but the user should be able to override this via a new sase configuration field (i.e. `5` should be the default value for this new field). The `@big_epic_lander` model alias should be configured to use `@epic_lander` as its default value. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %w:sase-6n

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/big_epic_lander.md`

> # Plan: Threshold-aware big epic lander routing
> ## Context and design decisions
> Approved epic plan files become an epic bead plus one phase bead per authored phase, and the Rust core builds the
> deterministic work plan consumed by the Python multi-prompt renderer. Today an epic without a top-level `model` always
> emits `%model:@epic_lander` for its land agent. Introduce `@big_epic_lander` as another built-in role alias and select
> it only when the epic's total authored phase count is greater than or equal to the configured threshold.
> The configuration contract will be `bead.big_epic_phase_threshold`, an integer with a shipped default of `5` and a
> minimum of `1`. Runtime access should defensively fall back to `5` for missing or malformed values, including booleans.
> The alias itself will implicitly fall back to `@epic_lander`, not directly to `@default`. Consequently, users who do
> nothing see the same concrete model as before, an existing `epic_lander` override continues to affect both sizes, and

*See full plan file for details.*

