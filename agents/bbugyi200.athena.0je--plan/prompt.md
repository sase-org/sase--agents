#gh:gh_sase-org__sase Something is wrong with grok's usage collector I think (see the command output below for context). Can you help me diagnose the root cause of this issue and fix it? #plan %m:@xlarge 
```
┏━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Provider         ┃          Remaining ┃ Window                                                  ┃ Reset                   ┃            Age ┃ Status                                                       ┃
┡━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│ claude           │           81% left │ Claude session                                          │ in 1h 32m               │            10s │ ok                                                           │
│                  │           10% left │ Claude weekly all models                                │ in 34h 12m              │            10s │ ok                                                           │
│                  │            0% left │ Claude weekly week (Fable)                              │ in 34h 12m              │            10s │ ok                                                           │
│ codex            │           47% left │ Codex                                                   │ in 5d                   │            10s │ ok                                                           │
│                  │          100% left │ GPT-5.3-Codex-Spark                                     │ in 4h 59m               │            10s │ ok                                                           │
│                  │          100% left │ GPT-5.3-Codex-Spark                                     │ in 6d                   │            10s │ ok                                                           │
│ grok             │            0% left │ Grok included weekly allowance                          │ reset passed            │        19h 53m │ degraded · malformed payload · 2x                            │
└──────────────────┴────────────────────┴─────────────────────────────────────────────────────────┴─────────────────────────┴────────────────┴──────────────────────────────────────────────────────────────┘
```