# Chat History - ace-run (research.3u.gem)

- **TIMESTAMP:** 2026-10-06 16:41:11 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3u.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261006_161855.md`

## Prompt

%id(gem, clan=research.3u)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3u.cdx`, `research.3u.cld`, `research.3u.grk`, `research.3u.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

# Research Report: Bead Store Scaling, Compression & Archival Analysis

**Author:** Researcher `gem` (`research.3u.gem`)  
**Report Artifact:** [`research:202610/bead_store_scaling_compression_and_archival__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/bead_store_scaling_compression_and_archival__gem.md)  
**Artifact Ref:** `file:explicit:3f88400144a7a0ef7605d417`

---

## Executive Summary & Core Verdict

1. **Does bead count matter for read/write performance, and by how much?**
   - **Yes, severely and linearly ($O(N)$)** across both read and write operations.
   - **Read Path**: The Rust core (`sase_core`) uses an unindexed, whole-store replay model. Every query (`sase bead read`, `show`, `ready`, `stats`, `blocked`) traverses the directory of stream files, opens and deserializes all **2,108 `.jsonl` files**, and replays all events into memory. In the live repository (**7,034 beads**, 38 MB event store), this raw load takes **~732 ms**. In agent environments (`sase bead read`), an additional unindexed linear scan over 11,432 artifact link outbox records in Python adds **~2.85 s**, resulting in a total read latency of **5.8 to 6.6 seconds** per bead.
   - **Write Path**: Every single mutation (`create`, `update`, `close`, `note`, `+1`) acquires an exclusive lock, reloads and reduces all 2,108 streams ($O(N)$), validates all 7,034 issues ($O(N)$), rewrites the entire **20.75 MB `issues.jsonl`** file ($O(N)$), and then immediately stages and commits that 20.75 MB file into Git. A single field update currently takes **~1.40 seconds** locally (726 ms in Rust + 669 ms in Git commit), which has bloated the `.git` directory to **104 MB** across **20,439 commits**.
   - **Synthetic Benchmarks**: Read latency scales at ~45 µs per stream file on NVMe: $N=100$ takes **4.1 ms**, $N=1,000$ takes **37.7 ms**, $N=5,000$ takes **211 ms**, $N=10,000$ takes **425 ms**, and $N=15,000$ takes **688 ms**.

2. **What are viable ways to compress or archive old beads?**
   - **Active vs. Cold Archive Partitioning**: Segregate closed streams into an archive partition (`events/archive/streams/`). Since **91.6% (6,444 of 7,034)** of beads are closed, this shrinks the active store from 2,108 streams to ~200 streams, immediately dropping active load time from 732 ms to ~25 ms (a 29x speedup).
   - **Stream Event Compaction (Snapshotting)**: Collapse historical multi-event streams into a single snapshot event (`issue_compacted`), reducing raw event count and parsing time by ~60%.
   - **Derived Read Projection Cache (Local SQLite / DuckDB)**: Decouple reads from raw event streams by querying an incrementally invalidated local cache. Read latencies drop from 732 ms to **< 2 ms**.
   - **Targeted Single-Stream Point Reads**: For point queries (`show`, `read`), load only `<stream_id>.jsonl` ($O(1)$ IO, < 5 ms).

3. **Critique of the Archival Plan (Is this a good idea? What is the alternative?)**:
   - **Treating Symptoms vs. Root Cause**: 7,000 JSON records (~20 MB) is tiny. In an indexed engine (like SQLite), querying 7,000 rows takes **< 1 ms**. The slowness is caused by **architectural I/O defects**: (1) opening 2,108 individual files per query, (2) rewriting a 20 MB snapshot on every mutation, (3) synchronously committing that 20 MB file to Git, and (4) linear scanning in Python outbox link checks. Archiving beads without fixing the architecture is a treadmill: as new beads accumulate, the system will slow down again.
   - **The Referential Integrity Danger**: In `sase_core/src/bead/events/reduction.rs` (line 405), `reduce_event_streams` strictly enforces dependency validity (`dependency_added target does not exist: <id>`). Archiving closed beads without resolving inbound dependency edges in active streams will **fail reduction and brick the store**.
   - **The Duplicate Detection Blindspot**: Agents run `/sase_new_task` to prevent duplicate issues. If closed beads are hidden in a cold archive, duplicate detection fails, causing duplicate bug filings and wasted agent tokens.

---

## Empirical Benchmark Findings

### Production Baseline (`sase/repos/beads`, $N = 7,034$)
```
Issue Breakdown:
  Total Beads:       7,034
  Closed Beads:      6,444  (91.6%)
  Active Beads:        590  ( 8.4%) [Open: 27, Ready: 393, In Progress: 169, Snoozed: 1]
  Stream Files:      2,108  (38 MB across events/streams/*.jsonl)
  issues.jsonl:      20.75 MB
  Git Commit Count: 20,439
  .git Size:         104 MB
```

### Measured Operation Timings

| Operation | Current Baseline | Primary Bottleneck |
| :--- | :---: | :--- |
| **`read_event_store_issues`** (Rust) | **732.5 ms** | Opening & parsing 2,108 separate `.jsonl` files + event reduction |
| **`read_legacy_jsonl_issues`** (Rust) | **324.2 ms** | Reading single 20.75 MB `issues.jsonl` (2.2x faster than 2,108 files) |
| **`bead_update`** (Rust) | **726.3 ms** | Re-reducing store under lock + serializing & writing 20.75 MB `issues.jsonl` |
| **`git add . && git commit`** | **668.8 ms** | Hashing & creating a new 20.75 MB Git blob delta on every mutation |
| **Total Local Mutation Round Trip** | **1,395.1 ms** | Rust mutation (726 ms) + Git commit (669 ms) |
| **`sase bead read <id>`** (Python CLI) | **5,863.0 ms** | Python outbox linear scan (2,871 ms) + Rust load (786 ms) + URL/render (1,285 ms) |

### Synthetic Scaling Curve ($N \in [100, 15,000]$)

| $N$ (Beads) | Streams ($S$) | Read Latency (`read_event_store`) | Write Latency (`bead_update`) | Generated `issues.jsonl` Size |
| :---: | :---: | :---: | :---: | :---: |
| **100** | 100 | **4.1 ms** | **57.6 ms** | 58.7 KB |
| **500** | 500 | **18.9 ms** | **68.2 ms** | 295.4 KB |
| **1,000** | 1,000 | **37.7 ms** | **94.6 ms** | 591.2 KB |
| **2,500** | 2,500 | **101.1 ms** | **148.1 ms** | 1.45 MB |
| **5,000** | 5,000 | **211.4 ms** | **262.0 ms** | 2.90 MB |
| **7,500** | 7,500 | **319.2 ms** | **344.3 ms** | 4.36 MB |
| **10,000** | 10,000 | **425.8 ms** | **461.9 ms** | 5.81 MB |
| **15,000** | 15,000 | **687.7 ms** | **631.3 ms** | 8.74 MB |

Both reads and writes exhibit strict $O(N)$ linear scaling.

---

## Justified Adjustments to Requirements

1. **Prioritize Architectural I/O Fixes Over Physical Archival**:
   Targeted point reads, Git commit decoupling, and a local read projection cache deliver a **50x to 300x speedup** immediately with *zero* data migration risk and *zero* loss of historical context.
2. **Archival Units Must Be Epic Subtrees, Never Arbitrary Beads**:
   Individual bead archival breaks DAG referential integrity in `reduction.rs`. Archival must only operate on *complete closed epics* where the parent plan, all child phases, and all dependent tasks are closed and carry zero active inbound dependencies.
3. **Decouple `issues.jsonl` from Synchronous Git Commits**:
   Committing a 20.75 MB projection file on every single mutation is the primary cause of write latency and Git repository bloat. Make `issues.jsonl` an untracked/ephemeral projection or update it on periodic sync cycles.
4. **Enforce a Unified Virtual Read Facade**:
   Search and `/sase_new_task` duplicate triage must query a unified index across active and archived beads so agents never lose historical visibility.
5. **Optimize the Python Artifact Link Outbox Scan**:
   Address the linear scan in `_artifact_link_outbox_io.py`, which currently wastes 2.85 seconds on every `sase bead read`.

---

## Recommended Solution & Phased Roadmap

```
┌──────────────────────────────────────────────────────────────────────────────────┐
│                             ENGINEERING ROADMAP                                  │
├──────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│  PHASE 1: Immediate High-ROI Architectural Fixes (Weeks 1-2, Zero Migration)    │
│  ├─ Targeted Single-Stream Point Reads (sase bead read/show): < 5 ms             │
│  ├─ Decouple issues.jsonl Git Commits: cuts 670 ms per mutation                  │
│  └─ Optimize Python Artifact Link Outbox Scan: cuts 2.85 s per bead read         │
│                                                                                  │
│  PHASE 2: Incremental SQLite Read Projection Cache (Weeks 3-4)                   │
│  ├─ Local, untracked beads.cache.sqlite in workspace                             │
│  ├─ Incremental sync via stream mtime / manifest transaction sequence            │
│  └─ Queue queries (ready, blocked, stats) execute in < 2 ms                      │
│                                                                                  │
│  PHASE 3: DAG-Aware Epic Subtree Archival (Weeks 5-6)                            │
│  ├─ sase bead archive command for closed epic subtrees                           │
│  ├─ Strict DAG boundary validation (no active inbound dependencies)              │
│  └─ events/archive/ partition with unified search fallback                       │
│                                                                                  │
└──────────────────────────────────────────────────────────────────────────────────┘
```

### Projected Performance Scorecard

| Metric | Current Production Baseline ($N=7,034$) | After Phase 1 (Targeted Reads & Git Decouple) | After Phase 2 (Local SQLite Cache) | After Phase 3 (Archive + Cache) |
| :--- | :---: | :---: | :---: | :---: |
| **`sase bead read <id>`** | **5,860 ms** | **~1,200 ms** (-80%) | **~300 ms** (-95%) | **~300 ms** |
| **Core Read Store Load** | **732 ms** | **< 5 ms** (targeted) | **< 2 ms** (cached) | **< 2 ms** |
| **Queue Queries (`ready`, `stats`)** | **1,070 ms** | ~1,000 ms | **< 20 ms** (-98%) | **< 15 ms** |
| **Local Mutation (`update`, `close`)** | **1,395 ms** | **~75 ms** (-95%) | **~45 ms** (-97%) | **~30 ms** |
| **Git Commit Size per Mutation** | **20.75 MB** | **< 5 KB** (stream only) | **< 5 KB** | **< 5 KB** |
| **Active Stream Files in Tree** | **2,108 files** | 2,108 files | 2,108 files | **~200 files** (-90%) |
| **Referential Integrity Risk** | None | None | None | **Zero (DAG-verified)** |
| **Duplicate Detection Intact?** | Yes | Yes | Yes | **Yes (Unified Index)** |

---

## Artifact Registration Details

The comprehensive investigation report has been authored and registered in the durable SASE artifact store:
- **Report Location:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/bead_store_scaling_compression_and_archival__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/bead_store_scaling_compression_and_archival__gem.md)
- **Repo-Relative Path:** `202610/bead_store_scaling_compression_and_archival__gem.md`
- **Artifact Label:** `research:202610/bead_store_scaling_compression_and_archival__gem.md`
- **Artifact Ref:** `file:explicit:3f88400144a7a0ef7605d417`
- **SHA-256:** `3d5ee804a38227ab0558ec2388a55558e92b9d4945219fe2f089602070ff2a7e` (32,020 bytes)

The finalizer declaration for `commit` has been successfully submitted and accepted for all required repositories (`sdd:research` and `sdd:beads`).
