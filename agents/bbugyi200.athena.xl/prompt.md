#gh:gh_sase-org__sase Can you help me add support to the prompt input widget for a new "snippet
target mode"?

- We will need to add a new sase config field to support this feature that specifies the
  user's preferred snippet location (i.e. the sase config file that we should write to
  when new snippets are added).
- We should default to using the ~/.config/sase/sase.yml file (or equivalent chezmoi
  file, if `use_chezmoi: true` is set) if this new sase config field is not set.
- This mode should be activated for a new prompt input widget that is added to the
  bottom of the prompt input widget stack when a new `<ctrl+g>t` (insert-mode) / `gt`
  (normal-mode) keymap is used.
- After triggering one of these keymaps (and before rendering the new prompt input
  widget), we should prompt the user for the name of their new snippet.
- If the snippet name the user types is used by an existing snippet, it should be made
  clear to the user somehow (live, as they type). If they press `<enter>` anyway, then
  that snippet's current definition should be loaded into the new prompt input widget
  (instead of leaving it empty).
- The user will then be expected to type the snippet definition into the new prompt
  input widget and then press `<enter>`. At which point, they should be prompted to
  confirm. There might be multiple confirmations required (i.e. if committing to a
  chezmoi repo). Make sure we show a good diff of the changes when editing an existing
  snippet. See how we do this from the existing "Save pane as snippet" panel for
  inspiration.
- Once the snippet has been saved, the new prompt input widget should disappear and the
  user should return to the exact same cursor position they had in the previously
  selected prompt input widget.
- See the prompt input widget stack's "xprompt target mode" (see the sase-hp epic bead
  for context) for inspiration on how this new "snippet target mode" prompt input
  widget should look, but keep in mind that snippet target mode should only be active
  for a single prompt input widget (not the whole stack).
- #beau

#plan #m_opus