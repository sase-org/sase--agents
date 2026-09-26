- **AGENTS:**
  - [bbugyi200.athena.research.2n.gem](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2n.gem/README.md)

%id(gem, clan=research.2n) %m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org**sase You are researcher gem in a 4-researcher swarm. The other
researchers, `research.2n.cdx`, `research.2n.grk`, `research.2n.mus`, are independently
investigating the same request and will write their own self-named reports ending in
`**cdx.md`and`**grk.md`and`**mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to merge the prompt stash panel with the prompt history panel using sub-tabs on
that new, merged panel.

- Also, I want to add a new, third sub-tab to this panel that contains archived/trashed
  prompts (aka the "stash trash"--this term should be added to the glossary as well as
  "prompt stash" and its alias, "stash") that the user deleted with the `d` keymap on
  the new sub-tab that the prompt stash panel is migrated to.
- We should start moving deleted prompts to this tab instead of deleting them entirely.
- We should only store up to the last `<N>` deleted prompts on this tab (then they
  should actually be deleted).
- `<N>` should be configurable via a new sase config field but should default to 20.
- Appropriate keymaps should be added to this new sub-tab that holds the stash trash.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.
#research(suffix=gem)
