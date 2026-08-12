# Chat History - ace-run (research.0c.cld)

- **TIMESTAMP:** 2026-08-12 18:17:23 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0c.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_180049.md`

## Prompt

%id(cld, clan=research.0c) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I want to add an llm provider to sase that supports grok. I think that there is a grok-cli tool available, right? Can you do some research to help me decide the best way to implement this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding how sase's LLM provider abstraction works today, and in parallel look into grok-cli.

I have everything I need. Writing the research document now.

Research written to `sase/repos/research/202608/grok_llm_provider.md`.

## What I found

**On your question — yes, but there are two "grok CLIs", and it's not the one you're probably thinking of.**

- `superagent-ai/grok-cli` is the one that popularized the name. It's since been renamed `grok-dev`, and **its last release was 2026-05-15** — ten days before xAI shipped their own CLI. Bespoke JSON event stream, API-key-only billing.
- **xAI's own "Grok Build"** (`grok`, `@xai-official/grok`) is the real target. It hit `1.0.0` on 2026-08-07 and shipped `1.0.3` *today*. Apache-2.0, source-available at `xai-org/grok-build`.

**The decisive finding:** Grok Build ships `--output-format streaming-messages-json`, which is deliberately wire-compatible with Claude Code's `stream-json` — its docs say "a consumer that reconstructs messages, reads spend, or detects errors works without changes." I verified the four token-usage field names match `initial_usage_totals()` exactly, both against the vendor docs and against the Rust serializers in `wire.rs`.

That means SASE reuses `_subprocess_claude.py` and `_tool_call_claude.py` **unchanged**. Every other provider (Codex, Qwen, OpenCode, Muse) needed a bespoke pair of both. Grok also gets `.grok` skill deployment and semver version parsing from SASE's defaults with no hooks, and needs no Rust core changes — so the work collapses to one provider module plus a ~5-line shared fix.

**Recommendation:** native in-tree `grok` provider on `streaming-messages-json`, registered explicit-only (no autodetect priority — `grok-dev` claims the same binary name *and* `~/.grok/`). Three stages, with the only real blocker being an authenticated account to capture test fixtures and the real model catalog.

## Verification approach

Rather than trusting blog posts, I installed `@xai-official/grok@1.0.3` into an isolated npm prefix (`/tmp/grokprobe`, still there if useful) and ran it under an isolated `HOME` — `--help`, every relevant subcommand's help, `inspect --json`, `models`, and argument-parse probes of the exact argv a SASE provider would emit. The 166 MB Rust binary embeds its full documentation, which is where the output-format schemas came from.

Two things worth flagging beyond the recommendation:

- **`grok inspect --json` in this workspace loads both `CLAUDE.md` and `AGENTS.md`** — identical content, 2,829 tokens each, injected twice. SASE generates both, and Grok's docs confirm top-level `CLAUDE.md` stays recognized even with Claude-compat disabled. Documented as a measured gotcha with a deferred follow-up.
- `--yolo` is accepted by the parser but absent from `--help`; `--permission-mode bypassPermissions` is the safer choice.

No changes to the sase repo itself (the research sidecar is a separate, gitignored checkout), so no `just check` was needed. The file is uncommitted — say the word if you'd like it committed, or a task bead filed for the implementation.

Sources: [Introducing Grok Build](https://x.ai/news/grok-build-cli) · [CLI Reference](https://docs.x.ai/build/cli/reference) · [Headless & Scripting](https://docs.x.ai/build/cli/headless-scripting) · [Grok Build overview](https://docs.x.ai/build/overview)

That's the file I wrote this session. Committing it.

Now writing the commit message.

Committed and pushed. Working tree is clean and in sync with `origin/main`.

## Summary

**Commit:** `6bc8240` — `docs(research): evaluate Grok CLI options for a SASE LLM provider` in the `research` sidecar (`sase/repos/research`). The finalizer listed the path twice (once as a linked repo, once as an SDD sidecar), but it's the same checkout, so one commit covered both entries.

The commit adds `202608/grok_llm_provider.md` (594 lines), the research note answering your question. Its findings, unchanged from the analysis:

- There are **two** tools called "grok-cli". The community one (`superagent-ai/grok-cli`, now `grok-dev`) is stale since 2026-05-15 and emits a bespoke event stream. xAI's own **Grok Build** (`@xai-official/grok`, 1.0.0 on 2026-08-07) is the integration target.
- Grok Build's `--output-format streaming-messages-json` is deliberately wire-compatible with Claude Code's `stream-json`, down to the four token-usage field names — so a Grok provider reuses `_subprocess_claude.py` and `_tool_call_claude.py` unchanged, where every other provider needed a bespoke pair. No Rust core changes.
- **Recommendation:** native in-tree `grok` provider, registered explicit-only (no autodetect priority, since `grok-dev` claims the same binary name and `~/.grok/`).

Verification was done by installing `@xai-official/grok@1.0.3` into an isolated npm prefix and running it under an isolated `HOME`; claims requiring an authenticated xAI account are quarantined in one section and the recommendation doesn't rest on them.

Two notes on the commit itself:

- A pre-commit hook (`sase_git_fix`) ran clean. The stitch also produced a preceding `eb605d2 docs: research Grok provider integration` commit as part of its own bookkeeping.
- The tool reported one deferred step: **prompt archive publication was deferred** because the agents sync lock was busy. It will retry via agent publication. The code commit itself succeeded and pushed — this only affects the archived prompt record, not the file.

No changes were made in the sase repo itself, so `just check` wasn't applicable. The implementation work has no task bead filed yet — worth running `/sase_new_task` if you want it queued.
