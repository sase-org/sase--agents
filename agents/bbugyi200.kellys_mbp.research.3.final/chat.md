# Chat History - ace-run (research.3.final)

- **TIMESTAMP:** 2026-09-03 16:47:04 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.3.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260903_162220.md`

## Prompt

%id(final, clan=research.3) %wait(priority=20) %m:@research_lead
%wait:research.3.cdx %wait:research.3.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I would like to add a new `,X` keymap to the "Agents" tab
that works in a very similar way to the `,x` keymap but targets the most recently
launched agent. Notably, this keymap should be able to target an agent that hasn't
started yet (i.e. the associated proc that launches the agent hasn't finished running
yet). The goal of this new keymap is to allow users to very quickly kill and edit the
last agent that they launched, which should be useful since users often realize they
want to change the prompt they just used to launch an agent (e.g. after hitting the
`<enter>` key too quickly, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.3.cdx` -> `__a`, `research.3.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading the two researcher transcripts to find which report file each wrote, then dig into the codebase myself.

Let me dig into the launch-admission path — the main substantive disagreement about whether a deferred kill covers queued/gated launches.

All citations check out. Now I'll set up the research directory — stem `agents_tab_kill_last_launch` (no collision in the month dir) — and move the two reports into it.

Now writing the consolidated report, merging both researchers' findings with my own verification.

The layout is complete. Per the SASE final declaration requirement, I'll submit the finalizer declaration before my closing response.

The consolidated research is complete and committed. Final layout under `sase/repos/research/202609/agents_tab_kill_last_launch/`: `agents_tab_kill_last_launch__a.md` (cdx report), `agents_tab_kill_last_launch__b.md` (cld report), and `agents_tab_kill_last_launch.md` (consolidated).

**The consolidated recommendation:** build `,X` as *"resolve this session's last accepted launch, reveal it, and run the existing `,x` flow on it — with a deferred kill when the launch is still in flight."* Track the last launch in a small session-local stack recorded at submit time (have `_submit_launch_proc` return the placeholder `ObservedProc` it currently reduces to a bool), restore the prompt instantly on `,X` even mid-launch, and when the target hasn't started yet, register a kill intent that fires from the launch-completion callback through the ordinary kill path. Never cancel the launch proc itself.

How the three perspectives merged:

- **Both researchers agreed** on the two hardest calls, and I verified both against the code: targeting must be session-scoped (disk scans miss the in-flight window and can retarget onto agents the user didn't launch), and killing the launch proc is unsafe (agent children are `setsid()`-detached, there's no stop API for operation-lifecycle procs, and SIGTERM bypasses the partial-launch rollback).
- **The main disagreement** was report A's durable backend cancellation protocol in `sase-core` versus report B's lightweight deferred kill. I sided with B's deferred kill for v1 — my verification found the placeholder→durable ID bridge A wanted to build already exists in the completion-callback plumbing — while adopting A's state-discipline guardrails (rejected submissions don't clobber the target, second press is idempotent, late-finishing older launches can't steal the slot).
- **My own pass confirmed one real gap both circled but neither pinned down:** typed `%if`/`%proc` launches report `admission_complete: false` and hand remaining units to a detached coordinator that outlives the launch proc, so killing the returned results under-kills those launches. The report scopes v1 to kill-what-returned plus a warning toast, with a backend "abort launch bundle" operation (where A's protocol becomes the right tool) as explicit follow-up.
- Other resolved conflicts: key `X` is free but the retired `kill_marked_and_edit` filter must stay (a legacy test proves stale overrides are dropped); confirmation policy merges both views — no modal on the in-flight branch, `,x`'s exact rule on the resolved branch; and the relaunch barrier's 30s timeout gets split so the pending-kill leg has its own warn-and-release budget, preserving the forced-name-reuse invariant from T0 through kill-settled.

The report also flags that the in-flight branch is the feature, not a phase-2 enhancement — the "hit enter too fast" reflex lands squarely in the multi-second T0→T4 launch window — so the record/keymap work and deferred kill should ship together.
