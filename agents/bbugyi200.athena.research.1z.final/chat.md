# Chat History - ace-run (research.1z.final)

- **TIMESTAMP:** 2026-09-15 22:08:29 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.1z.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260915_213404.md`

## Prompt

%id(final, clan=research.1z) %m:claude-fable-5
%wait:research.1z.cdx %wait:research.1z.cld %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.1z.cdx` and
   `research.1z.cld` dependencies, matching by `wait_name` and the canonical research
   label's existing `__a.md`/`__b.md` suffix. Never reassign `__a`/`__b` from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one A report and one B report, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports inside it as `<name>__a.md` and `<name>__b.md`, preserving each report's
   existing `__a`/`__b` suffix. Each report's `source_path` is provenance for where it
   lives in your own opened research checkout; resolve its canonical repo-relative path
   there before moving it. Never modify the other agents' checkouts or the stored
   snapshot recorded at `ref` — only the copy in your own checkout moves. Preserve both
   files and never overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'm the lead researcher for this dispatch. My plan: open the research repo, read both registered reports via audited artifact reads, do my own codebase research on the `%wait`/`%proc` directive machinery, then merge everything into a consolidated report. Starting by opening the research repo.

`sase-core` is a linked repo, so I'll open it through the skill before reading it.

Both of B's central code claims check out. Continuing verification of the remaining disputed claims in parallel.

Both reports are at their canonical paths in my checkout. I'll use the stem `reverse_wait_hold_barrier` (no collision in the month directory) and move the reports in, preserving their suffixes.

Now writing the consolidated report, merging both reports with my own verification findings and resolving the disagreements.

No duplicates in the search or recent sweep. Checking in-progress epics for a causal link before creating the bead.

Only one in-progress epic (flake retirement) — no causal link to proc-wait semantics. Creating the bug task bead.

The bead is filed. Verifying the final layout, then submitting the final declaration.

The consolidated report is written and committed. Here's the summary of what I found and concluded.

## What was done

- Read both registered reports through audited artifact reads: **A** (`percent_sink_admission_fence_design__a`, a durable admission-fence/constraint-journal design) and **B** (`sink_directive_inverse_wait__b`, a TTL-bounded hold-record-store design).
- Independently verified every load-bearing code claim in `sase` and `sase-core` (opened via `/sase_repo`): the `waiter_blockers` pure function at `runner_capacity.rs:608`, `%queue` forbidden on proc units at `agent_launch/mod.rs:1460`, the `provider_disable.rs`/`runner_limit_override.rs` store patterns, `agent_name_in_hood`, gate ordering in `run_agent_runner.py`, the `@tribe` forward-wait precedent, proc IDs allocated only at dispatch, and `sase agent wait -a`. All checked out.
- Moved both reports into `202609/reverse_wait_hold_barrier/` as `__a.md`/`__b.md` and wrote the consolidated report `reverse_wait_hold_barrier.md` beside them; the commit was declared through the final manifest.

## Key resolutions of the reports' disagreements

- **Mechanism:** B's pull-model hold store wins over A's materialized reverse edges. The atomicity A demanded already exists structurally — `wait_for_runner_slot` takes `record_run_started_at` as its claim callback under the existing host lock, so "whichever happens first wins" comes free, and a RUNNING agent is never affected *by construction*.
- **Release scope (A: family vs B: shell):** new evidence settles it for A — `%wait` on an agent name already resolves family-generation-wide and handoff-aware (`family_candidate_for_root`), and the glossary defines a sase agent as the family. Releasing at first-shell settle would make `%hold` and `%wait` disagree about when the same agent "completes."
- **Activation time:** I found an internal inconsistency in B — its "hold activates only when the armer starts running" rule would break its own recommended `%proc %q:1 %hold(pending, future)` quiesce composition (new arrivals keep resetting the drain). Resolution: active from arm time, armer exempt and priority-boosted, TTL bounding the hazard.
- **Drain:** B's decomposition wins over A's `drain=true` — capacity semantics were deliberately migrated to `%queue`, so phase 0 is allowing `%queue` on `%proc` units rather than a second drain vocabulary inside the new directive.
- **Adjacent defect found:** same-plan logical `%wait` on a proc resolves at supervisor *submission* while external `%wait(proc=…)` waits for *terminal* status — filed as bug task bead **sase-11k**.

## Recommendation (short form)

Implement it as **`%hold`** (rename called out; `%sink` reads backwards): sugar over a first-class, TTL-mandatory, fail-open hold store in the Rust core, enforced as one `hold-barrier` blocker in `waiter_blockers` for agents and in the admission-engine eligibility path for proc targets. Selectors: exact names, `hood=`, `tribe=`, frozen `pending`, live `future`; `scope=project` default; armer-kin excluded; `%repeat`/`%dispatch` rejected. Ship CLI-first (`sase agent hold run … -- <cmd>`), then the directive behind an `agent_holds` beta flag, then the shared-contract completion/LSP work (new `Hood` value role drives both ACE and external editors).
