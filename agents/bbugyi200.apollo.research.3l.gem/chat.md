# Chat History - ace-run (research.3l.gem)

- **TIMESTAMP:** 2026-11-07 09:57:02 EST
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3l.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261107_094530.md`

## Prompt

%id(gem, clan=research.3l)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3l.cdx`, `research.3l.cld`, `research.3l.grk`, `research.3l.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We have some remote machine support in sase currently. A lot is broken and there is
still a lot of features related to remote machines that I want to implement one day, but
some functionality exists. I would now like to start allowing sase agents to wait for
other sase agents running on remote machines which are configured (I think the
`sase machine init` command does this?) by the current machine. For example, the
`%wait:athena.foobar` directive should be able to be used in a prompt that launches an
agent on this machine (apollo) to wait for a sase agent named `foobar`, that is running
on my athena machine, to complete.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Synthesis: Cross-Machine Agent Wait Directives in SASE

**Researcher:** `researcher gem` (5-Researcher Swarm)  
**Report File:** [`sase/repos/research/202611/remote_machine_agent_wait_directives__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202611/remote_machine_agent_wait_directives__gem.md)  
**Artifact Registration:** `sase artifact create` succeeded (`id: explicit:d656b3f852d8f97be7b74744`, ref: `file:explicit:d656b3f852d8f97be7b74744`, label: `research:202611/remote_machine_agent_wait_directives__gem.md`).

---

### 1. Executive Summary & Findings

Extending `%wait` to allow an agent on controller machine `apollo` to wait for a remote agent `foobar` on enrolled machine `athena` is technically feasible within SASE's current architecture. The foundation—including machine enrollment via `sase machine init`, the remote HTTPS gateway daemon (`sase_gateway`), the local connection-pooling worker (`sase_federation_worker`), and the Python IPC client (`FederationFacade`)—already exists.

However, implementing cross-machine waiting requires critical syntax disambiguation and distributed failure management.

---

### 2. Critique: Is Cross-Machine `%wait` a Good Idea?

#### The Pros
- **Hardware Heterogeneity:** Allows chaining workflows across machines with different capabilities (e.g. running a long benchmark or GPU job on `athena`, followed by an analysis turn on `apollo`).
- **Ergonomic Familiarity:** Reuses existing prompt grammar without introducing complex orchestrator syntax.

#### The Pitfalls & Distributed Realities
1. **The Fallacy of the Local Filesystem:** Local `%wait` is completely resilient to network failures because it operates on local disk markers (`waiting.json` and `ready.json`). In contrast, a remote machine may sleep, reboot, experience Wi-Fi/Tailscale disconnects, or have its `sase_gateway` service crash. Without heartbeat and timeout policies, the local runner on `apollo` will hang indefinitely.
2. **Resource Holding:** SASE runners are parked OS processes. While parked, a waiting runner on `apollo` holds a process table PID, open file descriptors, a numbered ephemeral workspace reservation (`sase_<N>`), and local capacity slots.
3. **Target Existence & Purge Timing:** If `foobar` on `athena` hasn't started yet, is it a typo, or will it start soon? What if `foobar` ran yesterday and was pruned from `athena`'s 200-item recent window? The controller must distinguish between "pending launch" and "non-existent / purged target".
4. **Asymmetric State & Artifact Silos:** When an agent finishes locally, its git commits, output variables (`sase var`), and artifacts are on local disk. When `athena.foobar` completes, its commits and artifacts remain on `athena` unless explicitly pushed to an upstream repository. A downstream agent on `apollo` waiting for `athena.foobar` will fail if it expects local access to code that was never pushed.
5. **Distributed Deadlocks:** If an agent on `apollo` waits for `athena.foobar` while an agent on `athena` waits for `apollo.baz`, local cycle detection cannot see across the network boundary, creating an undetectable distributed deadlock.

---

### 3. Justified Requirement Adjustments

1. **Avoid Bare Dot Notation (`%wait:athena.foobar`):**
   - **Problem:** SASE allows dots in agent names (e.g., `research.3l.cdx`, `agent.v2`), clan member notation (`<clan>.<member>`), and machine hostnames (`mac.local`). An expression like `%wait:athena.foobar.baz` is lexically ambiguous.
   - **Adjustment:**
     - **Primary Canonical Syntax:** `%wait(foobar, machine=athena)` or `%wait(agent=foobar, machine=athena)` (aligns with `%wait(planner, target=turn)` and `%id(..., session=...)`).
     - **Shorthand Alternatives:** `%wait:athena/foobar` (Unix/git namespace style) or `%wait:athena:foobar` (SASE memory strand style).
2. **Support Target Granularity (`turn` vs `session`):**
   - SASE multi-turn interactions belong to an `agent_session`. Remote waiting must support `%wait(foobar, machine=athena, target=turn)` (wait for single turn) vs `target=session` (wait until the whole session settles).
3. **Mandatory Timeouts and Unreachable Host Detection:**
   - Add optional `timeout=` parameter (e.g., `%wait(foobar, machine=athena, timeout=30m)`).
   - If `athena` becomes unreachable for longer than a grace period (e.g. 10 minutes), the scheduler must flag a `remote_unreachable` diagnostic and trigger a user notification via `sase notify` rather than silently hanging forever.
4. **Upstream Publication Precondition:**
   - Cross-machine waiting only synchronizes execution timing, not repository files. Workflows expecting code handoff must ensure the remote agent uses a rollover macro (`#commit`, `#pr`, etc.) to publish commits upstream.

---

### 4. Recommended Architectural Implementation

We recommend extending the **AXE Background Scheduler (`wait_checks` chop)** rather than having parked runner processes poll remote gateways directly:

1. **Directive Parsing:**
   - In `src/sase/macro/`, parse `machine=` and remote shorthand syntax (`athena/foobar`).
2. **Marker Storage:**
   - In `src/sase/axe/run_agent_wait.py`, write remote dependencies into `waiting.json` under `waiting_for_remote: [{"machine": "athena", "agent": "foobar"}]`.
   - The runner continues its existing contract: park, call `release_idle_memory()`, and wait for `ready.json`. Zero runner networking required.
3. **Scheduler Resolution (`wait_checks` chop):**
   - In `src/sase/scripts/_chop_wait_checks_run_waiters.py`, when `wait_checks` scans active waiters, it batches remote queries per target machine.
   - Queries `FederationFacade.catalog_sync()` or `batch_lookup()` through the local `sase_federation_worker`.
   - When the remote agent's status transitions to `completed` / `done`, `wait_checks` marks the dependency satisfied.
   - If the remote agent terminates with failure (`failed`, `killed`, `stopped`), `wait_checks` flags a terminal blocker notification.
   - Once all local and remote dependencies are satisfied, `wait_checks` writes local `ready.json`, cleanly resuming the waiting agent.

The full research report with code touchpoints, failure state machines, and implementation milestones has been committed to the research repository and registered as a durable artifact snapshot.
