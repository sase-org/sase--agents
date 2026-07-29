# Chat History - ace-run (research.o.cdx)

- **TIMESTAMP:** 2026-07-29 06:57:34 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.o.cdx
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260729_064015.md`

## Prompt

%clan(research.@, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I've been thinking about creating a new /sase_search_skills xprompt skill that allows me to create skill bundles. The goal would be to allow skills to scale better since currently every skill has its description added to context for every agent, which is not ideal for all skills. Can you do some research to help me decide the best way to implement this? You should also audit all existing xprompt skills for good skill bundle candidates. End your analysis with a recommended solution.]]) %id:research.@.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I've been thinking about creating a new /sase_search_skills xprompt skill that allows me to create skill bundles. The goal would be to allow skills to scale better since currently every skill has its description added to context for every agent, which is not ideal for all skills. Can you do some research to help me decide the best way to implement this? You should also audit all existing xprompt skills for good skill bundle candidates. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll use the SASE memory-read guidance for xprompt/generated-skill internals, then the repo-opening workflow for the research sidecar. I’ll audit every existing xprompt skill, compare bundle/search designs, and finish the report with one concrete recommendation.

The applicable guidance requires audited reads of two long-term notes—`generated_skills.md` and `xprompts.md`—before inspecting or proposing changes in this area. I’m doing those reads now, then I’ll inventory the source templates and deployed skill surface.

The research sidecar is now opened at the exact requested path. I’m treating `src/sase/xprompts/skills/` as the canonical audit set (the deployed copies are generated), and I’ll cross-check generator/runtime code so the recommendation fits today’s loading model instead of assuming a new one.

Because the bundle idea depends on what Codex actually preloads versus progressively opens, I’m also using the official OpenAI documentation workflow for that narrow point. The SASE recommendation will remain provider-neutral, per the repo’s runtime-uniformity rule.

The canonical package has 16 skill templates, but the effective runtime catalog has a 17th config-supplied skill (`sase_gmail`). I’m including the effective catalog—not just package defaults—so “all existing” reflects what agents actually see. I’ll also use the skill-use audit log as evidence, with the caveat that three foundational skills deliberately disable use logging.

The key measurement is now clear: the effective catalog has 18 xprompt skills, whose names/descriptions/source paths total about 4,552 characters before host formatting. Codex’s documented initial skill-list budget is 2% of context (or 8,000 characters when unknown), so SASE alone already consumes a meaningful share even though it has not crossed the cap. I’m validating the proposed second disclosure layer against the open skill specification next.

The design crosses SASE’s shared frontmatter contract, so the repo instructions require checking the Rust core boundary too. I’m opening the linked core checkout through the audited repo workflow and tracing the exact schema/wire changes the proposal would need.

The design comparison favors a single search gateway over “one umbrella skill per bundle”: per-bundle umbrellas still make startup cost grow with bundle count, while a gateway can keep startup exposure constant and return only top matches. I’m now checking the July research directory’s naming/style, then I’ll write the full audit, migration design, risks, and final recommendation.

There is a directly relevant earlier report, `xprompt_skill_description_progressive_disclosure.md`. I’m incorporating it as prior art and explicitly separating what still holds from what the current code/docs/usage audit changes; the new deliverable will not just duplicate it.

The report is written. I’m doing a final integrity pass now: checking the sidecar’s own instructions, Markdown whitespace/link structure, the full 18-skill audit, and that the file ends—per your request—with the recommended solution rather than trailing appendices.

The content checks passed structurally, but the sidecar’s Markdown formatter reported style drift. I’m applying its standard formatter, then rerunning the 18-row and final-section assertions.

Created [sase_search_skills_bundles_research.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202607/sase_search_skills_bundles_research.md).

The report:

- Audits all 18 effective xprompt skills.
- Recommends one visible `/sase_search_skills` gateway with four hidden bundles.
- Identifies eight skills that should remain top-level.
- Details schema, Rust/Python, search/load, deployment-manifest, testing, and rollout changes.
- Flags the still-broken `sase_hg_commit` provider selector.
- Ends with the recommended solution as requested.

Formatting and structural checks passed. The new file remains uncommitted in the research sidecar.

The research file is mine, so I’m handling the finalizer by using the required SASE commit workflow in the research sidecar, scoped only to that new Markdown file. Afterward I’ll verify the sidecar is clean.

The scoped diff contains only the new 497-line research report; there are no unrelated changes to include. I’m committing it as documentation with a message limited to the research deliverable.

Committed the research report as `5a5baad` (`docs: research scalable xprompt skill bundles`).

The [report](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202607/sase_search_skills_bundles_research.md) is pushed, and the research repository is clean and synchronized with `origin/main`. Auxiliary agent-hood publication was queued for automatic retry because its sync lock was busy.
