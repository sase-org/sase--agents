#gh:gh_sase-org__sase The `sase ace` TUI just crashed (see the command output below for context) when I attempted to open the glossary using the `<ctrl+g>G` keymap in the prompt input widget. Can you help me diagnose the root cause of this issue and fix it? #plan 
```
│ ╭────────────────────────────────────────── locals ───────────────────────────────────────────╮                                                                                  │
│ │    identity = 'glossary:memory-web'                                                         │                                                                                  │
│ │      reason = 'ACE MemoryPane previewed glossary:memory-web'                                │                                                                                  │
│ │       scope = MemoryScopeRef(                                                               │                                                                                  │
│ │               │   kind='project',                                                           │                                                                                  │
│ │               │   key='gh_sase-org__sase',                                                  │                                                                                  │
│ │               │   display_name='sase',                                                      │                                                                                  │
│ │               │   content_root='/home/bryan/projects/github/sase-org/sase',                 │                                                                                  │
│ │               │   memory_read_root='/home/bryan/projects/github/sase-org/sase/sase/memory', │                                                                                  │
│ │               │   has_memory=True                                                           │                                                                                  │
│ │               )                                                                             │                                                                                  │
│ │ strand_slug = 'memory-web'                                                                  │                                                                                  │
│ │    web_slug = 'glossary'                                                                    │                                                                                  │
│ ╰─────────────────────────────────────────────────────────────────────────────────────────────╯                                                                                  │
│                                                                                                                                                                                  │
│ /home/bryan/projects/github/sase-org/sase/src/sase/memory/read_log.py:345 in require_agent_identity                                                                              │
│                                                                                                                                                                                  │
│   342                                                                                          ╭── locals ──╮                                                                    │
│   343 def require_agent_identity(env: Mapping[str, str] | None = None) -> AgentIdentity:       │ env = None │                                                                    │
│   344 │   """Return the current agent identity or raise a clear auditability error."""         ╰────────────╯                                                                    │
│ ❱ 345 │   return _require_agent_identity(env, purpose="memory reads")                                                                                                            │
│   346                                                                                                                                                                            │
│   347                                                                                                                                                                            │
│   348 def normalize_read_reason(reason: str) -> str:                                                                                                                             │
│                                                                                                                                                                                  │
│ /home/bryan/projects/github/sase-org/sase/src/sase/agent/identity.py:65 in require_agent_identity                                                                                │
│                                                                                                                                                                                  │
│    62 │   """Return the current agent identity or raise a clear auditability error."""         ╭───────── locals ──────────╮                                                     │
│    63 │   identity = discover_agent_identity(env)                                              │      env = None           │                                                     │
│    64 │   if identity is None:                                                                 │ identity = None           │                                                     │
│ ❱  65 │   │   raise AgentIdentityError(                                                        │  purpose = 'memory reads' │                                                     │
│    66 │   │   │   f"{purpose} require agent attribution; set SASE_AGENT_NAME, "                ╰───────────────────────────╯                                                     │
│    67 │   │   │   "or provide SASE_ARTIFACTS_DIR/agent_meta.json with a name"                                                                                                    │
│    68 │   │   )                                                                                                                                                                  │
╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
AgentIdentityError: memory reads require agent attribution; set SASE_AGENT_NAME, or provide SASE_ARTIFACTS_DIR/agent_meta.json with a name
```