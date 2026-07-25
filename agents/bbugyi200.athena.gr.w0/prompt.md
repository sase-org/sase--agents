#gh:gh_sase-org__sase Can you help me make it much clearer what commits we are filtering for on the the "Commits" sub-tab of the "Artifacts" tab by always showing a filter at the top?

- The filter should default to `sidecar:false since:24h`.
- You can remove the `Sidecars hidden` text we show at the top of this tab.
- Also, re-work the logic that makes sidecar repos hidden by default to just be a consequence of this default query.
- Also let's make the default query for this tab configurable via a new sase config field.

#plan %w:gr