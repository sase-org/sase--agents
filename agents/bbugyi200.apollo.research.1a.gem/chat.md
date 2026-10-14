# Chat History - ace-run (research.1a.gem)

- **TIMESTAMP:** 2026-10-14 09:32:02 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.1a.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261014_091543.md`

## Prompt

%id(gem, clan=research.1a)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 4-researcher swarm.
The other researchers, `research.1a.cdx`, `research.1a.cld`, `research.1a.grk`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure about our recent migration from agent instruction files to instruction
bundles (see the sase-1ko epic bead for context).

- The thing I am worried about is that an agent's core instructions are no longer
  transparent.
- I used to be able to just read the AGENTS.md file to understand what initial /
  project-level instructions a sase agent was given, for example. But now new users
  and/or non-sase agents need to generate it using a `sase` command I'm assuming?
- Also, it is not clear to me what the benefits are of this new solution? Your report
  should iterate over all of the immediate and long-term benefits.

Can you do some research with the goal of helping me decide whether or not I should
proceed with this work or revert it? 
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

# Research Summary: Dynamic Instruction Bundles vs. Static Instruction Files

**Researcher:** `research.1a.gem`  
**Report File:** [`instruction_bundles_migration_transparency_and_benefits__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/instruction_bundles_migration_transparency_and_benefits__gem.md)  
**Artifact Registration:**
- **Ref:** `file:explicit:79df8995bf2b338acd0a9f12`
- **Label:** `research:202610/instruction_bundles_migration_transparency_and_benefits__gem.md`
- **Storage Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261014091547/instruction_bundles_migration_transparency_and_benefits__gem-7b71a86bbefd.md`

---

## Executive Recommendation: Proceed With the Migration (Do NOT Revert)

**You should proceed with the migration.** Reverting would constitute a major technical regression, reviving verified, critical production bugs across LLM providers, resurrecting 111 commits per 60 days of git churn across 35 generated files, and abandoning deterministic instruction control.

Your worry that instructions are no longer transparent is understandable, but it stems from an **illusion of transparency** provided by static `AGENTS.md` files:
1. **`AGENTS.md` was a false proxy for reality:** What was written on disk did not match what providers ingested. In production, Grok loaded **zero** instruction files for over four weeks across 465+ sessions because workspaces were untrusted; Codex and Claude suffered severe **double-loads** of the 21 KB contract; Claude loaded conflicting linked repo rosters from ancestor `~/CLAUDE.md`; and Claude subagents inherited the root contract telling them to invoke `/sase_final`, causing subagent crashes. Furthermore, critical single-turn directives were injected out-of-band as Python string constants invisible to `AGENTS.md`.
2. **Dynamic instruction bundles provide verifiable, cryptographic transparency:** Instead of assuming an on-disk markdown file represents the prompt, dynamic bundles generate an auditable provenance trail for every invocation:
   - `$SASE_ARTIFACTS_DIR/instructions/NN-<provider>.md` captures the exact, byte-for-byte markdown bundle delivered to the model.
   - `$SASE_ARTIFACTS_DIR/instructions/NN-<provider>.json` records the normalized v2 manifest (section IDs, byte offsets, inclusion reasons, exclusion reasons like `shadowed` or `superseded_input`, and delivery status).
   - `SASE_INSTRUCTIONS_FILE` is exported during the invocation so the agent can inspect its own parameters.
   - Dedicated inspection commands provide immediate visibility:
     - `sase instructions render`: Previews what an agent would receive right now from current memory (`-s` for sections table, `-j` for JSON manifest, `-p` for legacy parity check).
     - `sase instructions show <agent>`: Displays historical bundle bytes and verifies SHA256 integrity (`bytes match`).
     - `sase instructions verify`: Live scoreboard tracking observed provider delivery and compliance.
     - `sase instructions readout`: Tracks declaration misses and memory reads.

---

## The Non-SASE & New User Experience

Under the legacy architecture, committing full SASE instructions to public repositories actively harmed outside contributors and non-SASE tools (Cursor, Aider, raw `claude`). SASE's full `AGENTS.md` instructed models to call SASE-internal harness skills (like `/sase_final`, `/sase_repo`, and `/sase_plan`), confusing external tools.

The migration roadmap resolves this cleanly across epics E4 and E5:
1. **Lightweight Repository Stub (Epic E4):** Public repositories can commit a concise 10–15 line `AGENTS.md` explaining basic build/test commands and stating that full SASE agent workflows are compiled dynamically by SASE.
2. **Interactive Local Projections (`sase instructions sync`):** Developers who want static files for local interactive tools or editors can run `sase instructions sync`, which projects clean, gitignored `AGENTS.md` and `CLAUDE.md` files in primary checkouts without polluting git history.
3. **Internal SASE Developers:** SASE engineers read or preview instructions in ~100 ms with `sase instructions render`, and author rules in modular, audited `sase/memory/` notes that take effect immediately on the next launch without requiring manual regeneration or multi-file commits.

---

## Comprehensive Catalogue of Benefits

### Immediate Benefits (Delivered & Active in E1–E3)
1. **Rescued Broken Ingestion:** Restored Grok from 0% instruction loading to 100% verified delivery via `--rules`; delivered the home layer (tailnet, Obsidian, chezmoi) to Grok and Muse for the first time.
2. **Eliminated Context Waste & Double-Loads:** Stripped ~790 tokens of duplicate contract text on every Claude and Codex call, resolving conflicting repository rosters.
3. **Unified Out-of-Band Directives into Audited Memory:** Eliminated scattered Python strings (`_SINGLE_TURN_DIRECTIVE`, `developer_instructions`, `_AGY_PRINT_MODE_DIRECTIVE`) by compiling them as standard package sections (`pkg.provider.<provider>`) derived from versioned templates.
4. **Actor-Specific Safety (Root vs. Helper):** Root agents receive `pkg.root.final_declaration`; helper subagents receive `pkg.helper.contract` (forbidding `/sase_final`), eliminating helper crash loops.
5. **Deterministic Workspace Isolation:** Suppressed Claude auto-memory and Grok memory-v2 in SASE workspaces, preventing cross-workspace state leakage across numbered ephemeral directories (`sase_<N>`).
6. **Atomic Fallback Resilience:** Any render, sizing, or delivery failure automatically and cleanly falls back to legacy delivery with deduplicated notifications—no agent is ever launched blind.
7. **Continuous Conformance Auditing:** `sase instructions verify` and `sase doctor -C instructions` continuously police provider session records against intended delivery.

### Long-Term Benefits (Roadmap Epics E4–E7)
1. **Zero Git Churn (Epic E4):** Permanently eliminates 111 commits per 60 days across 35 generated files, removing parallel agent merge conflicts during memory updates.
2. **Instant Memory Propagation (Epic E4):** Updates in `sase/memory/` take effect immediately on the very next agent run without manual `sase memory init` or commit choreography.
3. **Fleet & Remote Dispatch Parity (Epic E5):** Remote `%dispatch` targets (`apollo`, `athena`, `mac`) compile instruction bundles locally from local facts, retiring brittle chezmoi hostname templates.
4. **Audience Targeting & Token Budgeting (Epic E7):** Generates role-tailored bundles (e.g. omitting Symvision lint rules and TUI triggers for research swarms), saving thousands of context tokens per turn.
5. **Prompt Injection & Upstream Tampering Resistance:** Explicit system-prompt channels outrank and isolate against malicious `AGENTS.md` files in foreign or third-party repositories.

---

## Strategic Action Plan

1. **Complete Epic `sase-1ko`:** Maintain the dynamic bundle architecture and finalize live acceptance records.
2. **Soak the Sunset Flags:** Keep per-provider sunset flags (`<provider>_explicit_instructions`) active through the 7-day soak. If an isolated regression occurs on one provider, disable that single flag rather than reverting the entire system.
3. **Promote Ergonomic Tooling:** Make `sase instructions render` and `sase instructions show` prominent in onboarding and developer docs.
4. **Deliver E4 Ergonomics:** Implement `sase instructions sync` for gitignored local projections and commit a lightweight repository stub before retiring tracked shims.

The finalizer declaration for the required commit payload on `sdd:research` (`202610/instruction_bundles_migration_transparency_and_benefits__gem.md`) has been submitted and accepted.
