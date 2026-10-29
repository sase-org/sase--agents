#gh:gh_sase-org__sase The TUI just crashed on my apollo machine (see the partial command output below for context). Can you help me diagnose the root cause of this issue and fix it? #plan %m:@xlarge 
```
│ │                 │   │   tool_response_summary={                                                                            │ │
│ │                 │   │   │   'exit_code': 0,                                                                                │ │
│ │                 │   │   │   'output_preview': '[linked-repos] fast-forwarded                                               │ │
│ │                 /home/bryan/projects/github/bobs-org/bob-cli/sase/'+119,                                                   │ │
│ │                 │   │   │   'success': True                                                                                │ │
│ │                 │   │   },                                                                                                 │ │
│ │                 │   │   session_id=None,                                                                                   │ │
│ │                 │   │   transcript_path=None,                                                                              │ │
│ │                 │   │   cwd=None,                                                                                          │ │
│ │                 │   │   permission_mode=None,                                                                              │ │
│ │                 │   │   agent_id=None,                                                                                     │ │
│ │                 │   │   agent_type=None,                                                                                   │ │
│ │                 │   │   parent_tool_use_id=None,                                                                           │ │
│ │                 │   │   message_id=None,                                                                                   │ │
│ │                 │   │   error=None,                                                                                        │ │
│ │                 │   │   is_interrupt=False,                                                                                │ │
│ │                 │   │   source='stream',                                                                                   │ │
│ │                 │   │                                                                                                      │ │
│ │                 artifact_dir='/home/bryan/.sase/projects/gh_bobs-org__bob-cli/artifacts/ace-run/202610/29/2026'+10,        │ │
│ │                 │   │   source_path='/home/bryan/.sase/projects/gh_bobs-org__bob-cli/artifacts/ace-run/202610/29/2026'+27, │ │
│ │                 │   │   line_number=19                                                                                     │ │
│ │                 │   ),                                                                                                     │ │
│ │                 │   ... +30                                                                                                │ │
│ │                 )                                                                                                          │ │
│ ╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯ │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
SystemError: ../Objects/tupleobject.c:909: bad argument to internal function
```