%id(final, clan=research.1)
%wait(priority=20) %m:@xlarge
%wait:research.1.cdx %wait:research.1.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

Very often when using the new Artifacts Links panel to jump
to a linked artifact, I receive an error toast saying that that artifact is no longer
available on that tab. For the Patch tab what we used to do for situations like this
(for the `<enter>` keymap on the "Agents" tab, for example) is change the current search
query on that tab to an appropriate query that matches the missing PR in the case of
that tab (this way we could then jump to that PR/patch entry). The user would then be
able to switch back to the query that they were using previously by using the `^` keymap
(which should be supported on all sub-tabs of the "Artifacts" tab). I want to make the
links panel significantly more reliable, to the point where these types of errors
virtually never happen, using a similar strategy.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.1.cdx` -> `__a`, `research.1.cld` -> `__b`), then read both reports.
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