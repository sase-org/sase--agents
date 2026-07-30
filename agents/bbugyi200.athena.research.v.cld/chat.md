# Chat History - ace-run (research.v.cld)

- **TIMESTAMP:** 2026-07-30 16:32:59 EDT
- **MODEL:** claude/opus
- **AGENT:** research.v.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260730_161933.md`

## Prompt

%id(cld, clan=research.v) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I want to allow users to customize sase finalizers
via a new `%final` directive. Can you do some research to help me decide the
best way to implement this?

- First of all, we should generalize our current finalizer so users can define
  their own.
- Users should be able to disable the default finalier (and any additional
  default finalizers we add later).
- We should support multiple finalizers (we already have one builtin finalizer
  that requires the agent to commit changes).
- We should make each finalizer configurable (a prompt used for the finalizer
  followed by a custom script that is run and some extra configuration, like
  retry attempts, trigger conditions, other finalizers that this one depends on,
  etc...) and provide plugin support (i.e. allow sase plugins to define their
  own finalizers in sase plugin repos).
- We should expect all agents to set sase variables for the finalizer to read
  (see the sase-be epic bead for some related work that sets us up for this).

End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding the current finalizer implementation and related systems.

Research complete. Writing the report.

Research written to `sase/repos/research/202607/custom_finalizers_final_directive.md`.

## What I found

**Today's finalizer isn't a system — it's one function.** `run_commit_finalizer` (`commit_finalizer.py:128`) is called from exactly one place (`_invoke.py:308`), with commit semantics baked into every layer: trigger, prompt, retry loop, and failure handling. Config is two keys (`commit.finalizer.enabled/max_passes`).

Three findings that shaped the recommendation:

1. **The `sase-be` epic is already building the general contract.** Its plan turns commits into "agent records intent as sase variables → finalizer executes deterministically via a script." That *is* the generalized finalizer shape; generalizing is mostly naming it and letting other things plug in. It also means this work must sequence **after** `sase-be` phase 5 — they rewrite the same files.

2. **A `finalizers:` YAML *list* would be a bug.** The `user` config layer declares `list_strategy="replace"` (`layers.py:195`), so one custom finalizer in `~/.config/sase/sase.yml` would silently delete the builtin *and* every plugin contribution. A keyed map deep-merges — and gives you "disable the default" for free. `axe.lumberjacks.*.chops` already supports both forms for exactly this reason.

3. **Almost none of this needs new machinery.** Axe chops already have `enabled` / `timeout` / `env` / `inhibit_if` guards / `trigger` providers, script discovery, a `--context` JSON protocol, a result-document SDK, and a Rust decision engine. Plugins already contribute config layers (`sase_config` entry points) and console scripts.

## Recommendation

A keyed `finalizers:` config registry whose entries are **trigger → bounded prompt passes → script → re-evaluate**, with `%final` as a *selection and bounded-override* directive — never a definition site.

The one call I'd flag for your judgment: **`%final` must not accept `script=` or `env=`.** Prompts are produced by other agents, xprompt bodies, and swarm segments; a directive that injects a shell command into a privileged post-completion phase is arbitrary code execution with the agent's credentials. Overrides stay a closed set (`enabled`, `max_passes`, `on_failure`, `timeout`). That constraint is what makes the rest of the design safe, so if you want inline definitions the security model needs rethinking first.

Other notable calls: per-launch selections travel in `agent_meta.json` (not env — survives re-exec, no nested-launch leakage); one reserved-namespace rule (`<name>_*`) replaces the growing `STOP`/`commit_*` special cases; a `vars_absent` trigger provider is what makes "expect all agents to set sase variables" enforceable rather than aspirational.

Also surfaced a subtlety worth deciding early: the current finalizer runs after **every** provider turn, not once per agent — mentors, CRS, and fix hooks all route through `invoke_agent`. The doc proposes an explicit `scope: turn|agent` field rather than inheriting that ambiguity.

The doc ends with a 6-phase sequence; phase 1 is the whole bet — express today's commit finalizer as an ordinary registry entry with zero special cases, or the model is wrong.

I made these changes in this session — the research report. Committing it now.

Committed.

**`b37ffc2 docs(research): research customizable finalizers via %final`** — research repo is clean and in sync with `origin/main` (no ahead/behind markers).

Notes:
- The finalizer listed the research repo twice (once as linked repo, once as SDD sidecar), but both entries resolve to the same path `sase/repos/research`, so one commit covered both.
- `sase commit` reported one non-fatal warning: agent-hood publication was queued because the agents sync lock was busy. It retries automatically; the commit and push themselves succeeded.
- No changes were made in the sase workspace checkout itself, so `just check` doesn't apply here — the only file written this session was the markdown research report.
