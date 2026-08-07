#gh:gh_sase-org__sase Can you help me start splitting the existing `repos.sidecar` sase configuration field, which currently accepts
a list of sidecar repo config entries, into `repos.sidecar.builtin` and `repos.sidecar.custom`?

- Make sure to update this repo's sase/sase.yml file accordingly (the `research` sidecar is custom). Also do the same
  for all other enabled sase projects.
- See how we do this for model alias configuration for inspiration.

#plan #m_opus