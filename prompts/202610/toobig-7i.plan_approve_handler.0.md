- **AGENTS:**
  - [bbugyi200.athena.toobig-7i.plan_approve_handler.0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-7i.plan_approve_handler.0/README.md)

%auto %id(plan_approve_handler.0, clan=toobig-7i) %model:@medium %queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `src/sase/main/plan_approve_handler.py`
file into multiple files? Use your best %wait:toobig-7i.cli_show_batch.0 judgment, but
keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.
