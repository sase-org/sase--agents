- **PLAN:**
  [202608/usage_limit_reset_timestamp.md](https://github.com/sase-org/sase--plans/blob/main/202608/usage_limit_reset_timestamp.md)
- **AGENTS:**
  - [bbugyi200.athena.04f--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04f.md)

Codex just failed with a usage limit error and sase correctly detected this usage limit
error and disabled the codex provider for 24h. This worked well but could work even
better. Namely, the usage error contained the date that my usage limit is expected to
reset (see #sshot), so we should have used that date instead of defaulting to 24h. Can
you help me fix this? Make equivalent fixes for other providers if possible.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
