# Chat History - ace-run (1a5--plan)

- **TIMESTAMP:** 2026-11-08 13:37:28 EST
- **MODEL:** claude/opus
- **AGENT:** 1a5--plan

**Plan:** /home/bryan/.sase/plans/202611/research_sidecar_first_init.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/research_sidecar_first_init.md`

> # Plan: Create newly declared sidecars (research) on the first `sase repo init` run
> ## Problem
> Adding a project from the Admin Center **Projects** tab (New Project wizard) runs the
> durable `sase project add …`, whose result hands off to `sase init -p <key>`: the wizard
> runs `--check --json`, shows the init preview, and the terminal valve (`t`) runs the
> interactive `sase init -p <key>`. For the new `dev` project, that run created the plans,
> beads, agents, and attachments-private sidecar repos but **not** the research sidecar.
> The user had to run `sase init` a second time to create it.
> ## Root cause (verified)
> `sase repo init` (also the `repo` step of `sase init`) writes the standard sidecar

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase It doesn't look like the `dev` sase project's research sidecar repo was
initialized when I added this project from the "Projects" tab of the "SASE Admin Center"
panel. Can you help me fix this so I don't need to manually run `sase init` for new
projects like this again in the future?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

Exploring the New Project wizard's init flow to see why the research sidecar wasn't initialized.

Inspecting the `dev` project's on-disk state to see which sidecars exist.

Tracing what the TUI's `sase init --yes` handoff does when a sidecar's GitHub repo doesn't exist yet.

Checking when each `dev--*` sidecar repo was created on GitHub to pin down which code path skipped research.

Fix direction is clear. Looking at existing tests for `run_repo_init`/`plan_repo_init` so the plan can name the right test files and seams.

Checking how the planner phrases sidecar-creation actions and sets `requires_tty`, so the plan's acceptance criteria can be precise.

Two other projects (`tailnet`, `sase-spotify`) also declare research but never materialized it, likely from the same bug. Quick docs check, then I'll write the plan.

Root cause is pinned down and reproduced. Writing the plan now.

Validation passed. Submitting the plan.

I found the bug, reproduced it, and proposed a fix plan. Nothing is changed yet; the plan is waiting for your review. It's `sase_plan_research_sidecar_first_init.md`, a medium-size tale.

## What went wrong

The Projects tab didn't skip anything itself. The bug is in the `sase init` step it hands off to (the same step `sase repo init` runs):

1. Before writing anything, `sase init` works out which sidecars the project has. That lookup is cached for the life of the process.
2. It then writes the sidecar declarations into `sase/sase.yml`, including `repos.sidecar.custom.research`, but never clears that cache.
3. When it goes on to create the sidecar repos, it reads the stale list. That list only has the roles SASE adds by default: plans, beads, agents and the attachments repos. Research is the one standard sidecar that exists *only* through the `sase.yml` line it just wrote, so it was never checked, prompted for or created. A second `sase init` is a new process that reads the file fresh, which is why your manual run worked.

The `dev` repo's timeline matches: `dev--plans`, `--beads`, `--agents` and `--attachments-private` were created between 15:39:32 and 15:39:45Z. The `sase.yml` commit declaring research landed at 15:39:57Z, and `dev--research` only appeared at 18:15Z from your manual run. I also reproduced it in a scratch repo: right after the write, the sidecar list has no `research`; after clearing the cache it does.

There's a related gap: the init preview the Projects tab shows also works from the old config, so it never listed "create research sidecar". If research were the only missing sidecar, the preview wouldn't even say a terminal is needed.

## The plan

- **Clear the cache after the `sase.yml` write**, following the existing pattern in `sdd/_store_records.py`. This alone means one run creates research too. It applies to the wizard's terminal step, `sase project add`, bare `sase init` and `sase repo init`.
- **Base the preview on what the run is about to declare**, so `--check` and the Projects tab preview list the research repo creation and say a terminal is needed.
- **Tests:**
  - A regression test that fails on today's code.
  - Preview tests for a brand-new project and for an older project that has the other sidecars but not research.
  - A test for the config-loading change.
  - A mechanical update to the 25 existing test stand-ins for the sidecar lookup, so they accept the new optional argument.
- **Docs:** a short note in `docs/reference/agents/initialization.md`, then the `just check` verification.

Creating a GitHub repo still needs your interactive `y`; the plan doesn't change that.

## Other projects with the same gap

`tailnet` and `sase-spotify` both declare research in `sase/sase.yml` but never created it, probably from the same bug. The fix won't create remote repos on its own, so run `sase init -p <key>` for each (or use Projects tab init and choose the terminal option). `dev` is already fine.
