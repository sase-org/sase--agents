#gh:gh_sase-org__sase Can you help me make the panel that pops up when the `K` keymap is used in the
prompt input widget use a dynamic size based on the number of lines of content that
need to be shown?

- When the contents can fit in the panel without increasing the size, we should continue
  to use the current size.
- When the contents can't fit we should make the panel larger up to some maximum, which
  is close to but not quite the size of the current screen.
- For example, if the `K` keymap is used when the `#research_swarm` xprompt swarm is
  selected, we should probably use the maximum panel size (since that xprompt swarm is
  defined in a markdown file that is almost 300 lines long).
- #beau

#plan %q:6 %auto