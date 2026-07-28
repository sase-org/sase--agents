# Chat History - ace-run (sase-ag.6)

- **TIMESTAMP:** 2026-07-28 12:53:51 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-ag.6

## Prompt

#gh:gh_sase-org__sase
%id(6, clan=sase-ag, bead=sase-ag.6)
%model:@small_phase_worker
%auto
%w:sase-ag.1,sase-ag.5
%w(bead=sase-ag.1)
%w(bead=sase-ag.5)
Can you complete the work for bead sase-ag.6? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Closing an assigned phase bead is unaffected by the parent-close
descendant guard. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Install finished. Continuing with the display work.

Now the display value type and metadata plumbing:

Now the parse in `plan_file_metadata_from_content`:

Now the `__all__` export and the TUI widget rows:

Let me smoke-test the rendering with a real header block:

Now docs/sdd.md:

Now the frontmatter field paragraph and command table:

Now the epic string ending:

Now regression tests for the display surface:

Now I'll add tests:

Now the test bodies:

Now rerun the full check:

Waiting on the full `just check` run; it'll notify when it finishes.

Rule 2 applies — both are file-local. Making them private:

I'll wait for that run to finish.

Full check is running (lint + mypy + test suite). I'll report once it completes.

Waiting on the check run.

Still running; I'll report when the monitor fires.

Waiting on the check.

I'll stop polling and wait for the notification.

The change set is in place; waiting on the verification run to finish before closing the bead.

Verification run in progress. I'll continue as soon as it reports.

Still running — pausing until it finishes.

Lint, types, and tests pass. One remaining item: the plans sidecar README is now stale against my updated template, which `sase validate` flags.

The sidecar README regenerated and committed via `sase repo init`. Re-running the full check.

I'll wait for the check to complete.

Still running.

Waiting on the final verification run.

Pausing until the run reports.

I'll wait for the completion notification rather than polling further.

Waiting.

The check is still executing (3 processes active). I'll report when it finishes.

I'll hold here until the background check notification arrives.

Waiting on the check.

I'll stop polling; the notification will bring me back.

Still running; waiting for it to finish.

I'll wait for the notification instead of polling.

Waiting on the check run to complete.

Waiting.

I'll pause here and resume when the run reports back.

Waiting for the check to finish.

I'll hold until the notification arrives.

The test suite is running now. I'll report as soon as it completes.

Test suite still in progress; waiting.

I'll wait for the completion notification.

Waiting on the run.

I'll stop polling and resume when the check reports.

Both pass in isolation — they look like parallel-load flakes unrelated to this change. Re-running the full check to confirm.

Waiting on the confirmation run.

I'll wait for the notification.

Still running.

I'll wait for the run to report.

Waiting.

I'll pause until the check notification arrives.

Waiting for the check to finish.

I'll resume when the notification arrives.

Waiting.

I'll wait for the completion notification.

Waiting on the run.

I'll hold for the notification.

Waiting.

I'll wait for the notification rather than continuing to poll.

Still waiting on the check.

I'll stop polling and resume on the notification.

Running the suite once more with nothing else contending, since the only failure is a load-sensitive capacity soak test.

Waiting for the suite.

I'll wait for the notification.

Waiting.

Waiting on the suite run.

I'll hold until it reports.

Waiting.

I'll wait for the notification.

Waiting on the run.

I'll pause and resume on the notification.

Waiting.

The failure reproduces only inside a full-suite run. Verifying it's pre-existing by running the suite on a clean tree.

Baseline run on a clean tree is underway (changes stashed, restored automatically at the end).

Baseline suite running against the stashed (clean) tree; my changes are restored automatically when it finishes.

Waiting on the baseline run.

I'll wait for the notification.

Waiting.

I'll hold until the baseline result arrives.

Waiting on the baseline suite.

I'll resume when it reports.

Waiting.

I'll wait for the completion notification.

Waiting on the baseline run.

I'll pause until it finishes.

Waiting.

Confirmed pre-existing: the same `test_suite_gate_integration` failure (plus another flake) occurs on unmodified master. My changes are restored. Closing the bead.

Bead `sase-ag.6` (surfaces) is complete and closed.

**What changed**

- `src/sase/sdd/plan_display.py` — the shared plan viewer now parses the header block (via the Rust-owned `plan_header_block` adapter) and renders it as compact provenance rows below Title/Goal/Path: ` Prompt: `, ` Parent: `, ` Agents: `, `Commits: `, each aligned to the existing 9-cell label column, entries comma-joined with a `+N more` tail past 6 (folding in the renderer's `… and N more` cap). A malformed or unparseable block yields no rows instead of raising, so authored metadata stays visible. Parsing happens in the mtime-cached metadata path, not a render path.
- `src/sase/ace/tui/widgets/prompt_panel/_agent_plan_section.py` — the Agents-tab PLAN lane renders the same rows, keeping the TUI and shared logical text byte-identical.
- `src/sase/sdd/templates/sidecar-plans-README.md` — new "Plan Header Block" section: example, fixed section order, sub-bullet ordering, omission and cap rules, link policy with its degradations, projection-not-accumulator semantics, epic roll-up, `parent:` deprecation, plus a `sase plan links refresh` command entry.
- `src/sase/sdd/templates/README.md` — matching header-block paragraph and refresh command for the in-tree SDD store.
- `docs/sdd.md` — Artifact Links rewritten around the header block, a new "Header Block Sections" destination table, wrap tolerance, refresh/best-effort post-commit behavior, `parent:` deprecation, and `sase plan links refresh` added to the command table; the frontmatter field paragraph no longer presents `parent` as a supported managed field.
- `src/sase/main/plan_explain.py` — `sase plan validate --explain` now tells authors not to write the provenance block and never to name a parent via `parent:` frontmatter.
- `tests/test_plan_display.py` — four regressions: row ordering/content matching the TUI, absence without a block, `+N more` truncation, and malformed-block degradation.

**Verification**: `just check` passes on fmt, keep-sorted, ruff, mypy, pyscripts, symvision, and `sase validate`. `sase repo init` regenerated the plans sidecar README from the template (commit `0a7597d1` in the plans sidecar) — that was required to clear the `init repo --check` gate. One suite failure remains, `tests/test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill`; I confirmed it fails identically on unmodified master (a load-sensitive capacity soak, passes standalone), so it is pre-existing and unrelated.

I did not touch `src/sase/xprompts/skills/sase_plan.md` (the plan says leave it unless a check fails; none did), and I left the parent epic open.

Bead is closed. Committing now.

Committed and pushed; working tree is clean and level with `origin/master`.

**Bead `sase-ag.6`** — closed (resolution: done), parent epic `sase-ag` left open.

**Commit** `feat(plan): surface plan header block in viewers and docs (sase-ag.6)` covering the seven files:

- `src/sase/sdd/plan_display.py` — header block parsed in the mtime-cached metadata path, rendered as aligned `Prompt/Parent/Agents/Commits` provenance rows with a `+N more` tail past 6 entries; malformed blocks degrade to no rows rather than raising.
- `src/sase/ace/tui/widgets/prompt_panel/_agent_plan_section.py` — same rows in the Agents-tab PLAN lane, byte-identical to the shared text.
- `src/sase/sdd/templates/sidecar-plans-README.md`, `src/sase/sdd/templates/README.md` — new "Plan Header Block" documentation plus the `sase plan links refresh` command entry.
- `docs/sdd.md` — Artifact Links rewritten around the header block, new destination table, `parent:` deprecation.
- `src/sase/main/plan_explain.py` — `--explain` guidance not to hand-author the block or use `parent:` frontmatter.
- `tests/test_plan_display.py` — four regressions.

**Verification**: `just check` passes (fmt, keep-sorted, ruff, mypy, pyscripts, symvision, `sase validate`); the `just fix` pre-commit hook also passed. The one suite failure, `test_scaled_suite_runs_share_capacity_and_release_after_sigkill`, reproduces identically on unmodified master — pre-existing, load-sensitive, unrelated.

One thing to flag: the commit succeeded, but SASE reported **3 quarantined agent-hood publication requests** predating this commit, so the agent link written to it may not resolve until `sase agent sync --retry-quarantined` is run. I did not run it, since it affects the project outbox beyond this bead.
