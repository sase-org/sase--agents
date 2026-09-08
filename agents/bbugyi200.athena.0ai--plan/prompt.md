#gh:gh_sase-org__sase In the "New snippet" panel (triggered via the `<ctrl+g>t` and `gt` keymaps in
the prompt input widget), if the user types in an unused snippet name that is the prefix
of an existing snippet and hits `<enter>`, the TUI reports a failure and says that the
snippet doesn't exist (we should create a new one instead). See
~/tmp/screenshots/20260908_141035.png for context. Can you help me diagnose the root
cause of this issue and fix it?

#plan %w(runners=7)