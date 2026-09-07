# Chat History - ace-run (research.1l.cld)

- **TIMESTAMP:** 2026-09-07 14:08:06 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1l.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260907_134141.md`

## Prompt

%id(cld, clan=research.1l) %m:@research_b 
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1l.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I want to add support for integrating an LLM provider's usage
metrics into sase.

- In particular, users that are using their subscription instead of the API for the
  given provider are interested in how much usage they have remaining until they hit a
  limit.
- We should support this in a generic fashion that allows us to easily add support for
  any new LLM provider that might get added to sase in the future.
- We may eventually integrate input/output token usage, billing data, and other
  statistics for API users as well but this will not be a part of our initial solution.
- To start I was planning on implementing this for only the Claude provider, the Codex
  provider, and the Grok provider.
- I currently need to use the following URLs to check my usage limits manually. It would
  be much easier if they were shown in the TUI directly somewhere:
  - https://claude.ai/new#settings/usage
  - https://chatgpt.com/codex/cloud/settings/analytics#usage
  - https://grok.com/?checkout=success&tier=SUBSCRIPTION_TIER_GROK_PRO&interval=monthly&revenue=30&currency=USD&_s=usage

Can you do some research with the goal of helping me decide the best way to implement
this? Think hard about how to reliably fetch the current user's remaining usage before
hitting a limit for each of the three providers we intend to support at first. End your
analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
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

I'll start by understanding the SASE codebase's provider architecture, then research each provider's usage-limit surface.

I have all three providers solved. Writing the report now.

File written intact. Registering the artifact:

Research complete. Report written and registered.

**File:** `sase/repos/research/202609/llm_provider_usage_metrics__b.md`
**Artifact:** `research:202609/llm_provider_usage_metrics__b.md` → `explicit:5daa0a632420fa730c79e183`

## Headline finding

All three providers can be solved the same way, and it isn't the way most third-party usage monitors do it. **Every one of the three CLIs SASE already shells out to will report its own subscription usage over a local, zero-cost interface.** I verified all three live on athena:

| Provider | Probe | Cost | Latency |
|---|---|---|---|
| claude | `claude -p --output-format json "/usage"` | `total_cost_usd: 0`, `num_turns: 0` | 1.7 s |
| codex | `codex app-server` JSON-RPC → `account/rateLimits/read` | none | 1.0 s |
| grok | `grok agent stdio` ACP → `_x.ai/billing` (leading `_` is required) | none | 0.4 s |

Real numbers pulled during the research: Claude session 6% / week 25% / week-Fable 30%; Codex weekly 9% plus 3 unused rate-limit-reset credits; Grok weekly pool 49%, resets 2026-09-11.

Grok looked like the weak leg — `grok.com/rest/rate-limits` explicitly 403s OAuth tokens, and its `/usage` slash command is session-token-only. But `xai-grok-shell` ships an `x.ai/billing` extension that returns `creditUsagePercent` plus the weekly period and a per-product breakdown, matching the grok.com Usage tab.

## Two things worth your attention

**The Anthropic policy matters here.** The direct `GET api.anthropic.com/api/oauth/usage` endpoint works (undocumented; recovered from the 2.1.263 binary), but Anthropic's legal page restricts consumer OAuth tokens to Claude Code and native Anthropic apps and forbids third parties intermediating those credentials. The same page explicitly permits running the *unmodified binary*. Since `claude -p "/usage"` is free and sits on the right side of that line, I recommend CLI-only by default, with any HTTP fallback opt-in and using an honest `sase/<version>` UA — never impersonating `claude-code/<version>`, which is exactly what the policy targets.

**I rejected the option you'd ask about first.** Harvesting usage from the NDJSON SASE already parses doesn't work: Claude's print-mode `result` has no rate-limit fields (verified by running it), and `codex exec --json` uses the v2 thread-event schema, which drops the `rate_limits` member the raw protocol carries.

## Recommended shape

Normalize onto `used_percent` + `resets_at` — the only unit all three vendors agree on. Then follow the split epic `sase-n4` already established: probes as a new `llm_usage_probe()` pluggy hook in the provider plugins (so a fourth provider is a plugin change), durable snapshot store in `sase_core::provider_usage` as a sibling of `provider_disable.rs`, refresh from a durable proc on a 5-minute cadence, TUI reads only through a lock-free peek. Top-bar pill next to `ProviderDisablesIndicator`, plus a table in the Models panel, plus `sase usage` / `sase doctor`.

The follow-on I deliberately left out of scope: once a live percentage exists, SASE's existing **soft** provider disable lets you drain pools toward other providers at ≥90% *before* anyone hits a wall — inverting `sase-n4` from reactive to proactive. Worth designing the wire contract for, not worth shipping in v1.

§13 has four open questions for you, the sharpest being whether to ship the HTTP fallbacks at all.
