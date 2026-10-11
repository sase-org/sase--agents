# Chat History - ace-run (research.0v.cld)

- **TIMESTAMP:** 2026-10-11 10:12:23 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0v.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261011_095836.md`

## Prompt

%id(cld, clan=research.0v)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0v.cdx`, `research.0v.grk`, `research.0v.mus`, `research.0v.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research on the pi repo (see https://github.com/earendil-works/pi)? How
does this product compare to sase? In what ways can sase learn from pi? End your
analysis with a ranked list of improvements to sase that you think I should consider
implementing to make sase more appealing to someone who already uses pi. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

I've opened the pi repo and I'm reading its docs and architecture now. Next I'll go through sase's own docs so I can compare the two.

I've finished the main pi survey. Now I'm mapping sase's own feature set: its README, docs and CLI surface, so the comparison rests on the actual code.

I've covered sase's docs. Next I'm checking public sources on how pi is positioned and received, to back up the "what pi users value" part of the report.

Status: research is nearly done. I'm doing one last measurement, the size of sase's always-on instruction footprint versus pi's, and then I'll write the report.

I have what I need. I'm writing the report now: a comparison of pi and sase, lessons for sase, and a ranked improvement list.

Report is written; now registering it as a durable artifact.

Registered. Now submitting the final declaration.

I wrote the report and registered it as a durable snapshot with the `research:202610/pi_harness_vs_sase_lessons__cld.md` label (artifact `explicit:691847140c255d2e3c3c1972`). The host commits it to the research repo after this turn ends.

**Report:** `sase/repos/research/202610/pi_harness_vs_sase_lessons__cld.md`

**How pi compares to sase:**
- **Different layers.** Pi is a minimal, hackable harness for a single agent. Sase is the coordination layer above harnesses like it. That makes pi mainly a possible backend for sase, not a rival.
- **Sase can't run pi today.** Its providers are claude, codex, agy, qwen, opencode, muse, grok and fakey. Someone who lives in pi gets nothing from sase until that changes.
- **Pi documents the problem sase solves.** Pi's own `AGENTS.md` warns that several pi sessions in one directory "stomp on" each other's git work. Its community has built side-agent, worktree, PR-agent and orchestrator packages to fill that gap, which shows real demand for what sase does.
- **Pi is easy to hook into.** Its extension hooks can block a tool call, force one more model turn before the run ends, or end the run on a tool call. That would let sase *enforce* rules it now mostly states in prompt text: the final declaration, "never commit yourself", and "never run raw `just`".
- **Pi records the exact system prompt.** Each session file stores it, so `sase instructions verify` could confirm instruction delivery more precisely for pi than for any current provider.

**What sase can learn from pi:**
- Keep the core small and always-on prompt text cheap. Pi's base prompt is under 1k tokens; this project loads about 22.5 KB of instructions every turn.
- Make extensions nearly free: drop a file in a folder, or install from git, npm or a local path.
- Fork sessions natively instead of pasting the old transcript in as text.
- Show cost and context use live, broken down by the model that actually answered.
- Offer strictly specified JSON and RPC interfaces so other tools can drive it.
- Measure whether docs and instructions help, using paired with/without evals.

**Ranked improvements:**
1. **A built-in pi provider.** It would run pi's JSON mode and pass through any pi model, including routing models defined by pi extensions. It would also capture cost, deploy sase skills to pi, and add pi to the tmux Agent panel and instruction verification.
2. **A `sase-pi` package for pi.** It would add a typed `sase_final` tool and guards that enforce the declaration, commit and recipe rules. It would also add `/sase` commands so users can launch and watch sase agents from inside pi.
3. **Native fork and resume** using pi's session tree.
4. **A "Lite" profile** with fewer concepts, plus a readout of how many tokens sase's instructions cost each launch.
5. **Live dollar cost and context use** across all providers.
6. **Mid-run steering**, for providers that accept messages during a run. This needs a decision record first, since it touches the single-turn rule.
7. **Skills sharing with pi** in both directions, through the cross-tool `~/.agents/skills` location.
8. **Drop-in local extensions** without packaging, gated by an explicit trust decision.
9. **A stable sase agent event stream** that other tools can consume. The schema would live in sase-core.
10. **Terminal status reporting** (OSC 7501, which pi already emits), so terminals and dashboards can show whether sase is working, blocked or done.
11. **Paired evals** that measure whether each memory note or instruction section earns its tokens.
12. **Wider install and platform reach**: a Nix flake, a one-line installer, and a documented WSL path.

**Caveats:**
- Pi changes fast, with breaking changes in point releases. My facts come from its main branch as of today.
- The package-gallery count (about 5.4k) and the usage claims come from search snapshots or the vendor.
- I didn't fully confirm that sase lacks a cross-provider dollar-cost roll-up or a trust gate for project-local config. Check both before scoping items 5 and 8.
