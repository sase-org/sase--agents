#gh:gh_sase-org__sase The `sase screenshot` command is failing and the `sase_ace_agents` tmux session gets left open after it fails (see the command output below and the sase-123 epic bead for context). Can you help me diagnose the root cause of this issue and fix it? #plan %m:gpt-6-astra 
```
❯ sase screenshot
sase screenshot: TUI screenshot export failed: wait for settled frame: RuntimeError: timed out waiting for screenshot refresh; deadline=3.000s

Last tmux capture-pane output:
 ⭘                                                 sase tui (v0.17.1)    🎭 6% 1d12h · fable 12% 1d12h  🤖 40% 6d5h  +1
  Agents  │  Artifacts  │  Services                                  ⚙ 1  CODEX(gpt-5.6-sol)  GROK +1  +sase  ?8 #1 ◈85
 Agents: …
                                                            ┌──────────────────────────────────────────────────────────┐
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            └──────────────────────────────────────────────────────────┘
                                                            ┌──────────────────────────────────────────────────────────┐
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                         Loading...                         │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            │                                                          │
                                                            └──────────────────────────────────────────────────────────┘
▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔▔
                                                                                                SVC   ◴ starting 4.6s
```