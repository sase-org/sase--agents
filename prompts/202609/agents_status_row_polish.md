- **PLAN:**
  [202609/agents_status_row_polish.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_status_row_polish.md)
- **AGENTS:**
  - [bbugyi200.apollo.1h.f0.f0.f0.w2--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1h.f0.f0.f0.w2.md)

  Can you help me improve the way the agent status count row looks at the top of the
  "Agents" tab?

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
- Also, should we consider highlighting / styling / coloring all of `<load>/<capacity>`
  instead of just `<load>`? I'll let you make the final call on this one.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
