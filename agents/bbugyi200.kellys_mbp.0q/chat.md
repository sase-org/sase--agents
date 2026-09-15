# Chat History - ace-run (0q)

- **TIMESTAMP:** 2026-09-15 11:10:01 EDT
- **MODEL:** claude/opus
- **AGENT:** 0q

## Prompt

#gh:gh_sase-org__sase Why has this machine been using so much CPU recently? Does it have anything to do with sase?

## Response

I'll start by looking at what's using CPU right now and how busy the machine has been.

Yes, sase is a big part of it, but there are two separate causes. One comes from sase, and the other is in your shell setup, which sase makes much worse. Load average reached **34 on an 8-core machine** during this session.

## 1. A leftover Linux path in `~/.zshrc` (the constant, days-long drain)

Over 11 days of uptime, **`opendirectoryd` has used about 26 CPU-hours and `automountd` about 8.4**. That's more than anything else on the machine, including WindowServer and Chrome.

**Cause:** `~/.zshrc:191` does `export PATH="/home/bryan/.pyenv/bin:$PATH"`. That's a Linux path, and your user here is `bbugyi`. On macOS, `/home` is an automount point, so every attempt to find a command on `PATH` first checks `/home/bryan/...`. That check triggers a failing automount lookup.

**Measured:** I checked both paths 3,000 times each:

| Path checked | Time per check | Extra `opendirectoryd`/`automountd` CPU |
|---|---|---|
| `/Users/bbugyi/.pyenv/bin/nope` | 1.4 µs | ~0 s |
| `/home/bryan/.pyenv/bin/nope` | **12–25 ms** | **42–67 s** |

That's about 10,000× slower. `automountd` is currently doing about **7,500 of these lookups a minute**.

**Where sase comes in:** the sase background daemon (`sase axe`) inherited this `PATH`. Its scheduled jobs run constantly, and each one launches `git`, `gh`, Python and so on by name. Every launch pays the lookup cost first. Those job runs rose from about 36 an hour overnight to **about 360 an hour since 10:00**. Your tmux status bar, which runs commands every 2 seconds, adds to it.

**Fix:** delete or guard lines 191 and 300 of `~/.zshrc` (line 300 sources `/home/bryan/.config/broot/...`). pyenv isn't installed at that path anyway. `.zshrc` is chezmoi-managed, so change it in the chezmoi source, then restart the axe daemon and tmux so they pick up the clean `PATH`. I haven't changed anything.

## 2. sase's automatic Rust rebuilds (the recent spikes)

The ACE TUI (`sase ace --restart-axe`) checks for updates every 10 minutes (`prebuild_rust: true`). When `sase-core` has new commits, it compiles `sase_core` with full optimization:

- It starts a prebuild in `~/.sase/cache/rust-prebuild`.
- The update then runs `just rust-dev-install-uv-tool`, which compiles `sase_core` again into another target directory. Right after the prebuild finished today, a second full compile started.

This is what's new. From `~/.sase/logs/dev_update.jsonl`:

| | Update runs per day | Rust build time per day |
|---|---|---|
| Sep 2–11 | 1–3 | 3–6 min |
| Sep 12–14 | 6–8 | 11–14 min |
| **Sep 15 (by 11:07)** | 5 | **26 min** |

The recent builds took 4–8.5 minutes each and used 3–4 cores the whole time. The increase lines up with the heavy pace of `sase-core` commits.

## Not the cause
- **Agents:** only one Claude agent (this one) is running. Agent launches have been 10–24 a day since Sep 11, below the 50+ a day on Sep 3–4.
- **Heat:** no thermal or performance warnings are recorded.

## What I'd do
1. **Fix `~/.zshrc`.** This is cheap, and it also speeds up every command lookup in your shell.
2. **Cut the double compile:** set `prebuild_rust: false` to stop the automatic prebuilds, or change the update to reuse the prebuilt output instead of compiling again. That second option would be a sase change, and I can file a task for it if you want.
