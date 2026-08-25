# Chat History - ace-run (research.14.cld)

- **TIMESTAMP:** 2026-08-25 16:56:47 EDT
- **MODEL:** claude/opus
- **AGENT:** research.14.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260825_163920.md`

## Prompt

%id(cld, clan=research.14) %m:@research_b  #gh:gh_sase-org__sase It is very important that users that fully adopt sase and use
it in some of their projects can still use the agent CLIs that sase supports directly
(by using Claude code to do some research or create a quick commit, for example).
Currently, however, there seem to be some instructions that guide agents towards using
tools that only work when a sase agent is defined.

Can you do some research with the goal of helping me understand what it would take to
make sase projects usable by agent CLIs? Ideally, we should support as many of sase's
features as possible when running agent CLI's directly. For features that cannot be
supported, however, it should be clear to the agent (without adding to agent instruction
files too much--ideally, we don't add to agent instruction files at all) what they
should do instead. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current state of how sase generates agent instructions and what tooling assumes a sase agent context.

Now let me open the research sidecar properly before writing.

I have enough evidence. Writing the report now.

The sase repo is clean; only the research sidecar has the new report. Submitting the final declaration.

Research written to `sase/repos/research/202608/bare_agent_cli_compatibility.md`.

## What I found

I probed every SASE command with all 41 `SASE_*` env vars stripped — exactly what a bare `claude` in the primary checkout sees.

**The headline:** of the three always-loaded SASE directives that every adopting project gets, two point at commands that refuse to run — `/sase_memory_read` and `/sase_final`. The memory one is the worst failure in the surface because it's a *prohibition paired with a broken permission*: the agent is told never to open `sase/memory/*.md` directly, and the sanctioned tool errors out. Its only options are to violate the instruction or work without the memory.

The live audit logs quantify it: `repo_opens.jsonl` has 48 `interactive` events because that command degrades; `memory_reads.jsonl` has **0** across 8,728 because it doesn't.

**Most of SASE already works standalone** — repos, beads, plans (author + validate), gates, and the entire commit path via `sase stitch create`. Only nine commands fail, via four unrelated ad-hoc gates. There's no single "am I hosted?" predicate anywhere, so every gated command re-invents the check and re-invents (or forgets) the error text.

The cleanest illustration of the problem: the deployed Claude hooks already guard themselves with `[ -n "$SASE_AGENT" ]`, so plan mode and `AskUserQuestion` are only disabled inside a SASE agent — but the generated instruction text says flatly that both are disabled. **The runtime is already mode-aware and correct; the instruction text is mode-blind and wrong.**

## The recommendation, against your constraint

1. **Make it work** — `sase memory read` and `sase skill use` fail for no architectural reason. `resolve_audit_identity()` already lives in the same module, already falls back to an `interactive` identity, and the `MemoryReadEvent` schema already carries the `agent_source` field. Three one-line changes.
2. **Teach at the point of failure** — for what genuinely can't work, put the fallback in the CLI's error message. Zero context cost until the agent hits it, provider-neutral across all 7 CLIs, and it can't drift because it sits next to the gate it explains. `sase pipe` already does this right.
3. **Procedure in skill bodies, not `AGENTS.md`** — bodies load on demand; a hosted agent that never invokes `/sase_monitor` pays nothing.

Only three features are genuinely unavailable (`var set`, `pipe`, `final`), and `final` is unavailable by an accepted decision rather than oversight.

Two notes on things I'd flag:

- I recommend **against** a hooks-based fix. `docs/llms.md:279` records that SASE deliberately stopped installing Claude Code hooks; that route also covers 1 of 7 providers.
- The one instruction-file edit I do recommend *shortens* the ambiguity rather than adding length: `"…that ends this SASE provider turn"` → `"…that ends a SASE-hosted provider turn"` makes the whole 16-line `/sase_final` section correctly self-scoping for three words. That touches a canonical memory note, so it needs your explicit approval plus `sase memory init` — I did not make it.

There's also a zero-code interim workaround worth knowing: `SASE_AGENT_NAME=$USER claude` unblocks both broken commands today (verified). It's a stopgap — it claims agent identity the session doesn't have and writes a fake name into the audit log instead of an honest `interactive` one.
