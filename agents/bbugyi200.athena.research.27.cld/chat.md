# Chat History - ace-run (research.27.cld)

- **TIMESTAMP:** 2026-09-22 08:35:12 EDT
- **MODEL:** claude/opus
- **AGENT:** research.27.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260922_080247.md`

## Prompt

%id(cld, clan=research.27)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.27.mus`, `research.27.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the
goal of improving the recently added "sase services" feature (see the sase-11y epic bead
for context)? Look for any bugs that should be fixed, objective improvements that
should be made, or larger extensions that you think I should consider making. End your
analysis with a recommended set of changes you think I should definitely make and (if
you could think of any that deserve to be mentioned) any larger extensions that you
think I should consider making. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I've read the sase-11y epic and its plan. Next I'm going through the service-host source code to look for bugs and gaps.

The three review agents are done. Two of them independently found the same critical bug: the host ignores restart "give up" decisions. I'm checking that and the other top findings in the code myself.

Still checking findings: the host itself uses about 1% CPU, but the scheduler proc restarted about 3 minutes ago while the host has been up 42 minutes, so I'm tracing why.

Confirmed that `sase update` restarts only the scheduler proc, and that the live gateway and scheduler carry a dead `SSH_AUTH_SOCK`. Now I'm reviewing the CLI surface and a few design-level gaps.

I found an open bug bead, sase-14x, reporting 39 duplicate service hosts on athena. I'm checking whether that's still true on the live machine now.

Nearly done verifying. Open bead sase-15q is another env-contract gap (`SASE_TMPDIR` never reaches the host). Next I'm checking the `init --check` drift claim, then I'll write the report.

All the claims I spot-checked hold up. One more confirmed: routines don't pass SIGTERM on to their chops, which is why systemd SIGKILLs them on stop. Now I'm writing the report.

Line references check out. A few small line-number fixes to the report are needed (control.py stop is 236–259; lumberjack comment 507).

The report is written. Now registering it as an artifact.

Registration succeeded. Now running the SASE final declaration.

I wrote the report and registered it as an artifact (`file:explicit:d47f26afcedf2c1e1f79061f`, label `research:202609/service_host_post_landing_review__cld.md`). The host will commit it to the research repo.

The design works: the systemd unit came back by itself after this morning's reboot, and agents and oneshots correctly run outside the host's process group. But I found one critical bug and several failures that nobody would notice. Everything below is confirmed in the code, and most of it on athena today.

**Main findings:**
1. **The host restarts procs it decided to leave down.** For `restart: never`, or a clean exit under `on-failure`, it relaunches the proc every second anyway (`host.py:252-256`). This happened live after the reboot: `telegram_receiver` exited about 30 times, 2 seconds apart, because `pass`/gpg couldn't read the bot token yet. It came back up only because of this bug.
2. **The receiver fix has to ship with the host fix.** The receiver exits with code 0 when its credentials are missing. Fix the host alone and the receiver stays down after every reboot. It needs a non-zero, retryable exit for missing credentials.
3. **Crash loops only show up in an open TUI:**
   - The host never sends the crash-loop notification the Rust code asks for.
   - The crash-loop flag switches itself off once the retry delay reaches its 60-second cap.
   - The TUI only treats `failed`/`error` as failures, and Rust never emits either state.
4. **A bad config goes unnoticed:**
   - A fatal `service:` config stops the host from noticing crashes, and the TUI shows a healthy `SVC 0/0`.
   - A machine overlay saved with a YAML error is silently ignored, so the host stops the gateway and receiver within a second.
5. **The captured environment leaks on athena right now:**
   - A dead `SSH_AUTH_SOCK` saved on 09-20 overrides the working one, so the scheduler and gateway both run with it.
   - `sase service init --check` never stops reporting drift.
   - `SASE_TMPDIR` never reaches the host (already filed as sase-15q).
6. **Stops and updates aren't clean:**
   - Host stops kill the scheduler's jobs with SIGKILL, including `git`/`ssh` children; the journal shows this on 2 of the 3 stops since the reboot.
   - `sase service restart` often reports a timeout failure even though the restart worked.
   - `sase update` restarts only the scheduler, so the host and gateway keep running old code.
7. **Two TUI keys are risky and a few things fail quietly:**
   - `!x` from any tab stops the whole host (gateway and Telegram included) with no confirmation.
   - `!e` changes a proc's permanent enable/disable setting from any tab, based on a stale selection.
   - `sase service logs` prints nothing under the systemd unit.

The report also covers medium and low items. The biggest one: whenever a process with an older `sase_core_rs` rewrites `procs.jsonl`, it silently drops fields it doesn't know. That's what caused the 09-21 loss of the `service` markers.

**Recommended changes, in order:**
1. Fix the host restart bug and the receiver exit code together.
2. Notify on crash loops and give-ups, and make the TUI show the real failure states.
3. Have the host keep using the last good config when a new one is broken.
4. Clean up the captured environment, then re-run `sase service init --yes` on athena from a login shell (that one is yours to do).
5. Stop dropping unknown fields when rewriting the proc store.
6. Make stops graceful for the scheduler's jobs.
7. Have `sase update` restart the whole host.
8. Add confirmations and tab checks to the risky TUI keys.

**Larger extensions to consider:** a config validation gate before saves; a host that takes over already-running procs instead of starting duplicates, which also allows upgrades without downtime; a durable log of service events; read-only service status over the gateway, Telegram and `sase machine status`; per-proc CPU and memory accounting; and a heartbeat watchdog, but only if another hung-proc incident turns up.

The duplicate-host bug in sase-14x (39 copies on 09-20) doesn't reproduce now: there's exactly one host and one scheduler running.
