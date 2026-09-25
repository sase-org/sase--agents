%queue(weight=1)
%auto
#fork:sase-17d.12.2--1
%model:muse-spark-1.3-contributor@xhigh

%xprompts_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_25
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-09-25T14:47:13.872093+00:00 |
| **Finished** | 2026-09-25T14:55:42.734356+00:00 |
| **Elapsed** | 8m 28s of a 1h 0m 0s budget |
| **Output** | 7 KiB · evidence refs: `file:monitor-diagnostic-manifest:400scgasen4y`, `file:monitor-retained-log:400scgasen4y`, `file:monitor-stage:lint-test-waits-176083-1790348141637055892-7f3fccf6` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 400scgasen4y --all-lines` |
| **Tool run** | sase tool show 5c6903e572284d60f695e83dfd046953 |

**Why this was monitored:** Verify before host completion

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (test waits) (failed exit 1) ==
[counts: output_bytes=722, output_lines=7, retained_bytes=722]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
.venv/bin/python tools/check_test_wait_helpers
Private test bounded waits are retired. Use sase.ace.testing.wait.wait_for for raw Textual pilots, sase.ace.testing.set_agent_prompt_document for TUI prompt-panel document injection, or give non-pilot harness waits a domain-specific name. Positive literal test sleeps must use an inline '# sase-test-wait: <reason>' pragma, or be replaced by an observable wait.
tests/ace/tui/widgets/decks/test_deck_spread_pilot.py:90: inline-pause-wait
error: recipe `_lint-test-waits` failed on line 352 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%xprompts_enabled:true