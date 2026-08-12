# Chat History - ace-run (research.0a.cdx)

- **TIMESTAMP:** 2026-08-12 10:52:54 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0a.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_102659.md`

## Prompt

%clan(research.0a, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] The `sase ace` TUI's startup time has gotten progressively worse lately (it regularly takes >5s to finish starting up). Can you do some research with the goal of helping me reduce this start-up time? End your analysis with a recommended solution.]]) %id:research.0a.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase The `sase ace` TUI's startup time has gotten progressively worse lately (it regularly takes >5s to finish starting up). Can you do some research with the goal of helping me reduce this start-up time? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m going to trace the actual startup path and measure it, then compare the hot spots against recent code/history. I’m using the SASE memory-read guidance because this is TUI performance work, and the repo-opening guidance because the requested report lives in the research sidecar.

The performance guidance now governs the investigation, and I’ll use the path returned by SASE—not the literal sidecar path—as the write target if they differ. Next I’m establishing a baseline and identifying which startup phases are synchronous.

A strong candidate has emerged: the startup stopwatch waits for both the Agents load and a full AXE snapshot, while that AXE snapshot eagerly reads every configured lumberjack, every chop’s run index, every run record, and a 500-line tail for every recorded run. That cost naturally grows over time. I’m validating this against your on-disk scale and timings before settling on the recommendation.

The first local timing run exposed an expected stale-workspace problem: this checkout’s Rust extension is not installed, so measurements from it would be invalid. Following the project’s build guidance, I’m refreshing the editable environment before profiling; this changes only the workspace environment, not source.

The rebuild is still compiling the local Rust core. While it finishes, the history evidence is already unusually clean: commit `487a0c20d` changed the AXE startup collector from “lumberjack summaries” to “all chop run histories and output tails,” and the current AXE tree contains many run directories, including a 13 MB run-history directory. I’ll quantify the per-phase contribution once the environment is ready.

The real headless startup changes the ranking: AXE completes at about 1.8 s, while Agents completes at about 4.1 s and therefore owns the stopwatch. The AXE history growth is a real secondary scaling defect, but it is not today’s dominant gate. I’m now decomposing the Agents load into index read, disk scan, pure-data preparation, and UI apply.

The dominant growth mechanism is now concrete: each startup classifies 1,200+ persisted diff references across roughly 500 distinct files (about 20 MB in the current Tier‑1 result), and the index query itself reads from a 99 MB SQLite file containing 6,736 artifact rows plus 27,817 dismissed identities. The diff classifier was added to hide plan-only pencils and later expanded to linked-repo diffs; both are display enrichment, yet they currently run before the first Agents paint.

The data now points to two separate regressions: the Agents loader is the present critical path, while AXE’s eager history scan is a second, growing startup tax. I’m turning the measurements into a concrete cached-first design with rollout and regression targets.

The report is written. I’m doing a final consistency pass now—checking the cited measurements, the report’s last-section recommendation, and that no unrelated files were touched.

Research complete: [sase_ace_startup_latency.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/sase_ace_startup_latency.md).

The dominant issue is archive-wide filesystem revalidation during the Agents index query, compounded by eager diff parsing. The report recommends a cached-first, stale-while-revalidate startup path, followed by deferred badge enrichment and lazy AXE history loading.

I’m using the SASE git-commit workflow required by the finalizer to commit the completed research report in the research sidecar, then I’ll verify that repository is clean.

The report is the only uncommitted file, and its evidence and recommendation are intact. I’m committing it as a documentation-only research addition with that file explicitly scoped.

Research report committed successfully: [sase_ace_startup_latency.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/sase_ace_startup_latency.md).

The research repo is clean and synchronized. Recommended solution: cached-first, stale-while-revalidate startup, with deferred diff badges and lazy AXE history loading. Prompt-archive publication was deferred due to a busy sync lock, but the report commit itself succeeded.
