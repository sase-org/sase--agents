# Chat History - ace-run (17q--plan)

- **TIMESTAMP:** 2026-11-03 15:48:21 EST
- **MODEL:** claude/opus
- **AGENT:** 17q--plan

**Plan:** /home/bryan/.sase/plans/202611/research_swarm_tables_to_lists.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/research_swarm_tables_to_lists.md`

> # Add a `tables_to_lists` input to `#research_swarm`
> ## Goal
> Add a bool input, `tables_to_lists` (default `false`), to the `#research_swarm` macro.
> It controls whether the linker agent is told to convert every table in the lead's report
> into a list. With the default, published reports keep real Markdown tables so the user
> can judge how `bob ref create` renders them in the PDF. Passing `tables_to_lists=true`
> must restore today's linker instructions **byte-for-byte**. The user expects to remove
> the conversion entirely later, so each gate must be easy to delete in one step.
> ## Where the code lives
> - All changes are in the linked repo **`sase-research-artifacts`**. Open it with

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Can you help me add a new input to the `#research_swarm` macro that controls
whether we instruct the linker agent to convert tables to lists or not?

- Let's give this input a default value of `false`.
- My goal is to remove this functionality completely, but I'm not yet certain that I am
  okay with the way markdown tables are rendered once the markdown has been converted to
  a PDF (by the `bob ref create` command), so I want an easy way to re-enable it.
- Before submitting your plan, set some sase variables to express what you think of this
  plan (think hard about whether is the right move or not).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

I'm locating where `#research_swarm` is defined. It's in the global SASE config (`~/.config/sase/sase.yml`), which comes from the chezmoi repo, so I'll open it through `sase repo` next.

I've found the test that pins the table rule. Next I'm checking the test helpers and docs that list the macro's inputs, so the plan covers every place a new input has to appear.

I'm almost done researching. I'm checking whether any SASE memory notes or other docs describe the linker's table rule, since those would need updating too.

Research is done. I'm writing the plan now, then I'll record my assessment as SASE variables, validate the plan, and propose it.

The plan's claims check out: by default the macro produces 3 segments, and the venv note is right. Next I'm recording my assessment as SASE variables.

Variables are set. Now validating the plan.

The plan passes validation with 0 warnings. Proposing it now.

I've proposed a plan for a `tables_to_lists` input on `#research_swarm`, defaulting to `false`, and it's waiting for your review. Nothing has been edited yet.

**Where the change goes.** The macro lives in the `sase-research-artifacts` repo, not in `sase` itself, so the implementing agent will work there.

**What the plan does:**
- **The input:** it goes right after `linker_model`, as a bool defaulting to `false`. It only changes what the linker is told and never launches the linker on its own, like `linker_model` and `audio_edition`.
- **Gating:** the table-to-list rule touches the linker's instructions in five places, and each gets a switch:
  - the "record its cells" note when listing what must survive;
  - the full "No tables." bullet and its sub-rules;
  - the pandoc check that no table survives;
  - two diagram-placement sentences that refer to the rule.

  The check that every table cell survives stays on in both states.
- **Re-enabling:** with `tables_to_lists=true`, the linker gets exactly today's instructions, character for character. The implementer will save today's rendered linker instructions before editing and diff against them afterwards.
- **Removing it later:** you delete the `true` branches and the input, and nothing else.
- **Tests and docs:** the input-signature test and the existing table test get updated, with both states covered. `docs/macros.md` and `README.md` get updated too.

**One decision for you, `keep_tables_rule`.** It sets what the linker is told when the input is off:
- **`explicit` (default):** add a short "Keep tables as tables" rule. Otherwise a linker that is restructuring the report may still turn some tables into lists, which would spoil your PDF comparison.
- **`silent`:** go back to the wording from before the conversion was added.

**My assessment.** I recorded it in the SASE variables `plan_verdict` (`endorse_with_caveats`), `plan_confidence` (0.8) and `plan_assessment`:
- **Why it's right:**
  - It's easier than reverting the commit that added the conversion. Later diagram work edited the same lines, so a revert would now conflict.
  - You can compare the same topic with and without conversion.
  - A SASE feature flag doesn't fit: flags are only for the `sase` project, and this is a per-run choice in a plugin.
- **You can start evaluating now.** Plain `#research_swarm` runs that don't use the linker, plus `#research` and `#research/more`, already publish real tables.
- **The cramped columns are a renderer problem.** In pandoc, once any table row is longer than 72 characters, column widths come from the dash counts in the header separator line, so `|---|---|` gives equal widths. Fixing that in the renderer used by `bob ref create` would help every report, not just ones the linker publishes.
- **Inputs tend to stick.** This would be the macro's 24th input, so it's worth picking a date to decide whether to delete it.
