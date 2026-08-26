- **PLAN:**
  [202608/release_gate_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)
- **AGENTS:**
  - [bbugyi200.athena.0ek--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md)

This project currently uses release-please to create release PRs and the `ci_watch` chop
(defined in my bbugyi200/bugyi-chops GitHub repo) to submit those PRs automatically when
all GitHub workflows/jobs are green. The problem is that this project seems to move so
fast that many hours often go by where every GitHub workflow that's started gets
canceled by a subsequent one.

Can you help me solve this? Review the release_gate_liveness.md file in the research
sidecar repo for context and inspiration before planning. Make sure you also review the
annotations I left on this research file, which are stored in the
~/bob/ref/chat/release_gate_liveness.md file.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
