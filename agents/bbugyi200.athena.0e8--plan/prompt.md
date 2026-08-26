#gh:gh_sase-org__sase There are several places throughout sase's TUI where we seem to remember the
tab/subtab that the user was last on in their last TUI session. We default to activating
that tab instead of activating the first tab in the list. For example, the "XPrompts"
sub-tab of the "Config" tab of the "SASE Admin Center" panel seems to always be loaded
when I activate the "Config" tab (I'm not sure if this is related but fix this too). Can
you help me fix this so sase remembers the previous focused tab/subtab for this TUI
session only?

#plan #m_opus