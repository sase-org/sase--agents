# Chat History - ace-run (sase-1tz.3.1.10)

- **TIMESTAMP:** 2026-11-20 13:21:37 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.3.1.10

## Prompt

%auto
#gh:gh_sase-org__sase
%id(10, clan=sase-1tz.3.1, bead=sase-1tz.3.1.10)
%model:@medium
%w(sase-1tz.3.1.9, for_epic=false)
%w(bead=sase-1tz.3.1.9)
Can you complete the work for bead sase-1tz.3.1.10? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.3.1.10` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.3.1.10` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.3.1.10 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.3.1.10 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.3.1.10 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.3.1.10`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.3.1.10 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Reading the bead's plan and the landed `bundle_trim` work, then I'll implement the doctor check, test, and docs.

Now looking at how the Codex flag gate resolves per project, and the existing doctor check modules.

Flags are process-wide, so the cap resolves once per provider. Now the doctor side.

I need each project's checkout path, not just its key. Checking what project records carry and how `default_facts` derives facts.

`workspace_dir` is the primary checkout. Now checking how the launch boundary builds facts so the doctor compiles the same bundle.

Caps resolve: Codex 32 KiB, Grok 120 KiB. Checking the render-cache key for freshness and timing a cold compile across enabled projects.

Cold run of 20 compiles takes ~4.5 s and a warm cache ~0.8 s, so the check will be `deep=True`. Checking `DoctorContext` and the cache home for test isolation.

The plan says every enabled project, so I'll ignore the `--project` filter. Looking at existing tests for these doctor checks to match the patterns.

Now the parity test, since the new just-check test needs sase's own bundle compiled the same deterministic way.

I'll enable every `*_explicit_instructions` flag in the test so a capped provider can't silently drop out. Checking the `DiagnosticCheck` model and how JSON output and `deep` are rendered.

Reading the required reference memories (docs writing, lint/test) before editing docs and finishing.

Now the docs pages named in the plan.

The size test compiles in pure Python (compaction step names are a Python constant), so it's safe in the contract set. Checking the doctor runner for per-check time budgets before writing the check.

No per-check timeout. Writing the code now, starting with publicizing the delivered-size helper.

Now the provider-cap enumeration helper next to `provider_root_max_bytes`.

Now the doctor check module itself.

Registering the check in the `instructions` group as deep-only.

Per that decision, I'll label rows by `display_name` and keep the directory key only as a JSON identity field. Checking the presentation audit guard so the change satisfies it.

I'll label rows by `display_name`, falling back to the key only when a record has none, and keep the key in JSON as `project_key`.

Now the tests. Checking where doctor tests live and the timing of a cold sase compile for the contract test.

Writing the doctor check tests.

Now the contract test for sase's own bundle.

On failure the section table would show compacted lengths, so I'll list the largest sections from an uncapped compile instead.

The patched lister is also called by `detect_project` (with `states="all"`). I'll make the fake delegate non-matching calls to the real function and record calls in a list.

`DiagnosticCheck` freezes `data` lists into tuples; adjusting the assertion.

Those 3 failures reproduce on the clean base: this workspace's `.venv` has a `sase_core_rs` older than the pin `bundle_trim` moved. Checking how the venv gets the pinned core.

Manifest picked up exactly the new file. Now the budget guard; checking the measurement command its comments reference.

Marginal cost is ~0.9 s. Updating the budget guard with a re-curation comment.

Guard passes. Now the docs; first checking other pages that mention oversize fallback or the size limit.

`agent-clis.md` is the page that lists the `instructions` deep checks, so the new check goes there. Checking the docs lint's page budgets before writing.

No ceilings apply and every target page has room. Writing the doc updates now, starting with the user-facing reference page.

Now the contributor internals page: the size-handling sentence, cache key, fallback list, and a new compaction section.

Docs done. Running `just fix` to format, then the docs lint.

While that settles, the plan's measurement step: count Codex oversize fallback notifications on both hosts over 7 days (read-only). Checking how those notifications are keyed and stored.

Before-numbers captured: athena 8 notifications / 212 events, apollo 8 / 230, for 2026-11-13..20. Recording them on the bead, then running `sase tool run check`.

Only failure: symvision flags `BundleSizeProject` (public but used only in its own file outside tests). Reading the symvision memory for the preferred fix.

Following the hierarchy: make it private (`_BundleSizeProject`); tests may import privates.

Symvision clean. Reformatting after the rename, then rerunning the full check.

The check exceeded the 1-hour tool timeout. Inspecting where that run was before rerunning.

My run still shows `running` even though the Bash wrapper was killed. Checking whether the child is alive.

The scoped pytest child (`-n 4`) is still running from the killed wrapper. Getting the run id to follow it.

The run is still alive and detached to my turn. Checking which stage it's on.

Every lint stage passed; only the scoped test lane remains (host load ~40). Waiting on the run.

The test stage passed (escalated to the full suite because the contract manifest changed). Confirming the run settled green.

`sase tool run check` succeeded (exit 0, full suite after escalation). Verifying the working tree still holds my changes, then the epic-symbol check.

No epic-symbol leftovers. A final read of the new check module before closing.

All verified. Recording one follow-up (bob-cli still needs compaction, so the new check WARNs there), then closing the bead.

Bead closed. Now submitting the final declaration.

I finished bead sase-1tz.3.1.10 and closed it. `sase tool run check` passed on the final tree; its test stage escalated to the full suite. The host commits the work after this turn.

**Doctor check `instructions.bundle_size`** (deep-only, `src/sase/doctor/checks_instructions_bundle_size.py`)
- It runs for every enabled project and every provider whose root slot has a byte cap with explicit delivery on (Codex at 32 KiB and Grok at 120 KiB today). For each pair it compiles the root bundle the way a launch does, from the project's main checkout and your real home memory.
- **ERROR:** the bundle is still over the cap after compaction, so that launch falls back to native instructions.
- **WARN:** the bundle fits only after compaction (it names the step and the uncompacted size), or it failed to render.
- **OK:** everything fits; the summary shows the bundle closest to its cap.
- Projects are labeled by name, not directory key.
- Run live here, it reports WARN for one bundle: bob-cli on Codex fits only after compaction, 30,392 of 32,768 bytes, down from 36,425. All other projects fit both caps.
- It takes about 4.5 s cold and 1.2 s warm, so I made it deep-only.

**Size test for sase's own bundle** (`tests/instructions/test_sase_bundle_size_gate.py`)
- It fails if sase's root bundle needs compaction for any capped provider, and lists the largest sections when it does.
- I added it to the always-run contract test set and raised that set's entry budget from 89 to 90 in `tests/test_contract_manifest.py`. Without this, an edit that only touches `sase/memory/*.md` runs only the contract set, so growth there would never reach the test. It adds about 0.9 s.

**Docs:** the instruction-bundle reference and internals pages now describe the size caps and compaction. I also updated the Codex provider page's 32 KiB text and added the new check to the doctor check list in `agent-clis.md`.

**Before-measurement** (read-only, recorded on the bead and on sase-1tz.3 along with the command to repeat after install): Codex fell back to native instructions for being oversize 212 times on athena and 230 times on apollo between Nov 13 and Nov 20.

I left one `PROPOSED FOLLOW-UP:` on the bead: trim bob-cli's always-inlined memory, mostly its 75-entry decisions roster, so its Codex bundle fits without compaction. That work is in bob-cli, outside this epic.
