# Chat History - ace-run (research.0o.final)

- **TIMESTAMP:** 2026-10-08 22:55:24 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0o.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_202653.md`

## Prompt

%clan(research.0o, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I would like to make the case that Hermes can do everything that sase can and that the
smart move (for just about any user except for many me) would be to not bother with
sase.

Can you do some research with the goal of supporting/refuting that claim? Make sure that
this analysis / comparison is based on the feature sets of each product. Do not consider
popularity / adoption. End your analysis with a recommendation. If you think sase
realistically might have a role to play (as a tool used by many, not just me), justify
why and describe what that role is.]]) %id:research.0o.final %m:@xlarge
%wait:research.0o.cdx %wait:research.0o.cld %wait:research.0o.grk %wait:research.0o.mus %wait:research.0o.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I would like to make the case that Hermes can do everything that sase can and that the
smart move (for just about any user except for many me) would be to not bother with
sase.

Can you do some research with the goal of supporting/refuting that claim? Make sure that
this analysis / comparison is based on the feature sets of each product. Do not consider
popularity / adoption. End your analysis with a recommendation. If you think sase
realistically might have a role to play (as a tool used by many, not just me), justify
why and describe what that role is.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.0o.cdx`, `research.0o.cld`, `research.0o.grk`, `research.0o.mus`, `research.0o.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.0o.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.0o.linker`, can find it:

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
├── <name>__final.md
└── <name>_narration.md
```

## Response

Now reading each report through its canonical research reference.

Hermes is at `908e4a4b44` (6 commits past the researchers' `1e0c7730d7`). Now verifying the disputed claims.

Now checking the SASE side: land agent, finalizer verification, commit enforcement, sudo, bypass flags, usage routing.

Still verifying SASE's land-agent behavior (gem's claims about rebasing and integration testing) before writing the consolidated report.

Reports moved. Now writing the consolidated report.

Fixing the tally line (recount: 6 ✅, 4 🟡, 4 🟠, 5 ❌).

The edit and registration ran in parallel, so I'll check the snapshot captured the corrected tally.

The snapshot has the corrected tally and the layout is in place. Now submitting the final declaration.

The claim that Hermes can do everything SASE can doesn't hold up. The practical advice that most people shouldn't bother with SASE does. I've written the consolidated report and registered it so the linker agent can find it.

**Verdict**
- **"Hermes can do everything SASE can": refuted.** All five researchers agreed, and I re-checked it in both codebases. Hermes matches or beats SASE on the day-to-day features:
  - isolated workspaces, a task board with dependencies, scheduling, chat access and switching providers when one hits its usage limit;
  - checking work before it's marked done (review step, required-CI gate), where it is actually ahead.

  Of the 19 SASE capabilities I checked, 9 have nothing equivalent in Hermes's core or official plugins. The ones that matter most come from opposite design choices:
  - **Coding CLIs as workers:** Hermes doesn't run Claude Code, Codex, Grok and the others as workers. Its own docs call that "*not yet a paved path*".
  - **Commits:** in Hermes the agent commits itself. In SASE the host makes the commit and records which agent and plan produced it.
  - **Waiting for a human:** Hermes has no typed approvals that wait indefinitely on any agent turn. Its attempt at this was merged and reverted on 2026-10-01.
  - **Record in git:** SASE keeps its task tracking, plans and project memory in git. Hermes keeps its board in a local database on one machine.
- **"Skip SASE, for just about anyone": supported.** That includes most professional developers. The exception isn't you specifically. It's anyone who has moved from *using* a coding agent to *managing several* of them across vendors, on trusted repos, supervising them asynchronously. Saying "except me" confuses who wrote SASE with who it fits.
- **SASE's realistic role:** a vendor-neutral control layer that sits above the coding CLIs, for that fleet operator. To make that role reachable, the report recommends:
  - cut a release (nothing since 0.17.1, about 2,260 commits ago);
  - add an opt-in sandbox;
  - offer a small core path for new users;
  - add a review step and a CI gate;
  - add Hermes as an eighth SASE provider using its headless mode, so the two products work together instead of competing.

**Corrections from my own checks.** The gem report's architecture analysis was sound, but several of its strongest claims were wrong:
- Hermes is not limited to pay-per-token billing. It can bill Claude, Codex, Antigravity and Grok to their subscriptions through plugins, and it has usage-window tracking.
- SASE's provider switching happens after a usage-limit error, not before.
- SASE's land agent (the agent that finishes an epic) is an LLM following a prompt. It is not a host step that runs the full test suite before landing.
- Host-owned commits are a workflow and provenance rule, not a security boundary: SASE's agents run with permission checks bypassed.
- Hermes's 300-second timeout only covers per-command approvals. A blocked task on its board waits indefinitely for a human.

So in your argument, don't claim Hermes does everything SASE does. Make the practical claim and name the fleet-operator exception.

**Files** are in `202610/can_hermes_replace_sase/` in the research repo:
- the five researcher reports, moved in and renamed with their original suffixes;
- `can_hermes_replace_sase__final.md`, registered as `research:202610/can_hermes_replace_sase/can_hermes_replace_sase__final.md` (ref `file:explicit:a572e9989d52ac7458fedf32`).

I didn't create the narration file or `can_hermes_replace_sase.md`. The commit to the research repo has been declared and the host makes it after this turn.
