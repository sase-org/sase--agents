# Chat History - ace-run (research.13.gem)

- **TIMESTAMP:** 2026-10-13 16:51:18 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.13.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_162421.md`

## Prompt

%id(gem, clan=research.13)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.13.cdx`, `research.13.cld`, `research.13.grk`, `research.13.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
am considering launching agents to implement the E3 epic described in the
memory_built_instruction_migration_epics.md file in the research sidecar repo. Can you
do some research with the goal of helping me understand if we are ready for this work?
Also, explain how I would be able to figure out what a given sase agents instruction
bundle's contents looked like (for a completed agent on the "Agents" tab, for example). 
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

# Research Summary: Epic E3 Readiness & Agent Instruction Bundle Inspection

**Researcher Identity:** `research.13.gem`  
**Durable Artifact Reference:** `file:explicit:fcd624f9a09b4ba94ee6856f` (`research:202610/e3_instruction_delivery_cutover_readiness__gem.md`)  
**Repository Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/e3_instruction_delivery_cutover_readiness__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/e3_instruction_delivery_cutover_readiness__gem.md)

---

## 1. Readiness for Epic E3 (Explicit Delivery Cutover)

### Verdict: Ready for Planning & Implementation
The system has met all technical and empirical prerequisites established in the memory-built instruction migration roadmap ([`memory_built_instruction_migration_epics.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/memory_built_instruction_migration_epics/memory_built_instruction_migration_epics.md)):

1. **Epic E1 Soak & Health (Bead `sase-1gu`)**:
   - **Soak Window**: Landed on 2026-10-06 (**7 full days** of production runs, exceeding the required $\ge 3$-day gate).
   - **Readout Verification**: Grok receives the SASE contract 1×, project instructions, and the single-turn directive via `--rules` (`sase instructions verify` shows Grok at `1× / ✗ / ✓ / ✓ / 0`). Claude helpers have logged **0 accepted declarations** under the PreToolUse guard and subagent system prompt template (`sase doctor -D -C instructions` reports `instructions.helpers` as `OK`).
2. **Epic E2 Parity & Compiler Health (Bead `sase-1h3`)**:
   - **Wire Schema & Compiler**: The `sase-core` manifest schema is pinned at tip (`sase_core_rs 0.39.1`), and the Python instruction compiler (`sase.instructions.compile`) composes all 27 memory units across frame, package, project, and home layers.
   - **Parity Check**: `sase instructions render -p` exits with code 0 and reports 100% section parity against legacy files with zero missing sections.
   - **Manifest Coverage**: `sase instructions verify -c` confirms **100% manifest coverage** across all recent runs (47/47 manifests recorded across Claude, Codex, Grok, Muse, and Antigravity) with zero errors.
   - **Render Latency**: Warm p50/p95 latency is between 31 ms and 55 ms, far within the 250 ms budget.
3. **Subsequent Flag Convergence (Epic `sase-1jc`)**:
   - On 2026-10-10, epic `sase-1jc` retired feature flags across the codebase; shadow rendering and the E1 stopgaps are now unconditional.

### Prerequisite Next Step
No approved plan file exists yet for E3 (`sase/repos/plans/202610/e3_explicit_delivery_cutover.md`). Before launching agents:
- Author the epic plan with the 6 phases defined in the consolidated report: E3.1 `spikes`, E3.2 `delivery-plan` (defining per-provider `sunset` kill switches and fail-open fallbacks), E3.3 `claude` (system prompt appending + exact `claudeMdExcludes` + disabling auto-memory), E3.4 `codex-grok`, E3.5 `muse-agy`, and E3.6 `conformance`.
- Create and approve the epic bead.

---

## 2. Figuring Out What a Completed Agent's Instruction Bundle Looked Like

For any completed agent (e.g. selected on the "Agents" tab), you can inspect its instruction bundle through three surfaces:

### A. Direct Filesystem Artifacts
Every root invocation shadow-renders its bundle directly into the agent's run artifacts directory (`~/.sase/projects/<project>/artifacts/ace-run/<YYYYMM>/<DD>/<timestamp>/`):
- `instructions/00-<provider>.md`: The exact, full Markdown instruction bundle text compiled for that invocation.
- `instructions/00-<provider>.json`: The complete `sase-core` instruction manifest (facts, layer/section breakdown, token estimates, digests, and `common_digest`).
- `agent_meta.json`: Root metadata containing the `"instructions"` summary pointing to the latest manifest.

### B. CLI Commands (`sase instructions`)
1. **Render the Agent's Exact Bundle**:
   ```bash
   sase instructions render -a <agent-name>
   ```
   Resolves the agent's recorded facts and latest manifest. If recorded, prints:
   `agent <agent-name>: bundle matches recorded <sha>`
   and outputs the bundle Markdown. If memory has drifted since the agent ran, it reports which section IDs changed.
2. **Inspect the Section Breakdown**:
   ```bash
   sase instructions render -a <agent-name> -s
   ```
   Prints a table of all 27 sections (ID, layer, lifecycle, bytes, estimated tokens, source path).
3. **Inspect the Normalized Manifest**:
   ```bash
   sase instructions render -a <agent-name> -j
   ```
4. **Inspect Observed Delivery in Provider Logs**:
   ```bash
   sase instructions verify -a <agent-name>
   ```

### C. On the SASE "Agents" Tab (TUI)
- **Current State (Post-E2)**:
  - Select the completed agent in the Agents list.
  - Press `f` to switch to the **FILES deck**, navigate to `instructions/00-<provider>.md` or `instructions/00-<provider>.json`, and open/view it.
  - Press `r` to switch to the **RECORD deck** (Provenance card) to find the artifact path.
- **Future Native TUI Integration (Epic E6)**:
  - Epic E6 will add direct in-TUI visibility: a session header delivery chip and a dedicated **MEMORY deck** on picker key `p` then `y` featuring Manifest, Ledger, and Bundle viewer cards.

---

## 3. Artifact Registration Details

The research report was created and registered without `--move`:
```bash
sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/e3_instruction_delivery_cutover_readiness__gem.md" -l "research:202610/e3_instruction_delivery_cutover_readiness__gem.md"
```
- **Artifact ID:** `explicit:fcd624f9a09b4ba94ee6856f`
- **Stored Snapshot Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261013162426/e3_instruction_delivery_cutover_readiness__gem-481cc06e47f0.md`
- **Output Variable:** `artifacts[0]`
