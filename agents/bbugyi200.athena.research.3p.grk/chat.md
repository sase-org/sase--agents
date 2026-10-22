# Chat History - ace-run (research.3p.grk)

- **TIMESTAMP:** 2026-10-05 14:34:27 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.3p.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_141626.md`

## Prompt

%id(grk, clan=research.3p)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.3p.cdx`, `research.3p.cld`, `research.3p.mus`, `research.3p.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to use sase's memory files
dynamically to contruct instructions for each sase agent right before launching that
agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md,
  instruction_bundles_provider_parity_and_memory_ledger.md, and
  fresh_clone_bootstrap_and_native_subagent_instructions.md files in the research
  sidecar repo for context before performing your own research. I agree with all of the
  recommendations made in these research files for the most part, but you should call
  out any issues that you are able to identify.
- I think I want to split this work up into multiple epics with clear completion/exit
  criteria and verifiable results that are easy for me to confirm, but I'm not sure how
  this work should be split up or if it is even advisable to split this work up at all.

Can you do some research with the goal of helping me decide the best way to split this
work up (if at all)? End your analysis with a recommended set of epics (with clear
completion/exit criteria and verifiable results) or justification for why you don't
think that I should split up this work. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll start by reading the SASE research/repo skills and locating the three prior research files so I can form an independent view of how this work should be split.

I'll open the research sidecar through `sase repo` and locate the three prior research files before reading them.

Research sidecar is open. Next I’ll find the three prior reports and the repo’s AGENTS.md, without touching the other swarm reports.

I’ll read the three prior reports through `sase artifact read`, then inspect how instructions are generated today.

The prior reports are in hand. Next I’ll pull their phase/requirement sections and inspect the live instruction-generation and launch path.

I’ll pull the phase, requirement, and delivery sections from the prior reports while the bead search finishes.

I’ll inspect the live instruction pipeline, adapters, flags, and related tests so the epic split is grounded in the current tree.

I have enough independent evidence to recommend a four-epic program plus a small P0 tale cluster. Next I’ll write the report and register it.

**Split the work into four epics plus a small P0 tale cluster.** One mega-epic cannot close, and one epic per provider will collide on the shared renderer and `_invoke.py`.

The prior architecture (per-invocation bundles, explicit adapter channels, two-slot root/helper delivery, export stub) still holds. The prior “Phase 0–4” tables are not a work-breakdown: three reports reused those numbers for different piles of work, mixed a TUI product surface into delivery, and attached behavioral metrics that will keep an epic open.

Report: `sase/repos/research/202610/instruction_delivery_epic_split__grk.md`  
Registered as `research:202610/instruction_delivery_epic_split__grk.md` (`file:explicit:0ee2fc6eb0b01fcf17562cb6`).

### Recommended cuts

| Bead | Confirmable result |
| --- | --- |
| **P0 tales** (not an epic) | Grok `--rules` canary in `system_prompt.txt`; Claude helper PreToolUse denies `sase final`; stale double-load docs fixed |
| **Epic 1 — meter** | `sase doctor instructions` shows today’s Grok empty / Claude+Codex duplicate / Muse missing home. No argv changes |
| **Epic 2 — bundles + delivery** | Claude, Codex, Grok, Muse each get the bundle once through an explicit channel. 20 files still tracked. Flags removed before land |
| **Epic 3 — stub + sync + home** | Fresh clone has a stub with no `/sase_final`; `just install` leaves `git status` clean; chezmoi home files become interactive |
| **Epic 4 — audiences** | `when:` in sase-core; matrix budget check green; monitor render smaller than code render |
| **Epic 5 — MEMORY deck** (optional) | TUI ledger. Doctor + chip from Epic 1 are enough to run the migration |

Epic 2 is the actual migration. Epic 3 waits until Claude/Codex excludes are live. Epic 4 can overlap Epic 3. Do not file traits/`%tag`/`SASE.md` until a real section needs them.

### Issues that change the split

- Codex **can** suppress project `AGENTS.md` (`project_doc_max_bytes=0`). Untracking is contributor UX (Epic 3), not a delivery correctness dependency. Skip complement mode.
- “Helper finals go to 0” cannot close P0 while `CLAUDE.md` still contains `/sase_final`. That zero is an Epic 2 Claude exit criterion.
- The ledger report’s MEMORY deck picker `p` is reserved (`j,k,q,p`).
- `sase instructions` collides with existing `sase memory agent-docs`. Epic 1 owns one CLI group.
- Grok `--rules` presence is not in `prompt_context.json`. P0 must prove a canary lands in `system_prompt.txt`.
- Beta flags are epic scaffolding and must be removed in Epic 2’s last phase.

Independent checks on this tree: 20 tracked files, 285-line / 17,502-byte root `AGENTS.md`, 112 commits in 60 days, `grok inspect` in this workspace is untrusted with 0 project instructions, this session’s `agents_md_files: []`.
