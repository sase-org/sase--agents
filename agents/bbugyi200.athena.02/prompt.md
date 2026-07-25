#gh:gh_sase-org__sase

Write a new VHS demo tape at demos/tapes/sase_ace_prs_pipeline.tape that showcases the ACE PRs (ChangeSpecs) tab — the structured PR pipeline that gives SASE its name. This is demo video #3; the first two covered the prompt input and Agents-tab observability, so this one must sell the ChangeSpec lifecycle story.

Before writing the tape, study the existing pattern: demos/README.md, demos/tapes/CLAUDE.md, both existing tapes (demos/tapes/sase_ace_prompt_input.tape and demos/tapes/sase_ace_agents_observability.tape), and demos/scripts/seed_sase_ace_demo. Follow the same hermetic conventions exactly: identical Set geometry/font/theme header, seed via eval $(./demos/scripts/seed_sase_ace_demo), rebuild the agent index, cd into $SASE_DEMO_WORKSPACE, disable axe with -x, fixed data only, and no live agent submission.

The existing seeder already provides everything this demo needs: the fictional nova project ships five ChangeSpecs spanning WIP, Draft, Ready, Mailed, and Submitted, with HOOKS runs (PASSED entries), COMMITS with chat/diff links, COMMENTS, PARENT relationships, and TIMESTAMPS. Do not add real project data.

Demo beats (verify every keybinding against docs/ace.md and src/sase/default_config.yml before scripting — do not guess):
- Launch `sase ace --refresh-interval 0 --tab changespecs -x` from the seeded workspace.
- Walk PR rows with j/k so the detail panel cycles through specs in different lifecycle statuses, showing DESCRIPTION, HOOKS with PASSED runs, and COMMITS.
- Navigate the parent/child chain (nova_prompt_input and its child specs) with < and >.
- Cycle grouping with `o` so viewers see BY_PROJECT then BY_STATUS lifecycle buckets.
- Show fold controls: H to collapse all banners, then L to expand fully.
- Keep the whole demo read-only: no mail, checkout, rename, or status-change actions.

Output demos/out/sase_ace_prs_pipeline.mp4 and .gif. Register the new tape everywhere the existing two are registered (the `just demos` recipe and demos/README.md). Regenerate media with `just demos -y` as demos/tapes/CLAUDE.md requires, and verify the result by extracting a few frames from the rendered mp4 with ffmpeg and reading them — confirm the PRs tab, detail panel, and grouping badges actually appear.