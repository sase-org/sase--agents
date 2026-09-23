- **AGENTS:**
  - [bbugyi200.athena.research.2d.final](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2d.final/README.md)

%clan(research.2d, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I think I
want to redesign the agent metadata panel and files/LLM calls panels on the "Agents"
tab.

- Namely, I want to unify these using a new concept that I will name "agent data
  decks/cards" (aka "decks/cards"). Appropriate glossary memory web strands should be
  added.
- Instead of supportig two different types of panels (the agent metadata panel and the
  files/LLM calls panel), we will support just one panel type (a "deck panel") that
  hosts one or more agent data cards.
- Deck panels will render their cards dynamically based on the size of their contents.
  - We will prefer to render all cards on the same page (with clear, visually appealing
    separation of cards) if the size of the panel would not be forced to go over some
    configurable (via a new sase config field) threshold.
  - If that threshold is crossed, then we should render each card on its own page which
    the user can cycle through using the `<ctrl+shift+n/p>` keymaps, which you will need
    to add. This is inspired by how the files panel currently works. In fact, when the
    combined size of the files crosses our configured threshold, we should be able to
    cycle through the different files that used to be shown in the files panel in the
    "Files" deck (one card per file).
- How should the current contents of the agent metadata panel and files/LLM calls panels
  be migrated to decks/cards?
  - The agent metadata panel should be migrated to a "Main" deck that contains two
    cards:
    - One named "Context" that contains the `SASE CONTEXT`, `SLOW TOOLS`,
      `AGENT XPROMPT`, and `AGENT PROMPT` sections (this card should also contain any
      sections / content that I am forgetting about). This should be the default card
      shown (though the entire "Main" deck should be shown if it doesn't cross the
      threshold).
    - One named "Reply" that contains the `AGENT REPLY` section.
  - The migration for the files panel is described above.
  - The LLM calls panel should be migrated to a "Tools" deck with a single card for now
    (I plan on adding another card that works with the `sase tool` command at some point
    later).
- We should support two different "deck layouts" to start (controlled by the `\` / `|`
  keymaps described below):
  - A vertical layout with one deck on the left and one on the right.
  - A horizontal layout with one deck on the top and one on the bottom.
- We will need to add the following keymaps to the "Agents" tab:
  - `<ctrl+shift+n/p>`: Described above.
  - `<ctrl+n/p>`: Used to cycle the currently focused deck panel to the next/previous
    deck.
  - `\`: Used to create a new horizontal split (i.e. add a new deck panel below the
    current deck).
  - `|`: Create a new horizontal split (i.e. add a new deck to the right of the current
    deck panel).
  - `<ctrl+s>`: Used to collapse/expand the panel of nodes shown on the left of the
    "Agents" tab. Support for collapsing the node panel will be useful/necessary for
    vertical deck splits (and obsoleting the zoom panel, which should probably be done
    as a part of this work). Think hard about the best way to represent a collapsed node
    panel.
  - `<ctrl+f>`: Used to toggle which deck panel is currently focused. This should be
    used to control which panel we are acting on.
- More on the `\` and `|` keymaps:
  - We should automatically open the next, not currently shown, deck (if any--otherwise,
    show the current deck) when these keymaps are used and there is only one deck shown
    at the moment.
  - If a vertical split already exists and the `|` keymap is used, we should go back to
    showing a single deck (we should do the same thing for the `\` keymap when a
    horizontal split is already shown).
  - If the opposite type of split is currently shown when these keymaps are used, then
    we should keep the current decks visible but switch the layout accordingly.
- The panel that is triggered by the `p` keymap on the "Agents" tab currently can
  probably just be removed.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]])
%id:research.2d.final %m:@xlarge %wait:research.2d.cld %wait:research.2d.mus
%wait:research.2d.gem %q(w=0.25) #gh:gh_sase-org__sase You are the lead researcher: 3
independent researchers have reported on the request below, and you will add your own
research and merge every perspective into one consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I think I want to redesign the agent metadata panel and files/LLM calls panels on the
"Agents" tab.

- Namely, I want to unify these using a new concept that I will name "agent data
  decks/cards" (aka "decks/cards"). Appropriate glossary memory web strands should be
  added.
- Instead of supportig two different types of panels (the agent metadata panel and the
  files/LLM calls panel), we will support just one panel type (a "deck panel") that
  hosts one or more agent data cards.
- Deck panels will render their cards dynamically based on the size of their contents.
  - We will prefer to render all cards on the same page (with clear, visually appealing
    separation of cards) if the size of the panel would not be forced to go over some
    configurable (via a new sase config field) threshold.
  - If that threshold is crossed, then we should render each card on its own page which
    the user can cycle through using the `<ctrl+shift+n/p>` keymaps, which you will need
    to add. This is inspired by how the files panel currently works. In fact, when the
    combined size of the files crosses our configured threshold, we should be able to
    cycle through the different files that used to be shown in the files panel in the
    "Files" deck (one card per file).
- How should the current contents of the agent metadata panel and files/LLM calls panels
  be migrated to decks/cards?
  - The agent metadata panel should be migrated to a "Main" deck that contains two
    cards:
    - One named "Context" that contains the `SASE CONTEXT`, `SLOW TOOLS`,
      `AGENT XPROMPT`, and `AGENT PROMPT` sections (this card should also contain any
      sections / content that I am forgetting about). This should be the default card
      shown (though the entire "Main" deck should be shown if it doesn't cross the
      threshold).
    - One named "Reply" that contains the `AGENT REPLY` section.
  - The migration for the files panel is described above.
  - The LLM calls panel should be migrated to a "Tools" deck with a single card for now
    (I plan on adding another card that works with the `sase tool` command at some point
    later).
- We should support two different "deck layouts" to start (controlled by the `\` / `|`
  keymaps described below):
  - A vertical layout with one deck on the left and one on the right.
  - A horizontal layout with one deck on the top and one on the bottom.
- We will need to add the following keymaps to the "Agents" tab:
  - `<ctrl+shift+n/p>`: Described above.
  - `<ctrl+n/p>`: Used to cycle the currently focused deck panel to the next/previous
    deck.
  - `\`: Used to create a new horizontal split (i.e. add a new deck panel below the
    current deck).
  - `|`: Create a new horizontal split (i.e. add a new deck to the right of the current
    deck panel).
  - `<ctrl+s>`: Used to collapse/expand the panel of nodes shown on the left of the
    "Agents" tab. Support for collapsing the node panel will be useful/necessary for
    vertical deck splits (and obsoleting the zoom panel, which should probably be done
    as a part of this work). Think hard about the best way to represent a collapsed node
    panel.
  - `<ctrl+f>`: Used to toggle which deck panel is currently focused. This should be
    used to control which panel we are acting on.
- More on the `\` and `|` keymaps:
  - We should automatically open the next, not currently shown, deck (if any--otherwise,
    show the current deck) when these keymaps are used and there is only one deck shown
    at the moment.
  - If a vertical split already exists and the `|` keymap is used, we should go back to
    showing a single deck (we should do the same thing for the `\` keymap when a
    horizontal split is already shown).
  - If the opposite type of split is currently shown when these keymaps are used, then
    we should keep the current decks visible but switch the layout accordingly.
- The panel that is triggered by the `p` keymap on the "Agents" tab currently can
  probably just be removed.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}

- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }}
  path={{ a.path }} ref={{ a.ref }} {% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix in
   cld, mus, gem, belonging to this dispatch's `research.2d.cld`, `research.2d.mus`,
   `research.2d.gem` dependencies, matching by `wait_name` and the canonical research
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
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```
