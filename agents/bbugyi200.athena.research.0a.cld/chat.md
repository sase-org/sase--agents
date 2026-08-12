# Chat History - ace-run (research.0a.cld)

- **TIMESTAMP:** 2026-08-12 10:46:00 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0a.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_102659.md`

## Prompt

%id(cld, clan=research.0a) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase The `sase ace` TUI's startup time has gotten progressively worse lately (it regularly takes >5s to finish starting up). Can you do some research with the goal of helping me reduce this start-up time? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research the ACE TUI startup performance. Let me start by getting oriented in the codebase.

The instructions require reading the TUI performance memory before this kind of work. Let me do that plus initial recon.

Now let me profile the actual startup and find the startup instrumentation.

2402 modules imported. Let me analyze that properly with a script.

Import is ~1.7s of the >5s. Let me find the rest — the runtime mount work.

Real stall data exists. Let me mine it for startup-phase stalls.

Now let me get an actual end-to-end startup profile. Let me check for headless run support.

Found the smoking gun. Let me analyze the agent-load timing log thoroughly.

The log only records loads slower than 2s. Let me check the agent-count growth trend and find what the "disk" stage actually does.

Critical finding: disk time is **flat** (~2.6s) regardless of agent count (0-99: 2.77s; 700-799: 2.46s) — fixed overhead, not O(agents). Let me find what it is.

Let me directly benchmark and profile the loader — that's the dominant cost.

Need the Rust binding built in this workspace. Let me kick off `just install` in the background and keep reading code meanwhile.

**33 MB archive ProjectSpec.** That's the growth vector. Let me check if the startup path parses it.

Confirmed: `find_all_patches` parses **enabled and archive** specs — including the 33 MB archive. Let me check the cache layer.

3,317 archived Patches in a 304k-line file, parsed cold at every startup. Let me check install and benchmark.

**`record_json` = 79.7 MB across 6,732 rows (~11.8 KB/row).** Let me check the Tier-1 limits and the FFI conversion.

0.67s for the index query alone. Let me split Rust vs Python-conversion cost.

~0.25s fixed floor regardless of record count. Let me isolate it.

Install finished. Let me now benchmark the full loader, and open sase-core properly to inspect the Rust query.

`repair_stale_rows_for_query` runs on every read query. Let me examine it — prime candidate for the fixed floor.

**Root cause found.** Let me verify `MarkerSignatures::from_artifact_dir` does filesystem work.

Let me empirically isolate the repair cost — `include_hidden=True` short-circuits it entirely.

Let me confirm the syscall volume directly.

Definitive: **62,009 syscalls vs 11,132** — ~51k wasted on excluded rows. Let me check what sets `hidden` and whether the index is ever pruned.

Let me get one end-to-end startup-equivalent measurement, then write up.

I have a complete picture. Let me check the research directory conventions before writing.

Let me verify one concrete import-chain finding before writing.

Now let me write the research document.

The `sase repo open` cleaned the sidecar and removed my untracked file — that's exactly why the skill must come first. Rewriting now that the repo is properly opened.

Research written to `sase/repos/research/202608/ace_startup_latency.md`.

## What I found

Startup splits into two costs, and one is almost pure waste.

**~1.2–1.7s is Python import** — `import sase.ace.tui.app` pulls **2,401 modules**, 1,676 of them from `sase` itself. No single hot module; it's a flat module explosion averaging 0.6ms each.

**~2.6s (p50) to ~4.6s (p90) is the first agent load's `disk` stage** — from ACE's own `~/.sase/logs/tui_agent_loads.jsonl`. That stage gates the startup stopwatch. 1.24 + 2.66 ≈ 3.9s at p50, 1.24 + 4.55 ≈ 5.8s at p90, matching what you're seeing.

The key result is a **negative** one that rules out the intuitive explanation: the disk stage is **flat in agent count** (0–99 agents: 2.77s; 700–799 agents: 2.46s). It's fixed overhead, not data volume.

## Root cause

`query_agent_artifact_index` calls `repair_stale_rows_for_query` before doing any selection. Because the TUI passes `include_hidden: false`, that pass selects **every `hidden = 1` row** — currently 4,706 of 6,732 — and stats each one's artifact directory: 8 marker `stat`s plus a `read_dir`, per row. On rows the query is explicitly excluding from the result.

`strace -c`, same index, same process, toggling only `include_hidden`:

| | production | repair skipped |
|---|---|---|
| total syscalls | **62,009** | **11,132** |
| statx | 46,073 (28,374 ENOENT) | 8,327 |
| records returned | 529 | **858** |

**50,877 extra syscalls to return fewer rows.** 0.23–0.42s even with a warm page cache; worse cold at first launch.

That's also the "progressively worse" mechanism: hidden rows are never pruned and accumulate ~46/day (202607: 4,155 → 202608: 551 in 12 days). It tracks your cumulative dismissed agents, not your current workload. And it fires on every 10s auto-refresh too.

## Recommendation

Fix it in `sase-core` (`crates/sase_core/src/agent_scan/index.rs`) — gate each row on a single directory `mtime` stat instead of 9+ file ops, and bound the repair to recent rows. That's ~a dozen lines, kills the growth term, and changes no user-visible behavior since the inotify `ArtifactWatcher` already covers live marker changes. Import reduction is the secondary lever — worth the two obvious defects (`toast_log.py:20` dragging the whole `sase.axe` subtree into a logging module; `unittest.mock` imported in production), but the broader lazy-import work is an epic, not a patch.

Two notes: I ran `just install` in this workspace (Rust rebuild) to get a working binding — no source changes, `git status` is clean. And `sase repo open` cleans the checkout, which deleted my first draft of the file written before opening the sidecar; I've saved that gotcha to memory and rewrote it.

Want me to file this as a task bead via `/sase_new_task`?

The file is intact and untracked. Committing it now.

Committed.

**`research` sidecar** — `80be930 docs(research): trace the >5s sase ace startup to index repair and imports`, containing the single new file `202608/ace_startup_latency.md` (321 lines). `git status --short --branch` shows `## main...origin/main` with no dirty entries and no ahead/behind marker, so the commit is pushed and the tree is clean. The two finalizer entries (linked repo `research` and SDD sidecar `research`) resolve to the same directory, so one commit satisfies both.

The sase workspace repo itself is clean — `just install` rebuilt the Rust binding but touched no tracked sources.

The research note stands as summarized earlier: the >5s splits into ~1.2–1.7s of Python import (2,401 modules) and a 2.6s-p50 / 4.6s-p90 `disk` stage that is flat in agent count, caused by `repair_stale_rows_for_query` stat-walking every hidden row the query is about to discard (62,009 → 11,132 syscalls when that pass is skipped). Recommendation is an mtime-gated, recency-bounded repair in `sase-core`.
