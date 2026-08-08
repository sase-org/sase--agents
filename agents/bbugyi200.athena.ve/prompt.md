#gh:gh_sase-org__sase Can you use the research in the muse_code_harness_provider.md file in the
research sidecar repo to implement a new LLM provider that integrates Meta's Muse Code
into sase?

- I've already installed Muse Code (explore its functionality via the `muse` command)
  onto this machine and it is properly authenticated but make sure to add proper support
  for updating and installing this agent CLI using sase.
- Make sure that this new agent CLI has full support across all of sase's agent CLI
  integration surfaces (where possible).
- As far as the model catalog goes, see #sshot:3, #sshot:2, and #sshot for the
  up-to-date Muse Spark model names/descriptions.
- #beau

#plan #m_opus