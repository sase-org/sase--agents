# Chat History - ace-run (sase-ej.land.w2--plan)

- **TIMESTAMP:** 2026-08-03 14:46:50 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ej.land.w2--plan

**Plan:** /home/bryan/.sase/plans/202608/revert_stored_prompt_duality.md

## Prompt

#gh:gh_sase-org__sase
%w:sase-ej.land Can you help me revert all of the work that corresponds with the sase-e6 epic bead? I want to go back to storing prompts in chat/prompt markdown files the way we did before. Make sure you revert any existing chat/prompt markdown files that used the format introduced by sase-e6 (do not leave any backward-compatibility code for handling these obsolete chat/prompt file formats). Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/revert_stored_prompt_duality.md`

> # Plan: Revert stored prompt duality and xprompt linkification
> ## Background
> Epic `sase-e6` ("Store both prompt renderings and linkify xprompt references") shipped in six phases on 2026-08-02. It
> changed what SASE writes into two durable stores and added the machinery behind that change:
> | Phase       | Commit           | What it added                                                               |
> | ----------- | ---------------- | --------------------------------------------------------------------------- |
> | `sase-e6.1` | `4d83afb` (core) | `prompt_xprompt.rs` + three PyO3 bindings; extracted `prompt_rewrite.rs`    |
> | `sase-e6.2` | `cb90eaf00`      | launch-time `xprompt_sources.json` capture                                  |
> | `sase-e6.3` | `e30935808`      | `src/sase/xprompt_links.py` hosted-URL resolution                           |
> | `sase-e6.4` | `e6624e324`      | sentinel-delimited chat sections + `chat_history.rendered_prompt_max_bytes` |

*See full plan file for details.*

