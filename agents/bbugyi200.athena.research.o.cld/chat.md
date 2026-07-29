# Chat History - ace-run (research.o.cld)

- **TIMESTAMP:** 2026-07-29 06:52:26 EDT
- **MODEL:** claude/opus
- **AGENT:** research.o.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260729_064015.md`

## Prompt

%id(cld, clan=research.@) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I've been thinking about creating a new /sase_search_skills xprompt skill that allows me to create skill bundles. The goal would be to allow skills to scale better since currently every skill has its description added to context for every agent, which is not ideal for all skills. Can you do some research to help me decide the best way to implement this? You should also audit all existing xprompt skills for good skill bundle candidates. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current xprompt skill system.

There's already a related research doc. Let me read that plus the memory file.

Substantial prior research exists (2026-07-07). Now let me check what's changed in the code since then, and audit the actual skill sources.

Now let me verify a few implementation-relevant facts before writing.

Facts gathered. Writing the report.

Research written to `sase/repos/research/202607/xprompt_skill_bundles_search_20260729.md`.

## What I found

**Current cost is measured, not guessed.** The 17 deployed skills cost **2,900 chars ≈ 725 tokens** of always-loaded Level-1 context — 36% of Claude's default 8,000-char listing budget. Bodies are 73KB but already free. Marginal cost is ~170 chars per new skill; ~30 more average skills hits the cliff, where Claude *silently* drops descriptions and Codex silently omits skills.

**Telemetry (4,138 uses):** `sase_git_commit` + `sase_beads` = 85% of all invocations. Fifteen skills share the rest.

## The key design call

Your instinct is right, but I'd move the deferral unit. The prior research (2026-07-07, unimplemented) proposed one flat search skill — O(1) context, but its known weakness is that the model has to *think* to search, and "search the skill catalog" has poor semantic overlap with any real task.

**Make the bundle the always-listed entry**, with `/sase_search_skills` as the cross-bundle fallback and the retrieval verb the bundle bodies delegate to. A bundle description ("Inspect SASE's own state: running agents, prior chats, notifications, ChangeSpecs, projects") actually matches "what did agent X say?" — the model matches a domain, then reads a free Level-2 index. This is also where the 2026 literature landed (GoSkills, Graph-of-Skills: +25% reward, −57% tokens vs. loading all).

**Frequency is the wrong tiering axis.** The right split is *prohibitive* vs *permissive*: `sase_repo` is only 2.9% of uses but exists to stop the agent web-fetching a repo — if it never fires, the agent does the wrong thing and never learns it was wrong. Must stay pinned.

## Audit result

- **6 pinned** — `sase_git_commit`, `sase_beads`, `sase_repo`, `sase_memory_read`, `sase_questions`, `sase_plan`
- **Bundle A `sase_introspect`** (chats/project/notify/agents_status/changespecs) — 1,035 → ~230 chars, **4.5x compression**, highest cohesion, ship this first
- **Bundle B `sase_agent_io`** (gate/run/var/artifact_file) — 429 → ~200
- **Bundle C `bryan_personal`** (bob_query/sase_gmail) — tiny saving, but it's the proof case for user-authored bundles from `~/sase/xprompts/`, which is the real growth vector

Net: 2,900 → ~1,950 (−33%), or ~1,650 (−43%) with a free `sase_repo` description trim. **The point is the last row: skill #19 costs ~0 instead of ~170.**

## Three things worth acting on immediately

1. `sase_hg_commit` declares `skill: [gemini]`, but no `gemini` provider is registered — it **deploys nowhere**. Flagged on 2026-07-07, still unfixed. One-line fix to `[agy]`.
2. `sase_repo`'s 419-char description is 14% of the entire listing and restates a rule already in Tier-1 memory. Trim = 10% cut, zero mechanism.
3. **A tempting shortcut that doesn't work:** Claude's `disable-model-invocation: true` removes a description from context entirely while keeping `/name`. But it blocks the *Skill tool*, not just the menu — and `sase_git_commit` is invoked by the agent, prompted by `commit_finalizer_prompting.py:76`. It would break 44% of skill traffic. Checking the whole catalog, **no skill qualifies today** — even `bob_query` has agent-driven uses.

I didn't run `just check` — the only change is a new markdown file in the research sidecar, and no files in the sase repo were touched.

I made these changes — committing now.

Committed.

**`933b74d docs(research): evaluate skill bundles and a search meta-skill`** — research repo is clean and in sync with `origin/main`. The finalizer listed the file twice (once as linked repo `research`, once as SDD sidecar `research`), but both resolve to the same path, so one commit covers it.

The only artifact from this session was the new research report; no files in the sase workspace repo were touched, so `just check` doesn't apply.

**The report's bottom line:** bundle the *bundle*, not a single flat search skill. Keep 6 prohibitive/high-traffic skills pinned, group 11 into three bundles (`sase_introspect` first — 4.5x compression, highest cohesion), and ship `/sase_search_skills` as the cross-bundle fallback that bundle bodies delegate to. Net −33% on the always-loaded listing today, but the real win is that skill #19 costs ~0 instead of ~170 chars.

Three things worth acting on independent of the bundle work: `sase_hg_commit` deploys nowhere (declares an unregistered `gemini` provider), `sase_repo`'s description is 14% of the listing and restates Tier-1 memory, and `disable-model-invocation` is a dead end — it blocks the Skill tool itself, which would break the agent-driven `sase_git_commit` path.
