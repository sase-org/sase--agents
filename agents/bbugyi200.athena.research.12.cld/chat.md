# Chat History - ace-run (research.12.cld)

- **TIMESTAMP:** 2026-08-24 18:29:40 EDT
- **MODEL:** claude/opus
- **AGENT:** research.12.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260824_180955.md`

## Prompt

%id(cld, clan=research.12) %m:@research_b  #gh:gh_sase-org__sase I was working on improving artifact links when it was brought
to my attention (see the artifact_link_derivation.md file in the research sidecar repo
for context) that the "Agents" sub-tab of the "Artifacts" tab is a major missing piece
that prevents us from fully benefiting from artifact links.

- My plan is therefore to:
  1. Implement the "Agents" sub-tab.
  2. Make the improvements / fix the defects related to artifact links which are
     referenced in the artifact_link_derivation.md file in the research sidecar repo.
  3. Add a rich integration with artifact links to every tab in the TUI (even chops can
     link to the agent artifacts they were responsible for launching!).
- The "Agents" sub-tab should support excellent filtering via a query language that
  integrates well with the shared query infrastructure already used by the artifacts
  tab. I'm not sure how much work has already been done here but we want to make sure
  this new agent query language is exceptionally useful.
- We should still support the custom agent revival panel on the main "Agents" tab
  (triggered via the `R` keymap I think), but we should also support reviving agents
  from this new "Agents" sub-tab (since it should, ideally, be much easier to query
  from). We might deprecate the custom agent revival panel in favor of the "Agents"
  sub-tab at some point, but I'm not sure yet.
- We should keep the 2nd (artifact link improvements / fixes) and 3rd (TUI integration)
  steps in mind while implementing the new "Agents" sub-tab but they will initially be
  out of scope.

Can you do some research with the goal of helping me decide the best way to implement
this new "Agents" sub-tab on the "Artifacts" tab? Flesh out any open questions that
should be answered before implementation, but try your best to provide a default /
recommended answer for each of these questions. End your analysis with a recommended
solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by reading the research doc that motivated this, then explore the relevant TUI and query infrastructure.

Now I have enough evidence. Writing the report.

Research written to `sase/repos/research/202608/artifacts_agents_pane.md` (662 lines).

## What I found

I read `artifact_link_derivation.md`, then measured the live stores rather than reasoning from the code alone. Three findings drive the recommendation:

**1. No single store can back the pane.** Of the 55 distinct `agent:` refs in your live link graph, the agent **name registry** resolves 55/55, the agents sidecar 46/55 (84%), the dismissed-bundle index 33/55, and the agent artifact index only **4/55** — dismissed agents get pruned out of it. So: registry as identity spine, artifact index + bundle index left-joined for attributes (together they enrich 92.7% of 12,318 registry entries). Cold complete snapshot ≈370 ms on a worker thread; the join itself is 16 ms.

**2. The revival pane's real defect is already solved on disk.** `dismissed_bundles/index.sqlite` holds all **26,657** rows with `agent_name`/`status`/`model`/`provider`/`workflow`/timings columnar, and full-scans in **167 ms**. The current `R` → custom-search modal ignores it and offset-pages 26,657 JSON *files*, which is why it can only filter what it has already loaded.

**3. `agent:0b4` resolves to the wrong agent.** The sidecar page says a 2026-07-01 run; the local registry says `0b4` is a family container created 2026-08-22 whose member wrote the actual link row. Short names get recycled. I flagged this as a defect to file (Q12) and made the pane design not depend on `agent:<name>` being unique across time.

## Recommendation

Registry-backed rows; author `agents_query_schema()` as a **profile** (`boolean=True`) in the shared infrastructure and **delete `sase/ace/agent_query/`** (1,189 LOC fork) by migrating the Agents tab onto it — prior research already tagged it as the third dialect to fold in. Revive calls the existing `_do_revive_agent` app mixin; keep `R`, but reroute its `custom_search` escape hatch into the new pane with a seeded query. Five phases, dialect and row model landing headless first, Agents-tab migration last so it's revertible alone.

Twelve open questions each carry a default answer — including the one real regression I couldn't design around: the shared grammar has no general comparison operator, so `age>2h` has to become `min:2h` (with input sugar preserving the spelling). I noted a second instance of that gap (`retry` is equality-only) and said what would justify changing the closed host vocabulary.

Two corrections I made while drafting, since they change implementation details: `STABLE_MARKS` derives from `has_inventory`, not `has_stable_identity`; and a dialect gets exactly **one** `min`/`max` numeric range, spent here on runtime.
