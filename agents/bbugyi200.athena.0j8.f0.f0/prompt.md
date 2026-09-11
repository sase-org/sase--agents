#gh:gh_sase-org__sase #fork:0j8.f0 Can you now help me make another round of improvements?

- Let's add some whitespace to the left of the first provider icon and to the right of
  the last usage window (so the set of provider usage window indicators are clearly
  grouped together).
- It looks like when a provider is showing multiple usage windows, the first `|` is
  using the color of the second usage window. For example, in
  `🎭 10% 1d10h | fable 0% 1d10h |`, the first `|` is colored orange instead of red. Fix
  this so we use the color of the appropriate usage window (the last one) for these `|`
  characters.
- Let's start emphasizing the `<N>% <duration>` text when `<N>` is equal to `0` instead
  of just emphasizing `<N>%`.
- #beau

#plan %m:@xlarge