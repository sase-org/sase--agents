#fork:sase-s1.6--plan
%model:grok-4.6
%effort:xhigh

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
just check-full
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-08-22T13:58:18.877081+00:00 |
| **Finished** | 2026-08-22T14:22:56.434452+00:00 |
| **Elapsed** | 24m 36s of a 3h 0m 0s budget |
| **Output** | 328 KiB · log file: `/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202608/22/20260822135818/live_reply.md` · full log: `sase monitor show 5c8x58x1a4yz --all-lines` |

**Why this was monitored:** sase-s1.6 integration-verification: exhaustive just check-full on the combined epic tree after focused reproductions and just test-visual

## Your next action

You are the sase-s1.6 integration-verification follow-up. The bead is already in_progress and assigned to this family. Do not set status by hand. Do not close the parent epic sase-s1 or any ancestor. Do not create beads; record any new discovered work as: sase bead note sase-s1.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'.

Already verified in the previous turn on this workspace (master, originally 104e02e47; origin may have moved):
- Combined phase diffs are scoped (CI LSP artifact, portable CLI assertions, visual caret-cache helper, perf floor JSON, ratchet PyPI trailing-slash). No golden PNGs, release-branch files, or linked-repo files in the five phase commits.
- just install succeeded. just validate passed (including init memory --check).
- Fresh sase-xprompt-lsp 0.29.13 installed at .venv/bin. pytest tests/test_github_actions_ci.py plus ratchet plus parser/skills: 141 passed on Python 3.14. tox -e py312: 84 passed for the same parser/skills files. Directive/finalizer parity: 28 passed.
- Visual idle regressions test_visual_idle_clears_stale_cursor_on_blurred_textarea and test_visual_idle_repaints_focused_textarea_cursor: 2 passed.
- Representative modal confirm_dialog_neutral: 6605 px mismatch is the known split-badge {█} in the header vs empty expected; one focused search caret; no blurred-TextArea double caret. Do NOT update golden PNGs.
- just test-visual: 352 failed, 431 passed, 1 skipped in 173s. Dominant class 6556/6605 px split-badge (same as sase-s1.3). Outliers include family-roster/Shells copy, models-panel, footer/help, AXE chrome. A PROPOSED FOLLOW-UP note for golden rebaseline is already on sase-s1.6. Do not mass-rebase; that is out of this epic's diagnosed stale-cursor class.
- just phase7-perf-check passed: persistent_query_keystroke rust 146.09us vs python 4188.42us, ceiling 193.44us, must_beat_python true.
- Scratch worktree /tmp/sase-s1.6-release (origin/release-please--branches--master @ 7e7a81df0): tools/ratchet_core_window --allow-transitive-lock-refresh applied 0.29.9 -> 0.29.13; uv lock on 3.12 and 3.14 is idempotent; only sase version 0.16.0->0.17.0 and sase-core-rs stanzas change. Earlier master Publish jobs that failed with "uv.lock changed direct dependency package jinja2" used an older release-branch state; current reconciliation is clean locally.
- sase bead epic-symbols sase-s1.6 reported no leftovers. Justfile still has unrelated sase-n4 / sase-n4.5 symbols; do not re-key those.

Your job:
1. Read the monitor log for just check-full. If it failed, determine whether the failure is in this epic's diagnosed lanes (LSP missing, metavar/skills wrap, visual caret, perf floor, PyPI ratchet). Fix in-scope failures, re-run the owning focused tests, then re-run the failing check-full stage. If it is unrelated (pre-existing chezmoi/home memory, other HEAD product drift), record PROPOSED FOLLOW-UP and do not paper it over.
2. Inspect GitHub Actions for a settled master Publish and CI run whose SHA contains all five sase-s1 phase commits (fd1e42e97, b05d2d5bf, e52cc27d8, 0438e70e7, c718da911). Use actstat --repo sase-org/sase -n 8 and gh run view. Distinguish cancelled/superseded runs from settled failures. Download new failure artifacts if the diagnosed Publish/source-test/visual/performance failures recur. Earlier this turn gh auth reported an invalid token / rate limit; retry, and if still blocked record that Actions inspection was blocked rather than inventing a green result.
3. Run sase bead epic-symbols sase-s1.6. If this phase still has --epic-symbol leftovers, resolve or re-key them. Then close ONLY this bead: sase bead close sase-s1.6 --note "<what you verified>". Include focused results, check-full outcome, test-visual classification (diagnosed caret class gone; remaining split-badge/product golden drift), scratch ratchet outcome, and Actions signal (or that it was blocked).
4. Before your final reply, use /sase_final as required for a normal SASE turn.
%xprompts_enabled:true