#gh:gh_sase-org__sase The usage collection for codex and claude seems very unreliable (see the command output below and the sase-y5 epic bead for context). Can you help me diagnose the root cause of this issue and fix it? #plan %m:claude-fable-5 %w(bead=sase-y5)
```
❯ sase usage
No subcommand provided for 'sase usage'; delegating to 'sase usage list'.
                                                                                             Subscription usage
┏━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Provider               ┃                Remaining ┃ Window                                                                  ┃ Reset          ┃        Age ┃ Status                                        ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ claude                 │                        - │ -                                                                       │ -              │         6m │ error: probe failed                           │
│ codex                  │                        - │ -                                                                       │ -              │         8m │ error: probe failed                           │
│ grok                   │                 14% left │ Grok included weekly allowance                                          │ in 2d          │         1m │ unknown                                       │
└────────────────────────┴──────────────────────────┴─────────────────────────────────────────────────────────────────────────┴────────────────┴────────────┴───────────────────────────────────────────────┘
```