# Chat History - ace-run (research.1z.cld)

- **TIMESTAMP:** 2026-09-15 21:51:29 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1z.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260915_213404.md`

## Prompt

%id(cld, clan=research.1z) %m:@opus_or_grok %q(w=0.25)
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1z.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I want to add a new `%sink`
directive that acts like the `%wait` directive, but in reverse (i.e. the target agents
wait for the agent that specified the `%sink` directive in its prompt).

- This directive should have inputs that allow for a robust selection of agents that
  should wait for the agent we are launching with corresponding completion in the prompt
  input widget and external editors (via LSP support).
  - We need to have the ability to target all currently waiting agents.
  - We need to have the ability to target all agents in a particular agent hood.
  - We need to have the ability to target specific sase agents by name.
  - We need a way to specify that any agents that matches the specified selection
    criteria (by the other inputs described above) which are launched after this agent
    should also wait for this agent to complete.
- This directive also needs to work with stand-alone procs (i.e. prompts that are
  submitted that just contain the `%proc` directive and a VCS xprompt workflow) in both
  directions (i.e. the `%sink` directive should be able to be used in stand-alone proc
  prompts to have other waitingg/queued agents and/or stand-alone procs to wait for it).
  This will be useful, for example, when I want to run some command in an ephemeral
  workspace for some sase project but need to wait until no sase agents are running /
  for a certain set of sase agents to finish running before running the command.
- Notably, no agent that is running (e.g. not WAITING or QUEUED) should be effected by
  (i.e. need to wait for or stop for) the agent/proc that specified the `%sink`
  directive in its prompt.

Can you do some research with the goal of helping me decide the best way to implement
this? As a part of your research you should critique the idea itself. Make any
modifications to the design/proposal that you think are objectively beneficial but
clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll start by exploring the codebase to understand how `%wait` works today.

Research complete. Writing the report.

Report written and registered. Now the final declaration.

Research complete.

**Report:** `sase/repos/research/202609/sink_directive_inverse_wait__b.md`
**Artifact:** `file:explicit:1f045e818f68fd0f8b67984d` (label `research:202609/sink_directive_inverse_wait__b.md`)

## What I found

**Verdict: implementable, and the codebase has an almost perfect hook — but the proposal as written only solves half of its own motivating use case.**

The four highest-value findings:

1. **Your example needs two primitives, not one.** "Wait until no agents are running" decomposes into a *drain* (wait for the current set) and a *hold* (stop new starts). `%sink` is only the hold. The drain exists for agents as `%q:1`, but `%queue` is **explicitly forbidden on `%proc` units** (`agent_launch/mod.rs:1460`, `agent-directive-on-proc`), and `ProcUnitWire` carries no queue fields at all. So a stand-alone proc can't express *any* capacity condition today, and `%sink` alone would leave your command racing the five agents already running.

2. **The right hook is `runner_capacity.rs:608` `waiter_blockers`** — a pure function emitting typed blocker codes (`capacity-condition`, `deference-window`, …). Every agent passes through the runner-slot gate; a RUNNING agent has already left it forever. Adding one `hold-barrier` blocker there makes "no running agent is affected" true *structurally* rather than by a rule someone has to remember, covers agents with no `%wait`, handles future launches for free, and needs no new polling loop.

3. **Don't push waits into other agents' `waiting.json`.** Third parties write into other agents' wait markers today, but only ever to *unblock* (`_killing_utils.py:110`, `_directive_persistence.py:299`). That asymmetry is what keeps the wait system explainable. The push design also can't name a proc as a dependency — the marker schema has no `wait_for_procs`, which is exactly why ACE excludes proc rows from `%wait` completion. Instead: one flock-guarded, TTL-bounded hold record modeled file-for-file on `provider_disable.rs` / `runner_limit_override.rs`, both of which already do prune-expired-on-read.

4. **`%sink` names the opposite of what it does** — a sink is the terminal consumer, the thing that runs *last*. Recommend `%hold`.

14 called-out modifications are collected in §6, including: freeze the "currently waiting" selector at arm time into artifact dirs (it's otherwise an unpredictable moving target); rename the selectors `pending`/`future`; default `scope=project`; exclude the armer's own family/clan/descendants (self-match via `hood=` is the likeliest real bug); reject `%hold`+`%repeat` and `%hold`+`%dispatch`; add `tribe=` for symmetry with `%wait:@tribe`.

Two useful precedents I'd have missed without digging: `%wait:@tribe` is **already forward-looking** (`_resolution.py:76` passes `newer_than`), so your `future` semantics have a design ancestor — including the decision not to fault a forward wait that can't resolve yet. And `agent_name_in_hood` already exists in the Rust core, deriving hood membership from the family name that's *already* on the capacity record.

Phasing recommendation: ship `sase agent hold run -- <cmd>` (CLI-only, release bound to a process lifetime) before the directive. §3.2 raises a real layering objection — `%sink` would be the first directive whose effect escapes its own launch, which makes `%repeat`, `#fork`, and prompt-history replay into re-arm hazards.
