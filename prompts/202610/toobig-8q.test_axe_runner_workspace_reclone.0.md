- **AGENTS:**
  - [bbugyi200.athena.toobig-8q.test_axe_runner_workspace_reclone.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-8q.test_axe_runner_workspace_reclone.0/README.md)

%auto %id(test_axe_runner_workspace_reclone.0, clan=toobig-8q) %model:@medium
%queue(capacity=5) #gh:gh_sase-org__sase Can you help me split the
`tests/test_axe_runner_workspace_reclone.py` file into multiple files? Use your best
%wait:toobig-8q.test_artifact_link_quarantine_replay_evidence.0 judgment, but keep every
resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.
