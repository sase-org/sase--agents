#gh:gh_sase-org__sase Can you help me start requiring that sase monitors be given custom statuses
(one that is shown while the monitor is running and another that is shown when the
monitor's command finishes)?

- We currently advise agents in the sase/memory/build_and_run.md memory file to use
  monitors when running certain commands (the `just check-full` command, for example).
- We should update this guidance to instruct the agent to use the `TESTING` / `TESTED`
  monitor statuses for these monitors.
- Also let's add a cap of 20 characters for monitor statuses. Truncate any additional
  characters (e.g. replace them with "...").
- Make sure these custom statuses appear on every UI surface that shows monitors (e.g.
  the "Procs" tab of the "SASE Admin Center" panel, for example).
- Also make sure that these statuses are fully supported by agent family shells (i.e.
  they are shown as the status of the agent family shell when the most recently added
  child shell is a monitor).
- Finally make sure these custom statuses are displayed using a distinct color for each
  custom status pair. You'll need to figure out a way to do this deterministically
  despite not knowing what custom status values might be provided. See how we do this
  for the "current project" indicator shown on the top right of the TUI for inspiration.
- #beau

#plan