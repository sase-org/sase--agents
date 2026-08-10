- **PLAN:**
  [202608/rename_worker_alias_bucket.md](https://github.com/sase-org/sase--plans/blob/main/202608/rename_worker_alias_bucket.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-il.land.w1--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-il.land.w1.md)

Can you help me rename the `phase_worker` model alias bucket to just `worker`? Also,
update all of the model alias names in that bucket to remove the `_phase` part of the
names. Think this through thoroughly and create a plan using your `/sase_plan` skill.
Choose and author the appropriate tier, validate and revalidate until it passes, then
submit it with `sase plan propose` (as the skill instructs) before making any file
changes.

%xprompts_enabled:false
### Questions and Answers

#### Q1: Memory

> May I update `sase/memory/sase_sizes.md` and run `sase memory init` as required by the approved `worker` alias rename plan? This will regenerate `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `OPENCODE.md`, `QWEN.md`, and the memory README from the packaged memory template.

- [x] **Allow memory update** — Proceed with the template edit, generated memory note refresh, and provider shim regeneration so validation can pass.
- [ ] **Do not update memory** — Stop before implementation because the approved rename cannot pass `just check` while generated memory still contains the retired alias names.

%xprompts_enabled:true
