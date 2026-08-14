# Chat History - ace-run (research.0i.cld)

- **TIMESTAMP:** 2026-08-14 08:57:22 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0i.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260814_084958.md`

## Prompt

%id(cld, clan=research.0i) %wait(priority=20) %m:@research_b  #gh:gh_sase-org__sase I'm thinking about subscribing to a Supergrok account. Can you do some research to help me understand the different price tiers available and the benefits of each one? End your analysis with a recommendation for which tier I should subscribe to. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research SuperGrok pricing tiers for you. Let me start by loading the web tools.

Let me open the research repo properly and start the web research in parallel.

Good — sources converge. Let me verify against primary/official sources and check your existing Grok research for context.

Your prior research shows you're integrating Grok Build into SASE — that reframes the recommendation. Let me research the coding-agent access question specifically.

I have enough corroborated material. Writing the report now.

Written to `sase/repos/research/202608/supergrok_subscription_tiers.md`.

## The tier ladder (Aug 2026)

Seven consumer rungs, four of them actually "SuperGrok":

| Tier | Price | Notes |
|---|---|---|
| Free | $0 | Evaluation only |
| X Premium | ~$8/mo | Social-first, incidental Grok |
| SuperGrok Lite | $10/mo | Imagine-focused, 1 agent, no full DeepSearch |
| **SuperGrok** | **$30/mo** ($300/yr) | Cheapest complete product |
| X Premium+ | ~$40/mo | ≈SuperGrok Grok access + X perks |
| SuperGrok Plus | $100/mo | Capacity relief; launched ~Aug 1 |
| SuperGrok Heavy | $300/mo | 3–5× limits, video, bundles X Premium+ free |

## Recommendation: SuperGrok, $30/month, billed monthly

Two findings drove this rather than the generic "$30 is the sweet spot" line:

**The shared weekly pool.** Paid plans don't meter products separately — Chat, Imagine, Voice, Build, *and* API draw from one weekly pool. So above $30 you're buying capacity and priority, not capability (except video on Heavy, app-deploy on Plus). Your Grok Build sessions and casual chat compete for the same meter.

**Lite is disqualified, not just weaker.** Grok Build subscription auth reportedly works with SuperGrok and X Premium+ only. Given your live `grok` provider integration in SASE, $10 doesn't buy the use case at all — $30 is the hard floor.

Monthly over annual: the ~$60/yr discount is real, but the lineup shifted twice in five months (Lite in March, Plus in August) and Grok 4.6 shipped two days ago. Lock-in isn't worth $60 right now.

**The highest-value move in the report** is what to do *if* you exhaust the pool: don't jump to Plus at $100. Move automated SASE runs onto `XAI_API_KEY` (metered, attributable per-run, immune to consumer fair-use throttling that could stall an agent mid-task) and keep the $30 subscription for interactive use. That hybrid will very likely land under $100/mo.

## Two caveats on the evidence

- **No first-party page was machine-readable** — `x.ai`, `grok.com/pricing`, and Grokipedia all returned 403. Prices are corroborated across independent secondary sources but not vendor-confirmed. The tier *structure* is solid; glance at live checkout before paying.
- **Ignore circulating limit numbers, including the ones I quoted.** Standard SuperGrok's message allowance is reported as both 1,000/day and ~100/day — a 10× disagreement that says the aggregators are guessing. Settings → Usage in your account is the only trustworthy figure.

I did not file a task bead for the SASE-side follow-up (whether to add API-key-backed provider auth alongside subscription auth) — say the word if you want me to run that through `/sase_new_task`.

The file I wrote this session is untracked. Committing it via the commit skill.

Committed.

**`21654c8` — `docs(research): compare SuperGrok subscription tiers`** in the `research` repo (`202608/supergrok_subscription_tiers.md`, 306 lines).

`git status --short --branch` shows `main...origin/main` with no divergence markers and no dirty paths — clean and in sync with upstream. The pre-commit `sase_git_fix` hook ran without changes. The finalizer listed the repo twice (linked + SDD sidecar), but both entries point at the same path, so the single commit covers both.

The commit message records the two load-bearing findings — the shared weekly pool across Chat/Imagine/Voice/Build/API, and Grok Build auth being limited to SuperGrok and X Premium+ — plus the caveat that no first-party pricing page was machine-readable (403 from x.ai, grok.com/pricing, and Grokipedia).
