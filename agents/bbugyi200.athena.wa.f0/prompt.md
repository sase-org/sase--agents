#gh:gh_sase-org__sase #fork:wa Can you now help me make it so plural forms of all aliases (including
the one that gets added automatically based on the glossary term's name) get added to
the `aliases` list automatically?

- These plural forms should not be shown in the `ALIASES:` field that gets rendered in
  agent instruction files and the `ALIASES:` line (and the blank line above it)
  shouldn't be rendered at all when there are no aliases that need to be shown.
- These plural forms should, however, continue to be highlighted in the prompt input
  widget and in external editors (via LSP support).

#plan #m_opus