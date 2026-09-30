- **PLAN:**
  [202609/prompt_history_human_only.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_history_human_only.md)
- **AGENTS:**
  - [bbugyi200.athena.0ud--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ud.md)

We currently store too many prompts in prompt history (see the
~/tmp/screenshots/20260930_062115.png screenshot for an example of a prompt that likely
shouldn't have been stored). Can you help me fix this?

- Namely, prompt history is meant to be used to store user prompts, each of which is
  supposed to correlate with a specific request made by a human being (by using the
  prompt input widget in the TUI or the `sase run` command to launch a sase agent, for
  example).
- Any prompt used to launch agents that belong to an xprompt swarm should not be saved
  to prompt history, but the prompt containing the xprompt swarm invokation
  (`#research_swarm`, for example) which was used by the user to launch the swarm should
  be saved to prompt history.
- Any prompt used to launch agents from routines should not be saved to prompt history.
- Review the prompt_history_human_submissions_only.md file in the research sidecar repo
  for context and inspiration before planning.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
