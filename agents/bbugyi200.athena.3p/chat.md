# Chat History - ace-run (3p--plan)

- **TIMESTAMP:** 2026-07-09 13:04:11 EDT
- **MODEL:** claude/opus
- **AGENT:** 3p--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-3p__plan-260709_124908.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260709_124908.md`

**Plan:** /home/bryan/.sase/plans/202607/sdd_companion_artifact_discovery.md


## Prompt

#gh:gh_sase-org__sase Agents that produce sdd/research/ markdown files no longer list those files as artifacts (see #sshot, for example). This seemed to start happening after we recently migrated to using a separate repo for SDD artifacts. Can you help me diagnose the root cause of this issue and fix it? Make sure your fix will also resolve any issues we might be having with sase-telegram (ex: I bet that image files that are added/changed by agents are not sent with Telegram agent completion messages anymore, but I'm not sure).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/sdd_companion_artifact_discovery.md`

> # Plan: Discover agent artifacts & attachments from the separate SDD companion repo
> ## Problem / product context
> Agents that produce `sdd/research/**.md` files (and images that accompany them, e.g. research infographics) **no longer
> list those files as artifacts** on their completion entry. The same root cause also breaks **`sase-telegram`**: images
> an agent adds/changes are no longer attached to the Telegram agent-completion message.
> This regression started when SDD artifacts migrated from **in-tree** storage (`<workspace>/sdd/…`, inside the main code
> repo) to a **separate companion repository** (`separate_repo` storage), where SDD content lives at
> `<workspace>/.sase/sdd/…` — a _distinct_ git repo that is also git-ignored by the main repo (`.gitignore` contains
> `.sase/`).
> ### Root cause (confirmed)

*See full plan file for details.*

