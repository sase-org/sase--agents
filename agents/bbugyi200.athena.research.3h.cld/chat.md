# Chat History - ace-run (research.3h.cld)

- **TIMESTAMP:** 2026-10-03 14:01:22 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3h.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261003_133508.md`

## Prompt

%id(cld, clan=research.3h)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3h.cdx`, `research.3h.grk`, `research.3h.mus`, `research.3h.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

My
apollo machine keeps killing all of its sase agents due to OOM errors I believe. Can you
dig into this / do some research with the goal of helping me figure out what is causing
this and fix it? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Next I'll check the zero-code workaround: start the TUI inside a `sase-*` scope, so the current `detach_scope` code treats it as SASE-owned and escapes each agent into its own scope.

Probe scopes are cleaned up. The kernel counter now reads `oom_kill 9`: the 3 real kills plus 6 from my deliberately capped probes. I'm writing the report now.

Registration succeeded. Now the final declaration.

apollo's agents are dying because of two problems that only cause a wipe-out together. A `bob query` command uses a huge amount of memory and runs the machine out of RAM. Then systemd shuts down the whole tmux pane the kernel's OOM kill landed in, and every sase agent lives in the TUI's pane. The report is written and registered as an artifact.

**What triggers it.** I checked every agent command ever run on apollo. An unscoped `bob query … FLATTEN file.tasks … GROUP BY …` was running at all 3 OOM kills since boot (Oct 1 21:15, Oct 3 16:24 and 17:32 UTC), and each died in the same second, 7–49 s after it started. Every unscoped query of that shape coincided with an OOM; the scoped ones (`FROM "2026"`) finished fine. They came mostly from codex agents in bob-cli doing task counts across the whole vault.

**Why `bob query` uses so much memory.** For every task on a page, bob's Dataview engine makes a full copy of that page, and each copy contains all the page's tasks again. `GROUP BY` then copies every row twice more. The vault has pages with 2,413, 2,012 and 819 tasks. I measured it on apollo inside scopes with a hard memory cap:
- Any `bob query` costs 2.85 GiB just to load the vault.
- Flattening one 509-task page takes 6.96 GiB.
- One 819-task page goes past 8 GiB and gets killed.
- A query over the whole vault would need tens of GiB; apollo has 31 GiB and no swap.

A `TASK WHERE blockId = "ref" GROUP BY status` query gives the same answer in 1.6 GiB.

**Why every agent dies.** sase only moves an agent into its own systemd scope when the launcher is a sase-owned unit. The TUI runs in a tmux pane (`tmux-spawn-*.scope`), so in five days apollo never created a single per-agent scope: everything shares the TUI's pane. That pane uses systemd's default `OOMPolicy=stop`, so when the kernel kills the oversized query, systemd stops the whole pane, including the TUI and all agents. I reproduced this: with `stop`, a sibling process dies along with the runaway; with `continue`, only the runaway dies.

**Recommended fix:**
- **Today, no code changes:** in `~/.config/systemd/user.conf` on apollo, add `DefaultOOMPolicy=continue` under `[Manager]`, then run `systemctl --user daemon-reexec`. Then restart the TUI in a new tmux window as `systemd-run --user --scope -p OOMPolicy=continue --unit="sase-tui-$(date +%s)" sase -p tui`. I verified that the current sase code then puts each agent in its own scope. The pane the TUI runs in now can't be switched in place.
- **Today:** add a rule to the `bob_query` skill: never `FLATTEN file.tasks` across the whole vault; narrow it with `FROM` or use a `TASK` query.
- **Fix the cause in bob-cli:** stop copying whole pages when building rows, and stop copying the variables on every expression evaluation. Add a memory cap so a bad query fails with a clear error, plus a test with a 2,000-task page.
- **Fix in sase:** there's an uncommitted change in apollo's `sase_10` workspace that does most of the containment. It has one bug: it requires systemd 243 for `OOMPolicy`, but scopes only support it from systemd 253. As written, agent launches would fail on hosts with systemd 243–252 (Ubuntu 22.04, Debian 12). After that, put agent scopes in a memory-capped slice so a runaway hits a contained limit instead of a host-wide OOM.

**Open question:** for the 17:32 kill, systemd logged only a 4.3 GiB peak for the TUI pane, which doesn't fit a runaway query inside it. OOM-scoring arithmetic implies the victim was over ~6 GiB, so I treat that number as unreliable. `sudo journalctl -k` around 17:31–17:34 would name the killed process; I couldn't run it without sudo.

My test queries on apollo raised the kernel's OOM counter from 3 to 9; those scopes and temp files are cleaned up.

Files are in `sase/repos/research/202610`:
- apollo_oom_agent_wipeouts__cld.md

Registered as `research:202610/apollo_oom_agent_wipeouts__cld.md` (`file:explicit:5e04161b3e85873837e5776f`). The final declaration for committing the report was accepted.
