#gh:gh_sase-org__sase Can you help me start requiring that xprompt skills be defined in a
sase/skills/ directory?

- Currently, these are defined in sase/xprompts/skills/ directories normally, but it is
  the `skill: true` frontmatter property that really controls whether an xprompt is an
  xprompt skill or not (I think at least--you should verify this).
- Also, let's start requiring that, in order to invoke these as xprompts (instead of as
  skills using the `/` prefix), that we include the `skills/` prefix (e.g. `#skills/foo`
  instead of `#foo`).
- Make sure you migrate all of my xprompt skills accordingly across all of my enabled
  sase projects and my chezmoi repo.

#plan #m_codex