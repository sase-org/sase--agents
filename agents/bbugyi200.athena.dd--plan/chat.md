# Chat History - ace-run (dd--plan)

- **TIMESTAMP:** 2026-07-18 10:01:23 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** dd--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-dd__plan-260718_095558.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260718_095558.md`

**Plan:** /home/bryan/.sase/plans/202607/gate_primary_footer.md


## Prompt

#gh:gh_sase-org__sase Instead of "Submit primary" for the `<enter>` keymap on the sase gate panel in the TUI (see #sshot for context) can we show the name of the primary option (ex: "Tale" in the case of the screenshot) instead and make this keymap description in the footer stand out a bit more? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/gate_primary_footer.md`

> # Plan: Gate primary action footer
> ## Context and outcome
> The branch-driven plan and custom gate modals currently describe their primary-submit binding as “Submit primary.” That
> wording exposes the gate model instead of telling the reviewer what will happen, and the hint has no stronger visual
> hierarchy than secondary actions. The plan-review screenshot makes the consequence clear: the primary Tale button is
> visually prominent in the panel, but its matching `Enter` shortcut is easy to miss and requires the user to translate
> “primary” back to “Tale.”
> Replace that implementation-oriented description with the declared primary branch's display name and give the whole
> key/action pair a restrained call-to-action treatment. A tale plan should read `Enter=Tale`; an epic plan should read
> `Enter=Epic`; a custom singleton or group should use its configured option or group label. This is a footer-only

*See full plan file for details.*

