# Chat History - ace-run (research.1b.cld)

- **TIMESTAMP:** 2026-08-27 11:12:51 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1b.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260827_105638.md`

## Prompt

%id(cld, clan=research.1b) %m:@research_b  #gh:gh_sase-org__sase The TUI is incredibly slow recently. Can you help me do some research by digging into sase's logs to figure out where these performance problems are coming from and what we could do to significantly improve the `sase ace` TUI's performance? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by getting oriented — the TUI perf memory note, the log locations, and what the logs actually contain.

There's already an `ace_startup_critical_path` research doc. Let me read the TUI perf memory and find the logs.

Now let me dig into the actual logs.

Rich evidence here. Let me examine the stall watchdog log first — that's the direct freeze forensics.

Startup taking 15.8s to agents-ready. Let me analyze the full corpus systematically.

Clear regression today. Let me correlate with data volume and look at today's runs in detail.

The row count is *falling* while load time *rises* — so it's not proportional to visible agents. Let me check the agent-load log.

`agents: 694` loaded from disk to render ~12 rows. Let me analyze the whole agent-load corpus.

10,418 slow-load events in 8 days, 98% of them blocked on `disk`. Let me trend it.

Disk loads peaking at **373 seconds**. Now let me see what's actually blocking the UI pump, from the stall stacks.

Two distinct failure classes emerging. Let me aggregate across all stacks and pull the full stacks of the key offenders.

The watchdog record itself is 2.2MB of asyncio task stacks. Let me count those tasks — that's a leak signal.

**874 live asyncio tasks — 847 are Textual widget message pumps**, mostly Markdown nodes. That explains the CSS/compositor stalls. Let me verify in code.

13,118 entries in a 17MB JSON registry. Let me trace the disk stage and the widget accumulation.

Let me quantify the actual costs — registry parse, DB size, thread pool contention.

GIL is enabled — so `to_thread` doesn't free the loop for CPU-bound work. Let me check the 195MB index for bloat.

`agent_artifacts` is 17KB **per row** — an index table storing bulk payloads. Let me see what's in it.

`record_json` is 141MB — 95% of the index, 14.5KB/row. Let me see how it's queried.

Let me check the TUI debug log and trace the loader path.

Major new signal: 20 live `asyncio_N` threads at exit, plus heavy git subprocess work. Let me analyze the git-ops log.

Git subprocess time is mostly agent processes, not the TUI. Let me pin down what dominates the TUI's 3s `disk` stage.

Let me measure the real loader in-process rather than infer.

Workspace venv lacks the Rust core; let me benchmark with the installed sase runtime instead.

Hard numbers now. Let me check refresh cadence and whether the Rust query pulls `record_json`.

`refresh_interval` defaults to **10 seconds** — and each full load costs 1-3.5s. Let me check the Rust query's column selection.

Confirmed. Let me read both query sites — one does `LIKE` scans over the 141MB column.

Let me quantify the `LIKE` full-table scan and find when it runs.

Critical question: does the Rust binding release the GIL? Let me check.

The Rust query releases the GIL, but the **marshalling back to Python does not**. Let me measure that split.

784,314 Python objects per refresh, every 10s, to show ~12 rows. Let me measure how much that starves the UI thread.

Direct proof: one background load blocks the UI thread 234ms. Let me measure the full loader under realistic concurrency.

Concurrency gives **zero** parallelism — 8 threads take 8× as long. That's definitive GIL serialization. Now the interactive side: DOM size and watcher rate.

Let me check the loader's query bounds and startup import cost.

Let me check whether the widget count grows over a session (leak) or is steady-state.

Let me verify the delta path exists but is rarely taken — that's key to the recommendation.

Let me open the research sidecar properly and check the prior related report.

Let me capture scope metadata, then write the report.

Now I have a complete evidence chain. Writing the report.

Report written. Now the required final declaration.

Report written to `sase/repos/research/202608/ace_tui_steady_state_performance.md`.

## What the logs say

The slowness isn't in startup or rendering — it's a **refresh loop that rebuilds the entire agent history every 5–10 seconds**.

**The regression is dated.** `tui_startup.jsonl` shows `agents_ready` median jumping 4.88s → **11.15s** on 08-27, on top of a slow two-week creep. Critically, `agent_row_count` moved the *opposite* way (33 → 12 rows). Fewer rows, slower loads — the cost isn't proportional to what's on screen.

**The loop.** `tui_agent_loads.jsonl` logged **1,878 slow (>2s) loads today alone — 168 minutes of cumulative load time.** 98% of them block on `disk`; 96% are `load_kind: full`.

**Why "off-thread" isn't helping.** I measured this directly rather than inferring it:

- One refresh materializes **784,314 Python objects** from a **25.5 MB** payload to paint ~12 rows.
- Running 8 loads concurrently takes **8× as long** as one (1.08s → 9.21s) — literally zero parallelism.
- The Rust query correctly does `py.allow_threads(...)`, but `serde_json::to_value` + `json_value_to_py` right after it rebuild the whole object graph **holding the GIL**. That's the part that stops the UI.
- A single background load stalls a 1ms-tick probe thread for **234ms**; eight stall it for 359ms. ACE exits with 20 live `asyncio_N` threads.

This reframes the stall stacks: the main thread gets caught inside cheap operations (`query(PromptInputBar)` at 7.42s, CSS matching, compositing). Those aren't slow code — they're just where the UI thread was standing when the GIL was taken away.

**The root cost.** `record_json` is **141 MB of the 195 MB index — 95.3%, 14.5 KB/row** — and `select_records` pulls it for every row on every refresh. The table already denormalizes the 45 scalar columns the list view actually renders.

## Recommendation

Stage 1 is projecting `record_json` off the list-render path in sase-core and fetching it lazily per-row. That collapses the payload ~95% and the object graph with it, with no behavior change. Stage 2 fixes the delta path, which already exists but is taken 2% of the time — one unmapped watcher path discards the whole queued batch and escalates to a full reload.

Two notes: the 08-12 `ace_startup_critical_path` report flagged the `record_json` issue in `refresh_stale_rows`; it's still open, and the *main* query has the same problem. And the memory note's rule 1 ("push work off-thread") is actively counterproductive for CPU-bound Python here — I'd suggest amending it, though that's your call since it's a memory file.

Two incidental finds I did **not** file beads for: 14 `WorkerFailed: asyncio.run() cannot be called from a running event loop` crashes, and 90+ `git rebase failed` warnings on workspace plans clones. Both look like genuine separate bugs if you want them tracked.
