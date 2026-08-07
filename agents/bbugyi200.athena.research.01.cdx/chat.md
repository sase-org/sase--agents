# Chat History - ace-run (research.01.cdx)

- **TIMESTAMP:** 2026-08-07 15:30:28 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.01.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260807_151438.md`

## Prompt

%clan(research.01, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I want to add a sase LLM provider for Meta's new Muse Code agentic harness. Can you do some research to help me understand what this would entail? End your analysis with a recommended approach/solution.]]) %id:research.01.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I want to add a sase LLM provider for Meta's new Muse Code agentic harness. Can you do some research to help me understand what this would entail? End your analysis with a recommended approach/solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m going to use the `sase_repo` skill to access the research sidecar correctly, then study both SASE’s existing provider boundary and Muse’s primary documentation/source. I’ll use `sase_artifact_file` at the end if the research directory is artifact-managed.

The artifact skill requires an explicit audit marker before registration, so I’m recording that now. The research will live in the requested sidecar path and be registered only after its content is finalized.

The research sidecar is open at the requested location. I’m now mapping the integration from both ends: Muse’s invocation/configuration/event model and SASE’s existing provider/launcher/runtime contracts.

Meta’s announcement confirms the high-level architecture, but it does not document the noninteractive CLI contract SASE needs. I’m inspecting Meta’s signed/official launcher without installing it into your home directory; the key unknowns are prompt input, machine-readable output, permissions, model selection, resume behavior, and exit semantics.

The integration shape is now fairly clear. Two Muse-specific issues stand out: SASE’s top effort name (`max`) must map to Muse’s `ultra`, and Muse’s generic `muse` executable plus hourly self-updater make explicit selection/version pinning safer than immediate auto-detection. I’m validating its retained-session paths and export behavior before writing the recommendation.

I have enough evidence to write the report. The recommendation will be a staged native Muse CLI adapter—not merely routing Muse Spark through OpenCode—with an authenticated trace-capture spike first, then a conservative built-in MVP that preserves SASE’s outer lifecycle and treats Muse’s beta event/session surfaces as versioned inputs.

The report is drafted. I’m doing a final evidence and formatting pass now, then I’ll register the finished note as a durable SASE artifact.

One evidence boundary needed tightening: Meta’s public materials do not currently establish the reported “contributor” model variant or its terms. I’m removing that as a factual premise and keeping model catalog/terms verification inside the authenticated spike.

The content check is clean; the repository’s formatter found Markdown layout differences. I’m applying that mechanical format pass, then I’ll verify the final recommendation is still the document’s last section.

The report now passes formatting and diff checks, and only the requested new research directory is present in the sidecar. I’m registering the finalized Markdown file so it has a stable artifact reference.

Research completed: [Muse Code SASE provider analysis](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202608/muse_code_provider/muse_code_provider.md).

The recommendation is a staged native `muse exec --json` provider—not an OpenCode model configuration—because Muse’s co-trained harness, persistent agents, and event log are integral to the product. [Meta’s announcement](https://research.meta.ai/blog/introducing-muse-code-and-muse-spark-1-2)

The report passes Prettier and diff checks. No SASE code was changed.

Artifact:

- Ref: `file:explicit:d9a15060944eb8347b98ab1a`
- ID: `explicit:d9a15060944eb8347b98ab1a`
- Source: requested research path above
- Durable copy: [muse_code_provider-bca7f971e70a.md](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260807151438/muse_code_provider-bca7f971e70a.md)

The requested research file is already complete; this finalizer requires committing that file in the research sidecar. I’m using the `sase_git_commit` skill now, then I’ll verify the repository is clean.

The commit workflow is in progress and may be rebasing/pushing the sidecar. I’m waiting for it within this turn, then I’ll check both cleanliness and upstream synchronization.

Research completed and committed:

[Muse Code SASE provider analysis](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202608/muse_code_provider/muse_code_provider.md)

Recommended approach: build a staged native `muse exec --json` provider, beginning with authenticated trace capture, followed by a conservative built-in adapter and later operational hardening.

Commit: `eab3840 docs: research Muse Code provider integration`  
The research sidecar is clean and synchronized with `origin/main`.
