%id(final, clan=research.v) %wait(priority=20) %m:@research_lead %wait:research.v.cdx %wait:research.v.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request below, and you will add your own
research and merge all three perspectives into one consolidated report.

Research request:

I want to allow users to customize sase finalizers
via a new `%final` directive. Can you do some research to help me decide the
best way to implement this?

- First of all, we should generalize our current finalizer so users can define
  their own.
- Users should be able to disable the default finalier (and any additional
  default finalizers we add later).
- We should support multiple finalizers (we already have one builtin finalizer
  that requires the agent to commit changes).
- We should make each finalizer configurable (a prompt used for the finalizer
  followed by a custom script that is run and some extra configuration, like
  retry attempts, trigger conditions, other finalizers that this one depends on,
  etc...) and provide plugin support (i.e. allow sase plugins to define their
  own finalizers in sase plugin repos).
- We should expect all agents to set sase variables for the finalizer to read
  (see the sase-be epic bead for some related work that sets us up for this).

End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote (`research.v.cdx` -> `__a`,
   `research.v.cld` -> `__b`), then read both reports. Never assign `__a`/`__b` from filesystem order.
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