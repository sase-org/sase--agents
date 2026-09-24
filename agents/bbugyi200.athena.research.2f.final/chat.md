# Chat History - ace-run (research.2f.final)

- **TIMESTAMP:** 2026-09-24 09:30:15 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2f.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_085243.md`

## Prompt

%clan(research.2f, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I've been renaming a lot of sase concepts
to use terms that are more standard across the AI / tech industry lately. For example, I
renamed "axe" to "scheduler", "lumberjacks" to "routines", "chops" to "jobs", "ace" to
"tui", and am now in the process of (see the sase-17m epic bead and the `0qi` sase agent
for context) renaming "agent families" to "agent sessions" and "sase shells" to "sase
turns".

Can you do some research with the goal of critiquing these renames and searching for any
other concepts that you think should be renamed? Make sure that you have strong
justification if you recommend a new rename. End your analysis with a brief critique of
the renames that have already been implemented or will be implemented soon and a list of
new recommended renames that you think I should perform (if any).]]) %id:research.2f.final %m:@xlarge
%wait:research.2f.cld %wait:research.2f.mus %wait:research.2f.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I've been renaming a lot of sase concepts
to use terms that are more standard across the AI / tech industry lately. For example, I
renamed "axe" to "scheduler", "lumberjacks" to "routines", "chops" to "jobs", "ace" to
"tui", and am now in the process of (see the sase-17m epic bead and the `0qi` sase agent
for context) renaming "agent families" to "agent sessions" and "sase shells" to "sase
turns".

Can you do some research with the goal of critiquing these renames and searching for any
other concepts that you think should be renamed? Make sure that you have strong
justification if you recommend a new rename. End your analysis with a brief critique of
the renames that have already been implemented or will be implemented soon and a list of
new recommended renames that you think I should perform (if any).

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, gem, belonging to this
   dispatch's `research.2f.cld`, `research.2f.mus`, `research.2f.gem` dependencies, matching by `wait_name` and the canonical research
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

## Response

I've read two of the three reports (cld and mus). Next I'll read gem, then check the points where they disagree.

Now I'll check the claims where the reports disagree, starting with the in-flight epics and the glossary.

Confirmed the in-flight session epic already writes `agent_session_shell` keys. Next I'll check the CLI aliases, the bead tiers, and the rationale behind tag → tribe and xprompt.

Proc aliases and the TUI-session flag are confirmed. Now I'm reading the earlier naming research and plans on tribe, xprompt, stitch, and routine to settle where the reports disagree.

The turn-rename agent (0qi) is waiting for sase-17m to close, so the double schema migration will happen unless the plan changes. I'll check how far sase-17m.8 has progressed.

I've verified the main disputed claims. One last count, then I'll move the reports and write the consolidated report.

The consolidated report is written and the cited numbers are corrected. Now I'll confirm the final layout, then submit the final declaration.

I've written the combined report and moved the three researcher reports next to it. The research repo commit has been submitted.

**Critique of the renames done or in progress:** don't revert any of them.

| Rename | Verdict |
| --- | --- |
| **sase shell → sase turn** | The best rename. "Shell" collides with the Unix shell, and your accepted decision records already call this unit a "turn." |
| **chop → job**, **ACE → TUI** | Clean wins. Leftovers: the `ace:` config root, and new plans and commit scopes still say "ACE." |
| **AXE → scheduler** | Right but half-finished. `routine`, `job` and `maintenance` only exist under `sase axe`, not `sase scheduler`. |
| **agent family → agent session** | Good. One researcher called it the weakest, but "family" had at least as many other meanings in the code, and OpenAI's Agents SDK uses "session" for exactly this: history across several agent runs. |
| **lumberjack → routine** | The weakest. Claude Code has its own "routines" (scheduled agent runs), which every Claude-run agent sees in its context. Keep the name, write "scheduler routine" in agent-facing text, and remove the old "lane" wording from the routine descriptions in `default_config.yml`. |
| **background tasks → procs** (not on your list) | Good, but retire the `task` alias on `sase proc`. "task" is now the bead tier people type. |

**Most urgent:** as things are sequenced, the turn rename will force a second schema and fleet-protocol migration. Agent 0qi won't start until sase-17m closes. By then, sase-17m.8 will have made the `agent_session_shell*` keys part of the saved-data format. The Python side already writes those keys in 43 files. sase-17m.8 hasn't started yet, so change it now to write the "turn" spellings instead.

For the turn rename itself:
- Only members of a session become turns. Named procs, including the scheduler service, also use `shell_*` fields; give those proc names instead.
- Call the command member a "monitor turn," not a "proc turn."
- Never show Claude's `num_turns` count as "turns" in the UI; it counts tool-use round trips inside one turn.

**New renames I recommend:**
1. **`sase pipe` → `sase handoff`**. It hands control to one successor, one after another; it doesn't stream data like a Unix pipe. "Handoff" is the industry term, and SASE's help text and code already use it. One verb would then cover handing off to an agent, monitor or gate turn. Do it as part of the turn rename.
2. **"TUI session" → "TUI instance"** (`sase proc list --session` → `--instance`, and the session chip). After sase-17m, this is the only user-facing "session" that isn't an agent session.
3. **"LLM Calls" → "Tool Calls"**. The panel's rows are tool invocations; an "LLM call" means the model request itself. The artifact, config block and record type already say "tool call." This reverses a choice made six days ago; one glossary line ("a tool call is what the model asked for; a Tool Run is what `sase tool run` recorded") handles the `sase tool` clash it was avoiding.

Optional, only if you're already in those files: hood → namespace, mentor → review agent.

**Rejected researcher proposals:**
- **tribe → tag or label:** "tag" still has about nine other meanings in SASE, and "label" appears about 11k times.
- **clan → group, swarm or team:** "group" means saved agent groups, "swarm" is the launcher that creates a clan, and "team" is a Claude Code feature.
- **xprompt → skill:** in SASE a skill is what gets generated from an xprompt, and many xprompts are not skills.
- **stitch → commit or revision:** a stitch need not have a commit, and "revision" is ambiguous between VCS tools.
- **memory web/strand → collection/entry:** the concept is a month old and backed by accepted decision records.

One gap none of the researchers raised: "tale" (the plan tier) is missing from the glossary. A committed tale's bead also reports `Tier: plan` while its plan file says `tier: tale`. Keep the name "tale," but make the bead tier match.

Files are in `sase/repos/research/202609/sase_terminology_renames/`:
- `sase_terminology_renames.md` (the combined report)
- `sase_terminology_renames__cld.md`
- `sase_terminology_renames__mus.md`
- `sase_terminology_renames__gem.md`
