#gh:gh_sase-org__sase %w:1h.f0.f0.f0 Can you help me improve the way the agent status count row looks
at the top of the "Agents" tab?

- Let's stop surrounding any of the elements on this row with square brackets (except
  for the agent status counts), use the `refresh: <N>s (r)` syntax instead of
  `(auto-refresh in <N>s)`, and start using dots (like we do in-between agent status
  counts) to separate the different elements instead of spaces. For example, instead of
  `[view: none (p)]   [group: by status (o)]   (auto-refresh in 7s)`, we should render
  `view: none (p) · group: by status (o) · refresh: 7s (r)`.
- Let's start showing the `<load>/<capacity>` indicator on the right side of this row
  before the model/project text indicators (and a dot separator) using the
  `load: <load>/<capacity>` syntax.
- Let's start preferring to render `<load>` and `<capacity>` as integers when possible.
- Let's start using a much better set of colors to visually indicate the current
  `<load>`. See how we determine the colors for usage window indicators for inspiration.
- #beau

#plan %m:@xlarge %auto