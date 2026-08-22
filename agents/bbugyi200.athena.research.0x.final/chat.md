# Chat History - ace-run (research.0x.final)

- **TIMESTAMP:** 2026-08-22 17:01:12 UTC
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0x.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260822_162922.md`

## Prompt

%id(final, clan=research.0x) %m:@research_lead
%wait:research.0x.cdx %wait:research.0x.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I would like to implement a new `%if` directive that allows
me to specify (in the prompt) that agents should only only launch if a particular
condition, specified by a new code block argument type, holds.

- See the standalone_proc_launch_units.md file in the research sidecar repo for context and make sure this
  research either aligns with that research or that you reconcile any differences.
- This new directive will be particularly useful in xprompt swarms where we may want
  certain proc/agent shells to run conditionally.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0x.cdx` -> `__a`, `research.0x.cld` -> `__b`), then read both reports.
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

I’m using the SASE chat, repository, memory-read, and finalization skills because this task spans prior agent transcripts, a research sidecar, xprompt semantics, and a required final declaration. I’ll first map each transcript to its authored report, then inspect the relevant implementation and standalone-proc research before consolidating the evidence.

The two reports agree on the core abstraction—`%if` is a modifier on a normalized launch unit and should reuse the proposed structured code value—but differ on ordering. One recommends batch preflight before any launch; the other recommends evaluating after each unit’s waits. I’m tracing current wait/identity behavior now, since that determines whether those models can be reconciled or require an explicit split between static and dependency-aware predicates.

The implementation inspection supports a hybrid resolution: validate every predicate and the full launch graph before dispatch, but evaluate a unit’s predicate only when its dependencies are terminal. That preserves the standalone-proc report’s “wait first, acquire resources second” invariant and enables the motivating swarm use case, while avoiding a false claim of runtime atomicity for predicates that depend on predecessor outputs. I’ll encode this distinction explicitly in the consolidated recommendation.

The requested layout is now exact, with the Codex-authored report preserved as `__a` and the Claude-authored report preserved as `__b`. The consolidated report’s key addition is a language-neutral condition-context file and a clean separation between whole-plan static validation and dependency-aware runtime evaluation; this resolves the researchers’ strongest disagreement without weakening wait-before-resource admission.

The report and source preservation are complete. Verification confirms exactly the three requested Markdown files; no primary-repository code changed, so the repository’s `just check` requirement does not apply to this research-only sidecar update. I’m now performing the required SASE final declaration as the last action.

Completed the consolidated research report:

[conditional_launch_admission.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202608/conditional_launch_admission/conditional_launch_admission.md)

The directory contains exactly:

- `conditional_launch_admission__a.md` — Codex researcher
- `conditional_launch_admission__b.md` — Claude researcher
- `conditional_launch_admission.md` — consolidated report

Recommended solution: model `%if` as a fenced-code admission predicate on typed agent/proc launch units. Validate the entire graph before approval; after approval, wait for dependencies, evaluate the predicate, and only then acquire execution resources. Exit `0` launches, exit `1` records a terminal skip, and other outcomes are errors. Reuse `%proc`’s proposed `CodeValue`, fence parser, launch plan, and process-safety substrate.

I’m using the `sase_final` skill now to recover and submit the required declaration; I won’t touch repository files.

Finalizer declaration recovered and accepted successfully.
