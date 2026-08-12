# Chat History - ace-run (research.0c.cdx)

- **TIMESTAMP:** 2026-08-12 18:16:24 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0c.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_180049.md`

## Prompt

%clan(research.0c, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I want to add an llm provider to sase that supports grok. I think that there is a grok-cli tool available, right? Can you do some research to help me decide the best way to implement this? End your analysis with a recommended solution.]]) %id:research.0c.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I want to add an llm provider to sase that supports grok. I think that there is a grok-cli tool available, right? Can you do some research to help me decide the best way to implement this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m using the `sase_repo` skill because the report belongs in the research sidecar, and I’ll inspect SASE’s current provider architecture plus authoritative Grok/X API and CLI sources before writing a recommendation.

The local architecture confirms SASE is designed around coding-agent CLIs, not raw chat APIs, and exposes each runtime through a small entry-point provider plus shared subprocess, retry, model-routing, and finalization layers. I’m now checking whether “grok-cli” is official, maintained, and automation-friendly enough to fit that contract.

Grok does have an official tool now: xAI’s “Grok Build,” installed as the `grok` executable. Its headless JSONL mode, model/effort flags, tool events, usage totals, API-key login, and `AGENTS.md` compatibility line up unusually well with SASE’s provider boundary. I’m checking the remaining SASE integration surfaces—especially generated skills and CLI lifecycle metadata—before settling the recommendation.

The generated-skills part of the integration triggers the `sase_memory_read` workflow, so I’m reading that audited project memory before evaluating where Grok-specific skill files should be deployed.

I’ve narrowed the decision to a first-party Grok Build adapter versus using Grok indirectly through OpenCode. I’m now writing the comparison with concrete CLI flags, parser requirements, model-routing caveats, and a phased implementation checklist.

The report is drafted. Its main finding is that the official CLI is Grok Build (`grok`), but SASE should keep it explicit-only at first because an unrelated Homebrew tool also owns that executable name; that changes the safe autodetection strategy. I’m doing a final consistency and citation pass now.

The generated-skills memory I had to consult is stale relative to SASE’s current provider set. Per this project’s workflow, I’m using `sase_new_task` to check whether that documentation gap is already tracked before filing any follow-up; this does not change the Grok report.

Research is complete: [grok_llm_provider_research.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202608/grok_llm_provider_research.md).

The recommendation is a built-in, explicit-only `grok` provider wrapping the official [Grok Build](https://docs.x.ai/build/overview) CLI in headless `streaming-json` mode. OpenCode is suitable as a temporary evaluation path, but not the permanent integration. Autodetection should wait because an unrelated [Homebrew `grok`](https://formulae.brew.sh/formula/grok.html) executable creates an identity collision.

The report includes architecture analysis, command-line design, model policy, event parsing, security considerations, alternatives, implementation steps, and tests. It notes that an authenticated CLI smoke test remains necessary because Grok Build is not installed locally.

I also corroborated and reopened existing task `sase-ca`, which tracks stale generated-skills runtime guidance discovered during the research. No SASE source files were changed.

The research report was created in the prior pass, and this finalizer now requires committing that exact sidecar change. I’m using the `sase_git_commit` skill to commit it through SASE’s approved workflow, then I’ll verify the research repository is clean.

The research repository contains only the intended new report, with no unrelated edits to exclude. I’ll commit it as a documentation-only change; no test suite is needed for this standalone Markdown report.

The SASE commit workflow is still running its synchronization and push steps. I’m waiting for it to finish in this turn, then I’ll check both cleanliness and upstream status.

Committed and pushed the research report:

- [grok_llm_provider_research.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202608/grok_llm_provider_research.md)
- Commit: `eb605d2` (`docs: research Grok provider integration`)
- Repository is clean and synchronized.

Recommendation: implement an explicit-only built-in `grok` provider around xAI’s official Grok Build CLI using headless streaming JSON. Defer automatic detection because an unrelated executable also uses the `grok` name.
