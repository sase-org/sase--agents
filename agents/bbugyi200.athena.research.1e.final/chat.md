# Chat History - ace-run (research.1e.final)

- **TIMESTAMP:** 2026-08-30 12:42:34 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1e.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260830_121835.md`

## Prompt

%id(final, clan=research.1e) %m:@research_lead
%wait:research.1e.cdx %wait:research.1e.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Sase's memory webs are inspired by Hub notes.

- See the
  https://writing.bobdoto.computer/the-difference-between-hub-notes-and-structure-notes-explained/
  article for context.
- According to that article, "By pointing to where particular trains of thought can be
  found, indicated by the first note in the sequence, hub notes make it easy to find
  areas of your zettelkasten you'd like to explore.".
- For memory webs, the `sase/memory/<web>.md` file is analogous to a hub note in a way
  currently since it points to many different memory strand files.
- The problem with memory webs is that all memory strand files are always referenced.
  Ideally, we should be able to have one memory strand supersede another, which should
  result in the superseded note being rendered (either "inline" or as a "reference")
  when the new note is read via the `sase memory show/read` commands.
- The superseded memory file would then not be shown in the hub note (and thus would not
  be rendered in the "Memory Webs" section of agent instruction files).
- For the "sase" sase project, this functionality will be useful for the decisions
  memory web (since new decisions might supersede old ones), for example.
- Make sure that agents are aware of the ability of memory strands to supersede one
  another by updating the /sase_memory_write xprompt skill's instructions.

Can you do some research with the goal of critiquing the above idea? Is it worth doing
at all? End your analysis with either a recommended solution or justification for why
you think I should not proceed with this idea.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.1e.cdx` -> `__a`, `research.1e.cld` -> `__b`), then read both reports.
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

## Response

I'll start by reading both researcher transcripts to identify their report files.

Now let me look at the month directory and understand the artifact-read path.

`__a` = cdx = `memory_web_strand_supersession_critique.md`; `__b` = cld = `memory_strand_supersession.md`. Reading both via the audited path.

Both reports are strong but reach opposite conclusions. Let me verify the load-bearing claims myself, starting with B's central technical claim.

Confirmed empirically — the `![[...]]` link renders as literal text. Now gathering my own independent data.

Now the key structural question neither report resolved — where the roster actually reaches agents. Let me check the roster generator.

All of B's technical claims check out (including the ACE-panel one my narrower grep missed). Let me prove the proposed one-line fix actually works, since neither report demonstrated it.

`resolve_memory_selector_batch` takes a `project_root` override — I can test the fix in a temp tree without touching the repo.

The workspace clone lacks the built Rust extension. The code path is decisive on its own — and there's a side effect neither report checked.

The fix is provably surgical. Let me check one precedent neither report examined — whether any SASE roster already filters or annotates entries.

Verified. Now let me set up the output directory.

Note the artifact link index tracks these by path. Let me check before moving.

The layout convention is clear. Moving the reports and their link indexes.

Now fixing the relative links inside report A that broke when it moved into a subdirectory.

One design question decides the A-vs-B conflict: whether `metadata` is free-form enough to carry supersession without new syntax.

All claims verified. `metadata` is a free-form `dict[str, Any]` — which resolves the central disagreement. Writing the consolidated report.

Let me verify the output — structure, fences, and cited paths.

Every line citation and commit hash resolves correctly. Final layout check:

Consolidated report written and both source reports preserved.

**Layout** (`sase/repos/research/202608/superseding_memory_strands/`):
- `superseding_memory_strands__a.md` — cdx report
- `superseding_memory_strands__b.md` — cld report
- `superseding_memory_strands.md` — consolidated (448 lines)

## What the two researchers found, and where they split

Both independently landed the two strongest points, and both hold up under verification: hiding superseded records contradicts *both* cited models (Doto's hub notes are a locating device that never prunes; ADR practice flips a **status** field and keeps the record listed), and the corpus's one real supersession is **partial** — `webs-render-in-their-own-section` retires *one sentence* of `memory-webs`, which a third record still cites. Hide it and you delete an authoritative record; don't, and the mechanism has zero uses.

They split on the remedy: **A** wanted a typed `supersedes:` frontmatter edge with roster hiding; **B** wanted no new mechanism — fix a config bug, render the existing `metadata.status`, document the link system.

## What I verified and added

**B's central technical claim is real, and I confirmed it live.** `decisions.md` declares `closure: none`, which `frontmatter.py:279-281` maps to `link_reference: none`, which makes `selector.py:390` skip every authored link. An audited read of `decisions:gates-never-block` returns a literal `![[decisions/single-turn-agents]]` mid-sentence — the link you added today is dead text.

Three things neither report established:

1. **The one-line fix is provably side-effect-free.** `_closure_for_link_reference` returns `"mentions"` only for `implicit` (`frontmatter.py:244-245`), so `link_reference: explicit` yields closure mode `none` — identical behavior to today except links work. No reason to defer it.

2. **The read log reframes the design.** Decision strands have **9 audited reads ever** (4 of 8 records: zero), against 3,960 agents who receive the roster every turn. So B's read-time banner lands almost nowhere, and A is right that the roster is the surface that matters — but wrong to hide there. **The synthesis both missed: annotate the roster.** It reaches every agent, preserves the audit trail, and can express *partial* supersession, which a hide/show boolean cannot.

3. **A's design collides with the governing decision more expensively than A prices.** `memory-webs`' reopen clause names artifact relations as adopted "— not a new, parallel link syntax." A's field is exactly that, so A's plan requires first writing a decision superseding that clause — a mechanism whose prerequisite is a use of itself. Unnecessary: `metadata` is a free-form `dict[str, Any]`, so scoped supersession is expressible **today with zero parser change**.

Also verified: `sase_memory_write.md` is 49 lines mentioning `[[…]]`, `link_reference`, and Linked References **zero times**, and `docs/memory.md` still teaches the spelling that disables links.

**Recommendation: proceed, but build annotation, not supersession machinery.** Fix the one line; add a scoped `[[…]]` back-pointer to `memory-webs.md`; annotate the roster from `metadata.status` with a doctor check; render status on read (on stdout — the artifact precedent it mirrors prints to stderr, which agents may miss); document the link system. Don't build roster hiding, a parallel typed edge, or any coupling of `sase memory init` to the artifact link store — A's §5 argument for that last one is correct and I've kept it.

One caveat on the reopen threshold: B argues the corpus is too small to have outgrown prose. The sharper reason is that prose was **never tried** — `memory-webs.md` carries no mark at all. That's an enforceability failure at n=1, not a scale failure, so the first move is to use the convention once and make it validatable.
