# Chat History - ace-run (research.1a.cdx)

- **TIMESTAMP:** 2026-10-14 09:34:37 EDT
- **MODEL:** codex/gpt-6.1-sol
- **AGENT:** research.1a.cdx
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261014_091543.md`

## Prompt

%id(cdx, clan=research.1a)
%m:codex/gpt-6.1-sol@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cdx in a 4-researcher swarm.
The other researchers, `research.1a.cld`, `research.1a.grk`, `research.1a.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__cdx.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure about our recent migration from agent instruction files to instruction
bundles (see the sase-1ko epic bead for context).

- The thing I am worried about is that an agent's core instructions are no longer
  transparent.
- I used to be able to just read the AGENTS.md file to understand what initial /
  project-level instructions a sase agent was given, for example. But now new users
  and/or non-sase agents need to generate it using a `sase` command I'm assuming?
- Also, it is not clear to me what the benefits are of this new solution? Your report
  should iterate over all of the immediate and long-term benefits.

Can you do some research with the goal of helping me decide whether or not I should
proceed with this work or revert it? 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cdx` suffix, i.e. `<stem>__cdx.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I’ll use the SASE repo, bead, memory-read, and artifact skills to trace the migration, assess the transparency tradeoff, and write an independent report without consulting the other swarm reports.

The migration is still in acceptance testing. It also retains the generated `AGENTS.md` files, so I’m checking two separate questions: whether a fresh checkout remains easy to understand, and whether the archive makes a specific agent run easier to audit. I’ll use official provider documentation to check the assumptions behind instruction delivery.

The bundle design addresses a real delivery problem: earlier Claude and Codex runs loaded the SASE contract twice, while Grok and Muse missed the home layer. It also records the bundle prepared for each invocation. The planned removal of committed instruction files is a later step, and I’m evaluating whether those benefits require giving up a readable `AGENTS.md`.

My emerging recommendation is to keep explicit bundle delivery and pause the later removal of readable project instructions. The acceptance record shows successful delivery probes for Claude, Codex, and Grok, but Muse’s live probe was blocked by quota and the production sample is too small to establish better behavior. I’m checking a fallback edge case and the fresh-checkout experience before finalizing the report.

The fallback check found a concrete gap: with Codex’s explicit-delivery flag on but no active bundle, the shadow home still omits SASE’s home `AGENTS.md`. I also confirmed that `mode=export` removes home memory sections but retains home-linked repository metadata. I’ll record these against the migration epic using the SASE new-task workflow and include both in the report.

The report is written. It recommends keeping bundle delivery, preserving a substantive public `AGENTS.md`, and holding file retirement until inspection and fallback requirements pass. It covers 16 immediate benefits, 12 longer-term benefits, the evidence limits, and the two reproduced findings. I’m checking the report and registering its durable snapshot now.

The durable snapshot registered successfully, and both findings are recorded on `sase-1ko`. I’m using the SASE finalization skill to hand the report to the host for commit.

[Report completed](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research/202610/instruction_bundles_keep_delivery_preserve_readable_contract__cdx.md).

Recommendation: keep explicit bundle delivery, preserve substantive `AGENTS.md` guidance, and delay file retirement. Two reproduced gaps are documented on `sase-1ko`.

[Durable snapshot registered](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261014091543/instruction_bundles_keep_delivery_preserve_readable_contract__cdx-82faf8f2e2c2.md): `file:explicit:8ccecece271b668ba9820e83`.
