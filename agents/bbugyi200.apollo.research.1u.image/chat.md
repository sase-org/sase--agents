# Chat History - ace-run (research.1u.image)

- **TIMESTAMP:** 2026-10-16 19:11:05 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** research.1u.image
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_175332.md`

## Prompt

%id(image, clan=research.1u) %m:gpt-6-astra
%wait:research.1u.final %q(1.5x, w=0.25) #gh:gh_sase-org__sase 
%macros_enabled:false
# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first projections of exact continuation nodes; any historical source without recoverable node provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:455427e9905115f856ea6bc3bc4ded03`

- **Node:** `agent-delta:20261016175339:150828ecb437d8be`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:** `local:continuation/records/agent_delta/agent-delta:20261016175339:150828ecb437d8be.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update supersedes it.

%clan(research.1u, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some research with the goal of comparing sase with gastown (see the
https://github.com/gastownhall/gastown GitHub repo), with a particular focus on the
things that gastown does better than sase? End your analysis with a ranked list of ways
that gastown is superior to sase along with a (not necessarily one-to-one) ranked list
of recommended changes you think I should consider making to sase based on your report's
findings.]]) %id:research.1u.final %m:@xlarge
%wait:research.1u.cdx %wait:research.1u.cld %wait:research.1u.grk %wait:research.1u.mus %wait:research.1u.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some research with the goal of comparing sase with gastown (see the
https://github.com/gastownhall/gastown GitHub repo), with a particular focus on the
things that gastown does better than sase? End your analysis with a ranked list of ways
that gastown is superior to sase along with a (not necessarily one-to-one) ranked list
of recommended changes you think I should consider making to sase based on your report's
findings.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.1u.cdx`, `research.1u.cld`, `research.1u.grk`, `research.1u.mus`, `research.1u.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.1u.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1u.linker`, can find it:

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

I'm reading the five researcher reports now, then I'll verify the disputed points against the gastown and sase checkouts.

Still verifying SASE-side claims. So far, two of gem's headline claims don't hold up: SASE workspaces already share Git objects through alternates, and SASE workflows are typed multi-step DAGs.

Confirmed the workflow executor always starts from step 0 (no crash-resume). Now checking how HITL continuation works and SASE liveness/timeouts.

Confirmed SASE has no OTel export, only two doctor `--fix` flags, and no auto-resolve for launch gates. Checking gate timeouts and the current master-landing situation next.

Checking the prior master-CI-red research and the May 2026 sase-vs-gastown report, since cld's top recommendation rests on them.

Master Gate is failing on today's HEAD and the four commits before it, so the landing-path problem is still live. Checking how long it's been red.

Master went green Oct 13–15 and red again on Oct 16 (52 failures, 6 passes). It reaches green but doesn't stay there. Now checking the Gas City successor and the project's status.

No open beads cover these gaps. One last check: the May 2026 sase-vs-gastown report, to see which of its recommendations have since landed.

I have what I need, so I'm writing the consolidated report now.

The report is written and the layout is correct. Registering the consolidated report as a durable artifact.

Registered (`file:explicit:27ab94819e7052b6590f86f5`). Submitting the final declaration.

The consolidated report is written and registered for the linker as `file:explicit:27ab94819e7052b6590f86f5`. The five swarm reports are moved into `202610/gastown_vs_sase_lessons_to_borrow/` next to `gastown_vs_sase_lessons_to_borrow__final.md`. I submitted the commit declaration for the research repo, so the commit itself happens after this turn ends.

**Bottom line:** Gas Town is ahead at keeping work moving without a human. SASE is ahead wherever correctness and human judgment matter. The biggest gap is the landing path. Master Gate failed on 52 of 58 runs on `master` today, including the current HEAD. Master went green on Oct 13–15 and went red again, because nothing stops a failing change from landing.

**Where the reports disagreed, checked against the code:**
- **Batch-then-bisect merge queue:** Gas Town's README advertises it, and gem ranked it #1. The functions have no non-test callers, and the shipped Refinery merges one branch at a time.
- **Worktrees vs. full clones:** gem claims SASE's full clones waste disk. SASE workspaces are a reused pool sharing the primary's Git objects; a workspace `.git` is 40 MB against 3.0 GB for the primary.
- **"SASE macros are prompt expansions":** wrong. They are typed multi-step workflows. What's actually missing is resuming after a crash; the executor always restarts at step 0.
- **Gas Town's recovery is not fully autonomous:** redispatch-with-model-promotion and stale re-escalation only run when its LLM patrol agents call them.
- **Prior recommendations still open:** the May 2026 comparison already recommended a coordinator agent, an agent-health subsystem and a landing queue. None exists, and no open bead covers any of them.

**Ways Gas Town is superior (top of the ranked 15):**
1. It refuses to land untested merges and proves each merge landed.
2. It notices live agents that have stalled or hung.
3. It handles failed work automatically: retries on a stronger model, circuit-breaks, or skips.
4. Agents can send each other addressed, acknowledged messages.
5. You can hand coordination to a coordinator agent (the Mayor).
6. It escalates blockers by severity and re-escalates ones nobody answers.
7. It keeps work through crashes and usage limits.

**Recommended changes (top of the ranked 14):**
1. **Landing lane:** refuse a landing that adds failures compared with the current tip, then confirm the push landed. This works even while `master` is red. It needs a new decision record alongside `ci-two-speed-split`, which rejected a GitHub merge queue.
2. **Stuck-agent detection:** classify running agents from the events SASE already streams, and add a Problems view.
3. **Failure policy for bead work:** retry on a stronger model, cap attempts, then skip and escalate.
4. **Gate escalation:** add severity and re-raise unanswered gates. This is the cheapest quick win.
5. **Agent inbox:** messages delivered at the start of the next turn.
6. **Coordinator session:** a chain of single turns with a budget for launching agents without approval.
7. **Work preservation:** snapshots during long turns, freeze/thaw of running agents, and pausing on usage limits instead of draining.

Explicitly not recommended: tmux keystroke injection, LLM patrols for mechanical checks, Dolt, an always-on Mayor, account rotation, a bisecting queue, and migrating to worktrees.

Nobody in the swarm ran a live Gas Town instance, so the Gas Town findings come from source and docs, not observed behaviour.

Sources:
- [Simon Willison, 2026-08-04, quoting Yegge on Gas Town and Opus 4.7](https://simonwillison.net/2026/Aug/4/steve-yegge/)
- [The New Stack on Gas Town by Kilo](https://thenewstack.io/steve-yegges-ai-agent-orchestration-project-gas-town-comes-to-the-cloud-and-brings-the-wasteland-with-it/)
- [Steve Yegge, Wikipedia](https://en.wikipedia.org/wiki/Steve_Yegge)

---

%macros_enabled:true
# New Query

 Generate an infographic that illustrates the main points made in this research markdown
file. Write the image to `<stem>_infographic.png` in the same directory, where
`<stem>` is the source file's stem with any trailing `__final` removed (so
`topic__final.md` becomes `topic_infographic.png`; other stems are unchanged).
Create it without overwrite. If it already exists, stop and report the collision.


## Response

I’ll read the registered research report and use the imagegen skill to create an infographic beside it, after checking that the output filename is available. I’ll use the SASE repository and artifact tools to access the report.


The report isn’t available at its canonical path in this checkout yet. I’m opening the registered snapshot while SASE prepares the research repository.


The filename is available. I’m building the infographic around the report’s top seven advantages and recommendations, with the landing-path evidence, corrected claims, and a note that Gas Town’s behavior was reviewed in source rather than tested live.


The first image is clear and readable. I’m correcting the CI graphic so it shows the exact counts without implying an inaccurate proportion, then I’ll save and register the PNG.


The 1024 × 1536 infographic is saved beside the report without overwriting anything. I’ve checked the image and PNG integrity and registered a durable copy. I’m using the SASE final skill to submit the repository change for host completion.


Created [gastown_vs_sase_lessons_to_borrow_infographic.png](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research/202610/gastown_vs_sase_lessons_to_borrow/gastown_vs_sase_lessons_to_borrow_infographic.png) beside the report without overwriting anything.

1024 × 1536 PNG, generated with built-in imagegen. [Generation prompts](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261016175340/gastown_infographic_prompt-ab34bf20995a.txt).

[Durable snapshot](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261016175340/gastown_vs_sase_lessons_to_borrow_infographic-944ad48b4982.png): `file:explicit:e9d4a75796353956413bac54`.
