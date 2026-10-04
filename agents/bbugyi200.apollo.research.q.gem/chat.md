# Chat History - ace-run (research.q.gem)

- **TIMESTAMP:** 2026-09-29 15:04:24 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.q.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260929_145445.md`

## Prompt

%id(gem, clan=research.q)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.q.cdx`, `research.q.cld`, `research.q.grk`, `research.q.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm pretty sure the
E1-E5 epics described in the sase_tool_epic_roadmap.md file in the research sidecar repo
are complete. I'm now considering whether or not to move forward with E6-E8. Can you
help me re-evaluate the worth of these epics? What new functionality do these
immediately give me and/or what functionality might it unlock in the future? End your
analysis with a recommendation. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

# Re-evaluating the Worth of SASE Tool Epics E6–E8

**Independent Research Report** · Researcher `gem`  
**Report File:** [`sase_tool_e6_e8_worth_reevaluation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/sase_tool_e6_e8_worth_reevaluation__gem.md)  
**Registered Artifact:** `file:explicit:449a1e0f44144d828fa10df0` (`research:202609/sase_tool_e6_e8_worth_reevaluation__gem.md`)

---

## 1. Baseline Verification: Epics E1–E5 Are Complete

An independent audit of the current master tree (`9d60b97513`), closed beads, and live CLI subcommands confirms that epics **E1 through E5** are fully implemented and landed:

- **E1 (`sase-135`):** Named tools catalog in `sase/sase.yml` (`check`, `check-full`, `install`, `test`, `test-visual`), Rust-backed SQLite entity store, foreground execution, fingerprinting, host load sampling, and CLI (`list`, `run`, `runs`, `show`).
- **E2 (`sase-17p`):** Durable `-H` hand-off execution, linking to monitor and detached proc (`detach_scope`) execution engines, plus CLI controls (`stop`, `wait`, `show --follow`).
- **E3 (`sase-18j`):** Failure triage normalizing failure signatures into NEW vs. KNOWN vs. FLAKY against red-master baselines (`sase tool failures`), enabling known-gated continuation past historical master failures like `sase-j0`.
- **E4 (`sase-1ah`):** Verification receipts (`sase tool receipt`, `sase tool receipts`), prepared-completion gating, and content-equivalent repeat opportunity measurement.
- **E5 (`sase-1bt`):** TUI integration with live ⚒ chips on agent rows, ToolRun detail card with stage waterfalls, and the Admin Center Tools pane.

---

## 2. Re-evaluation of Epics E6, E7, and E8

### Epic 6: Forecasts and Automatic Inline-vs-Hand-off
- **Worth Assessment:** **Very High (Immediate & Strategic).**
- **What it immediately gives:**
  1. *Elimination of the routing dilemma for agents:* Agents no longer need prompt instructions on whether to pass `-H`. SASE predicts runtime against the provider's inline budget: fast commands run inline with streaming logs; heavy commands automatically hand off with a concise 1-line reason on stderr.
  2. *Runtime transparency:* `sase tool run -E` explains expected duration, quantiles (`p50`/`p90`), and routing rationale without side effects; `sase tool stats` surfaces distribution health.
  3. *Deadlock and hang alerts:* Replaces static elapsed timers with active state transitions: `running` $\rightarrow$ `overdue (+Xm over typical)` $\rightarrow$ `stalled`.
  4. *Self-adjusting timeouts:* `timeout: auto` computes `clamp(3 × p90, 10m, 3h)` per tool per machine, eliminating brittle static timeout thresholds.
- **What it unlocks in the future:**
  - **Prerequisite for E7 (Admission):** Capacity queues cannot compute expected start times or backfill short jobs without duration predictions.
  - **Agent turn budgeting:** Enables agents to dynamically decide whether verification fits within their current turn budget or requires a checkpoint.
- **Corpus Maturity & Staging:**
  - The ToolRun ledger is ~10 days old with ~30–50 samples for `check` (`TYPICAL: 7m 11s (n=30)`) and fewer for other tools.
  - **Recommendation:** **Proceed with E6 in an Advisory-First posture.** Build the Rust statistical models, `sase tool stats`, `run -E`, and overdue detection immediately. Keep predictions advisory and hold automated inline-vs-hand-off routing until the planned $\ge 80\%$ chronological backtested interval coverage threshold is met.

---

### Epic 7: Local Tool Capacity Admission
- **Worth Assessment:** **High Long-Term, Medium Immediate.**
- **What it immediately gives:**
  1. *Host thrashing prevention:* Prevents multi-agent swarms (e.g. 5+ concurrent agents) or parallel phase workers from running heavy suites simultaneously and exhausting CPU/RAM.
  2. *Unified resource accounting:* Extends the Rust `runner_capacity` authority (schema v5) to absorb pytest worker tokens (`WorkerTokenLease`) and agent capacity into a single accounting ledger.
  3. *Fair queueing & backfill scheduling:* Fast commands slip into temporary capacity gaps ahead of heavy queued jobs without delaying them; queued runs receive predictable start times and typed retry/bypass commands (`-B`).
- **What it unlocks in the future:**
  - High-density autonomous swarms on single workstations without manual concurrency throttling.
- **Risks & Sequencing:**
  - **Strictly dependent on E6:** Admission without duration prediction repeats the failure mode of the superseded `sase-zm` epic (queueing and pricing work without knowing how long it will take).
  - High blast radius: Fail-closed admission risks deadlocks or command starvation if token accounting leaks.
  - **Interim solution exists:** Heavy runs can continue arming a `sase-11l` `%hold` as a lightweight mutual-exclusion barrier.
  - **Recommendation:** **Sequence strictly after E6 calibration.** Do not author the E7 plan until duration distributions stabilize and queue capacity epics (`sase-zp`) have settled.

---

### Epic 8: Fleet Capacity Surfaces and Coordinated Rollout
- **Worth Assessment:** **Low Immediate ROI, Disproportionate Risk.**
- **What it immediately gives:**
  1. *Cross-node visibility:* Displays remote host capacity and active lease holders ("why is apollo busy?") in TUI/CLI meters.
  2. *Staged multi-machine cutover:* Tooling for drain, migration, and rollback across athena, apollo, and mac.
  3. *Cross-machine duration hints:* Displays estimates of what a command would take on another machine in `run -E` (hints only).
- **What it unlocks in the future:**
  - Foundation for future capacity-aware remote dispatch (`%dispatch`).
- **Critical Critique & Risk:**
  - **No distributed execution in scope:** E8 explicitly excludes remote execution dispatch and cross-machine caching (hermeticity is unestablished).
  - **Historical #1 driver of remediation chains:** Empirical analysis of 600 SASE epics shows that multi-machine protocol cutovers across athena, apollo, and mac repeatedly spawn 4–5 tiers of fix-up epics due to wire schema skew and network timeouts. Paying this tax for read-only status meters is not justified.
  - **Recommendation:** **Defer indefinitely / Re-scope.** If cross-machine visibility is needed, append lightweight loadavg/PSI strings to the existing `sase fleet` command rather than engineering an elaborate multi-machine lease synchronization protocol.

---

## 3. Summary Matrix

| Dimension | E6 (Forecasts & Auto-Routing) | E7 (Local Admission) | E8 (Fleet Surfaces & Rollout) |
| :--- | :--- | :--- | :--- |
| **Immediate Utility** | **Very High** (Auto-routing, overdue alerts, `run -E`, `stats`) | **Medium** (Single-host swarm protection, fair queue) | **Low** (Passive multi-machine meters; hints only) |
| **Future Unlock** | **Critical** (Enables E7 duration pricing & turn budgeting) | **High** (Enables high-density local agent swarms) | **Moderate** (Stepping stone for capacity-aware dispatch) |
| **Technical Risk** | **Low-Medium** (Additive, fail-open, advisory-first) | **High** (Fail-closed accounting, deadlock/starvation risk) | **Very High** (Multi-machine wire skew & remediation chains) |
| **Readiness** | **Emerging** (~10d corpus; ready for advisory components) | **Blocked** (Strictly blocked on E6 duration calibration) | **Blocked** (Strictly blocked on E7 stability) |
| **Recommendation** | **PROCEED NOW (Advisory-First)** | **HOLD (Sequence After E6)** | **DEFER INDEFINITELY / RE-SCOPE** |

---

## 4. Suggested Next Steps

1. **Plan Epic 6 with a Two-Stage Landing:**
   - *Phase 1:* Implement Rust statistical quantile models, `sase tool stats`, `sase tool run -E`, and overdue/stalled detection in an **advisory mode**.
   - *Phase 2:* Activate automatic inline-vs-hand-off routing and `timeout: auto` once backtesting confirms $\ge 80\%$ interval coverage.
2. **Use `%hold` as the Interim Capacity Safeguard:**
   - Rely on `sase-11l` `%hold` barriers to prevent parallel test contention while E6 data matures.
3. **Re-evaluate E7 Post-Calibration:**
   - Unfreeze E7 planning only when empirical duration pricing is live and multi-agent contention warrants a local fair queue.
4. **Formally Shelve E8:**
   - Avoid cross-machine wire and cutover work until automated remote dispatch is prioritized.

---

### Artifact Reference
The complete research report has been committed to the research sidecar and registered as a durable SASE artifact:
- Local Path: [`sase_tool_e6_e8_worth_reevaluation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_21/sase/repos/research/202609/sase_tool_e6_e8_worth_reevaluation__gem.md)
- Artifact Ref: `file:explicit:449a1e0f44144d828fa10df0` (`research:202609/sase_tool_e6_e8_worth_reevaluation__gem.md`)
