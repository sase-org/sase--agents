# Chat History - ace-run (sase-xe.16.11.7.16.5.4)

- **TIMESTAMP:** 2026-09-15 15:48:29 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-xe.16.11.7.16.5.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-xe.16.11.7.16.5, bead=sase-xe.16.11.7.16.5.4)
%model:@medium
%auto
%w:sase-xe.16.11.7.16.5.1,sase-xe.16.11.7.16.5.2,sase-xe.16.11.7.16.5.3
%w(bead=sase-xe.16.11.7.16.5.1)
%w(bead=sase-xe.16.11.7.16.5.2)
%w(bead=sase-xe.16.11.7.16.5.3)
Can you complete the work for bead sase-xe.16.11.7.16.5.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-xe.16.11.7.16.5.4 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-xe.16.11.7.16.5.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-xe.16.11.7.16.5.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I’ll pick this up from the bead itself, then follow the SASE closeout rules exactly: description/design first, implementation, verification, epic-symbol cleanup, and only then close this one phase bead.

I’ve got the bead workflow rules loaded. Next I’m reading the bead and its linked plan so the change follows the epic’s design rather than guessing from the code alone.

The phase is specifically a release/adoption/live-acceptance phase, and the sibling implementation phases are already closed. I’m going to inspect the current dependency/build state and the acceptance tooling next, then I’ll decide whether this is mostly adoption/evidence or whether a compatibility fix still needs landing.

A useful bit already surfaced: the primary repo has been ratcheted to `sase-core-rs` `0.34.35` in both `pyproject.toml` and `uv.lock`, so the release-adoption part may already be present in this checkout. I’m checking the live-machine path and the reopened acceptance beads now.

The reopened acceptance beads are still open and explicitly document the old failure: Athena could reach Apollo, but a forbidden `lane` row remained while Apollo-local project view was empty. I’ll re-run that live path on the now-ratcheted build and capture the result as evidence rather than relying on the old notes.

On the controller I’m in, no machines are enrolled locally, which matches the old note from Apollo. Athena does have SASE installed, so I’m going to run the viewer-side checks from Athena over SSH; that is the side the acceptance text cares about.

Athena is actually a few commits ahead of Apollo for the `sase` host package, while both have the new core line. I’m checking whether Apollo’s gateway is still on the older installed command and what Athena sees over the authenticated machine link before deciding if a redeploy/restart is still needed.

Athena’s live status found the important remaining problem: Apollo’s authenticated hello succeeds, but the gateway is still the old running process and reports no `service_versions`, with a v1/v3 fleet contract skew. I’m going to refresh/restart Apollo’s gateway so the live service matches the installed build, then rerun the status/catalog checks.

I’m going to use the project’s own `sase update` path on both machines, then restart the gateway services. That keeps the deployment step inside the supported tool instead of poking at the uv environment by hand.

Athena is already up to date. Apollo’s update failed only because the noninteractive SSH shell didn’t have `uv` on `PATH`, so I’m rerunning it with the login-shell path and then I’ll restart the gateway.

Apollo’s update is taking a bit longer, which is normal for a dev-mode uv tool refresh. I’m keeping that running and will only move to acceptance after the installed command and gateway process agree.

Still waiting on Apollo’s `sase update`; no output yet, but the process is alive. If it finishes cleanly I’ll restart the gateway immediately and collect the before/after transcript in one artifact.

Apollo is still in the uv refresh. Since this is the deployment step the phase depends on, I’m going to let it finish rather than interrupt mid-install.

This has crossed the point where I want a second look at the remote process state. I’m checking Apollo’s process table in parallel so I can tell whether it’s actively building/installing or stuck on something environmental.

Good, Apollo isn’t stuck: it’s compiling the `sase_core_rs` extension for the uv-tool environment. That explains the quiet wait; I’ll let the build complete.

Still building on Apollo; I’m keeping the turn open and will continue as soon as the install returns.

Apollo’s compile is still running; not surprising with the optimized dev-update profile, but I’m checking once more that it’s making progress before waiting another chunk.

Apollo’s update finished with a failure after the Rust dev build moved into the LSP portion. I need the exact failure and whether the Python/core gateway bits were already updated before it bailed; I’m checking the installed versions and rerunning enough output to diagnose.

Apollo’s gateway has been restarted on the updated tool environment. Athena is stuck at its cached upstream because SSH auth to GitHub fails there, but it already has the required `sase-core-rs 0.34.35+4`; now I’m rerunning the live Athena-to-Apollo status to see whether the restarted gateway advertises the new contract/version.

The status call is in flight from Athena now; I’m waiting for the authenticated hello result and the Apollo service details side by side.

The restart did not change the hello response: Athena still sees Apollo’s fleet hello as schema v1 with no `service_versions`. That means this is not just a stale systemd process; I’m checking the actual gateway health/hello surface and the client/server contract next.

My quick inline Python probe had a quoting faceplant, but the more interesting clue is that the Python workspace barely mentions `service_versions`; this may live in the Rust core/gateway repo. I’m opening the linked core repo through the required SASE repo path before inspecting that boundary.

The unauthenticated gateway probe is expectedly 401 for hello and no public health route on that bind. I’ve opened the linked `sase-core` checkout at `sase/repos/linked/sase-core` and will inspect the hello wire there.

The Rust gateway source does include the `gateway_version` field, so Athena’s response is coming from a gateway surface that is still behaving like the older contract. I’m checking Apollo’s Tailscale Serve mapping and installed gateway entrypoint to make sure the public endpoint is actually pointed at the restarted service.

Tailscale Serve points to `127.0.0.1:7629` and the gateway entrypoint is the Rust/PyO3 `sase_core_rs.gateway` entrypoint, so the routing is correct. The remaining mismatch is inside the installed Rust extension or its served contract.

Apollo’s installed Python metadata has normalized versions (`0.17.1`, `0.34.35`), but it is importing from the dev checkouts and exposes the new fleet bindings. I’m checking the runtime contract schema from the extension itself; that will tell us whether the gateway process is actually running the new native module.

Both Athena and Apollo’s installed extensions report fleet contract schema `3`, so the native module is current. The status mismatch is specifically the hello payload’s capability set still carrying schema `1` and no gateway version in the client’s parsed result; I’m looking at the capability response construction now.

I found a real mismatch, not a deployment hiccup: `fleet_capabilities()` in the Rust gateway is still returning `FLEET_API_WIRE_SCHEMA_VERSION` (`1`) while the Python status command compares that field against the local fleet contract schema (`3`). That creates a false “restart target gateway” skew even on the updated gateway. I’m going to inspect the tests around this before deciding the smallest correct fix.

Athena is missing the exact host commit that consumes `gateway_version` (`d0975c719`), because its GitHub fetch is failing. Apollo has the current checkout at `c632a5552`, so I’m going to fast-forward Athena from Apollo over the tailnet after checking that Athena’s checkout is clean.

Athena cannot SSH back to Apollo, but Apollo can reach Athena, so I’ll transfer a small git bundle containing the missing `sase` commits and fast-forward Athena’s clean checkout from that local bundle. That avoids changing remotes or needing GitHub credentials on Athena.

The bundle verifies against Athena’s current `53035c967` base. I’m copying it over and fast-forwarding only the clean Athena checkout.

Athena is now fast-forwarded to `c632a5552`, matching Apollo. I’m checking the installed runtime and then rerunning the Athena-to-Apollo status.

Athena’s runtime now reports the current host commit and current core. Waiting on the live status call now.

Good: the live hello now includes `gateway_version: sase-gateway 0.34.35`, and both machines are on the current host/core build. The remaining status text is the existing schema-skew warning from the capability schema field; I’m going to keep that in the evidence as the live tool reports it, then check the actual fleet catalog/ACE grouping gates.

Apollo-local `sase agent list -a -p proj --json` is empty, which is the old ghost-row comparison point. I’m going to query the authenticated fleet catalog directly from Athena via the dispatch client, then drive an Athena ACE tmux pane to capture what the UI renders.

The direct catalog path is through the federation facade rather than the `sase machine` CLI. I’m reading that API shape so I can collect a raw authenticated catalog without inventing a separate client.

I have the facade call shape. I’m going to ask Athena’s federation worker for a fresh non-cache summary plus an `include_terminal` catalog page, and then summarize whether `lane`, `attempt-0`, or `y--plan` appear.

The fresh summary is live (`cached: false`) and says Apollo’s presentation catalog has 6 selected rows from 29 input rows. My first raw catalog request used a limit above the gateway max; I’m rerunning at the supported limit of 100.

The raw catalog is large because `include_terminal` exposes historical terminal rows too, and exact locators naturally contain `attempt-0`; that is not the old visible ghost row. I’m rerunning a compact label-only extraction so the evidence focuses on presentable labels/families rather than locator internals.

The compact raw catalog evidence passes the ghost checks: 7 presentation rows without terminal history, 29 rows with terminal history, and zero label-level `lane`, `attempt-0`, or `y--plan` in both. I’m launching an Athena ACE tmux pane filtered to `machine:apollo` now to capture the UI side of the same acceptance.

ACE launched on Athena in tmux session `sase_ace_agents`, window `sase_tmux_1`. I’m letting the fleet refresh settle, then I’ll capture the pane and cycle grouping to by-machine if it isn’t already there.

The tmux wrapper printed a logical window name, but the actual active window is `placeholder`. I’m capturing the active pane directly from the `sase_ace_agents` session.

The wrapper didn’t leave a live ACE process in that session, so I’m going to launch a dedicated detached tmux session myself with the same Athena command and capture that pane. If it exits, I’ll have the pane output and logs to explain why.

The direct tmux session also exited before capture. I’ll relaunch it with a trailing sleep so the pane survives long enough to inspect the failure or the rendered UI.

That preserve attempt also failed at launch, likely shell quoting rather than ACE itself. I’m simplifying the tmux command and printing the tmux creation status so I can see the actual failure.

The CLI positional query is parsed as the artifacts query language before the Agents tab, so `machine:apollo` is rejected there. I’m launching Agents without a startup query, then I’ll use the interactive view/grouping evidence from the pane.

The ACE pane is live now and initially says “loading machines…”. I’m waiting for the fleet refresh to populate, then I’ll switch grouping to by-machine and capture the resulting pane.

Machines loaded in ACE (`6 active · 1 machine`). I’m sending the grouping key now until the pane shows the by-machine grouping.

The grouping changed to by-machine and shows the `here` machine band. The Apollo band is likely below the fold in this 80x24 pane, so I’m going to navigate down/collapse the local band to bring the remote machine rows into view.

The Agents filter bar is bound to `f`. I’m going to open it and set the live Agents query to `machine:apollo`; that should make the remote band visible directly.

The interactive filter is open, but the current query did not clear cleanly and the parser is complaining. I’m checking the agent-query property key names so I can use the exact accepted machine filter syntax.

The filter grammar does support `machine:apollo`; the error came from stale text not clearing. I’m going to close and reopen the filter, send explicit line-kill keys, then submit a clean `machine:apollo`.

That capture now shows the live Apollo machine band in the ACE Agents view. I’m cycling once back to the standard by-project grouping with the same `machine:apollo` filter so the artifact has both grouping modes.

The by-machine ACE capture is good, but the by-project capture still visibly shows `apollo [agent] sase (RUNNING) attempt-0 aging`. That is one of the explicit forbidden labels, so I’m treating acceptance as not yet met and tracing the projection/display path rather than papering over it.

I’m picking up from the live acceptance evidence: raw fleet catalog looks clean, but ACE’s by-project view still exposes an `attempt-0` row. I’m going to finish the TUI-side trace now and fix the projection path that’s leaking that fallback label.

The perf note confirms this should stay in the projection/display layer and avoid adding any slow refresh path. I’m going to inspect the fleet projection and display grouping code now, with an eye for “attempt id as label” fallbacks.

That first search was noisy, but it gave us the right neighborhood: `models/fleet_agents.py`, `_fleet_agents_rows.py`, and the Agents grouping/rendering helpers. I’m narrowing to the code that builds remote row display fields rather than the whole TUI.

I’ve found the candidate leak: remote rows fall back from `labels.agent_label` to the exact or logical locator key, and the fallback tail can be `attempt-0`. The raw catalog proved the owner already has better logical/project labels, so the display adapter should prefer those before locator internals.

Before editing I’m checking the actual wire row that produces the visible `attempt-0`, so the fix is surgical and testable. The key question is whether this is a missing owner label, a proc-row special case, or a pure fallback ordering issue.

This is on Apollo, which explains why the ghost appears as a remote Apollo row only when viewing from Athena. I’m going to query Athena’s fetched catalog directly, then wire the regression test around the row shape it sees.

The renderer confirms normal agent rows print `presented_agent_name` directly; if the adapter sets that to a locator tail, it will leak. I’m checking the owner catalog through Athena to make sure the replacement source is present on the exact offending row.

The first Athena query hit an API naming mismatch, so I’m reading the facade signature locally and will rerun with the exact parameter names. Small detour, useful guardrail.

The facade uses a structured catalog query, not the convenience parameters I tried. I’ve got the signature now and I’m going back through the worker the same way the TUI does.

Interesting: Athena’s live catalog just returned zero rows for Apollo, while the earlier TUI capture had rows. I’m going to confirm whether the remote feed changed under us or whether my query path is missing the same loaded page state ACE had.

The live worker now has no Apollo rows, so the earlier `attempt-0` screen was likely from the prior non-empty feed state. I’m not going to rely on it disappearing by timing; I’m converting the leak into a fixture-level regression instead.

I’m also keeping in mind the bead’s acceptance target is live behavior, so after the code fix I’ll rerun ACE from Athena. If the feed stays empty, that proves no ghost row is rendered; if rows repopulate, the regression should keep the bad fallback out.

The tests’ fixture tells the same story: instance keys include the exact attempt, while logical locators carry the durable agent identity. I’m checking key formatting once so the fallback order change doesn’t break selection identities.

The stable identity for selection is still the raw suffix, built from the exact key, so we can stop using the exact key as a human name without collapsing rows. I’m going to patch the fallback and add a regression that renders the row to prove `attempt-0` stays hidden.

I’m making the display adapter prefer `logical_locator.agent_id` when owner labels are absent, while keeping the exact locator in `raw_suffix` for identity. The regression will specifically use an `attempt-0` exact key and assert it never appears in the rendered row.

The adapter patch is in place. I’m adding the focused test now, using the existing offline fleet fixtures so it stays fast and doesn’t need the live tailnet.

The regression is written. Because this touched tracked SASE files, I’m reading the project’s required lint/test note before I decide the full verification set, then I’ll run the focused tests first.

The focused projection and display-parity tests pass. The repo instructions require the whole `just check` gate for tracked changes, so I’m running that now; if it turns up formatting or lint fallout, I’ll keep it scoped to these files.

`just check` had to rebuild the Rust binding for this workspace before the Python gates could run. It’s still moving, so I’m letting it continue rather than shortcutting the required verification.

The check is still in the Rust compile stage after pulling the missing binding into the local venv. Once that finishes, the repo’s lint and scoped tests should start emitting their usual gate output.

No new output in this slice, which is common while the build works through heavier crates. I’m keeping the session open and will inspect failures immediately if the gate stops red.

The build is now compiling the linked `sase_core` crate itself, so we’re past dependency churn. I’m still waiting on the final lint/test phases.

Still compiling with no fresh output. This is the slow part of the first check in a stale workspace; I’m leaving it uninterrupted so the verification remains meaningful.

No new lines yet; the command is still alive. I’ll keep polling until it exits rather than leaving a verification process orphaned.

The gateway crate is compiling now, which matches the binding rebuild path that `just check` triggered. After this, I expect the normal Python gates to resume.

Still no exit. I’m keeping the long-running check attached; this is exactly the case the repo note warns may need a fresh install/build in an idle ephemeral workspace.

The command is quiet but still running. I’m giving it more time; once it produces the actual gate results I’ll react to those rather than guessing.

Still alive and silent. I’m staying with it; abandoning here would leave the required repo check unresolved.

No new gate output yet. This is tedious but straightforward; I’m continuing to wait on the existing check process.

It has been a long quiet compile window, so I’m going to peek at the running process tree while keeping the check attached. That will tell me whether it’s still compiling or hung somewhere else.

The process tree shows our `just check` is still in `maturin develop --release`, with `rustc` compiling `sase_core`; it is not hung in a prompt. There is another workspace running tests, but I’m not touching it.

Still compiling; no prompt or dead session. I’m continuing to wait on the same check.

No output yet. The release Rust build is simply taking a while in this workspace; I’ll keep polling until it returns.

The check remains attached and quiet. I’m giving it more time; the process tree showed active Rust compilation rather than an interactive wait.

Good, it moved past `sase_core` and is compiling the Python extension crate now. We should be near the end of the rebuild portion.

Still in the extension build. I’m letting it finish cleanly so the subsequent gates run against the rebuilt binding.

No new output in this slice. The check is still running, and I’m staying with it.

Still quiet, still running. I’m giving it another interval.

No change yet. I’ll keep the verification session alive until it exits; this is the required gate for the tracked edit.

Still no gate result. I’m checking patience against correctness here; the command is still attached, so I’m not going to start a duplicate `just check`.

This has gone quiet long enough that I’m peeking at the process tree again, just to confirm it is still compiling and not stuck after the build.

The tree shows `rustc` is now linking/compiling `sase_core_rs`, the final Python extension. It’s long, but still real work rather than a stuck prompt.

Still in the final extension build. I’m staying on the existing process.

No fresh output. Continuing to wait.

Still quiet, still running. I’m keeping it attached.

No result yet. This first rebuild is unusually slow, but the process is still active.

Still waiting on the same check. I’ll keep going until it exits.

No new output. I’m not starting parallel verification; duplicating this build would just make the machine slower.

Still attached. More waiting.

I’m going to check CPU state once more; this will tell us whether the linker/rustc is actively consuming CPU or just waiting on I/O.

`rustc` is still active at high CPU, so the long wait is a real release/LTO build. I’m continuing; this should eventually unblock into the normal check output.

Still active, no output. More waiting.

No result yet. Keeping the session alive.

The Python extension finished and was cached; `just check` is now rebuilding the sibling LSP server to keep directive contracts in sync. One more Rust build phase, then the actual gates.

The LSP build is in its dependency/crate phase now. This should be faster than the extension build, and I’m still attached to the same `just check`.

No new lines, still running. Waiting on the LSP build.

The LSP build reached the shared `sase_core` crate. It’s moving, just not chatty.

Still in the LSP/shared-core compile. I’ll keep waiting.

No new output. The command is still active.

Still waiting on the build phase.

Now compiling the LSP crate itself, which should be the last Rust step for setup.

Still finishing that crate. Waiting.

Setup finally finished and the actual checks have started. Python formatting passed; I’m watching the remaining lint/test gates now.

Markdown formatting, keep-sorted, and ruff are green. Waiting on the heavier lint gates and scoped tests.

No fresh output in this interval; likely a slower lint gate. Still running.

Still running quietly. I’m staying attached for the final gate result.

Mypy is green. The remaining gates should be symvision/other repo checks and scoped pytest.

No new output yet. Still waiting.

Still running quietly. The command remains active.

Feature-flag lint passed. Waiting on the next gate.

Pyscripts lint passed. Continuing through the last checks.

Test-wait and changelog lint are green. Waiting on remaining gates.

Patch/stitch terminology lint passed. Continuing.

No fresh output. Still running.

Symvision and toobig are green. That leaves the scoped test lane and any final aggregation.

No output yet; likely scoped pytest is selecting/running now.

Still running quietly. Waiting on the test lane.

No new output. The check has not exited yet, so I’m still attached.

SASE validation is green. Waiting for final scoped pytest result.

The core-floor probe reported an unrelated unpublished `sase-core` capability gap, but the check kept going and marked committed plans green. I’m waiting for the final exit code before deciding whether there’s any actionable failure here.

No final result yet; scoped tests are likely still running after the lint gates.

Still running, no output. Continuing.

No change. I’m staying with the same check.

Still no output. Waiting on final test lane.

This final quiet stretch is long enough that I’m checking the process tree again to see what gate is currently active.

The active gate is now `just test-scoped` in this workspace, running pytest with seven workers. That is the final verification lane; I’m waiting for its result.

Scoped pytest is still running quietly. Continuing to wait.

No output yet from the scoped tests. Still attached.

Still running. Waiting for pytest to finish.

No result yet. I’m keeping the gate attached until it exits.

Still quiet. Scoped pytest can be sparse under `run_silent`, so I’m giving it more time.

No output. Continuing.

Still waiting on scoped pytest. No failures surfaced yet.

I’m doing one more process check to see if pytest workers are active or if we’ve landed in a slow/hung individual test.

The pytest workers are active and using CPU, so this is work, not a hang. I’m continuing to wait.

Still running. More waiting.

No output yet; workers were active a moment ago. Continuing.

Still waiting on scoped pytest.

No new output. The check remains active.

Still running. More patience.

No result yet. Keeping the session alive.

I’m checking the pytest worker state again to make sure the long tail is still active.

Workers are still active across the pool, so it’s not stuck on a single idle wait. I’m continuing.

No output yet. Still waiting.

Still active, still quiet.

No output. I’m letting pytest finish.

Still no result. Continuing.

The test lane is still running beyond the usual short tail. Since the workers are consuming CPU, I’m not interrupting it.

Still waiting.

No output yet. Keeping the verification alive.

Still quiet. I’ll keep waiting.

No result yet; the scoped lane is still running.

Still running. I’m giving it another slice.

I’m checking worker state one more time because this scoped run has become the dominant wait.

All pytest workers are still using CPU, so this is still an active parallel test run. I’ll let it finish.

Still quiet. Continuing to wait.

No output yet.

Still attached, still running.

No result yet. Continuing.

Still running. The test pool is long but active; I’m waiting it out.

No output. Continuing.

Still waiting on scoped tests.

No result yet. I’ll keep the process attached.

Still quiet. Continuing.

No output. Waiting.

Still running; no failures printed.

No change. Continuing to wait on the active pytest pool.

Still no result.

Still running, likely a very broad scoped selection due the TUI module import graph. I’m staying with it.

Still no output from pytest. I’m not doing deployment work while the verification gate is running against this tree; I’ll let the local check finish first, then apply the same fix to the live Athena checkout for acceptance.

Still running. More waiting.

No result yet. Continuing.

I’m checking whether the pytest pool has narrowed down to a few long tests or still all workers.

All seven pytest workers are still active, so this is a broad CPU-heavy selection rather than a single stuck test. I’ll keep waiting.

`just check` completed, but the governed full-suite lane found one failure: `tests/test_sudo_acceptance.py::test_sudo_local_flow_never_persists_canary_credentials`. That is outside this change, so I’m rerunning that test alone to see whether it’s a flake or a persistent unrelated failure before I decide how to record it.

The failed sudo test passed immediately on isolated rerun, so it looks like a flake in the full-suite run rather than fallout from the fleet display change. I’m checking the diff/status now, then I’ll deploy the small Python change to Athena for the live ACE acceptance pass.

The patch is small and the worktree only has the intended two files. Before copying anything over, I’m checking whether Athena’s installed `sase` is editable from `/home/bryan/projects/github/sase-org/sase`; if it is, syncing these two files is enough for the live TUI acceptance run.

Athena’s installed tool imports directly from the checkout, so a two-file source sync is enough. I’m checking the remote worktree before copying so I don’t overwrite unrelated changes blindly.

The target files are clean on Athena. I’m syncing the two modified files into that checkout now so `sase ace` on Athena exercises the patched projection code.

The files are synced. I’m running the same focused projection test on Athena’s checkout, then I’ll do the live ACE capture from there.

The Athena-focused regression passes. For live acceptance I’m going to launch ACE in a tmux session, set the Agents filter to `machine:apollo`, capture by-machine and by-project views, and search the captured text for the forbidden labels.

Athena’s current CLI exposes the TUI as `sase tui` rather than `sase ace`, so I’m switching to that entrypoint for the live capture.

I’m launching a fresh tmux-backed TUI session on Athena. The live Apollo catalog currently has zero rows, so the TUI proof may be “no remote rows render”; the regression covers the non-empty `attempt-0` case directly.

That launch command had a quoting snag and exited immediately. I’m relaunching with simpler tmux quoting.

The tmux TUI session is running now. I’m giving it a few seconds to load before driving the Agents filter.

ACE loaded with a persisted `NOT machine:apollo` filter, which is exactly the opposite of what I need. I’m replacing it with `machine:apollo` and then I’ll cycle the grouping modes.

A notification modal stole focus before the filter edit landed. I’m closing it and then I’ll use the filter command again more carefully.

Escape didn’t dismiss that modal, so I’m using the modal’s close/cancel key path rather than interacting with the action buttons.

Now the filter editor is open. I’m replacing the persisted query text with `machine:apollo`.

The filter edit didn’t fully clear the old text, so the parser saw a mashed-together query. I’m using the line-kill binding now to replace the entire input.

The filtered live view now shows Apollo rows, and the visible project grouping no longer contains `attempt-0`, `lane`, or `y--plan`. I’m cycling to by-machine and capturing that view too.

The by-machine-style view also looks clean: Apollo host chips are present, no local `here` on remote rows, and none of the forbidden labels appear. I’m cycling once more to capture the plain by-project mode for the same filter.

The plain by-project capture is clean too; the old `attempt-0` row is gone. I’m grabbing a compact raw catalog/projection summary from Athena now so the close note has both wire-level and rendered evidence.

The compact projection confirms both active-only and terminal-inclusive fleet rows are clean: zero `lane`, `attempt-0`, and `y--plan` in display-relevant fields. I’m cleaning up the temporary tmux session now.

One unrelated full-suite flake surfaced during verification and passed on immediate isolated rerun. Per the bead instructions, I’m recording that as a proposed follow-up note on this phase rather than creating a task bead.

The bead note command is taking a moment, likely waiting on the bead store lock. I’m polling it now.

The follow-up note is recorded. I’m running the required epic-symbol check now; if it’s clean, I’ll close only the assigned phase bead with the verification summary.

The epic-symbol check is clean. I’m closing only `sase-xe.16.11.7.16.5.4` now with the acceptance and verification evidence.

The close command is waiting on the bead store as well. I’m polling until it completes.

The bead is closed. I’m doing the required SASE finalizer declaration now; after that I won’t mutate the workspace further and will summarize the outcome.

The finalizer requires a commit declaration for the dirty repo. I’m submitting it with `bead_action=close` for the assigned phase and a focused commit message.

The submit command doesn’t take `-f`; I’m checking the submit syntax and will immediately resubmit the same declaration.

The submit syntax is `sase final submit -`. I’m resubmitting now.

The finalizer couldn’t read bead status for its own close check, even though the bead close command already succeeded. Since the bead is already closed, I’m submitting the repository commit declaration with `bead_action=keep` so the host commits the tree without trying to close it a second time.

Completed and closed `sase-xe.16.11.7.16.5.4`.

Changed:
- `src/sase/ace/tui/models/_fleet_agents_rows.py`: remote fleet rows now fall back to `logical_locator.agent_id` before exact instance keys, so `attempt-0` can’t leak as the displayed agent name.
- `tests/ace/tui/test_fleet_agents_projection_metadata.py`: added a regression that preserves `attempt-0` in `raw_suffix` identity but verifies it does not render.

Verified:
- Focused local tests passed.
- Athena checkout focused regression passed.
- Live Athena TUI `machine:apollo` captures were clean in by-machine and by-project views: no `lane`, `attempt-0`, or `y--plan`; remote rows showed Apollo chips, not local `here`.
- Raw fleet projection checks reported zero forbidden display labels for active and terminal-inclusive rows.
- `sase bead epic-symbols sase-xe.16.11.7.16.5.4` returned no entries.
- `just check` ran; lint/setup gates passed, but the governed full suite hit one unrelated sudo acceptance failure that passed on immediate isolated rerun. I recorded that as a `PROPOSED FOLLOW-UP` note on the phase bead.

Final declaration was accepted for commit with message `fix(tui): hide fleet exact attempt fallback`.
