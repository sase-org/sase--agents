%id(final, clan=research.q) %wait(priority=20) %m:@research_lead %wait:research.q.cdx %wait:research.q.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I've been thinking a lot about codex sites and how SASE can take inspiration from that. Can you do some research with the goal of helping me understand the best way to implement SASE sites?

- We already have agents, beads, and plans sidecar repos. I want to use this to support the ability to create a SASE site that encapsulates all knowledge from these repos in one site, with multiple tabs of course and other niceties.
- I also want to write a /sase_sites xprompt skill that allows agents to fetch and create new sase sites.
- I'm thinking we should create a new sase web server to support this new functionality but use your best judgment.

End your analysis with a recommended solution including a high-level design/plan.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote (`research.q.cdx` -> `__a`,
   `research.q.cld` -> `__b`), then read both reports. Never assign `__a`/`__b` from filesystem order.
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