# Chat History - ace-run (research.0b.cdx)

- **TIMESTAMP:** 2026-08-12 12:54:19 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0b.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_123932.md`

## Prompt

%clan(research.0b, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I recently made some improvements to the "Artifacts" tab (see
the sase-js epic bead for context) and would like to continue improving these sub-tabs
by adding new functionality. Before doing that however, I think it's a good idea to try
to unify these sub-tabs as much as possible by providing a similar interface for each
for users and a practical contract for artifact ref type designers to follow to make
sure new sidecar repo tabs follow the same standard. Can you do some research with the
goal of helping me decide the best way to implement this? End your analysis with a
recommended solution.]]) %id:research.0b.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I recently made some improvements to the "Artifacts" tab (see
the sase-js epic bead for context) and would like to continue improving these sub-tabs
by adding new functionality. Before doing that however, I think it's a good idea to try
to unify these sub-tabs as much as possible by providing a similar interface for each
for users and a practical contract for artifact ref type designers to follow to make
sure new sidecar repo tabs follow the same standard. Can you do some research with the
goal of helping me decide the best way to implement this? End your analysis with a
recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll research this as an architecture and UX contract question: first the `sase-js` epic and recent Artifacts-tab changes, then the current Python/JS tab implementations and artifact-ref/provider interfaces. I’m using the SASE memory, repo, and artifact-file skills because this crosses bead history and the research sidecar, and the finished report should be registered as a durable research artifact.

The artifact-file skill requires an explicit usage audit before file creation; I’m recording that now. The bead-memory rules also require an audited long-term-memory read before I query the epic, and the repo skill requires opening the research sidecar through SASE rather than touching its path directly.

The epic confirms the new dynamic panes are intentionally provider-driven, but phase 7 mainly unified discovery and mounting—not each pane’s interaction model. I’m now comparing the actual pane APIs and the original design’s extension points; this is where the practical contract should emerge (data shape, list/detail behavior, filtering, commands, and provider-owned customization).

A key gap is already visible: the runtime passes `provider_spec` into `ArtifactsDocumentsPane`, but the pane still renders through plan-specific data models and ignores most declarative `properties`/`detail` hints. I’m checking the shipped research provider and Rust schema next to separate “contract already promised” from “contract the UI can actually honor.”

The local architecture points toward a host-owned “resource browser” with declarative presentation metadata, rather than provider-supplied widgets. I’m validating that against mature extension systems—especially how they keep a uniform shell while still letting resource types declare columns, fields, actions, and capabilities.

Because the recommendation changes how every provider pane loads and refreshes, I’m applying the TUI performance memory now. This is the constraint that decides whether the shared browser should eagerly normalize all providers or preserve per-pane lazy workers and revision-keyed caches.

The evidence is consistent enough to write the report. The central recommendation will be a host-owned generic artifact browser with typed adapters and a versioned declarative presentation contract—not a single lowest-common-denominator pane, and not plugin-supplied TUI code. Patches remains the deliberate exception; Plans-specific workflow actions become host capabilities layered onto the shared document browser.

The report is written and its research repo is clean apart from the requested new file; the main SASE checkout remains untouched. I’ve also checked the final section and basic diff hygiene. I’m registering the Markdown snapshot now so it has a durable `file:` reference in addition to its research-sidecar path.

Research is complete: [artifacts_subtab_contract.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202608/artifacts_subtab_contract.md).

The recommended solution is a host-owned shared Artifact Browser shell with typed adapters and a declarative provider-spec v2. Patches remains specialized; third-party providers supply data and presentation hints, never TUI code.

Durable artifact:

- ID: `explicit:c2d8d83ad7676062e8aa34ea`
- Ref: `file:explicit:c2d8d83ad7676062e8aa34ea`
- Source: the research file linked above
- Stored snapshot: [artifact copy](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260812123932/artifacts_subtab_contract-6011eca307ea.md)

I created the listed research file in the prior pass, so the finalizer requires me to commit it now. I’m using the SASE git-commit skill because it is the mandated commit workflow, then I’ll confirm the research sidecar is clean.

The diff contains only the requested 635-line research report, and the repository has no unrelated edits. I’m committing that single file as documentation with an intentionally scoped file list.

Committed the completed [Artifacts sub-tab contract research](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202608/artifacts_subtab_contract.md).

Commit: `a805b4f docs: research unified Artifacts sub-tab contract`

The research repository is clean and synchronized with `origin/main`.
