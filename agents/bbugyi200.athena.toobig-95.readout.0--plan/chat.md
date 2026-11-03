# Chat History - ace-run (toobig-95.readout.0--plan)

- **TIMESTAMP:** 2026-11-03 08:49:55 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-95.readout.0--plan

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: jg8yqm4kdaa9
Inspect with: sase monitor show jg8yqm4kdaa9
Monitor turn: toobig-95.readout.0--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11

Command:

```sh
just check
```

Reason:

Verify readout split before host completion


## Prompt

%id(readout.0, clan=toobig-95)
%model:@medium
%auto
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/instructions/readout.py` file into multiple files? Use your best
%wait:toobig-95.run_agent_runner_lifecycle.0
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

I'll split `readout.py` into smaller modules, then verify with the requested lints. First I'll inspect the file, its tests, and the split/lint conventions.

The file is large; I'll read it in chunks and look at similar splits plus the lint notes.

The file is 806 lines; I'll split along classification vs aggregation, put shared helpers in a private module, and keep the public `readout` import path.

I'll retarget the tests so private helpers come from the modules that define them, not the facade.

Formatting is clean. Next I’ll run the three requested lints on the split files.

All three lints passed. I'll read the monitor and finalizer skills before running `sase tool run check`.

The three lints are green. I'll prepare host completion and start the verify monitor for `sase tool run check`.

Split `src/sase/instructions/readout.py` (806 lines) into four modules, each under 500 lines. The public import path `sase.instructions.readout` is unchanged.

- `readout.py` — facade that re-exports the original public names
- `_readout_shared.py` — constants plus `read_json`, shared as public names in a private module
- `_readout_classify.py` — evidence gathering and `classify_artifact_dir`
- `_readout_build.py` — aggregation, table render, and the private helpers only it uses (`_delivery_mode_for_dir`, `_is_excluded_run`, `_is_research_run`)

Tests that imported `_classify_artifact_dir` and the other private helpers from the facade now import them from the defining modules.

`just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig` all passed. A verify monitor is staged to run `just check` (`sase tool run check`) after this turn ends.
