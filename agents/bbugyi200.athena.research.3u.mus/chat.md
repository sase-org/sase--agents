# Chat History - ace-run (research.3u.mus)

- **TIMESTAMP:** 2026-10-06 16:32:07 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3u.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_161855.md`

## Prompt

%id(mus, clan=research.3u)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3u.cdx`, `research.3u.cld`, `research.3u.grk`, `research.3u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Does the number of beads that exist for a sase project matter for bead read/write
performance? If so by how much? What are some ways that we can compress and/or archive
old beads in order to improve performance without losing any information permanently?

Can you do some research with the goal of answering all of these questions? Also,
critique this plan in general. Is this a good idea? Would you take a different approach?
Make any adjustments to the requirements that you think are justified but clearly call
these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Top finding: yes, bead count costs ~1–2s per operation at 7k beads, scaling linearly — because every op loads the full store — and ~92% of that tax comes from closed beads. But archiving alone is the wrong prescription without indexed reads.

Report written independently (no peer reports consulted) to [bead_count_performance_and_archival__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/bead_count_performance_and_archival__mus.md) and registered as durable snapshot `research:202610/bead_count_performance_and_archival__mus.md` (artifact `file:explicit:5ecaa0280f926abb6b58c0c1`).

Measured evidence: 7,034 beads (6,444 closed), `issues.jsonl` 20.7MB, 2,108 event streams (38MB), pages 33MB, git pack 101MB; `stats` 1.1–1.7s, `list` ~2s, single `read` 3.5–5.6s vs 0.5s startup floor; parse cost perfectly linear (~25µs/bead) but file-opens plus reduce dominate. Recommended: hot/cold projection split + pages GC first, then eligibility-gated closed-subtree archive sidecar with hash tombstones and lazy fetch, then indexed point reads — with latency-based acceptance thresholds, never hard deletion.

Declaration submitted for `sdd:research` report commit. Done.
