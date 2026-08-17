# Chat History - ace-run (051)

- **TIMESTAMP:** 2026-08-17 12:33:36 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 051

## Prompt

#gh:gh_sase-org__sase How are feature flags enabled? For example what would I need to do to enable the `coder_inherits_planner_chat` feature flag? %model:sonnet

## Response

I'll check the feature flags memory doc since that's required reading before working with SASE flags.

Now let's find how flags are actually toggled at runtime — CLI or config.

Now I have everything I need to give a complete answer.

## How SASE feature flags get enabled

Flags resolve in this order (later wins): **registry default → user config → overlay config → project-local config (project-scoped flags only) → in-process test override → `SASE_FEATURE_FLAGS` env var**.

To check current state:
```bash
sase flag show coder_inherits_planner_chat
```

### For `coder_inherits_planner_chat` specifically

It's a `beta` kind, `global` scope flag (default `off`), defined in `src/sase/feature_flags/registry.py`. Global scope means **it cannot go in project-local config** — only user config, an overlay config, or the env var will work.

**Option 1 — user config** (`/home/bryan/.config/sase/sase.yml`), add:
```yaml
feature_flags:
  coder_inherits_planner_chat: true
```

**Option 2 — overlay config** (e.g. `/home/bryan/.config/sase/sase_athena.yml`), same `feature_flags:` block.

**Option 3 — env var**, for a single process/session:
```bash
export SASE_FEATURE_FLAGS='{"coder_inherits_planner_chat":true}'
```

One thing worth flagging: your current shell already has `SASE_FEATURE_FLAGS='{"coder_inherits_planner_chat":false,"prettier_enabled":true}'` exported. Since env is the highest-priority layer, it overrides *any* config-file setting — so if you set it via config but this env var stays exported, the flag will still resolve to `off`. You'd need to update or unset that env var too.

There's no `sase flag set` CLI command — toggling is purely config/env driven; `sase flag list`/`show` are read-only inspection.
