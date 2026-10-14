# Chat History - ace-run (research.1a.grk)

- **TIMESTAMP:** 2026-10-14 09:37:13 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.1a.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261014_091543.md`

## Prompt

%id(grk, clan=research.1a)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 4-researcher swarm.
The other researchers, `research.1a.cdx`, `research.1a.cld`, `research.1a.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__gem.md`. Your report will end in `__grk.md`.

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
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll research the instruction-bundle migration independently, starting with the research and artifact skills plus the sase-1ko epic context.

I'll gather the epic context, glossary, and artifact rules, then inspect the instruction-bundle implementation.

Glossary selectors with spaces failed, so I’ll reread those terms correctly and pull the epic, plans, and related decisions.

The epic is E3 of a three-step instruction migration. Next I’ll read the plans, earlier epics, and the live instruction CLI.

The founding research and live CLI/docs are next, so I can compare file-based instructions with the bundle path.

I have the architecture. Next I’ll check live inspection surfaces, remaining committed files, and the E4/E5 transparency plan.

I’ll verify the live repo, CLI, and scoreboard so the report can separate current E3 behavior from the later E4/E5 file-retirement plan.

I have enough evidence. Next I’ll write the independent report and register it as a durable snapshot.

Do not revert the instruction-bundle cutover. Finish E3’s soak. Hold E4 (deleting committed `AGENTS.md`) until a stub, `sase instructions sync`, and an in-product bundle view exist.

The full report is `research:202610/instruction_bundles_transparency_proceed_or_revert__grk.md`, registered as `file:explicit:592f53324f6105a61acdb92b`. The source file stays in the research repo.

**What is actually true today.** E3 changed *delivery* for SASE agents. It did not delete the files. This checkout still tracks 20 generated instruction files. A clone that runs `claude` or `codex` still loads `AGENTS.md`. A SASE agent does not: this run’s bundle is `bc648948db99` on `grok.rules` (`sase instructions show research.1a.grk` → `bytes match`). The committed `AGENTS.md` is 18,694 bytes with numbered headings; the delivered bundle is 20,238 bytes with a home line and a Grok overlay.

**Transparency.** Opening `AGENTS.md` is no longer what a SASE agent was told. The replacement is `sase instructions show` / `render` / `verify`. The TUI still does not open the bundle (that is E6). New users do **not** need a `sase` command yet; they will after E4, via a planned stub plus `just agent-instructions`. That command does not exist.

**Proceed vs revert.** Reverting would restore Grok-empty, Claude/Codex contract-twice, missing home layers, and helper `/sase_final`. Per-provider rollback is already `sase flag disable <provider>_explicit_instructions`. Live 24h: Codex and Grok are explicit 1×; Claude is still legacy on the installed host; Muse is still shadow (quota). That mix is install skew, not a failed design.

**Hold E4** until export/sync, glossary/docs, and some Agents-tab view of the archived bundle exist. Casual inspection is the real complaint; it does not require undoing delivery.
