# Chat History - ace-run (research.14.final)

- **TIMESTAMP:** 2026-08-25 17:24:25 EDT
- **MODEL:** claude/opus
- **AGENT:** research.14.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260825_163920.md`

## Prompt

%id(final, clan=research.14) %m:@research_lead
%wait:research.14.cdx %wait:research.14.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

It is very important that users that fully adopt sase and use
it in some of their projects can still use the agent CLIs that sase supports directly
(by using Claude code to do some research or create a quick commit, for example).
Currently, however, there seem to be some instructions that guide agents towards using
tools that only work when a sase agent is defined.

Can you do some research with the goal of helping me understand what it would take to
make sase projects usable by agent CLIs? Ideally, we should support as many of sase's
features as possible when running agent CLI's directly. For features that cannot be
supported, however, it should be clear to the agent (without adding to agent instruction
files too much--ideally, we don't add to agent instruction files at all) what they
should do instead.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.14.cdx` -> `__a`, `research.14.cld` -> `__b`), then read both reports.
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

I'll start by reading both researcher transcripts to identify which report each wrote.

Two candidate reports exist. Let me read both transcripts to determine authorship.

Authorship confirmed: `cdx` → `direct_agent_cli_compatibility.md` (`__a`), `cld` → `bare_agent_cli_compatibility.md` (`__b`). Reading both reports now.

Now report B:

Both reports are read. Now let me do my own research, focusing on gaps and disagreements between them.

B's core claim checks out. Let me verify the audit-log claims and the disputed command behaviors.

Now let me independently reproduce the standalone probe and test the disputed commands.

The unquoted loop misfired. Let me redo the probes properly and check `sase doctor` and `sase agent-cli`, which neither report examined.

`sase agent-cli` and `sase doctor`'s check framework are significant finds neither report covered. Let me dig further.

Found the seed template that ships to every adopting project. This is decision-critical for the "don't grow instruction files" constraint.

This corrects a provenance claim in report B. Let me verify against other adopting projects.

Confirmed — the Ephemeral Workspace section ships to every adopting project. Let me verify the rest of the generic-adopter surface.

I have enough independent evidence. Let me open the research sidecar properly before writing.

Both preserved with correct authorship mapping. Now writing the consolidated report.

Layout verified. Now submitting the final declaration.

Declaration accepted. Consolidated report is written.

## Final layout

```
202608/standalone_agent_cli_mode/
├── standalone_agent_cli_mode__a.md   (research.14.cdx — was direct_agent_cli_compatibility.md)
├── standalone_agent_cli_mode__b.md   (research.14.cld — was bare_agent_cli_compatibility.md)
└── standalone_agent_cli_mode.md      (consolidated)
```

Authorship was taken from the transcripts, not filesystem order; both source reports are preserved via `git mv`.

## What my own pass added

**The reframing finding neither report made:** SASE already ships `sase agent-cli` (installs/updates all 7 CLIs) *and* `sase tmux-agent` (launches them, tmux-keybound). Its dry run is damning — `env: (none)`, launched in the **primary checkout**. SASE's own launcher hands agents zero SASE env vars and drops them in the repo whose `AGENTS.md` tells them to run commands that then fail. This is a gap in a shipped feature, not a feature request.

**I found the actual shipped surface.** `src/sase/main/init_memory/templates/memory-sase.template.md` is the template that renders into every adopter's `AGENTS.md`. That settles the scope question both reports guessed at, and corrects both:

- **B was wrong** that the "Ephemeral `<N>` workspaces" section is sase-repo-local — it's in the shipped template under `{% if project_name %}` and renders as `actstat_<N>` / `bob-cli_<N>` in the two other adopting projects. Fixing it is a global fix.
- **A overstated the problem by roughly half** — "agents never create commits" and "use `/sase_monitor`" are sase-repo-local. Adopter `AGENTS.md` files contain **0** occurrences of either. A's minimal-edit table targets text most adopters never receive.

**One recommendation I upgraded:** `sase final context` standalone should be a *successful no-op*, not a better error. Since the always-loaded directive tells every agent to call it every turn, that mandatory call becomes the delivery vehicle for the truth — making the shipped `/sase_final` directive correct standalone **with zero instruction-file edits**. That's the best fit to your constraint in the whole report.

Other resolutions: `sase monitor start` (both partly right — it's a lane-resolution default with `-a` as the documented escape, not a hosted-only gate); `/sase_git_commit` readability (A right, B overstated); `sase pipe` as "the model to copy" (B overstated — it names the condition but offers no fallback); and the hooks/bridge apparent conflict, which dissolves once you separate *SASE-installed provider hooks* from a *user-installed optional bridge*.

Verified as exact: B's 19 skills / 13 with audit prelude, the 48-vs-0 audit asymmetry, the four gate mechanisms; A's five byte-identical provider shims. I also confirmed the `log_skill_use: false` opt-out already exists (6 skills use it) — which means `sase memory read` is single-gated, so B's one-line fix fully unblocks it with no skill-template work.

The report's bottom line matches B's shape: ~2 one-line changes plus point-of-failure error text gets you most of the way, and the only instruction-file edit I'd recommend is **three words** that shorten ambiguity rather than adding length.
