%id(final, clan=research.02) %wait(priority=20) %m:@research_lead
%wait:research.02.cdx %wait:research.02.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I recently migrated xprompt skills to the sase/skills/
directory and allow users to invoke them via xprompt invokations that have the
`#skills/` prefix. Work is also in-progress to migrate sase memories to xprompts that
use the `#memory/` prefix when invoked (see the sase-hf epic bead for context). I would
like to also start making artifact references (ex: `@commit` or `@research`) defined by
xprompts as well. These should allow the user to customize what text gets substituted
for these artifact references (we should consider supporting other useful customizations
too--spend some time thinking about this) when rendered while providing builtin
functionality that is useful for all artifacts (e.g. artifact reference usage tracking,
artifact linking, etc...). Can you do some research with the goal of helping me decide
the best way to implement this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.02.cdx` -> `__a`, `research.02.cld` -> `__b`), then read both reports.
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