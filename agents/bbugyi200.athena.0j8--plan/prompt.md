#gh:gh_sase-org__sase We recently added and improved the usage window indicators shown on the
top-right of the TUI. Can you help me make another round of improvements?

- Let's stop showing the little caution triangle (takes up space and doesn't provide
  much value).
- Let's start merging all usage windows from the same provider by showing any usage
  windows that are not the default usage window to the right of the default window's
  percentage / time remaining using the form `<name> <N>% <duration>`, where `<name>` is
  the name of the window (e.g. `fable`). Also, let's start coloring `<name>` the same as
  `<N>% <duration>`. These should continue to only be shown when that window reaches a
  certain threshold and this behavior should continue to be configurable.
- Let's start separating these usage windows using `|` (one per usage window), where the
  `|` character is the same color as the last usage window shown for that provider.
- #beau

#plan %m:@xlarge