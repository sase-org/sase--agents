- **PLAN:**
  [202608/prevent_host_config_test_leak.md](https://github.com/sase-org/sase--plans/blob/main/202608/prevent_host_config_test_leak.md)
- **AGENTS:**
  - [bbugyi200.athena.0a3--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0a3.md)

Something keeps resetting the ~/.config/sase/sase.yml file on this machine (see the
command output below for context), which is managed by chezmoi. Can you help me diagnose
the root cause of this issue and fix it? Think this through thoroughly and create a plan
using your `/sase_plan` skill. Choose and author the appropriate tier, validate and
revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.

```
bryan in 🌐 athena in sase on  master is 📦 v0.16.0 via  v22.14.0 via 🐍 v3.11.13
❯ bat ~/.config/sase/sase.yml
─────┬──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
     │ File: /home/bryan/.config/sase/sase.yml
─────┼──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1 │ feature_flags:
   2 │   ref_sync_gesture: true
─────┴──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```
