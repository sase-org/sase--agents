# Chat History - ace-run (research.27.final)

- **TIMESTAMP:** 2026-09-22 08:52:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.27.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_080247.md`

## Prompt

%clan(research.27, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some research with the
goal of improving the recently added "sase services" feature (see the sase-11y epic bead
for context)? Look for any bugs that should be fixed, objective improvements that
should be made, or larger extensions that you think I should consider making. End your
analysis with a recommended set of changes you think I should definitely make and (if
you could think of any that deserve to be mentioned) any larger extensions that you
think I should consider making.]]) %id:research.27.final %m:@xlarge
%wait:research.27.cld %wait:research.27.mus %wait:research.27.gem %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 3 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some research with the
goal of improving the recently added "sase services" feature (see the sase-11y epic bead
for context)? Look for any bugs that should be fixed, objective improvements that
should be made, or larger extensions that you think I should consider making. End your
analysis with a recommended set of changes you think I should definitely make and (if
you could think of any that deserve to be mentioned) any larger extensions that you
think I should consider making.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cld, mus, gem, belonging to this
   dispatch's `research.27.cld`, `research.27.mus`, `research.27.gem` dependencies, matching by `wait_name` and the canonical research
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

Read the cld report; now reading the mus and gem reports.

Confirmed the host's give-up relaunch bug in code. Now checking the restart/enable/start action paths that the reports disagree on.

Verified live: gateway, scheduler and receiver still carry the dead SSH socket (the 08:23 fix only takes effect on host restart). Now checking the TUI failure vocabulary and Rust-side claims.

Verification is done. Now creating the consolidated report directory and moving the three reports.

Report written and layout staged. Submitting the final declaration.

I merged the three reports into one, after checking their key claims against the current code and the live host on athena (plus a read-only check of apollo). The design is fine and nothing needs rethinking; the problems are in how the host supervises procs, how failures surface, and the environment it captures. The commit of the research repo was handed to the host finalizer.

**The researchers disagreed on a few points:**
- **`sase scheduler restart` does nothing (gem was right).** It clears its stop marker instantly (`delay=0.0`), before the host can see it. The normal 0.5 s restart path usually works, because the nudge wakes the host at once and loading config takes about 4 ms. It fails when the host is busy stopping another child. mus overstated how often the 0.5 s path fails.
- **The log-rewrite, stale `status.json` and `after:` issues are real but not live yet.** Every log is far below the 2 MiB cap, and nothing writes `status.json`. `after:` is never enforced, but no proc uses it.
- **I favour cld's lighter fixes over gem's bigger ones:** a restart counter in the existing state file instead of a Unix-socket control plane, and a heartbeat watchdog instead of a health-check language.

**What's new since the three reports:**
- **Dead SSH socket:** commit `ba71aa524` (08:23 today) fixes it in code, but the running host started at 07:42. As of 08:44 the gateway, scheduler and Telegram receiver still use it. The host needs one restart to pick the fix up.
- **Feature flags could get frozen:** the host saves `SASE_FEATURE_FLAGS` along with the rest of the captured environment. Running `sase service init --yes` from an agent or TUI shell would pin that shell's flags into the always-on host and every agent it launches. It's the same bug as `sase-11c`, in a longer-lived process. Meanwhile `init --check` reports drift from every shell and tells you to run exactly that command.
- **Telegram token file:** sase-telegram can already read a boot-safe `~/.sase/telegram_bot_token`, but athena doesn't have one. That is why the receiver can't start until you log in: its log shows 101 "credentials unavailable" exits.

**Changes you should definitely make (P0, small enough for one epic):**
1. **Make the host respect "don't restart" decisions, and fix the Telegram receiver in the same change.** Today the host relaunches a proc it decided to leave down every ~2 s, with no backoff; I saw 17 clean-exit relaunches of the receiver after the reboot. The receiver also reports missing credentials as a clean exit, so it only comes back because of that bug. Fix the host alone and Telegram stays down after every reboot.
2. **Track restarts with a counter the host consumes,** so restarts can't be lost and the CLI can print the new PID.
3. **Make failures loud.** Nothing reads the crash-loop notify flag. The flag switches itself off once backoff reaches its 60 s cap. The TUI's failure states don't match what the core emits.
4. **Keep the last config that parsed.** Today a machine overlay saved mid-edit with a YAML error makes the host stop the gateway and receiver within a second, while the TUI shows a healthy `SVC 0/0`.
5. **Clean up the captured environment:** stop saving the flag snapshot, ignore values that differ per shell in `--check`, warn when `init --yes` runs from an agent or TUI shell, and pass through `SASE_*` path settings (fixes `sase-15q`).

P1 and P2 are in the report. The main items are graceful parallel stops that don't kill in-flight jobs, making `sase update` restart the whole host, and honest CLI messages and exit codes. The rest: `sase service status` drops from 4.3 s to under 1 s, and `sase service logs` stops printing nothing under systemd. Orphaned procs become visible, the TUI hotkeys get safety fixes, and control-plane hardening covers the rest.

**Things to do yourself today:**
- Create `~/.sase/telegram_bot_token` (mode 600) on athena.
- Restart the host once at a quiet moment. Until graceful stops land, that will kill any jobs in flight.
- Only run `init --yes` from a login shell.

**Larger extensions worth considering:**
- A config validation gate on top of the last-good config (strongest candidate).
- A durable service event log.
- A host that re-adopts its running children after a crash and can restart itself in place for updates.
- Read-only service health visible from other machines and Telegram.
- Per-proc resource tracking and limits.
- A heartbeat watchdog, after one more stuck-proc incident.

Files are in `sase/repos/research/202609/sase_services_post_landing_hardening/`:
- sase_services_post_landing_hardening.md
- sase_services_post_landing_hardening__cld.md
- sase_services_post_landing_hardening__mus.md
- sase_services_post_landing_hardening__gem.md
