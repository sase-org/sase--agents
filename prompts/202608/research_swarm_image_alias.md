- **PLAN:**
  [202608/research_swarm_image_alias.md](https://github.com/sase-org/sase--plans/blob/main/202608/research_swarm_image_alias.md)
- **AGENTS:**
  - [bbugyi200.athena.082--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.082.md)

Can you help me change the model used for the `#research_swarm` xprompt swarm's (which
lives in the sase-research-artifacts repo) image generation agent? Let's start using a
new `@image` model alias, which should be defined as
`codex/gpt-5.6-sol@xhigh | grok/grok-4.6@xhigh` (to use a model pool).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
