#gh:gh_sase-org__sase Pressing `<ctrl+]>` to go from insert-mode to normal-mode in the prompt input
widget does not always work the first time it is pressed, so the user often winds up
typing the next few characters into the prompt input widget instead of performing
whatever normal-mode operation they were trying to. Can you help me diagnose the root
cause of this issue and fix it? Make pressing `<ctrl+]>` ALWAYS result in a transition
from insert-mode to normal-mode, while preserving (and acting on) any keys the user
presses after `<ctrl+]>`.

#plan %m:claude-fable-5