# Chat History - ace-run (research.1g.cld)

- **TIMESTAMP:** 2026-09-05 19:12:07 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1g.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260905_182106.md`

## Prompt

%id(cld, clan=research.1g) %m:@research_b  #gh:gh_sase-org__sase I've been thinking about ways we could allow sase to dispatch
to other known machines so the user can open up one TUI on one machine and manage all of
their agents across all machines.

- In practice, I plan to use this to manage all (e.g. launch, view, kill, etc...) sase
  agents that are running on any of my Tailscale devices from the `sase ace` TUI on my
  MacBook.
- Some lag is to be expected across network devices. But, once fully synced, I should be
  able to view and manage (e.g. from the "Agents" tab in the TUI) sase agents running on
  different machines in all of the same ways I can view and manage sase agents that are
  running on the local machine (i.e. the same machine as the TUI).
- I already did some research on this (see the tailnet_agent_fleet.md file in the
  research sidecar repo), but have since decided to remove the `agent_sync` import leg
  (see the sase-ws epic bead and the sase_collaboration_architecture.md file in the
  research sidecar repo for context). Review the tailnet_agent_fleet.md file for context
  and inspiration before performing your own (much improved I would expect, since you
  have more up-to-date information and a better starting point) research.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Make sure that the solution you
recommend is reliable, robust, and beautiful. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by gathering context — the prior research, the sase-ws epic, and the current architecture.

Now let me survey the current state of the tree — what's changed since that research.

I have a solid evidence base. Writing the report now.

The report is written. Now the required finalizer declaration.

Research written to `sase/repos/research/202609/cross_machine_agent_control_plane.md` (832 lines), linked as superseding `tailnet_agent_fleet` and deriving from `sase_collaboration_architecture`.

## What I found

I re-verified the predecessor report against the current tree (`sase` @ `302e6d643`, `sase-core` @ `fe9a643`) and measured live on **athena**. Its transport conclusion holds — but it misidentified the hard part, and two of its load-bearing assumptions no longer hold.

**Four findings that changed the design:**

1. **The fleet wire already exists.** `AgentArtifactRecordWire` is a versioned contract shared by Rust (`sase_core::agent_scan::wire`) and Python (`sase.core.agent_scan_wire`), and `_done_snapshot_loaders.py` already builds ACE rows from it with **zero filesystem access**. Inventing a "fleet DTO" beside a 209-field row model would be the mistake — remote records should flow through the *same* Python presentation code as local ones, so parity is structural rather than a 162-module checklist.

2. **The index is a catalog, not a liveness oracle.** On athena, **1,860 index rows carry an active status while 17 agents are alive** — 99.1% phantom. Any design where the viewer decides liveness renders 1,843 agents that don't exist. `_running_loaders.py:253` would call `is_process_running()` on a *remote* PID against the local process table, then try to mutate the local index on a remote path.

3. **Reads must be resident, and it's worse than measured before.** The fork bridge is **6.3–6.7 s** on athena; the same data from SQLite is **14 ms** (~450×). Interpreter startup is only 0.85 s of that — so the resident-read case is stronger, not weaker, than the predecessor's model.

4. **The deleted import leg took the offline story with it.** The predecessor leaned on `agents_sync` as a partition-proof second plane; sase-ws deleted it and `agents-sync-publish-only` forbids rebuilding it. A viewer-side snapshot cache is now load-bearing, and the report specifies the constraints that keep it from becoming a second import leg.

I also corrected the predecessor's §5.3: **`sase_core` cannot host the client.** It has no tokio and no reqwest and is deliberately PyO3-free; the client belongs in `sase_gateway`, which already has both.

## The recommendation

Extend `sase_gateway` into one binary with two roles — `serve` and `federate` — with the scan wire as the fleet contract, consumed through the ACE provider seam that already exists. The ordered work:

1. **Split resolution from presentation in the ACE loader** — ~50 enumerable call sites, a local win with no network involved. Do it first.
2. Make serve reads resident (6.3 s → 14 ms).
3. Add one monotonic `revision` to the index that serves as cursor, delta query, and mutation fence simultaneously.
4. Ship read-only fleet visibility.
5. Only then mutations, behind ten fault gates.

Eight invariants make it robust by type and ownership rather than discipline — most importantly: local rows are never daemon-mediated, liveness is a resolved verdict never an inference, and stale `RUNNING` degrades to `UNKNOWN` rather than inviting a kill.

Two things worth your attention: the report has **5 open questions** (§12) — the sharpest being whether the MacBook needs a supervised daemon or an ACE-lifetime child — and one payoff neither prior report noticed: because the federate role speaks the gateway's own contract, `sase mobile` would see the whole tailnet through one pairing instead of one machine.

I'll start by inspecting the paused VCS operation and the conflicts.

Conflict resolved and staged. Now let me read the verification-gate memory note before running the gate.

Now running the project verification gate.

All lint gates passed, but my own `timeout 900` killed the run (SIGTERM) before the test lane finished — most of the time went to rebuilding the Rust core. Re-running now that the build is cached.

The aggregate confirms the resolution: every row I kept is a genuine durable row, and the doctor's 2-row drift is exactly the not-yet-applied `b3200b7` commit. Let me prepare the reusable union-merge for the conflict I expect on the next pick.

Mine is pid 2571812. Waiting on it directly.

`just check` passed clean — every lint gate plus the scoped test lane. No fixes to fold in. Continuing the paused rebase.

The expected second conflict. Applying the same identity-union merge.

The rebase completed and the working tree is clean. Now resuming the stitch.

Referenced-by index check is now **OK**. The aggregate check still reports drift, but with a *different* row delta than before (`read: 2` missing / `related: 2` extra vs. the earlier `derives-from`/`read` pair) — ambient churn from other agents, not my resolution, and it's host state outside any repo.

The resume surfaced a real defect worth tracking:

Exact same root cause, already tracked. Corroborating rather than filing a duplicate.

All work is complete and no repository is left dirty. Finishing the turn.

`submission_required: false` with no obligations — the resumed stitch already committed and pushed everything, and no repository is left dirty.

## Done

**The conflict.** The paused operation was an interactive rebase of `research`'s `main` onto upstream `72fc612`, mid-way through three picks. Two agents in the same family (`research.1g.cdx` and `research.1g.cld`) had each appended rows to the same artifact-link sidecar indexes.

Both conflicts were the append-to-the-same-list shape you flagged, so I resolved them by **union on row identity** — `(source_ref, target_ref, relation, origin)` — rather than by textually picking a side:

| File | base | ours | theirs | merged |
|---|---|---|---|---|
| `links/202609/tailnet_agent_fleet/tailnet_agent_fleet.md.json` | 5 | 7 | 7 | **9** |
| `links/202609/sase_collaboration_architecture.md.json` | 6 | 8 | 8 | **10** |

That identity choice mattered: each side contributed a `derives-from` row, and a naive dedupe on relation would have dropped one. They are genuinely distinct — `file:explicit:ae30a4f4…` (cdx, the then-uncommitted `tailnet_agent_fleet_v2.md`) versus `research:202609/cross_machine_agent_control_plane.md` (cld). I asserted no duplicate identities and no lost rows on both merges, and cross-checked the result against the durable aggregate in `~/.sase/projects/gh_sase-org__sase/artifact-links.json`, which independently contained exactly the rows I kept.

I also verified every `links/**.json` in the repo parses and is byte-identical to what `atomic_write_json` emits (`indent=2`, `sort_keys=True`, trailing newline) — the format check the sidecar has no linter for.

**Verification.** `just check` passed: all 14 lint gates plus the scoped test lane (63 of 3522 files). One correction to my own first attempt — my initial run reported `terminated by signal 15`, which was my `timeout 900` killing it, not a gate failure; most of that budget went to an unrelated `sase_core_rs` rebuild. The re-run was clean. Nothing needed folding in, since the sase repo was untouched.

**Resume.** `git rebase --continue` through both conflicts, then `sase stitch create --resume` succeeded. `research` is clean and in sync with `origin/main` at `8250318`.

Two things worth your attention:

- The resume printed `referenced-by write-back failed: sequence item 0: expected str instance, bytes found`. This is **already tracked as `sase-va`** (READY, `task(bug)`, `_pull_rebase_if_remote` passing no `text=True`). I recorded a `+1` instead of filing a duplicate. Notably, this bug is why the conflict was awkward to diagnose: it masked the real `git pull --rebase` conflict behind a Python `TypeError`.
- `sase doctor -C project.artifact_links_aggregate` still reports the aggregate stale — but the delta *changed* across the resume (`derives-from`/`read` before → `related`/`read` after), so it is ambient churn from other agents, not my resolution. `project.referenced_by_index` went from ERROR to **OK**. I did not rebuild the aggregate: it is host state outside any repo, and that is a lifecycle mutation needing your authorization. Say the word if you want it rebuilt.
