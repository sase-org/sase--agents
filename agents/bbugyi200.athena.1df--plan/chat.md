# Chat History - ace-run (1df--plan)

- **TIMESTAMP:** 2026-11-17 10:17:07 EST
- **MODEL:** claude/opus
- **AGENT:** 1df--plan

**Plan:** /home/bryan/.sase/plans/202611/bead_preview_large_card.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/bead_preview_large_card.md`

> # Make the `K` bead preview card much larger
> ## Problem
> Pressing `K` on a bead ID in the prompt input opens `BeadPreviewModal`. It inherited the
> compact-card sizing of its siblings, the glossary and repo cards. In
> `src/sase/ace/tui/styles.tcss`:
> - `BeadPreviewModal > Container` uses
>   `width: auto; max-width: 84; height: auto; max-height: 80%`.
> - `BeadPreviewModal #bead-preview-scroll` is capped at `max-height: 20` cells. A comment
>   explains why the cap is in cells: auto-height parents ignore `%`/`fr`/`vh` caps on
>   their children before the first layout, which would clip the in-flow footer.

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase We recently added support to the `K` keymap in the prompt input widget for beads.
Can you now help me make the panel that pops up to preview the bead much larger? See the
~/tmp/screenshots/20261117_092846.png screenshot for an example of what this looks like
now.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

I'm looking at how the bead preview modal is styled and sized so I can plan a larger layout.

Still exploring: I'm checking where the child order comes from (the screenshot sorts phases as .1, .10, .11 …) and which tests pin the modal's current size.

I'm comparing the bead card's CSS with the other modals' sizing to pick a consistent "large" size. Next I'll look at the shared preview-panel sizing helper.

Next I'm checking whether any test parses this TCSS or asserts the card's geometry, and where the child ordering comes from.

The child order comes from the Rust `bead_show_issue_detail` binding, so it's outside this sizing change. I'll quickly check whether the CLI shows the same order before deciding how to report it.

The original epic sized this as a "compact card" matching the glossary and repo cards. Next I'm checking whether the docs describe it that way and what else depends on the 84-column width.

The docs call it a "compact bead card", so the plan will update that line. Next I'm reading the docs-writing and lint/test memory notes the plan depends on.

The plan will replace the hard-coded 66-dash separator, so I'm checking whether any test asserts on it, and how the existing modal tests mount the card.

The modal tests use a bare `App` that doesn't load `styles.tcss`, so a geometry test needs a different harness. I'm checking how other tests apply the real stylesheet.

I'll follow the `_StyledTestApp` pattern (point `CSS_PATH` at the real `styles.tcss`). Next I'm checking test file sizes against the repo's line limit.

Only the bead-preview snapshot file opens this card. Last check: whether the CLI lists child phases in the same `.1, .10, .11` order the card showed.

Validation passes. Submitting the plan.

I've written the plan and submitted it for your approval; no code has been changed yet. It's a single-agent plan sized `small`.

**Why it's small today:** the bead card copied the compact sizing of the glossary and repo `K` cards. In `styles.tcss` it's at most 84 columns wide, and its scrollable body stops at 20 rows. On your ~256×80 terminal that's about 84×32, which is why only phases 1–9 of `tailnet-x` were visible.

**What the plan does:**
- **Size:** the card becomes 90% of the terminal's width and height, with width capped at 160 columns so description text stays readable on very wide screens. On your terminal that's about 160×72; on 120×40 it's 108×36.
- **Layout:** the body fills all the space between the title and the footer, using the same layout as the `K` file preview. The footer hints stay visible at every size, including 100×30.
- **Separator:** the line above the property grid is a fixed 66 characters today. It will span the card's full width instead.
- **Tests:** new layout tests run against the real stylesheet. They check the frame size, the 160-column cap, that the footer stays visible on small terminals, and the separator width.
- **Screenshots:** the four existing bead-card goldens get regenerated and reviewed. One new golden shows a long epic on a 200×60 terminal.
- **Docs:** `docs/reference/tui/prompt-completion-panels.md` stops calling it a "compact bead card".

**One decision for you at review:** should a short bead fill the whole large frame, or get a shorter card that grows with its content?
- **`fixed`** (the default) always opens the full frame, like the `K` file preview, and needs only CSS changes. The cost is empty rows on short beads.
- **`fit`** keeps short beads short and adds a small Python hook that recalculates the body height when the terminal is resized.

**Not included:**
- The glossary and repo cards stay compact; you only asked about beads.
- In your screenshot the phases are listed `.1, .10, .11, … .2`, so pressing `2` opens `.10`, not `.2`. That order comes from the Rust core (`bead_show_issue_detail`), and the CLI shows yet another order. I didn't file a bead for it; tell me if you want one.
