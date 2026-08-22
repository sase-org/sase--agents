# Chat History - ace-run (research.0x.cld)

- **TIMESTAMP:** 2026-08-22 16:53:16 UTC
- **MODEL:** grok/grok-4.6
- **AGENT:** research.0x.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260822_162922.md`

## Prompt

%id(cld, clan=research.0x) %m:@research_b  #gh:gh_sase-org__sase I would like to implement a new `%if` directive that allows
me to specify (in the prompt) that agents should only only launch if a particular
condition, specified by a new code block argument type, holds.

- See the standalone_proc_launch_units.md file in the research sidecar repo for context and make sure this
  research either aligns with that research or that you reconcile any differences.
- This new directive will be particularly useful in xprompt swarms where we may want
  certain proc/agent shells to run conditionally.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by loading the research, repo, and xprompt skills so the work stays aligned with SASE conventions and the existing research sidecar.

Next I’ll open the research sidecar and pull xprompt memory plus glossary terms so the `%if` design sits on the existing launch-unit work.

The glossary call needed separate terms; I’ll retry that, then locate the launch-units research and nearby 202608 write-ups.

I’ll read the launch-units report as an artifact, then pull nearby research and the current xprompt directive implementation.

I’ll map the current directive parser, input types, and workflow `if` so the `%if` proposal can sit on real launch-pipeline constraints.

I have enough of the launch pipeline, wait semantics, and `%proc` research to write the `%if` recommendation and reconcile it with the existing launch-unit work.

The rebase conflict is in the standalone-proc link index; I’ll merge both researchers’ rows, then resume the stitch.

**Recommended solution:** make `%if` a launch-unit admission predicate that shares the `code` argument type already specified for `%proc`, not a third kind of `if` and not a `%wait` variant.

The full write-up is [`202608/xprompt_if_directive.md`](sase/repos/research/202608/xprompt_if_directive.md) in the research sidecar (`@research:202608/xprompt_if_directive.md`).

## What to build

A mixed xprompt swarm should still expand into typed launch units (`Agent` or `Proc`), as in the [stand-alone proc launch-units report](sase/repos/research/202608/standalone_proc_launch_units/standalone_proc_launch_units.md). Each unit may carry at most one `%if` whose argument is a structured `CodeValue` (`source`, `language`, `info_string`).

Admission order:

1. Reserve a stable identity so `%wait` has a target.
2. Wait (no LLM slot, no workspace lease).
3. Evaluate the condition.
4. True → claim a workspace / admit the runner / spawn the proc.
5. False → publish `outcome: "skipped"` with `skip_reason: "if"` and never run the payload.

Suggested surface:

````text
%if("test -f Cargo.toml")
%if(python="from pathlib import Path; Path('Cargo.toml').exists()")

%wait:review
%if::
```python
from pathlib import Path
from sase.launch_conditions import waited

waited["review"].succeeded and Path(waited["review"].workspace, "needs_fix.md").exists()
```
%id:fix
Fix the issues found by review.
````

Unlabelled fences stay Bash for both `%if` and `%proc`. Python conditions should treat a last expression as the boolean (so `Path(...).exists()` works) and otherwise use the process exit code. Evaluation errors fail the unit; they must not look like a quiet skip.

## How this lines up with existing `if`s

| Mechanism | Question it answers |
| --- | --- |
| Jinja `{% if %}` in an xprompt body | Known at expansion time from invocation args; the segment never becomes a unit |
| YAML workflow `if:` | Jinja over step context inside one workflow run |
| `%wait` | Block until a predecessor is terminal (today: success-like completion) |
| `%if` | After waits, one-shot: should this unit run at all? |

The proc report already said `%wait` should mean “terminal” and that requiring success is a separate condition. `%if` is that condition.

## What not to do

- Do not reuse YAML Jinja `if:` in markdown swarms (no step context; fail-open skip hides broken predicates).
- Do not make `%if` poll until true (that is `%wait`).
- Do not skip without allocating identity (`%wait:fix` would hang).
- Do not reuse `noop` for skip (`noop` means the workflow ran and had nothing to do).
- Do not add `%if` to the known-directive list without capturing the following fence; the same trap the proc report called out for `%proc` would either leak code into the model prompt or drop the predicate and still launch.

## Shared primitive

Land one complete `type: code` slice first (parser, Rust frontmatter/LSP contract, type-directed `#xprompt::` fence binding, previews). `%proc` and `%if` are two consumers of that type. `%if` is a modifier on a unit; `%proc` classifies the unit. Both fences in one unit are valid.

Until wait-on-terminal lands, add `skipped` to the wait-success set so dependents unblock. Authors who need “only if it actually ran” add a second `%if` on `waited["x"].succeeded`.

The report also covers the condition runtime API (`waited` / `inputs`), feature-flag rollout, Jinja-inside-fence pitfalls, and a delivery sequence that sits inside the `%proc` work rather than beside it as a second fence dialect.
