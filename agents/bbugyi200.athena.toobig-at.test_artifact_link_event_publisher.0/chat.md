# Chat History - ace-run (toobig-at.test_artifact_link_event_publisher.0)

- **TIMESTAMP:** 2026-11-27 18:09:25 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-at.test_artifact_link_event_publisher.0

## Prompt

%id:toobig-at.test_artifact_link_event_publisher.0
%clan(toobig-at, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 1 FILE[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 719  tests/sdd/test_artifact_link_event_publisher.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/sdd/test_artifact_link_event_publisher.py` file into multiple files? Use your best
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I'll start by reading the test file and the split/lint conventions so the new modules stay under 500 lines and keep the original import path.

The file is large, so I’ll read the rest in chunks and check how similar test modules were split.

I'll inspect existing split patterns and the rest of this 719-line test file so the new modules stay under 500 lines.

I'll look at recent split examples and the toobig/symvision rules so the new modules follow the same layout.

I'll split the 719-line file into three focused modules plus a facade that keeps the original import path.

The split is in place. Next I’ll confirm each file is under 500 lines, then run the three lints one at a time.

Toobig passed. Waiting for mypy and symvision to finish.

The lints are still compiling the Rust extension; I’ll wait for that rebuild to finish.

Both lints exited 0. I'll confirm mypy's last lines, then run `sase tool run check`.

All three lints passed. I'll format with `just fix`, then run `sase tool run check`.

The scoped suite failed on a nested-check test. I’ll inspect that failure to see whether the split caused it.

The nested-check failure is the known flake `sase-1ve`. Publisher tests all passed, so I’ll refresh the finalizer context and submit the commit.

Split `tests/sdd/test_artifact_link_event_publisher.py` (719 lines) into three focused modules plus a facade that keeps the original import path.

**Layout**
- `test_artifact_link_event_publisher.py` (43 lines) — public re-exports, `__test__ = False`
- `test_artifact_link_event_publisher_sidecar.py` (332) — dual-root writes, collisions, quarantine, bead-without-store
- `test_artifact_link_event_publisher_local.py` (233) — ownerless and bead-only local receipts
- `test_artifact_link_event_publisher_deferral.py` (191) — phase order, aggregate deferral, lock/headroom

Git helpers stay private in the sidecar module. `_ownerless_event` and `_PUBLISH_PHASES` stay private in the deferral module. Monkeypatch targets still hit `ArtifactLinkStore.rebuild_aggregate` and `sase.sdd._artifact_link_event_publish._admit_incoming_event_objects`.

**Verification**
- `just _lint-symvision`, `just _lint-mypy`, `just _lint-toobig`: pass
- Split tests: 13 passed
- `sase tool run check`: lints passed; scoped tests had 1 NEW failure in `tests/tool/test_admission_processes.py::test_nested_agent_check_keeps_parent_and_never_queues` (`assert len(_started_children(w)) == 0 == 1`). That is the known flake tracked by `sase-1ve`; this split does not touch admission code.
