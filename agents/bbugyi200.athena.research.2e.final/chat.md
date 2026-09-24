# Chat History - ace-run (research.2e.final)

- **TIMESTAMP:** 2026-09-24 09:18:13 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2e.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260924_081856.md`

## Prompt

%clan(research.2e, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I've been thinking about implementing a
new service proc that serves as an optional daemon that makes reading and, ideally
(though this might be harder), writing sase beads much faster when it is running. I'm
not really sure if/how this will work though.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.2e.final %m:@xlarge
%wait:research.2e.cld %wait:research.2e.mus %wait:research.2e.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I've been thinking about implementing a
new service proc that serves as an optional daemon that makes reading and, ideally
(though this might be harder), writing sase beads much faster when it is running. I'm
not really sure if/how this will work though.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, gem, belonging to this
   dispatch's `research.2e.cld`, `research.2e.mus`, `research.2e.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cld.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

I've read the cld report. Next I'll read the mus and gem reports, then check the places where they disagree.

I'm still checking the claims the reports disagree on. Now I'm tracing whether the TUI bead pane really does a forced reload on every periodic tick.

The first `sase bead ready` run took **50 s** (the second took 1.3 s). I need to know whether reads can block on sync, so I'm investigating that outlier.

Before writing, I'll verify one detail: that the loose-object bloat really is old `issues.jsonl` copies.

The report says I filed a bug for the slow sidecar clone this turn, so I'll file it now through `/sase_new_task`.

No in-progress epic causally owns this: the grep found no sidecar-clone or dissociate work. Next I'm checking the `bug` task type's required fields.

Now I'll add the bead ID to the report's follow-ups and check the final layout.

The layout is correct. Now the final declaration.

I'd skip the read/write daemon. The slowness is real, but most of it comes from a few specific bugs a long-running process wouldn't touch. I verified the three reports against the code, production logs and my own timings, and wrote them up as one report, `202609/bead_speedup_daemon_vs_direct_path/bead_speedup_daemon_vs_direct_path.md`. The cld, mus and gem reports sit next to it, and the host committed everything to the research sidecar.

**Where the time goes**

| Cost | Size | Would a daemon remove it? |
| --- | --- | --- |
| Mutations: a publication safety check runs ~6,850 `git show` calls per write (`sase-17q`) | ~20 s of the 22–31 s per mutation; slowest 10% of real sync runs take 23.8 s | No; it would still have to run the check. The fix is ~2 git calls |
| First bead command in a new workspace: cloning the beads repo (new finding, filed as `sase-17r`) | typically 22 s, up to 47 s; 41 times in 13 h | No |
| `list`/`show`/`read` load the pager, Textual and TUI widgets at startup | 1.3–2 s per read | Only if the CLI became a thin client, which is the same work as fixing the startup |
| Every read replays the full 28 MB event history | 0.4–0.55 s, 1–3 times per command | Yes, but an on-disk cache inside `sase_core` also does this, for every caller |

The clone finding: the beads repo that new clones copy from has 1.15 GiB of unpacked git objects, mostly old copies of the 16.7 MB `issues.jsonl`, one per bead commit. Git's automatic cleanup never runs because it counts objects, not bytes. The clone flag `--dissociate` then copies all of that into every new workspace. With no network involved, that clone took 24 s from the bloated repo and 2 s from a packed copy.

**Where the reports disagreed**
- **Write speed:** cld (22–31 s) is right and gem (1.8–4.5 s) is wrong; 2,368 production sync runs confirm cld's numbers.
- **Socket precedent:** mus said SASE has none, but the federation worker already uses one.
- **Using `beads.db` as the cache:** gem's plan can't work as written, because that file is the Rust lock for bead writes. SQLite is still fine for a separate cache file; sase-core already runs a working SQLite index for agent artifacts.

**What's still right about your idea:** keeping a warm copy of bead state instead of rebuilding it every time is the correct instinct; it just doesn't need a process. The service host also fixes one thing that sank the earlier `sase-3e` daemon: nobody ever ran that daemon.

**Why not a daemon anyway:**
- Every command would work in two modes, with and without the daemon, and those modes drift apart. SASE's own `sase-3e` daemon was reverted in May (−40k lines), and upstream Beads deleted its daemon (~19.7k lines) for this reason.
- A daemon that confirms writes before pushing them breaks the rule that bead changes are published before the command reports success. An agent can exit and its workspace be deleted with the change unpushed.
- After the cache exists, a read daemon would save only ~10–30 ms per read.

**Changes I'm proposing to your requirements:**
- Beads should be fast for every consumer (CLI, TUI, scheduler, gateway) whether or not the daemon runs. Targets: reads ≤150–250 ms, writes ≤2 s including the push.
- Keep "published before success" for now. Loosening it is a separate product decision.
- Include the TUI, scheduler, gateway and editor, not just the CLI.
- Stop rewriting `issues.jsonl` on every write. This is the riskiest change: about 25 modules still read it.
- Add no new on/off switches. The cache must always match a full rebuild.
- Test performance on a store the size of the real one; the current perf test uses 50 beads.
- New: first-use latency in a fresh workspace counts as part of the goal.

**Recommended solution**
1. **Fix the obvious costs.** The safety check (`sase-17q`), a scheduler job that packs the beads repos (`sase-17r`), slimmer startup imports, a single push per write, ID lookup without loading the whole store, and dropping the TUI's forced reload on every refresh.
2. **Add a cache inside `sase_core`.** It's a throwaway file validated on each read by a ~6.5 ms check of the event files. It is not `beads.db`. It gets rebuilt whenever its format version changes.

   Estimated results: `ready` ~0.1 s (now 0.8–1.3 s), `list`/`read` ~0.2 s (now 2.7–3.8 s), a write ~1.5–2 s (now 22–31 s), and a new workspace's first bead command ~2–3 s (now ~22 s).
3. **Only if numbers still justify it:** a cache-warmer service proc that answers no requests.
4. **The one job that genuinely needs a daemon:** a machine-local queue that pushes bead writes to GitHub in the background. It only makes sense if you relax "published before success."

Decisions for you:
- Is "durable somewhere outside the workspace" an acceptable bar for bead writes? If yes, the background push queue is worth building early; if no, no write daemon is worth building.
- Can `issues.jsonl` stop being rewritten on every write, and can it leave git entirely?

A few follow-ups are listed in the report but not yet filed as beads: the TUI forced reload, the gateway starting Python for every bead request, and the perf-test size.
