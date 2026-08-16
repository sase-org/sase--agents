#gh:gh_sase-org__sase Attempting to update sase with the `,U` keymap just caused `sase ace` to crash (see the partial command output below for context). Can you help me diagnose the root cause of this issue and fix it? #plan 
```
│ │           │   │   │   │   │   │   'install',                                                                                                                                 │ │
│ │           │   │   │   │   │   │   '--python',                                                                                                                                │ │
│ │           │   │   │   │   │   │   '/home/bryan/.local/share/uv/tools/sase/bin/python3',                                                                                      │ │
│ │           │   │   │   │   │   │   '--force-reinstall',                                                                                                                       │ │
│ │           │   │   │   │   │   │   'sase-core-rs<0.28.0,>=0.27.9'                                                                                                             │ │
│ │           │   │   │   │   │   ),                                                                                                                                             │ │
│ │           │   │   │   │   │   repair_cwd=None,                                                                                                                               │ │
│ │           │   │   │   │   │   repair_label='Restore published sase-core-rs wheel',                                                                                           │ │
│ │           │   │   │   │   │   repair_reason=None                                                                                                                             │ │
│ │           │   │   │   │   )                                                                                                                                                  │ │
│ │           │   │   │   )                                                                                                                                                      │ │
│ │           │   │   ),                                                                                                                                                         │ │
│ │           │   │   subject='sase',                                                                                                                                            │ │
│ │           │   │   error=None,                                                                                                                                                │ │
│ │           │   │   managed_argv=(                                                                                                                                             │ │
│ │           │   │   │   'uv',                                                                                                                                                  │ │
│ │           │   │   │   'tool',                                                                                                                                                │ │
│ │           │   │   │   'install',                                                                                                                                             │ │
│ │           │   │   │   '--color',                                                                                                                                             │ │
│ │           │   │   │   'never',                                                                                                                                               │ │
│ │           │   │   │   '--editable',                                                                                                                                          │ │
│ │           │   │   │   '/home/bryan/projects/github/sase-org/sase',                                                                                                           │ │
│ │           │   │   │   '--with',                                                                                                                                              │ │
│ │           │   │   │   'git+https://github.com/bbugyi200/bugyi-chops',                                                                                                        │ │
│ │           │   │   │   '--with',                                                                                                                                              │ │
│ │           │   │   │   ... +11                                                                                                                                                │ │
│ │           │   │   ),                                                                                                                                                         │ │
│ │           │   │   managed_packages=(                                                                                                                                         │ │
│ │           │   │   │   PlannedPackage(name='bugyi-chops', role='plugin', current_version=None),                                                                               │ │
│ │           │   │   │   PlannedPackage(name='sase-research-artifacts', role='plugin', current_version='0.1.0')                                                                 │ │
│ │           │   │   )                                                                                                                                                          │ │
│ │           │   ),                                                                                                                                                             │ │
│ │           │   sase_current=False,                                                                                                                                            │ │
│ │           │   sase_blocker=None,                                                                                                                                             │ │
│ │           │   provider_plan=AgentCliNothingToUpdate(entries=(), all_clis=False),                                                                                             │ │
│ │           │   provider_dropped=(),                                                                                                                                           │ │
│ │           │   provider_error=None,                                                                                                                                           │ │
│ │           │   agents_updates=(),                                                                                                                                             │ │
│ │           │   agents_error=None                                                                                                                                              │ │
│ │           )                                                                                                                                                                  │ │
│ │    self = PluginsBrowserPane(id='updates')                                                                                                                                   │ │
│ │  submit = <bound method ProcActionsMixin._submit_session_worker of AceApp(title='sase ace (v0.16.0+644.g37fe22b81)', classes={'-dark-mode', '-theme-flexoki'},               │ │
│ │           pseudo_classes={'dark', 'focus'})>                                                                                                                                 │ │
│ ╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯ │
╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
TypeError: ProcActionsMixin._submit_session_worker() got an unexpected keyword argument 'dedup_key'

```