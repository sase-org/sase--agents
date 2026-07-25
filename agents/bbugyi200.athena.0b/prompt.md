#gh:gh_sase-org__sase

Write a new VHS demo tape at demos/tapes/sase_ace_multi_model_fanout.tape showing SASE's multi-runtime fan-out:
composing one prompt that becomes three agents on three different models/runtimes (Claude, Codex, and Gemini), ending
on the Launch Approval modal without ever launching. This is demo video five; the first prompt-input demo only briefly
showed a two-pane prompt stack, so this one makes uniform multi-runtime orchestration the headline.

Before writing the tape, study the existing pattern: demos/README.md, demos/tapes/CLAUDE.md, the existing tapes
(especially demos/tapes/sase_ace_prompt_input.tape, whose prompt-input choreography this builds on), and
demos/scripts/seed_sase_ace_demo. Follow the same hermetic conventions exactly: identical Set geometry/font/theme
header, seed via the seeder script, rebuild the agent index, cd into the seeded demo workspace, disable axe with -x,
fixed fictional data, and absolutely no live agent submission - the Launch Approval modal is the finale and must be
dismissed with Escape.

Demo beats (verify the exact model-directive syntax and multi-agent separator behavior against docs/xprompt.md and the
prompt parser, and the prompt-stack keybindings against src/sase/default_config.yml, before scripting - do not guess):

- Launch ACE from the seeded workspace, open the prompt input with Space, and reference the seeded nova project through
  project completion (typing a plus sign then "nov" and accepting the completion), the way the first tape does.
- Compose a multi-agent prompt of three short segments separated by the multi-agent separator lines, giving each segment
  its own per-segment model directive using three distinct models already present in the seeded data: claude-sonnet-4-6,
  gpt-5-codex, and gemini-2.5-pro. Let the directive/completion menus render on screen while typing.
- Show the prompt input reflecting that the prompt now represents three agents (agent-count indicator or prompt-stack
  view, whichever the widget surfaces).
- Press Enter to reach the Launch Approval modal listing all three agents with their three distinct models, hold for a
  beat so viewers can read it, then Escape without launching and quit the way the existing tapes do.

Output demos/out/sase_ace_multi_model_fanout.mp4 and .gif. Register the new tape everywhere the existing tapes are
registered (the `just demos` recipe and demos/README.md). Regenerate media with `just demos -y` as demos/tapes/CLAUDE.md
requires, and verify the result by extracting a few frames from the rendered mp4 with ffmpeg and reading them - confirm
all three model names are visible in the Launch Approval modal frame.