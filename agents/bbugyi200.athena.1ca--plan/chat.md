# Chat History - ace-run (1ca--plan)

- **TIMESTAMP:** 2026-11-13 17:52:24 EST
- **MODEL:** claude/opus
- **AGENT:** 1ca--plan

**Plan:** /home/bryan/.sase/plans/202611/fix_gh_owner_repo_refs.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/fix_gh_owner_repo_refs.md`

> # Fix `#gh:<owner>/<repo>` refs rejected by the hardened `word` input type
> ## Symptom
> Every agent launched by the `refresh_docs` routine fails before it starts, for example
> `chop.refresh_docs.bob-cli.<run>.1` and `chop.refresh_docs.sase.<run>.1`:
> ```
> Step 'main' failed: WorkflowExecutionError: Workflow '#gh' argument error:
> Argument 'gh_ref' expects word (no spaces) matching [A-Za-z0-9._-]+, got 'bobs-org/bob-cli'
> ```
> Each run's `.2` polish agent waits on the failed `.1` agent, so the TUI shows it as
> `WAITING ✗1` indefinitely. The same error hits any prompt that starts with

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Can you help me diagnose the root cause of this issue and fix it? See the
~/tmp/screenshots/20261113_173252.png screenshot for context. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

I'm tracing the failure: the `refresh_docs` chop starts its agents with `#gh:bobs-org/bob-cli`, and the `#gh` macro's `gh_ref` argument rejects the `/`. Next I'll find where that prefix gets built.

The `sase` refresh_docs agent failed the same way on `#gh:sase-org/sase`, so this hits every GitHub project. Opening the `sase-github` repo to find where `#gh` and its `gh_ref` argument are defined.

The `#gh` macro (in the `sase-github` plugin) declares `gh_ref` as `type: word`. Next I'll check how `word` is validated in sase and whether that rule changed recently.

The root cause looks recent: commit `22e1ef1249` (sase-1sb.4, "shell-arg-hardening") narrowed `word` to `[A-Za-z0-9._-]+`, which rules out `/`. Reading that commit and the rest of the sase-1sb epic.

Output-schema `word` still only rejects whitespace, so only input binding is affected. Checking the Rust core for a parallel `word` rule, and how `sase-github` is installed.

The sase dev venv can import `sase_github`. Next I'll reproduce the failure directly by binding `owner/repo` against the real `gh.yml`, then confirm `line` fixes it.

Validation flagged missing `title`/`goal` and over-length decision text. Fixing those now.

Validation passes. Submitting the plan.

I found the cause and reproduced it. The fix plan passed validation and is waiting for your review; no repo files have been changed yet.

## What broke

The `refresh_docs` routine starts each agent's prompt with `#gh:<owner>/<repo>`, built from the project list in `src/sase/axe/_config_targets.py`. The `#gh` macro lives in the `sase-github` plugin, and its `gh_ref` argument is declared as `type: word`.

Commit `22e1ef1249` (part of the sase-1sb security epic) narrowed `word` to letters, digits, `.`, `_` and `-` only, so any `/` is now rejected. That commit already moved sase's own `#git` macro from `word` to `line` for exactly this reason. The upgrade guide in `docs/reference/upgrading/macros.md` also says to use `line` for refs that contain `/`. But the epic only checked macros shipped inside sase, so the `#gh` macro in the plugin was missed.

**Evidence:**
- **Timeline:** the workflow logs show `#gh:owner/repo` prompts succeeding through Nov 11. Every one has failed since Nov 13, after that commit was installed.
- **Same failure elsewhere:** the `sase` refresh agents (`#gh:sase-org/sase`) and the `bbugyi200/cash` launches fail with the same error.
- **Why normal launches still work:** the TUI writes `#gh:gh_sase-org__sase`, which has no `/`.
- **Reproduction:** binding `bobs-org/bob-cli` or `ghe.example.test/acme/widget` against the real `gh.yml` raises your exact error. Changing `gh_ref` to `line` makes both work.
- **Polish agents:** the `.2` agents show `WAITING ✗1` only because they wait on the failed `.1` agents.

## The plan (one agent, size small)

1. **The fix:** in `sase-github`'s `gh.yml`, change `gh_ref` from `word` to `line`, the same change `#git` got. The value only reaches Python steps through `| tojson`, so this doesn't reopen the shell-injection hole the epic closed.
2. **Keep the safety check:** now that `/` is allowed again, values like `../x` could reach the code that turns `owner/repo` into a folder under `~/projects/github/`. The plan rejects owner or repo names outside GitHub's allowed characters, and `.`/`..`, at that point.
3. **Regression tests in `sase-github`:**
   - Bind the real `gh.yml` with `owner/repo`, `host/owner/repo`, a project name, and a Patch name.
   - Confirm that unsafe repo paths are refused before any clone.

   CI runs these against sase master, so it will catch this if it happens again.
4. **Decision for you, `stale_rule_text`:** by default the agent also fixes the outdated "single word, no whitespace" wording in `docs/reference/workflows.md` and in sase-core's type list, which `sase macro types` prints. That wording is how this kind of mistake gets missed. If you'd rather defer it, the agent files a task instead.

I chose not to change the routine to emit the project-name form. That would only fix this one caller, while `#gh:owner/repo` typed by hand or inserted by the TUI's own completion would stay broken.

The plan also tells the agent to file a separate task for one more gap: gate form fields still accept `word` values with `/` that the macro check now rejects, even though the code says the two must agree.

**After it lands:** your local `sase-github` install picks up the change once its main checkout is updated. Then retry the failed `chop.refresh_docs.*.1` agents, or let the next scheduled run replace them, and the waiting `.2` agents will continue.
