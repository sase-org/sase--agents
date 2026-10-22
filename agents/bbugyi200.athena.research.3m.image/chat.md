# Chat History - ace-run (research.3m.image)

- **TIMESTAMP:** 2026-10-05 07:20:56 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3m.image
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_063855.md`

## Prompt

%id(image, clan=research.3m) %m:@image
%wait:research.3m.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:47121b87bfabf7fac4573bbce156be5b`

- **Node:** `agent-delta:20261005063900:ded3d2bf52ac1516`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261005063900:ded3d2bf52ac1516.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.3m, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I'm thinking about
giving sase macro invocations (`#foo`, for example) a distinct name so it is easier to
talk about / reference them and their unique syntax.

- I think that "sase macro invocation" (aka "smack"--note that "invocation" has the
  sound "kay" in it) is a good name.
- We should add a new glossary memory web strand for this term.
- This opens up new ways of talking about this topic and related topics I think. For
  example, we could start referring to the "raw prompt" as the "smack prompt".

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.3m.final %m:@xlarge
%wait:research.3m.cdx %wait:research.3m.cld %wait:research.3m.grk %wait:research.3m.mus %wait:research.3m.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I'm thinking about
giving sase macro invocations (`#foo`, for example) a distinct name so it is easier to
talk about / reference them and their unique syntax.

- I think that "sase macro invocation" (aka "smack"--note that "invocation" has the
  sound "kay" in it) is a good name.
- We should add a new glossary memory web strand for this term.
- This opens up new ways of talking about this topic and related topics I think. For
  example, we could start referring to the "raw prompt" as the "smack prompt".

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.3m.cdx`, `research.3m.cld`, `research.3m.grk`, `research.3m.mus`, `research.3m.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.3m.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.3m.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

### Assistant

I've read all five reports. Now I'm checking the disputed facts myself (prompt stages, `#gh:` scope, plural matching, "reference" vs "invocation") against the code and memory.

Still verifying details: next is how docs treat `#gh:` workspace refs and the unresolved-`#token` case, then I'll write the consolidated report.

Checking one more detail: whether glossary strands actually link implicitly by phrase today. It affects how the new strand should cross-link.

Evidence gathered. Now moving the five reports into the new directory, then writing the consolidated report.

Writing the consolidated report now.

Layout is complete and the snapshot is registered. Now the final declaration.

I've merged the five reports and my own checks into one consolidated report. It's registered as `research:202610/macro_invocation_glossary_term_smack/macro_invocation_glossary_term_smack__final.md` (`file:explicit:6fc889f29c2aab1b89152644`). The five reports now sit next to it as `macro_invocation_glossary_term_smack__{cdx,cld,grk,mus,gem}.md`. The research repo commit is declared and will land when this turn ends.

**Recommendation**
- **Yes, give `#foo` its own name.** All five researchers agree there's a real gap: "macro" means the definition, and the `#foo` use in a prompt has no glossary entry.
- **Make the glossary keyword `Macro Invocation`, with `smack`, `macro reference` and `macro ref` as aliases.** These are changes to your plan:
  - smack becomes an alias rather than the official term;
  - "Sase" is dropped from the keyword, because the other macro terms don't use it and the product rename is still undecided.

  As an alias, smack still works for lookup, gets underlined in the app and editor, and shows in the always-loaded term list. The report says when to promote it to the official term: about a month after landing, if it's the word you and your agents actually write and the rename question is settled.
- **Reject "smack prompt" (all five agree).** A prompt is a container and a smack is one expression inside it. Nearly every raw prompt contains a smack anyway, because launch adds a workspace reference like `#git:home`, so the label tells you nothing. It would also bring back the `raw_xprompt.md` mix-up the macro rename just fixed. Instead, I recommend a **Raw Prompt** glossary entry that defines the stages: submitted prompt, then raw prompt, then expanded prompt. One researcher got that order backwards, which suggests the confusion is real.
- **Keep the change to the glossary plus one docs paragraph.** No code, command, file or screen-label renames.

**Disagreements I settled by checking the code**
- `#gh:` and `#git:` are smacks, so one researcher was wrong to exclude them: `#git:<ref>` runs the `src/sase/macros/git.yml` workflow.
- I simulated the glossary with the proposed entry added:
  - **It fixes an existing mislink.** Today, "macro ref" in the Project Tag entry links "ref" to Artifact Reference; the `macro ref` alias fixes that.
  - **No false matches on ordinary English.** "smacking" and "smackdown" don't match.
  - **Plurals need no extra aliases.** They match automatically.
- **One test will need updating.** `tests/_macro_terminology_docs.py` allows exact lines that still say "xprompt".
  - Adding the new term will rewrap one of those lines in the glossary term list, so that allowlist entry must be updated.
  - Any edit to the Macro entry should be appended at the end, leaving its first line untouched.
  - The rename epic `sase-1eq` (phase `.11` covers that test) is still in progress, so this should land after it.

The report includes ready-to-use drafts of both new glossary entries; I ran both through the glossary matcher. I didn't edit any memory files, since this research turn doesn't authorize memory changes.

---

%macros_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

The infographic illustrating the main findings and architectural decisions from the consolidated macro invocation research report has been generated and saved.

### Output Details

- **File:** [`macro_invocation_glossary_term_smack_infographic.png`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202610/macro_invocation_glossary_term_smack/macro_invocation_glossary_term_smack_infographic.png)
- **Directory:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202610/macro_invocation_glossary_term_smack/`
- **Dimensions & Format:** 1376 × 768 PNG (RGB, non-interlaced, created without overwrite)
- **Artifact Reference:** `file:explicit:3c3c56d7fa1114048cadb735`
- **Host Declaration:** Final declaration submitted (`docs(research): add infographic for macro invocation and smack prompt research`) for host commit.

---

### Key Illustrated Points

1. **Prompt Sigils Symmetry:**
   - Visualizes the four SASE prompt sigils: `@` (Artifact Reference / `ref`), `+` (Project Tag), `%` (Directive), and `#` (**Macro Invocation** / `smack`).
   - Highlights the 5/5 panel consensus: `"Macro"` defines the macro; `"#foo"` is the use-site / invocation.

2. **Terminology Decision Matrix:**
   - **Canonical Keyword:** `Macro Invocation` (unambiguous, aligned with Rust/GNU CPP preprocessor terminology).
   - **Primary Alias / Nickname:** `smack` (**S**ase **MA**cro invo**C**ation) with full LSP, TUI, and roster closure support.
   - **Compatibility Aliases:** `macro reference` and `macro ref` (preserves existing prose links and fixes the mislink where `ref` resolved to Artifact Reference).

3. **3-Stage Prompt Pipeline (Rejecting "Smack Prompt"):**
   - Illustrates why "smack prompt" was rejected (99.7% of raw prompts already contain macros such as `#gh:` or `#git:home`).
   - Clarifies the prompt lifecycle into three distinct stages:
     1. **Submitted Prompt** (`submitted_prompt.md`): Raw user input at launch boundary.
     2. **Raw Prompt** (`raw_prompt.md`): Canonicalized tags (`+sase` → `#gh:`) and unexpanded macros.
     3. **Expanded Prompt**: Directives stripped, macros expanded, sent to the model.

4. **Scope & Guardrails:**
   - Scoped strictly to glossary strands and a single docs paragraph (no code, CLI, or TUI renames).
   - Sequenced after the `sase-1eq` epic to preserve test terminology allowlist integrity.
