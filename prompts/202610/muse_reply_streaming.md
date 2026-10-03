- **PLAN:**
  [202610/muse_reply_streaming.md](https://github.com/sase-org/sase--plans/blob/main/202610/muse_reply_streaming.md)
- **AGENTS:**
  - [bbugyi200.athena.0vt--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vt.md)

I would like to add support to the Muse LLM provider for streaming its output. Can you
help me implement this?

- I'm pretty sure we used to support this but then fixed a related bug which caused Muse
  agent replies to be chunked poorly.
- Unfortunately, I don't think that reply streaming has worked for the Muse provider
  ever since.
- Review the muse_live_reply_streaming.md file in the research sidecar repo for context
  and inspiration before planning.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
