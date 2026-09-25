#gh:gh_sase-org__sase #fork:0j8.f0 Can you now help me make another round of improvements?

- Let's add some whitespace to the left of the first provider icon and to the right of
  the last usage window (so the set of provider usage window indicators are clearly
  grouped together).
- Lets' start only using the `|` character to separate different usage windows from the
  same provider (the provider icons themselves clearly separate the different provider
  usage window sections). Also, let's start wrapping a provider's usage windows in
  parentheses when that provider is showing indicators for multiple usage windows. For
  example, instead of showing `🎭 10% 1d10h | fable 0% 1d10h |` we should start showing
  `🎭 (10% 1d10h | fable 0% 1d10h)`. Finally, stop coloring the `|` character.
- Let's start emphasizing the `<N>% <duration>` text when `<N>` is equal to `0` instead
  of just emphasizing `<N>%`.
- Also, let's change the default configuration so we start always showing the claude
  provider's fable usage window by default.
- #beau

#plan %m:@xlarge