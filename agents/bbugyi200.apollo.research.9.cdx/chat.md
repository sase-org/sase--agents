# Chat History - ace-run (research.9.cdx)

- **TIMESTAMP:** 2026-09-25 14:07:41 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.9.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260925_135331.md`

## Prompt

%id(cdx, clan=research.9)
%m:codex/gpt-5.6-sol@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cdx in a 4-researcher swarm.
The other researchers, `research.9.cld`, `research.9.mus`, `research.9.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to rename the `%proc` directive to
`%tool` and add some features to it to better support the `sase tool` command (see the
sase_tool_epic_roadmap.md file in the research sidecar repo for context).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cdx` suffix, i.e. `<stem>__cdx.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I’m using the SASE repo, memory-read, artifact, and final-declaration skills. They govern access to the research sidecar and roadmap, required xprompt/artifact context, durable registration, and the turn-closing declaration. I’ll keep this investigation independent and will not inspect any peer report or transcript.

The research sidecar is open at the audited workspace path. I’m locating only the named roadmap and will read it through the artifact interface; peer reports remain out of scope.

The roadmap frames `%tool` as more than a spelling change: it must preserve “one semantic run, one execution owner” while avoiding a second supervisor. I’m now tracing the current `%proc` parser, launch model, tests, and the live `sase tool` CLI so the recommendation is grounded in today’s implementation rather than the roadmap’s older snapshot.

The current tree has already landed the ToolRun ledger, named catalog, durable `-H` proc handoff, stop/wait/follow, and failure triage. That materially changes the design: `%tool` can target a real stable facade now, but the existing `%proc` launch unit still carries raw code, proc-specific timeouts/cwd/workspace, and queue/hold policy. I’m checking the Rust planner boundary next because that is where the semantic migration should live.

One important versioning check: the linked core checkout is ahead of the `sase-core-revision.txt` pin. I’m comparing only the relevant planner and ToolRun contracts against the pinned revision so the report distinguishes deployed behavior from unreleased core changes.

The central conclusion is now firm: `%tool` is a good addition but a poor mechanical rename. A ToolRun is the semantic work record; a proc is one possible execution owner. The clean design is a first-class named-tool launch unit that reuses the existing proc supervisor and ToolRun handoff, while retaining `%proc` as the explicit raw-code escape hatch. I’m writing the report with the proposed syntax, wire/runtime shape, compatibility strategy, risk analysis, and phased acceptance criteria.

The report is written without overwrite and passes `git diff --check`. I’m registering the exact source path now as `research:202609/tool_directive_design__cdx.md`; the source will remain in the research repo as requested.

Research and durable registration are complete. The source report remains live in the research repo, and the artifact resolves exactly with ID `explicit:2e05c7890bdf8f3c5c1ff751`. I’m submitting the required host final declaration for the new report.

Research completed and registered successfully.

Report: [tool_directive_design__cdx.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202609/tool_directive_design__cdx.md)

Artifact: `file:explicit:2e05c7890bdf8f3c5c1ff751`

Core recommendation: add `%tool` as a first-class named ToolRun launch unit backed by the existing proc supervisor. Do not mechanically rename `%proc`; retain it for raw durable Bash/Python execution.
