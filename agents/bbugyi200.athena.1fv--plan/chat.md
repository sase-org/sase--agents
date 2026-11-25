# Chat History - ace-run (1fv--plan)

- **TIMESTAMP:** 2026-11-25 07:02:05 EST
- **MODEL:** claude/opus
- **AGENT:** 1fv--plan

**Plan:** /home/bryan/.sase/plans/202611/prompt_composer_rename.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/prompt_composer_rename.md`

> # Rename the prompt input widget to "Prompt Composer"
> ## Goal
> The TUI's bottom-docked prompt-authoring widget currently has several names: "prompt
> input widget", "prompt bar", "prompt input bar", "prompt widget", and "prompt input".
> This change makes **Prompt Composer** the one canonical name everywhere a user or agent
> reads it:
> 1. Add a `Prompt Composer` glossary strand to the glossary memory web. Its aliases are
>    `composer`, `prompt bar`, and `prompt input widget`.
> 2. Update the documentation and the user-visible TUI strings to say "prompt composer".
> Background: the research report

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase I would like to rename the prompt input widget to "prompt composer" (update any
appropriate documentation) and add a new glossary term for "prompt composer"? See the
prompt_composer_glossary_term.md file in the research sidecar repo for context.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

Looking up the research report in the research sidecar, then I'll study the prompt input widget code.

Found the report; reading it now via the audited artifact path.

Report read. Now surveying how the widget is named across code, docs, and memory.

Reviewing existing glossary strand files and the memory-write rules before drafting the plan.

Now cataloguing user-visible strings (help text, keymap descriptions, notifications) that name the widget.

Checking docs nav/redirects and config-schema descriptions that feed generated docs.

Checking whether visual snapshots (glossary highlight, help, onboarding) would be affected by the new strand or renamed strings.

Still mapping the docs anchor/move machinery so the rename doesn't break deep links.

Checking how the `ace.md` legacy-anchor stubs are generated (affects the heading rename).

Verifying the key bindings the strand will cite still match current docs, then I'll write the plan.

Exploration is done; drafting the plan now. One quick check of the `docs_move` CLI for the optional page-move branch.

Plan validates; fixing the one remaining warning (memory selector coverage for the new strand file).

Validation is clean. Doing a final read-through of the plan before proposing it.

Both alias spellings resolve. Tightening two phrases in the plan, then proposing.

Staged. Finishing the turn through `/sase_final`.

I've submitted the plan for the rename and the glossary term. Nothing has been changed in the repo yet; work starts once you approve it in review.

**What the plan does** (one agent, medium size):
- **Glossary term:** adds a `Prompt Composer` glossary entry with the aliases `composer`, `prompt bar` and `prompt input widget`, so the old names still lead to it. The entry covers the widget, how its prompt stack and panes work, and its property panel. The draft is taken from the research report and checked against current docs. The generated agent instructions and the docs glossary page are then regenerated so they include it.
- **Docs:** retitles `docs/reference/tui/prompt-input.md` and its nav label to "Prompt composer" and renames its "Prompt Input Widget" heading. It also retitles the "Authoring a snippet from the prompt bar" heading in `snippets.md`. Both renamed headings keep their old anchors, so existing links and blog posts still work. About 30 other docs pages get their wording updated, plus the config option descriptions that the generated config docs come from.
- **TUI text:** renames the help section "Prompt Input", the onboarding text, the jump-modal option, and several notifications. It updates the tests that check those strings and re-captures only the three screenshot sets whose text changes (onboarding, help panel, jump action).
- **Left alone:**
  - Code names such as `PromptInputBar`, `FrontmatterPanel` and `#prompt-input-bar`, as the research recommended.
  - Internal comments.
  - `CHANGELOG.md` and blog posts.
  - The unrelated "Prompt Inputs" feature (`ace.prompt_inputs`), which the plan's rules say must not be renamed.

**Choices you'll make when reviewing:**
1. **`page_path`** (default: keep): keep the page's URL, or move it to `prompt-composer.md` with a redirect from the old one.
2. **`property_panel_name`** (default: property): the entry calls the panel above the stack the "property panel", the research's pick. It notes that its title bar and the docs say "frontmatter panel".
3. **Glossary memory change** (default: on): adding the glossary entry, which you asked for.

A full code-level rename (about 230 files and roughly 50 module renames) isn't in this plan; it would need its own plan.
