- **PLAN:**
  [202610/listen_urls_any_machine.md](https://github.com/sase-org/sase--plans/blob/main/202610/listen_urls_any_machine.md)
- **AGENTS:**
  - [bbugyi200.athena.0wl--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wl.md)

I want to add support to sase-listen for converting URLs to podcasts (supporting "brief"
and "full" editions). Can you help me implement this?

- I'm pretty sure we did some research on this within the last few days or so (check the
  research sidecar repo for this markdown file). Use that research for further context
  and inspiration.
- Prove your implementation works by using it to produce a "full" edition audio file for
  the https://openai.com/index/harness-engineering/ blog post and make sure it publishes
  automatically to my AntennaPod feed.
- I'm pretty sure that sase-listen only works on my apollo machine right now and I know
  that the apollo machine is the only machine that has a podcast feed set up. You should
  fix this so I can create audio files using sase-listen from any of my machines (i.e.
  this machine, apollo, or my mac) as a part of this change. Think hard about the best,
  most reliable way to achieve this.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
