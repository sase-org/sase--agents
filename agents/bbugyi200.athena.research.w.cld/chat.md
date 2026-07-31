# Chat History - ace-run (research.w.cld)

- **TIMESTAMP:** 2026-07-31 16:33:04 EDT
- **MODEL:** claude/opus
- **AGENT:** research.w.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260731_161739.md`

## Prompt

%id(cld, clan=research.w) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I wanna start using GLM 5.2 with sase. Can you do some research to help me understand the best way to achieve this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. First, let me understand what "GLM 5.2" refers to and how sase handles model/provider configuration.

The research doc is written. Two concrete bugs surfaced during the investigation that the project instructions say to capture as beads — let me file those.

Research written to `sase/repos/research/202607/glm_5_2_sase_integration.md`.

## Recommendation

**Add a first-class `glm` LLM provider plugin that reuses the Claude Code CLI as a harness but injects Z.ai's Anthropic-compatible endpoint per-subprocess** — then introduce GLM through the `@cheap`/`@cheaper` alias pools, not as `@default`.

The reasoning, in short:

**Why not the obvious thing.** Z.ai's documented setup (put `ANTHROPIC_BASE_URL`/`ANTHROPIC_AUTH_TOKEN` in `~/.claude/settings.json`) is an all-or-nothing hijack. Every agent, finalizer, and one-shot invocation becomes GLM, while `%model claude/opus` keeps *reporting* opus in ACE headers and statistics. Your alias pools become fiction and you can't run both backends at once. Fine as a smoke test; wrong as an answer.

**Why the plugin is cheap.** GLM ships behind an Anthropic-shaped API, so the Claude Code client works unmodified — and the stream-json parsing, tool-call capture, usage artifacts, hooks, skills, and commit workflow all live on the *client* side, so they're unaffected by swapping the API host. Per-provider env injection is already an established pattern here (`codex.py:463` yields a shadow `CODEX_HOME`; `agy.py:575` augments env). `claude.py:329` just happens not to use it. The new logic is roughly one env-builder function plus metadata hooks.

**Three findings worth flagging:**

1. **`%model:` silently truncates `glm-5.2[1m]` → `glm-5.2`**, and swallows any trailing `@effort` with it. Verified empirically in the workspace. You'd quietly get a standard-context agent believing it had 1M. The design works around this by exposing a bracket-free `glm-5.2-1m` and translating inside the provider.
2. **`llm_skill_deploy_subpath` must be explicitly `".claude"`.** The default is `f".{provider}"` (`_init_skills_sources.py:29`), so a provider named `glm` would deploy your SASE skills to `~/.glm/skills` where Claude Code never looks — the most likely silent failure in a naive build.
3. **The provider must scrub `ANTHROPIC_API_KEY`/`CLAUDE_CODE_OAUTH_TOKEN`** from the child env. SASE inherits ambient environment, so without this you'd hand Anthropic credentials to a third-party host on every request.

**Suggested sequence:** spike it first with shell env vars and `%model claude/glm-5.2` on one throwaway agent (~30 min) to confirm hooks/skills/commit behave — that de-risks everything before you write code. Then build the provider, then run a week of `@cheaper` phase workers on it. The real unknown is quota: GLM meters *prompts per 5-hour window* with a 2–3× multiplier on 5.2, which sits awkwardly against SASE's parallel fan-out.

Two related bugs filed as ready task beads: **sase-cs** (the `%model:` truncation) and **sase-ct** (`claude.py:257` hardcodes `"claude"`, ignoring `SASE_CLAUDE_PATH` that detection and doctor both honor).

One thing I deliberately left as a decision rather than a finding: routing agents through Z.ai sends full repo context to a third-party, China-based provider under their terms. Worth making that call consciously before the first non-toy agent runs.

I made these changes. Let me commit them.

Single untracked file, and both finalizer entries point at the same path. Committing once.

Repo history uses `docs(research):`. Writing the message.

Committed. Working tree is clean and `main` is level with `origin/main` — no ahead marker, so the push went through.

## Summary

The finalizer listed `research` twice — once as a linked repo, once as an SDD sidecar — but both entries resolve to the same path (`sase/repos/research`), so one commit covered both.

- **Committed:** `202607/glm_5_2_sase_integration.md` (new, untracked) as `docs(research): evaluate GLM 5.2 integration options for sase`, matching the `docs(research):` tag the repo's history already uses for research docs.
- **Verified:** `git status --short --branch` clean, branch in sync with upstream.

No other repos were dirty. The two task beads filed earlier (**sase-cs** for the `%model:` bracket truncation, **sase-ct** for `claude.py:257` hardcoding `"claude"` over `SASE_CLAUDE_PATH`) live in the bead store and needed no separate commit here.
