#gh:gh_sase-org__sase The "XPrompts" tab of the "SASE Admin Center" panel doesn't feel like it serves
enough value to be a main "SASE Admin Center" tab and its functionality overlaps with
the "Config" tab on that panel (which also serves less value than I'd like at the
moment). The "Glossary", "Memory", and "Snippets" panels (all recently added and all
currently only accessible from the prompt input widget) all seem related to config as
well. Can you help me consolidate this functionality and make the "Config" tab of the
"SASE Admin Center" panel much more useful?

- Let's start hosting multiple sub-tabs on the "Config" tab.
- The current contents of that tab should be migrated to the new "Misc" sub-tab.
- The "XPrompts" tab should be migrated to a sub-tab on the "Config" tab.
- The "Glossary", "Memory", and "Snippets" panels should all be migrated to sub-tabs of
  the "Config" tab as well (these might be more difficult to migrate, so think hard
  about the right way to do this).
- The keymaps in the prompt input widget that currently trigger the "Glossary",
  "Memory", and "Snippets" panels should continue to work, but should open these panels
  in their new locations (i.e. they should open the "Config" tab of the "SASE Admin
  Center" panel and focus the appropriate sub-tab).
- #beau

#plan %w:sase-rd.land