#gh:gh_sase-org__sase #fork:sase-ri.land.w1 Can you now help me add numeric keymaps for each of the
sub-tabs on the "Config" tab of the "SASE Admin Center" panel?

- See how we do this for the sub-tabs on the "Statistics" tab of the "SASE Admin Center"
  panel for inspiration.
- As a part of this change let's start prefixing the numbers shown next to the sub-tab
  titles (for both the "Config" and "Statistics" tabs) with a `0`. Since each keymap
  used to focus those tabs starts with a `0`, I think this is a bit clearer.

#plan