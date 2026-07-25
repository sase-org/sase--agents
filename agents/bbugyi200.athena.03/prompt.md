#gh:gh_sase-org__sase

Write a new VHS demo tape at demos/tapes/sase_ace_prompt_history_stash.tape showing that SASE never loses a prompt: prompt-history recall and the prompt-stash workflow inside the ACE prompt input. This is demo video #4; the prompt-input basics (completion, xprompts, launch approval) are already covered by demos/tapes/sase_ace_prompt_input.tape, so focus purely on the history/stash power features.

Before writing the tape, study the existing pattern: demos/README.md, demos/tapes/CLAUDE.md, both existing tapes, and demos/scripts/seed_sase_ace_demo. Follow the same hermetic conventions exactly: identical Set geometry/font/theme header, seed via eval $(./demos/scripts/seed_sase_ace_demo), disable axe with -x, fixed fictional data, and no live agent submission.

You will need to extend demos/scripts/seed_sase_ace_demo so the demo has deterministic history to recall: write a $SASE_HOME (the seeder's sase-home) prompt_history/ monthly shard — see docs/prompt.md, docs/configuration.md, and src/sase/history/prompt_store.py for the exact shard path (YYMM.json) and entry schema — containing roughly eight to ten varied fictional nova prompts with fixed timestamps, mixed statuses, and at least one that uses an xprompt reference. Keep all data fictional and privacy-safe like the rest of the seeder, and keep the seeder deterministic (no wall-clock-dependent values).

Demo beats (verify every keybinding for history search, the prompt history modal, stashing, and the stashed-prompts panel against docs/ace.md, docs/prompt.md, and src/sase/default_config.yml before scripting — do not guess):
- Launch ACE from the seeded workspace and open the prompt input with Space.
- Open the prompt history modal; browse and search the seeded entries, letting the preview of an older prompt render.
- Load a history entry into the input and visibly tweak it.
- Stash the edited prompt, show the stashed-prompts indicator/panel, and restore the stash back into the input.
- End without launching anything: Escape out and quit the way the existing tapes do.

Output demos/out/sase_ace_prompt_history_stash.mp4 and .gif. Register the new tape everywhere the existing two are registered (the `just demos` recipe and demos/README.md). Regenerate media with `just demos -y` as demos/tapes/CLAUDE.md requires, and verify the result by extracting a few frames from the rendered mp4 with ffmpeg and reading them — confirm the history modal and stash panel actually appear on screen.