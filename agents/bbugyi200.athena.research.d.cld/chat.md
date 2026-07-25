# Chat History - ace-run

- **TIMESTAMP:** 2026-07-16 14:06:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.d.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260716_134144.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research #gh:gh_sase-org__sase I want to unify agent families so users can more
easily conceptualize them as just a different way of grouping agents on the
agents tab. Can you do some research to help me understand what conceptual
barriers I'm going to need to design around / implement solutions for in order
to make this happen? Keep in mind that part of the goal is to migrate as much
functionality from xprompt workflows (YAML files) as possible to xprompt swarms
(markdown files), which I would ideally like to be able to use to define
workflows that are just as robust as those that we currently define using YAML
xprompt workflows. For example:

- I know that I will need to allow agents in the same family to run in parallel.
  I plan on adding support for a new `wait=<bool>` keyword argument to the
  `%name` directive for this.
- I know that Python and Bash xprompt workflow steps will need to be allowed to
  be root agent rows in order to support, for example, defining an xprompt swarm
  that requires a command to be run that updates the software you are working on
  (e.g. sase) before one or more agents (e.g. to verify the work) can run.
  Moreover, this is just needed to make them definable in xprompt swarms I
  think, which would be preferable to xprompt workflows.

What are some of the requirements I have not thought of? Are there any design
decisions that you would absolutely need from me before working implementing
something like this? End your analysis with a set of <=7 of the highest-value
questions you can think to ask to help push this initiative forward. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by understanding the current architecture — how agent families, agent hoods, xprompt swarms, and xprompt workflows are modeled today.

The research directory exists. Let me fan out parallel exploration across the key subsystems — agent families, swarms, workflows, and the ACE agents tab.

Three strong reports in. The central finding is already surprising: a family today is **not** N launched agents — it's sequential iterations of one `while True` loop in a single process. Let me dig into the consequences before writing.

I have a rich picture. Let me check the research directory conventions and probe the two specific mechanisms the user proposed extending.

I have what I need. The picture is clearer — and more surprising — than the framing in your prompt suggests. Let me write it up.

Written to `sase/repos/research/202607/unified_agent_families_swarm_migration.md`.

## The headline

**An agent family isn't a group of agents today — it's one OS process.** `foo--plan`, `foo--q`, `foo--code` are sequential iterations of a single `while True` loop (`src/sase/axe/run_agent_exec.py:312-342`), each writing an artifacts directory that ACE renders as a row. The grouping you see is a rendering artifact of a linked list, not a scheduling structure. `spawn_custom_role_followup` spawns nothing — it mutates a scalar and lets the loop go around again.

So the initiative isn't "add a flag so members can run in parallel." It's **inverting the model from _one process → N rows_ into _N processes → one group_**. Parallelism falls out of that; it isn't the change itself.

## On your two stated plans

**`%name(wait=<bool>)` — right requirement, I think wrong mechanism.** What forces sequencing today isn't a missing flag. When a parent is running, the launcher forces `deferred_workspace=True` (`_family_attach_launch.py:64-74`) — the member waits *because it shares a workspace*. So `wait=false` doesn't grant parallelism, it exposes the absence of it, and the first symptom will be `run_sase_hg_clean` eating a sibling's uncommitted work. It also inverts the swarm default (segments are parallel-by-default; `%wait` opts *in*), and gives your grouping directive scheduling side effects — the exact confusion you're trying to remove. The real prerequisite is that **family members aren't `%wait`-referenceable at all** (`agent_completion.py:254` excludes every child row), which collides with `--` being rejected in user-typed names.

**Python/bash root rows — correct, and about 3× bigger than the two filters.** `appears_as_agent` is unreachable by construction for a script step; script steps have no workspace, no `cl_name`, no `agent_meta.json`, no name. And the sharp one: `is_root_user_agent_record` is *simultaneously* the ACE listing filter and the runner-slot admission counter, so making script roots listable naively would throttle real agents behind `echo`.

## Things you didn't mention that will bite

The one I'd most want you to see: **failure doesn't propagate through `%wait`.** A failed segment never satisfies a dependency, so dependents wait *forever*. YAML has skip-on-failure, `on_error`, and `finally`. "As robust as YAML" is unreachable while a robust swarm degrades into a hung one.

Also a trap laid directly on the obvious implementation: `release_workspace` has no PID predicate — it removes *every* line matching `(workspace_num, workflow, cl_name)`. It's masked today only because `workflow_name` embeds a per-slot timestamp. Model "one family = one workflow", and the first member to finish silently releases all its siblings' claims.

And `prompt_part` wrap-around (`tags: vcs|rollover|commit` — how `#git:foo #commit do X` works) has no swarm equivalent, because a swarm segment *is* a whole agent with nowhere to inject text into a sibling.

## Live bugs found along the way

Independent of this work: **only the first custom role at a placement ever runs** — `_select_custom_role_after` returns on first match while `active_roles_after` gathers all of them, so installing a `tester` and a `linter` both at `after: code` silently drops one. **`on_done` is dead** — validated, stored, listed, read by nothing; `on_failure`'s two values are also behaviorally identical. And the Rust splitter is backtick-only while the Python classifier honors `~~~`, so a `---` inside a tilde fence tears it in half and launches a garbage agent.

The doc ends with the seven questions — the load-bearing one being #1: does "family" keep meaning *phases of one CL*, or become *a group of peers*? Every axis wants the opposite answer for each, which is why one flag can't straddle them. My suggestion in there is that **hoods** (`.`) may already be the "just a grouping" concept you're reaching for — display-only, parallel-safe, zero runtime baggage.

The research file is mine from this session, so I'll commit it. Let me check the repository state first.

One untracked file, and both finalizer entries point at the same checkout — so a single commit covers both. Invoking the commit skill now.

Untracked research doc only, and history uses the `docs(research):` convention. Writing the commit message now.

The commit failed, but not because of anything in the message: the globally-installed `sase_core_rs` wheel is stale and doesn't expose the `update_commit_footer` binding. Let me investigate before running the suggested repair, since that touches a shared tool venv other agents may be using.

Confirmed stale in the shared tool venv. Let me check the version situation and whether my workspace venv has a good copy.

Both venvs have `sase-core-rs` **0.5.0**, and neither exposes the binding — so this isn't a stale-wheel-in-one-venv problem, and the suggested force-reinstall would just reinstall the same version. Let me confirm what the wheel actually exposes and whether a newer one exists.

Now it gets interesting — `dir()` **lists** `update_commit_footer`, but `getattr` raises `AttributeError`. That points at a lazy-loading wrapper whose native extension is out of sync, not a missing package. Let me read the wrapper.

`dir()` shows it in the package namespace, which contradicts my earlier `hasattr` check — and the `.so` is timestamped today at 14:05. Something may have changed underneath me. Let me re-test directly.

That resolves it. The **tool venv** — which `/home/bryan/.local/bin/sase` actually uses — now exposes the binding (its `.so` was rebuilt at 14:05 today, evidently by a concurrent repair between my two checks). The workspace venv is still stale, but it isn't in the commit path. Retrying with the same message file.

Commit succeeded. Verifying the tree is clean and pushed, as the skill requires.

Clean and pushed. But a commit I didn't make — `99c5c1f "docs: research unifying agent families and swarms"` — appeared beneath mine; it wasn't in the log when I started (HEAD was `eeb18c4`). Let me check whether my commit duplicated it.

Committed. My research doc is on `main` and pushed — working tree clean.

**`e583274 docs(research): analyze unifying agent families for swarm migration`** — adds `202607/unified_agent_families_swarm_migration.md` (563 lines). Both finalizer entries (the `research` linked repo and the `sase-org/sase--research` sidecar) pointed at the same checkout, so the one commit covered both. I used the `docs(research):` scope the repo's history already follows, and skipped `just check` since the change is a markdown file in the research sidecar — an explicit exception in CLAUDE.md.

Two things worth your attention:

**A concurrent agent wrote the same research.** When I started, HEAD was `eeb18c4`; my commit's parent is now `99c5c1f docs: research unifying agent families and swarms`, which landed mid-session and added `202607/unifying_agent_families_with_xprompt_swarms.md` (539 lines). So `202607/` now holds two independent reports on your question, both timestamped 14:06:

| File | Lines | Author |
|---|---|---|
| `unified_agent_families_swarm_migration.md` | 563 | mine, this session |
| `unifying_agent_families_with_xprompt_swarms.md` | 539 | concurrent agent |

My commit isn't a duplicate in the git sense — it added a distinct file, and the diff against its parent is the full 563 lines. But you likely have redundant coverage, and possibly two different sets of conclusions on the same design question. I left the other file alone since I didn't create it. Worth a look before you act on either; if they disagree anywhere, that disagreement is itself informative, and consolidating them into one doc is probably the right follow-up.

**The first commit attempt failed on a real environment fault**, which resolved itself. `sase commit` crashed because `sase_core_rs` didn't expose the `update_commit_footer` binding. The error suggested a force-reinstall, but I checked before running it — both venvs had the same version `0.5.0`, so the reinstall would have been a no-op, and it would have churned a tool venv other agents are actively using. On re-inspection the tool venv's `.so` had been rebuilt at 14:05 and exposed the binding, so I simply retried and it went through. Almost certainly the same concurrent agent repairing it.

One residual: **your workspace venv at `sase_15/.venv` still has the stale `sase_core_rs`** — `getattr(m, 'update_commit_footer')` raises `AttributeError` there, while the tool venv is fine. It didn't affect this commit (the `sase` binary uses the tool venv), but it will bite anything running `just check` or tests out of that workspace. `just install` in the workspace should clear it — I didn't run it, as it's outside the scope of what you asked and wasn't needed here.
