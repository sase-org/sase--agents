# Chat History - ace-run (research.01.cld)

- **TIMESTAMP:** 2026-08-07 15:27:19 EDT
- **MODEL:** claude/opus
- **AGENT:** research.01.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260807_151438.md`

## Prompt

%id(cld, clan=research.01) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I want to add a sase LLM provider for Meta's new Muse Code agentic harness. Can you do some research to help me understand what this would entail? End your analysis with a recommended approach/solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by understanding how sase's LLM provider system works, and in parallel look into what "Muse Code" actually is.

Let me first check the research directory and the provider architecture.

There's an `llm_provider` package. Let me explore it and research Muse Code in parallel.

Muse Code is real and shipped 2026-08-05 — after my training cutoff. Let me dig into its actual CLI surface while reading sase's provider contract.

Now let me get the deep technical details on Muse Code's CLI and map the full sase integration surface.

Found `docs/agent_providers.md` — likely the canonical "how to add a provider" guide. Let me read the remaining touchpoints.

Let me get the authoritative Meta developer blog and check the last few sase surfaces.

I have what I need. Per the repo rules, let me open the research sidecar properly before writing to it.

Written to `sase/repos/research/202608/muse_code_llm_provider.md` (in the research sidecar, opened via `sase repo open`).

## What I found

**Muse Code is real and two days old.** Meta Superintelligence Labs shipped it 2026-08-05 — a `muse` binary for macOS/Linux, installed via `curl -fsSL https://dev.meta.ai/install.sh | bash`, powered by the co-trained Muse Spark 1.2 model. It postdates my training cutoff, so everything came from the web.

**The good news: it's structurally a Codex clone.** Muse's headless mode is reportedly `muse exec "<prompt>" --json` streaming JSONL to stdout — the same shape as `codex exec --json`, which sase already supports at `src/sase/llm_provider/codex.py:364`. The provider class is ~250 lines modeled on that file, plus a stream parser, plus one line in `pyproject.toml`. Autodetect, `%model:muse/...` routing, `muse_coder` aliases, `foo.mus` agent naming, and `sase agent-cli` inventory all fall out of declarative pluggy hooks for free.

**The real cost is breadth, not depth**: ~16 hand-edited files. I inventoried them by grepping every `opencode` reference — doctor hints, ACE styles, emoji badges, and about nine separate sites in `docs/llms.md`.

## Three things worth your attention

1. **Every flag I found is unverified, and sources actively contradict each other.** One deep dive documents `muse exec`, `--json`, `--yolo`, `META_API_KEY`, `.agents/skills/`, and exit codes. Another guide published the same week says subcommands, flags, MCP, AGENTS.md support, and auth env vars are all "not documented at launch." Notably, *no* source documents a `--model` flag or any reasoning-effort control. I graded every fact by confidence and made recon a blocking Phase 0.

2. **Muse's persistent background subagents compete with sase's clan/family/lane model.** One `muse exec` could silently fan out to 14 subagents on a 16-core box — none of which sase can name, attribute, bead, or show in ACE. I recommend accepting the opacity for v1 rather than fighting a co-trained harness feature, with subagent event projection as a follow-up.

3. **Two smaller items:** Muse's sandbox makes `.git` read-only to the agent, which may break `sase commit` — worth testing before reaching for `--yolo`. And the `small` tier maps to `muse-spark-1.2-contributor`, whose usage may train Meta products; that belongs in the docs, not buried in a tier table.

**Recommendation: in-tree sixth built-in provider, four phases, ~2.5–3 days after a blocking ~1-hour recon phase.** The plugin route looks tempting for an unstable beta but requires importing private `_subprocess_*` internals and cross-repo edits anyway.

I did not file a task bead for the implementation — that's your call on scoping.

Sources: [Meta AI Developers blog](https://developer.meta.com/ai/resources/blog/build-with-muse-code/) · [Digital Applied deep dive](https://www.digitalapplied.com/blog/muse-code-deep-dive-fan-out-event-log-skills) · [Layer3 Labs](https://www.layer3labs.io/guides/muse-code-explained) · [muse-code.dev](https://muse-code.dev/) · [MarkTechPost](https://www.marktechpost.com/2026/08/05/meta-superintelligence-labs-releases-muse-code/) · [TechCrunch](https://techcrunch.com/2026/08/05/meta-launches-muse-code-an-ai-agent-for-large-code-bases/) · [VentureBeat](https://venturebeat.com/orchestration/meta-enters-the-ai-coding-wars-with-muse-spark-1-2-and-muse-code-with-persistent-async-background-agents) · [The Register](https://www.theregister.com/ai-and-ml/2026/08/06/meta-wants-to-get-inside-your-terminal-with-its-new-coding-agent/5283717)

I made these changes in this session — the research file is mine. Let me commit it.

Confirmed: one untracked file, the research note I wrote. Committing via the commit skill.

The repo convention is `docs(research):`. Let me confirm the file content before writing the message.

Committed and pushed.

## What I did

Committed the research note to the research sidecar as `c4aa9be docs(research): analyze adding a Muse Code LLM provider`. `git status --short --branch` shows `## main...origin/main` with no dirty files and no ahead/behind marker — clean and in sync with the remote.

The finalizer listed `research` twice (once as a linked repo, once as an SDD sidecar), but both entries point at the same path, so the single commit covers both.

## The deliverable

`202608/muse_code_llm_provider.md` — 593 lines covering what Muse Code is, sase's provider contract, the mapping between them, where the fit breaks down, options considered, the recommended approach, and a per-file change checklist.

The three findings worth remembering from it:

- **It's structurally a Codex clone.** Muse's headless mode mirrors `codex exec --json`, so the provider class is ~250 lines modeled on `src/sase/llm_provider/codex.py`. Autodetect, `%model:muse/...` routing, and ACE inventory fall out of the declarative pluggy hooks for free. The real cost is breadth — ~16 hand-edited files — not depth.
- **Every flag is unverified and sources contradict each other.** One deep dive documents `muse exec`, `--json`, `--yolo`, and `META_API_KEY`; another from the same week says all of that is undocumented at launch. No source documents a `--model` flag at all. That's why recon is a blocking Phase 0 rather than something to discover mid-implementation.
- **Muse's persistent background subagents compete with sase's clan/family/lane model.** One `muse exec` could fan out to subagents sase can't name, attribute, or show in ACE. The note recommends accepting that opacity for v1.

Recommendation in the note: in-tree sixth built-in provider, four phases, ~2.5–3 days after a ~1-hour recon phase.

I did not file a task bead for the implementation — that's still your call on scoping.
