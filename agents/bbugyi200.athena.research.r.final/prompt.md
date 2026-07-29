%id(final, clan=research.r) %wait(priority=20) %m:@research_lead %wait:research.r.cdx %wait:research.r.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I recently produced some research (see the sase_sites_platform.md file in the research sidecar repo) related to an initiative to support sase sites, which are meant to be custom (though with a structured framework / expected API usage by site readers/writers) HTML websites that can be shared with agents/humans (e.g. teammates) and read from / written to by sase agents. Can you do some more research to help me refine this idea a bit?

- It seems like the original research is leaning towards having two different types of sase sites: A project site and a custom site.
- I would like to explore the idea of instead just supporting a single generic sase site that can be linked with zero or more other sase sites and/or artifacts.
- To produce the project sase site for each enabled sase project, we could just start producing a single sase site for every meaningful sase artifact, like plans and beads and agents for example, and then linking them all together under the same project site. This perhaps acts like a structural /hub node that specifies tabs and website layout.

End your analysis with a recommended approach.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote (`research.r.cdx` -> `__a`,
   `research.r.cld` -> `__b`), then read both reports. Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory (do NOT end the name with
   `_consolidated` or `_<YYYYmmdd>` or anything similar unless it relates to the research topic), create
   `<month-dir>/<name>/`, and move the two reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files
   and never overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings from both reports and your own
   research, resolve conflicts, cut duplication, and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```