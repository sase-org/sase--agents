#gh:gh_sase-org__sase Something keeps resetting the ~/.config/sase/sase.yml file on this machine (see the command output below for context), which is managed by chezmoi. Can you help me diagnose the root cause of this issue and fix it? #plan
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