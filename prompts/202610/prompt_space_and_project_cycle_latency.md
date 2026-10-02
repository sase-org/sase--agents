- **PLAN:**
  [202610/prompt_space_and_project_cycle_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)
- **AGENTS:**
  - [bbugyi200.athena.0vk--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md)

Traversing through the "current project" stack using the `<ctrl+n/p>` keymaps can be
painfully slow in the prompt input widget. Also, activating the prompt input widget
using the `<space>` keymap can be pretty slow sometimes too. It is very important that
both of these operations are very fast. Can you help me improve the performance of these
two keymaps by making the changes recommended by the
prompt_space_and_project_cycle_latency.md file in the research sidecar repo (I already
have another swarm of agents looking into what's causing the TUI to freeze 10% of the
time, so you don't need to look into that)?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
