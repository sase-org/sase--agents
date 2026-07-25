# Chat History - ace-run (athena.j9--plan)

- **TIMESTAMP:** 2026-07-23 12:40:14 EDT
- **MODEL:** claude/opus
- **AGENT:** athena.j9--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-athena_j9__plan-260723_121620.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-athena_j9__code-260723_121620.md`

**Plan:** /home/bryan/.sase/plans/202607/pdf_plan_properties.md


## Prompt

The user sent an image via Telegram with the following caption:

#gh:gh_sase-org__sase As shown in the attachment, PDF plan files that are attached to Telegram plan approval messages do not include any of the frontmatter properties that were defined in that plan file. Can you help me fix this by showing all of those properties in the plan file somehow? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
  %model:opus

The image has been saved to: /home/bryan/.sase/telegram/images/20260723_161618_AgACAgEAAxkB.jpg
Please read the image file and respond to the user's request.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/pdf_plan_properties.md`

> # Render plan frontmatter as a Properties card in Markdown PDFs
> ## Problem
> When a plan is proposed, SASE attaches a PDF rendering of the plan `.md` to the Telegram plan-approval message. That PDF
> shows the plan body but **none of the YAML frontmatter properties** (`tier`, `title`, `goal`, `model`, and, for epics,
> `phases`, plus system fields such as `create_time`, `status`, `bead`, `parent`, `bead_id`). The reviewer therefore
> cannot see the plan's metadata in the PDF at all — the document jumps straight into the body.
> ## Root cause
> The Markdown->PDF conversion is `render_markdown_pdf()` in `src/sase/attachments/markdown_pdf.py`. It hands the raw
> `.md` file directly to `pandoc` (see `_pandoc_cmd()` and the `subprocess.run(cmd, ...)` call inside
> `render_markdown_pdf`). Pandoc's Markdown reader natively treats a leading `---` ... `---` YAML block as **document

*See full plan file for details.*

