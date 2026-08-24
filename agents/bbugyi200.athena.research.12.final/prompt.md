%id(final, clan=research.12) %m:@research_lead
%wait:research.12.cdx %wait:research.12.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I was working on improving artifact links when it was brought
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
solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.12.cdx` -> `__a`, `research.12.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```