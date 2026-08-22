%id(final, clan=research.0w) %m:@research_lead
%wait:research.0w.cdx %wait:research.0w.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to add support for stand-alone proc shells (i.e.
shells that don't belong to an agent family) to sase.

- MOTIVATION
  - This will allow the user to run commands that claim (and release when appropriate)
    sase project workspaces.
  - These proc shells should also support standard xprompt directives when possible and
    useful (the `%wait` directive should be supported to wait for agents or anything
    else that directive supports, for example).
- REQUIREMENTS
  - We should introduce a new `%proc` directive to support this functionality.
  - The `%proc` directive should be able to be used in xprompt swarms and should thus
    support excellent multi-line and single line syntax.
  - For multi-line syntax, let's start supporting code blocks after the `::` with the
    `%proc` directive and as a new, general-purpose type (I want to be able to specify
    this type as a xprompt input argument at some point in the future). This code block
    may or may not contain a language specifier. If it doesn't, we should default to
    using Bash.
  - For single-line syntax, let's accept a string argument (execute that string as a
    Bash script), a `bash=` kwarg (the same as the string case), and a `python=` kwarg
    (execute the string as a Python script--I'm thinking we should probably inject
    sase's environment here, right? Otherwise why use a Python script?).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0w.cdx` -> `__a`, `research.0w.cld` -> `__b`), then read both reports.
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