#gh:gh_sase-org__sase #fork:062 Can you now help me use this same MRU store to establish a new
"current project" concept in sase?

- The current project should be shown to the right of the current default model on the
  top right of the TUI.
- Prefix the project name with a `+` character in this visual indicator and try to give
  each enabled sase project a unique color (you will need to do this programmatically
  somehow since we have no way of knowing what sase projects a particular user might
  have enabled).
- Note that the MRU store can store patch names as well as project names. If the most
  recently added entry to the MRU store is a patch name, we should consider the current
  project to be the project associated with that patch.
- We should use the current project as the default project throughout the TUI any time a
  particular tab / panel / UI element has some way to filter what is shown by project
  (e.g. a tab that supports a `project:<project>` search query filter, a panel with an
  option to filter by project or toggle through projects, etc...).
- I expect there are many places throughout the TUI where this is applicable. Make sure
  you update all references (by adding support for the "current project") and that your
  search for these references is thorough.
- #beau

#plan