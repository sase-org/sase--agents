# Chat History - ace-run (research.02.grk)

- **TIMESTAMP:** 2026-10-02 11:15:52 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.02.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261002_110156.md`

## Prompt

%id(grk, clan=research.02)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.02.cdx`, `research.02.cld`, `research.02.mus`, `research.02.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would love to be able to reduce this project's agent instruction files down to <=100
lines. Sase has pretty good support for progressive disclosure with memory files
already.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

I'll research how to shrink this project's agent instruction files to ≤100 lines, using SASE memory/progressive disclosure as the main option. First I need the project layout, current instruction files, and the artifact/finalizer skills.

I'll map the current instruction files, memory system, and research-repo layout before forming a recommendation.

The research tree looks like a linked repo, so I’ll open it properly and then measure the current instruction surface.

Memory Webs look like the main bulk. Next I’ll measure token cost, generation, and any existing size-budget work.

I'll read the AGENTS.md generator, prior SASE research on progressive disclosure, and how often agents actually load reference memory.

A prior decision already flags inlined web descriptors as a token-budget problem. I'll check sase-core's ~100-line AGENTS.md, the sase.md generator, and how providers actually load these files.

There's prior work on AGENTS.md token optimization from April. I'll read that and then write the report.

I have the measurements and the industry picture. Next I’ll write the independent report and register it as an artifact.

**Yes — shrink the always-loaded file. Treat ≤100 lines as a soft budget for project-root `AGENTS.md`, not as the only metric and not as a dump-everything-into-memory rewrite.**

Report: `sase/repos/research/202610/shrinking_agent_instruction_files_to_100_lines__grk.md`  
Artifact: `file:explicit:19255a136a363e5b55bd5b41` (`research:202610/shrinking_agent_instruction_files_to_100_lines__grk.md`)

### Critique

The instinct is right. The current project `AGENTS.md` is **283 lines / ~4,316 tokens / 17 KB**. Memory Webs are **51% of it** (the 24-decision list roster alone is ~90 lines). That is the reopen condition already written into `decisions:webs-render-in-their-own-section`: descriptor bodies are always paid for, and the escape hatch is a new opt-out, not putting `type:` back on webs.

A naive “cut to 100 lines and hope agents open memory files” would fail. Progressive disclosure already works **because the always-loaded file still names the note**. `lint_and_test.md` is 160 lines of procedure, kept as `type: reference`, and was still read **490 times by 415 agents**. Hard rules (`/sase_final`, `/sase_repo`, `just check`, rust-core litmus) belong in the always-loaded file. Catalogs do not.

The generated `sase.md` template is already **81 lines**. A 100-line budget for the whole file is impossible unless that generator shrinks. Nested `tools/AGENTS.md` (81) and home `AGENTS.md` (74) should stay on their own budgets. Grok also double-loads identical `AGENTS.md` + `CLAUDE.md` (~42 KB with home), which is a separate tax.

### Recommended solution

**Pointer-map `AGENTS.md` using memory you already have.** Three phases:

1. **Content, existing knobs:** compact `memory-sase.template.md`; switch `decisions` off `roster: list`; keep rust-core and the eight hard rules always-loaded. Lands around 140–160 lines.
2. **Product:** add `roster: index` (names only, hide superseded strands), overflow to `sase memory web show`, and a `sase memory init --check` ratchet at **100 lines / 2,000 tokens**. This is the ≤100 hit.
3. **Follow-ups, separate beads:** Grok double-load; skill-description two-tier catalog; `sase memory read` with no args as a catalog.

Do not revive keyword/dynamic memory (`corpus-before-mechanism`). Do not move procedures into skills as the main fix (skill descriptions are already ~1k always-loaded tokens). Do not hand-edit `AGENTS.md`; it is generated.
