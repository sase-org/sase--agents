#gh:gh_sase-org__sase It seems like the "Updates" tab of the "SASE Admin Center" panel always refreshes
all related data when the tab is loaded, even if the user just opened the tab 5 seconds
ago. This makes going back and forth from this tab painful. Can you help me fix this by
making that page never auto-refresh (we should use cached data from the periodic
job/task that checks for these updates if possible)? The user should still be able to
use the `r` keymap to trigger a refresh explicitly.

#plan %m:@xlarge