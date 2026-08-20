# Chat History - ace-run (sase-qy.4--mon)

- **TIMESTAMP:** 2026-08-19 15:09:58 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-qy.4--mon

## Prompt

sase monitor start --command 'just check-full' --reason 'sase-qy.4 grammar phase: exhaustive lint + full test suite before close'

## Response

        '-Q',
  +                                     '--request-path',
  +                                 ],
  +                                 'dest': 'operation_request_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--result-path',
  +                                 ],
  +                                 'dest': 'operation_result_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                             {
  +                                 'metavar': 'parent',
  +                                 'dest': 'parent',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'ref',
                            'path': [
                                'patch',
                                'ref',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '61442b7731c6b7ff',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [
                                {
  +                                 'name': 'add',
  +                                 'path': [
  +                                     'patch',
  +                                     'ref',
  +                                     'add',
  +                                 ],
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '13545b5ff6c97843',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'add',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'patch',
  -                                         'hidden': False,
  -                                         'kind': 'patch',
  -                                         'repeatable': False,
                                            'strings': [
                                                '-p',
                                                '--patch',
                                                '-c',
                                                '--changespec',
                                            ],
  +                                         'dest': 'patch',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': 'patch',
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [
  +                                     {
  +                                         'metavar': 'refs',
  +                                         'dest': 'refs',
  +                                         'nargs': '+',
  +                                         'choices': None,
  +                                         'kind': 'artifact',
  +                                         'is_remainder': False,
  +                                     },
  +                                 ],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'list',
                                    'path': [
                                        'patch',
                                        'ref',
  -                                     'add',
  ?                                      ^^^
  +                                     'list',
  ?                                      ^^^^
                                    ],
  -                                 'positionals': [
  -                                     {
  -                                         'choices': None,
  -                                         'dest': 'refs',
  -                                         'is_remainder': False,
  -                                         'kind': 'artifact',
  -                                         'metavar': 'refs',
  -                                         'nargs': '+',
  -                                     },
  -                                 ],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '9d1ec7ca208a96b4',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'list',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'patch',
  -                                         'hidden': False,
  -                                         'kind': 'patch',
  -                                         'repeatable': False,
                                            'strings': [
                                                '-p',
                                                '--patch',
                                                '-c',
                                                '--changespec',
                                            ],
  +                                         'dest': 'patch',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': 'patch',
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'json',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-j',
                                                '--json',
                                            ],
  +                                         'dest': 'json',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'resolve',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-r',
                                                '--resolve',
                                            ],
  +                                         'dest': 'resolve',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'rm',
                                    'path': [
                                        'patch',
                                        'ref',
  -                                     'list',
  ?                                      ^^^^
  +                                     'rm',
  ?                                      ^^
                                    ],
  -                                 'positionals': [],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': 'd795fc877a9aecb3',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'rm',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'patch',
  -                                         'hidden': False,
  -                                         'kind': 'patch',
  -                                         'repeatable': False,
                                            'strings': [
                                                '-p',
                                                '--patch',
                                                '-c',
                                                '--changespec',
                                            ],
  +                                         'dest': 'patch',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': 'patch',
  +                                         'hidden': False,
                                        },
  -                                 ],
  -                                 'path': [
  -                                     'patch',
  -                                     'ref',
  -                                     'rm',
                                    ],
                                    'positionals': [
                                        {
  +                                         'metavar': 'refs',
  +                                         'dest': 'refs',
  +                                         'nargs': '+',
                                            'choices': None,
  -                                         'dest': 'refs',
  ?                                           ^^  --------
  +                                         'kind': 'artifact',
  ?                                          +++ ^^^^^^^^^^^
                                            'is_remainder': False,
  -                                         'kind': 'artifact',
  -                                         'metavar': 'refs',
  -                                         'nargs': '+',
                                        },
                                    ],
                                    'subcommands': [],
  -                             },
  -                         ],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  +                                 'default_child': None,
  ? ++++++++
  -                         'description_digest': '7d1fe9166ca158be',
  +                                 'mutex_groups': [],
  +                             },
  -                         'hidden': False,
  ?                         ^^^^^^^^^^^^^^^
  +                         ],
  ?                         ^
  +                         'default_child': 'list',
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'restore',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project-file',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-Q',
  -                                     '--request-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-R',
  -                                     '--result-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'patch',
                                'restore',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'patch',
  -                                 'metavar': 'name',
  -                                 'nargs': None,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'status',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'status',
  -                                 'nargs': '?',
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '9f9f047fa80326bf',
                            'hidden': False,
  +                         'description_digest': '7d1fe9166ca158be',
  -                         'mutex_groups': [],
  -                         'name': 'revert',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  ?                                           -----------
  +                                 'dest': 'help',
  ?                                          +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project-file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  ?                                  ---    ^ ^
  +                                 'dest': 'project_file',
  ?                                   +++   ^^^ ^ ++++++++
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-Q',
                                        '--request-path',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  ?                                                       --
  +                                 'dest': 'operation_request_path',
  ?                                                      +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-R',
                                        '--result-path',
                                    ],
  +                                 'dest': 'operation_result_path',
                                    'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                             {
  +                                 'metavar': 'status',
  +                                 'dest': 'status',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'revert',
                            'path': [
                                'patch',
                                'revert',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'patch',
  -                                 'metavar': 'name',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '9aafe05147d6e0ca',
                            'hidden': False,
  +                         'description_digest': '9f9f047fa80326bf',
  -                         'mutex_groups': [],
  -                         'name': 'rewind',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  ?                                           -----------
  +                                 'dest': 'help',
  ?                                          +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project-file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  ?                                  ---    ^ ^
  +                                 'dest': 'project_file',
  ?                                   +++   ^^^ ^ ++++++++
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-Q',
                                        '--request-path',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  ?                                                       --
  +                                 'dest': 'operation_request_path',
  ?                                                      +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-R',
                                        '--result-path',
                                    ],
  +                                 'dest': 'operation_result_path',
                                    'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'rewind',
                            'path': [
                                'patch',
                                'rewind',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'patch',
  -                                 'metavar': 'name',
  -                                 'nargs': None,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'entry',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'entry',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '582eee9bf46e929c',
                            'hidden': False,
  +                         'description_digest': '9aafe05147d6e0ca',
  -                         'mutex_groups': [],
  -                         'name': 'reword',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  ?                                           -----------
  +                                 'dest': 'help',
  ?                                          +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project-file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  ?                                  ---    ^ ^
  +                                 'dest': 'project_file',
  ?                                   +++   ^^^ ^ ++++++++
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-Q',
                                        '--request-path',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  ?                                                       --
  +                                 'dest': 'operation_request_path',
  ?                                                      +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-R',
                                        '--result-path',
                                    ],
  +                                 'dest': 'operation_result_path',
                                    'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                             {
  +                                 'metavar': 'entry',
  +                                 'dest': 'entry',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'reword',
                            'path': [
                                'patch',
                                'reword',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'patch',
  -                                 'metavar': 'name',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '6848f6389773ae4b',
                            'hidden': False,
  +                         'description_digest': '582eee9bf46e929c',
  -                         'mutex_groups': [],
  -                         'name': 'search',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project-file',
  +                                 ],
  +                                 'dest': 'project_file',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-Q',
  +                                     '--request-path',
  +                                 ],
  +                                 'dest': 'operation_request_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--result-path',
  +                                 ],
  +                                 'dest': 'operation_result_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'search',
  +                         'path': [
  +                             'patch',
  +                             'search',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '6848f6389773ae4b',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'plain',
                                        'rich',
                                        'markdown',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
  -                         ],
  -                         'path': [
  -                             'patch',
  -                             'search',
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^
  +                                 'metavar': 'query',
  ?                                  ^ ^^^^^   ^^^ +++
                                    'dest': 'query',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
                                    'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'query',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '4fa85c08570998e3',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'set-origin',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project-file',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'patch',
                                'set-origin',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '4fa85c08570998e3',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project-file',
  +                                 ],
  +                                 'dest': 'project_file',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^
  +                                 'metavar': 'name',
  ?                                  ^ ^^^^^   ^ ++ +
                                    'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
                                    'is_remainder': False,
  -                                 'kind': 'patch',
  +                             },
  +                             {
  -                                 'metavar': 'name',
  ?                                              ---
  +                                 'metavar': 'origin',
  ?                                             +++++
  +                                 'dest': 'origin',
                                    'nargs': None,
  -                             },
  -                             {
                                    'choices': [
                                        'sase',
                                        'external',
                                        'unknown',
                                    ],
  -                                 'dest': 'origin',
  ?                                   ---   ^ ---- ^
  +                                 'kind': None,
  ?                                  +++    ^  ^
                                    'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'origin',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'e3d94bc9d3c09feb',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'status',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project-file',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-Q',
  -                                     '--request-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-R',
  -                                     '--result-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'patch',
                                'status',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'patch',
  -                                 'metavar': 'name',
  -                                 'nargs': None,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'status',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'status',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'b4870c1db993ef6c',
                            'hidden': False,
  +                         'description_digest': 'e3d94bc9d3c09feb',
  -                         'mutex_groups': [],
  -                         'name': 'submit',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  ?                                           -----------
  +                                 'dest': 'help',
  ?                                          +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project-file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  ?                                  ---    ^ ^
  +                                 'dest': 'project_file',
  ?                                   +++   ^^^ ^ ++++++++
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-Q',
                                        '--request-path',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  ?                                                       --
  +                                 'dest': 'operation_request_path',
  ?                                                      +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-R',
                                        '--result-path',
                                    ],
  +                                 'dest': 'operation_result_path',
                                    'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                             {
  +                                 'metavar': 'status',
  +                                 'dest': 'status',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'submit',
                            'path': [
                                'patch',
                                'submit',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'patch',
  -                                 'metavar': 'name',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '8932087ba00d4c75',
                            'hidden': False,
  +                         'description_digest': 'b4870c1db993ef6c',
  -                         'mutex_groups': [],
  -                         'name': 'sync',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  ?                                           -----------
  +                                 'dest': 'help',
  ?                                          +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project-file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  ?                                  ---    ^ ^
  +                                 'dest': 'project_file',
  ?                                   +++   ^^^ ^ ++++++++
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-Q',
                                        '--request-path',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  ?                                                       --
  +                                 'dest': 'operation_request_path',
  ?                                                      +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-R',
                                        '--result-path',
                                    ],
  +                                 'dest': 'operation_result_path',
                                    'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'sync',
                            'path': [
                                'patch',
                                'sync',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'patch',
  -                                 'metavar': 'name',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '93df48a5733236eb',
                            'hidden': False,
  +                         'description_digest': '8932087ba00d4c75',
  -                         'mutex_groups': [],
  -                         'name': 'sync-deltas',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'cl_name',
  ?                                          ^ ^^^^^
  +                                 'dest': 'help',
  ?                                          ^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project-file',
  +                                 ],
  +                                 'dest': 'project_file',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-Q',
  +                                     '--request-path',
  +                                 ],
  +                                 'dest': 'operation_request_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--result-path',
  +                                 ],
  +                                 'dest': 'operation_result_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'sync-deltas',
  +                         'path': [
  +                             'patch',
  +                             'sync-deltas',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '93df48a5733236eb',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-P',
                                        '--patch',
                                        '-c',
                                        '--cl',
                                        '--changespec',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  ?                                          ----- ^ ^^^
  +                                 'dest': 'cl_name',
  ?                                           ^ ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project-file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'workspace_dir',
  ?                                          ^ ^^^^^  ----
  +                                 'dest': 'project_file',
  ?                                          ^^ ^^ +++++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-w',
                                        '--workspace-dir',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^ ^
  +                                 'dest': 'workspace_dir',
  ?                                  ^  ^   ^^^ ^^^^^ +++++
  +                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'patch',
  ?                                 ^^
  +                                 'repeatable': False,
  ? ++++                             ++ +  ^^^^ +++++++
  -                             'sync-deltas',
  ?                              --- ^^ ---
  +                                 'choices': None,
  ? ++++                              ^^^^   ++++++
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '7fbf535d63e38c85',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'sync-external',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-d',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'full',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-f',
  -                                     '--full',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'patch',
                                'sync-external',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '7fbf535d63e38c85',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-d',
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--full',
  +                                 ],
  +                                 'dest': 'full',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '64e7ac6c325fb5dd',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'tag',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project_file',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project-file',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-Q',
  -                                     '--request-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-R',
  -                                     '--result-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'patch',
                                'tag',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '64e7ac6c325fb5dd',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project-file',
  +                                 ],
  +                                 'dest': 'project_file',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-Q',
  +                                     '--request-path',
  +                                 ],
  +                                 'dest': 'operation_request_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--result-path',
  +                                 ],
  +                                 'dest': 'operation_result_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^
  +                                 'metavar': 'name',
  ?                                  ^ ^^^^^   ^ ++ +
                                    'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'patch',
                                    'is_remainder': False,
  -                                 'kind': 'patch',
  +                             },
  +                             {
  -                                 'metavar': 'name',
  ?                                             ^ ^^
  +                                 'metavar': 'tag',
  ?                                             ^ ^
  +                                 'dest': 'tag',
                                    'nargs': None,
  -                             },
  -                             {
                                    'choices': None,
  -                                 'dest': 'tag',
  ?                                   ---
  +                                 'kind': 'tag',
  ?                                  +++
                                    'is_remainder': False,
  -                                 'kind': 'tag',
  -                                 'metavar': 'tag',
  -                                 'nargs': None,
                                },
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^
  +                                 'metavar': 'value',
  ?                                  ^ ^^^^^   ^^^^^ +
                                    'dest': 'value',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': None,
                                    'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'value',
  -                                 'nargs': '?',
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'path',
  +                 'path': [
  +                     'path',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  +                 'hidden': False,
                    'description_digest': '5a67dd90d5fcce0e',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'path',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'path',
                    ],
                    'positionals': [
                        {
  +                         'metavar': 'name',
  +                         'dest': 'name',
  +                         'nargs': None,
                            'choices': [
                                'config-schema',
                                'xprompts-dir',
                                'xprompts-schema',
                                'xprompts-collection-schema',
                            ],
  -                         'dest': 'name',
  ?                           ---   ^ -- -
  +                         'kind': None,
  ?                          +++    ^^
                            'is_remainder': False,
  -                         'kind': None,
  -                         'metavar': 'name',
  -                         'nargs': None,
                        },
                    ],
                    'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'pipe',
  +                 'path': [
  +                     'pipe',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  +                 'hidden': False,
                    'description_digest': '5bad3a61bc3aa588',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'pipe',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'fresh',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-f',
                                '--fresh',
                            ],
  +                         'dest': 'fresh',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'json',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-j',
                                '--json',
                            ],
  +                         'dest': 'json',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'model',
  -                         'hidden': False,
  -                         'kind': 'model',
  ?                                 ^^ ^ --
  +                         'kind': None,
  ?                                 ^ ^
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-m',
                                '--model',
                            ],
  +                         'dest': 'model',
                            'takes_value': True,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'name',
  -                         'hidden': False,
  -                         'kind': None,
  ?                                 ^ ^
  +                         'kind': 'model',
  ?                                 ^^ ^ ++
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-n',
                                '--name',
                            ],
  +                         'dest': 'name',
                            'takes_value': True,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'reason',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-r',
                                '--reason',
                            ],
  +                         'dest': 'reason',
                            'takes_value': True,
  +                         'repeatable': False,
  +                         'choices': None,
  -                     },
  -                 ],
  -                 'path': [
  -                     'pipe',
  ?                      ^ ^ -
  +                         'kind': None,
  ? ++++                     ^ ^^^^^^^^
  +                         'hidden': False,
  +                     },
                    ],
                    'positionals': [
                        {
  +                         'metavar': 'PROMPT',
  +                         'dest': 'prompt',
  +                         'nargs': None,
                            'choices': None,
  -                         'dest': 'prompt',
  ?                           ---   ^^^ ^^^^
  +                         'kind': None,
  ?                          +++    ^ ^^
                            'is_remainder': False,
  -                         'kind': None,
  -                         'metavar': 'PROMPT',
  -                         'nargs': None,
                        },
                    ],
                    'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'plan',
  +                 'path': [
  +                     'plan',
  +                 ],
                    'aliases': [],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': 'baa415214d8946fc',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'plan',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  -                     },
  -                 ],
  -                 'path': [
  -                     'plan',
  ?                      ^^^
  +                         'kind': None,
  ? ++++                     ^^ + ++++++
  +                         'hidden': False,
  +                     },
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  +                         'name': 'approve',
  +                         'path': [
  +                             'plan',
  +                             'approve',
  +                         ],
                            'aliases': [],
  -                         'default_child': None,
  +                         'hidden': False,
                            'description_digest': 'e22e946be59eac09',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'approve',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-k',
  +                                     '--kind',
  +                                 ],
  +                                 'dest': 'kind',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'approve',
                                        'commit',
                                        'epic',
                                        'tale',
                                    ],
  -                                 'dest': 'kind',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-k',
  -                                     '--kind',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'model',
  -                                 'hidden': False,
  -                                 'kind': 'model',
  -                                 'repeatable': False,
                                    'strings': [
                                        '-m',
                                        '--model',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'prompt',
  ?                                          ^^ ^^^
  +                                 'dest': 'model',
  ?                                          ^ ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'model',
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--prompt',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^ ^^
  +                                 'dest': 'prompt',
  ?                                  ^  ^   ^^ ^^^^^
  -                             },
  -                         ],
  -                         'path': [
  -                             'plan',
  -                             'approve',
  ?                               ^^^^
  +                                 'takes_value': True,
  ? ++++                             + ^^^^ +++  ++++++
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  +                                 'metavar': 'SELECTOR',
                                    'dest': 'selector',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': None,
                                    'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'SELECTOR',
  -                                 'nargs': '?',
                                },
                            ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': 'list',
  ?                                          ^^^^^^
  +                         'default_child': None,
  ?                                          ^^^^
  -                         'description_digest': 'ae5775b31f54a85b',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'links',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'plan',
                                'links',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'ae5775b31f54a85b',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [
                                {
  +                                 'name': 'list',
  +                                 'path': [
  +                                     'plan',
  +                                     'links',
  +                                     'list',
  +                                 ],
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '2b1cde50d11f1c26',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'list',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'json',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-j',
                                                '--json',
                                            ],
  +                                         'dest': 'json',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'path',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-p',
                                                '--path',
                                            ],
  +                                         'dest': 'path',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'refresh',
                                    'path': [
                                        'plan',
                                        'links',
  -                                     'list',
  ?                                      ^^ ^
  +                                     'refresh',
  ?                                      ^^^^^ ^
                                    ],
  -                                 'positionals': [],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '1dcae110db4d927b',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'refresh',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'json',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-j',
                                                '--json',
                                            ],
  +                                         'dest': 'json',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'path',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-p',
                                                '--path',
                                            ],
  +                                         'dest': 'path',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'plan',
  -                                         'hidden': False,
  -                                         'kind': 'plan',
  -                                         'repeatable': False,
                                            'strings': [
                                                '-P',
                                                '--plan',
                                            ],
  +                                         'dest': 'plan',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': 'plan',
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'write',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-w',
                                                '--write',
                                            ],
  +                                         'dest': 'write',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'repair',
                                    'path': [
                                        'plan',
                                        'links',
  -                                     'refresh',
  ?                                        ^ ---
  +                                     'repair',
  ?                                        ^^^
                                    ],
  -                                 'positionals': [],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '6150ee22819f980e',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'repair',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'path',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-p',
                                                '--path',
                                            ],
  +                                         'dest': 'path',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'write',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-w',
                                                '--write',
                                            ],
  +                                         'dest': 'write',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'validate',
                                    'path': [
                                        'plan',
                                        'links',
  -                                     'repair',
  ?                                      ^ ----
  +                                     'validate',
  ?                                      ^^^^^^^
                                    ],
  -                                 'positionals': [],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': 'af3d17a85440bf9a',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'validate',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'json',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-j',
                                                '--json',
                                            ],
  +                                         'dest': 'json',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'path',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-p',
                                                '--path',
                                            ],
  +                                         'dest': 'path',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'quiet',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-q',
                                                '--quiet',
                                            ],
  +                                         'dest': 'quiet',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'show_warnings',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-W',
                                                '--show-warnings',
                                            ],
  +                                         'dest': 'show_warnings',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
  -                                 ],
  -                                 'path': [
  -                                     'plan',
  -                                     'links',
  -                                     'validate',
                                    ],
                                    'positionals': [],
                                    'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
                                },
                            ],
  +                         'default_child': 'list',
  +                         'mutex_groups': [],
                        },
                        {
  +                         'name': 'list',
  +                         'path': [
  +                             'plan',
  +                             'list',
  +                         ],
                            'aliases': [],
  -                         'default_child': None,
  +                         'hidden': False,
                            'description_digest': 'e19f600b3ccafcb7',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'list',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-j',
                                        '--json',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'limit',
  ?                                          ^^^^^
  +                                 'dest': 'json',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-n',
                                        '--limit',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^^^^
  +                                 'dest': 'limit',
  ?                                  ^  ^   ^^^^^^^
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--status',
  +                                 ],
  +                                 'dest': 'status',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
                                    'choices': [
                                        'approved',
                                        'proposed',
                                        'rejected',
                                    ],
  -                                 'dest': 'status',
  -                                 'hidden': False,
                                    'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--tier',
  +                                 ],
  +                                 'dest': 'tier',
  +                                 'takes_value': True,
                                    'repeatable': True,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--status',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
                                    'choices': [
                                        'tale',
                                        'epic',
                                    ],
  -                                 'dest': 'tier',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  ?                                  ^^^  --   ^
  +                                 'hidden': False,
  ?                                  ^ +++    ^^^^^^
  -                                     '-t',
  -                                     '--tier',
  -                                 ],
  -                                 'takes_value': True,
                                },
  -                         ],
  -                         'path': [
  -                             'plan',
  -                             'list',
                            ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '47562d22311f8466',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'propose',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'plan',
                                'propose',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'plan_file',
  -                                 'is_remainder': False,
  -                                 'kind': 'path',
  -                                 'metavar': 'PLAN_FILE',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '1ac9ca2da9212890',
                            'hidden': False,
  +                         'description_digest': '47562d22311f8466',
  -                         'mutex_groups': [],
  -                         'name': 'reject',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'PLAN_FILE',
  +                                 'dest': 'plan_file',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'path',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'reject',
                            'path': [
                                'plan',
                                'reject',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'selector',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'SELECTOR',
  -                                 'nargs': '?',
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'dfbabeb51c530272',
                            'hidden': False,
  +                         'description_digest': '1ac9ca2da9212890',
  -                         'mutex_groups': [],
  -                         'name': 'search',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'SELECTOR',
  +                                 'dest': 'selector',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'search',
  +                         'path': [
  +                             'plan',
  +                             'search',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'dfbabeb51c530272',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--color',
  +                                 ],
  +                                 'dest': 'color',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'auto',
                                        'always',
                                        'never',
                                    ],
  -                                 'dest': 'color',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-c',
  -                                     '--color',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'compact',
                                        'full',
                                        'json',
                                        'markdown',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'kind',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': True,
                                    'strings': [
                                        '-k',
                                        '--kind',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'limit',
  ?                                          ^ ^^^
  +                                 'dest': 'kind',
  ?                                          ^ ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-n',
                                        '--limit',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'since',
  ?                                          ^ ^^^
  +                                 'dest': 'limit',
  ?                                          ^ ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-A',
                                        '--since',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^  ------
  +                                 'dest': 'since',
  ?                                  ^  ^^^^^^^^^
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-o',
  +                                     '--source',
  +                                 ],
  +                                 'dest': 'source',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'all',
                                        'repo',
                                        'local',
                                    ],
  -                                 'dest': 'source',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-o',
  -                                     '--source',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-r',
  +                                     '--sort',
  +                                 ],
  +                                 'dest': 'sort',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'relevance',
                                        'recent',
                                        'title',
                                    ],
  -                                 'dest': 'sort',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-r',
  -                                     '--sort',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--status',
  +                                 ],
  +                                 'dest': 'status',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
                                    'choices': [
                                        'wip',
                                        'done',
                                    ],
  -                                 'dest': 'status',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--status',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  +                             },
  +                             {
  -                                 'dest': 'until',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-B',
                                        '--until',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^^ ^
  +                                 'dest': 'until',
  ?                                  ^  ^   ^ ^^^^^
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'query',
  +                                 'dest': 'query',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'show',
                            'path': [
                                'plan',
  -                             'search',
  ?                               ----
  +                             'show',
  ?                                ++
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'query',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'query',
  -                                 'nargs': '?',
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  +                         'hidden': False,
                            'description_digest': 'e3ce2da9884dcd69',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'show',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--color',
  +                                 ],
  +                                 'dest': 'color',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'auto',
                                        'always',
                                        'never',
                                    ],
  -                                 'dest': 'color',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-c',
  -                                     '--color',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'compact',
                                        'full',
                                        'json',
                                        'raw',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--target',
  +                                 ],
  +                                 'dest': 'target_kind',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'auto',
                                        'bead',
                                        'name',
                                        'path',
                                        'proposal',
                                        'ref',
                                    ],
  -                                 'dest': 'target_kind',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-t',
  -                                     '--target',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'wrap',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-w',
                                        '--wrap',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^ ^^
  +                                 'dest': 'wrap',
  ?                                  ^  ^   ^^ ^^^
  +                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'plan',
  ?                                 ^^
  +                                 'repeatable': False,
  ? ++++                             ++ +++++ +++++ ^^^
  -                             'show',
  ?                              ^  ^
  +                                 'choices': None,
  ? ++++                             ^  ^^^^ ++++++
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^^
  +                                 'metavar': 'TARGET',
  ?                                  ^ ^^^^^   ^^^^^^^^
                                    'dest': 'target',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': 'plan',
                                    'is_remainder': False,
  -                                 'kind': 'plan',
  -                                 'metavar': 'TARGET',
  -                                 'nargs': '?',
                                },
                            ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '5b648b3c4da7ccf7',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'validate',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'explain',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-e',
  -                                     '--explain',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'quiet',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-q',
  -                                     '--quiet',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'plan',
                                'validate',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '5b648b3c4da7ccf7',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-e',
  +                                     '--explain',
  +                                 ],
  +                                 'dest': 'explain',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-q',
  +                                     '--quiet',
  +                                 ],
  +                                 'dest': 'quiet',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^    ^^^
  +                                 'metavar': 'PLAN_FILE',
  ?                                  ^ ^^^^^   ++++ ^^^^^^
                                    'dest': 'plan_file',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'path',
                                    'is_remainder': False,
  -                                 'kind': 'path',
  -                                 'metavar': 'PLAN_FILE',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'plugin',
  +                 'path': [
  +                     'plugin',
  +                 ],
                    'aliases': [],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': '6a3f19bad67792d1',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'plugin',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  -                     },
  -                 ],
  -                 'path': [
  -                     'plugin',
  ?                      ^^^^
  +                         'kind': None,
  ? ++++                     ^  + ++++++
  +                         'hidden': False,
  +                     },
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'bf7c26605e5864fa',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'install',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'git',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-g',
  -                                     '--git',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-n',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'refresh',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-r',
  -                                     '--refresh',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-Q',
  -                                     '--request-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-R',
  -                                     '--result-path',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'plugin',
                                'install',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'plugin',
  -                                 'is_remainder': False,
  -                                 'kind': 'plugin',
  -                                 'metavar': '<plugin>',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '109ca50b2e1bd936',
                            'hidden': False,
  +                         'description_digest': 'bf7c26605e5864fa',
  -                         'mutex_groups': [],
  -                         'name': 'list',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-g',
  +                                     '--git',
  +                                 ],
  +                                 'dest': 'git',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-j',
                                        '--json',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'offline',
  ?                                           ---- -
  +                                 'dest': 'json',
  ?                                          ++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-o',
  -                                     '--offline',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'refresh',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-n',
  ? ++++                                 ^^
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-r',
                                        '--refresh',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all_latest',
  ?                                          ^^^^^^^  ^
  +                                 'dest': 'refresh',
  ?                                          ^^^^  ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-A',
  -                                     '--all-latest',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'verbose',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-Q',
  ? ++++                                 ^^
  -                                 'strings': [
  +                                     '--request-path',
  -                                     '-v',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--verbose',
  +                                 'dest': 'operation_request_path',
  -                                 ],
  ?                                 ^
  +                                 'takes_value': True,
  ?                                 ^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--result-path',
  +                                 ],
  +                                 'dest': 'operation_result_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': '<plugin>',
  +                                 'dest': 'plugin',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'plugin',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'list',
                            'path': [
                                'plugin',
                                'list',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '109ca50b2e1bd936',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-o',
  +                                     '--offline',
  +                                 ],
  +                                 'dest': 'offline',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-r',
  +                                     '--refresh',
  +                                 ],
  +                                 'dest': 'refresh',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-A',
  +                                     '--all-latest',
  +                                 ],
  +                                 'dest': 'all_latest',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-v',
  +                                     '--verbose',
  +                                 ],
  +                                 'dest': 'verbose',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'bec792066af143d3',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'show',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'offline',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-o',
  -                                     '--offline',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'refresh',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-r',
  -                                     '--refresh',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'plugin',
                                'show',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'plugin_name',
  -                                 'is_remainder': False,
  -                                 'kind': 'plugin',
  -                                 'metavar': '<plugin_name>',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'd1f11a3ac74ec272',
                            'hidden': False,
  +                         'description_digest': 'bec792066af143d3',
  -                         'mutex_groups': [],
  -                         'name': 'uninstall',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-j',
                                        '--json',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  ?                                          ^^^^^^
  +                                 'dest': 'json',
  ?                                          ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-n',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'refresh',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-o',
  ? ++++                                 ^^
  +                                     '--offline',
  +                                 ],
  +                                 'dest': 'offline',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-r',
                                        '--refresh',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  ?                                          ----------  ^^  -----
  +                                 'dest': 'refresh',
  ?                                            ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-Q',
  -                                     '--request-path',
  -                                 ],
  -                                 'takes_value': True,
  ?                                    ^^^^^^ -    ^^^
  +                                 'repeatable': False,
  ?                                  +++++  ^     ^^^^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'operation_result_path',
  -                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  -                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^^
  +                             {
  ?                             ^
  -                                 'repeatable': False,
  ?                                  ^ ---  ^^^   ^ ^^
  +                                 'metavar': '<plugin_name>',
  ?                                  ^   ^^^   ^^^^^^^^^^ ^ ++
  -                                 'strings': [
  ?                                    ^  ^^ ^^^
  +                                 'dest': 'plugin_name',
  ?                                  ++  ^^^^^^^^  ^^^^^ ^
  -                                     '-R',
  ? ----                                 ^^
  +                                 'nargs': None,
  ?                                  ^^^^^ ++++++
  -                                     '--result-path',
  -                                 ],
  ?                                 ^
  +                                 'choices': None,
  ?                                 ^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                  -- ^^^^^  ^ ------
  +                                 'kind': 'plugin',
  ?                                   ^^^^^^^^  ^^^
  +                                 'is_remainder': False,
                                },
                            ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'uninstall',
                            'path': [
                                'plugin',
                                'uninstall',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'plugin',
  -                                 'is_remainder': False,
  -                                 'kind': 'plugin',
  -                                 'metavar': '<plugin>',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'd9ed28fde7247012',
                            'hidden': False,
  +                         'description_digest': 'd1f11a3ac74ec272',
  -                         'mutex_groups': [],
  -                         'name': 'update',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all',
  ?                                          ^ ^
  +                                 'dest': 'help',
  ?                                          ^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-a',
  -                                     '--all',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'json',
  ?                             ^^^^^^^^^^^^^^^^^^
  +                             },
  ?                             ^
  +                             {
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-j',
                                        '--json',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  ?                                          ^^^^^^
  +                                 'dest': 'json',
  ?                                          ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-n',
                                        '--dry-run',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'refresh',
  ?                                           ^^ ^^^
  +                                 'dest': 'dry_run',
  ?                                          + ^^ ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-r',
                                        '--refresh',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_request_path',
  ?                                          ----------  ^^  -----
  +                                 'dest': 'refresh',
  ?                                            ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-Q',
                                        '--request-path',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'operation_result_path',
  ?                                                       --
  +                                 'dest': 'operation_request_path',
  ?                                                      +++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-R',
                                        '--result-path',
                                    ],
  +                                 'dest': 'operation_result_path',
                                    'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': '<plugin>',
  +                                 'dest': 'plugin',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'plugin',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'update',
                            'path': [
                                'plugin',
                                'update',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'd9ed28fde7247012',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--all',
  +                                 ],
  +                                 'dest': 'all',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-r',
  +                                     '--refresh',
  +                                 ],
  +                                 'dest': 'refresh',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-Q',
  +                                     '--request-path',
  +                                 ],
  +                                 'dest': 'operation_request_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--result-path',
  +                                 ],
  +                                 'dest': 'operation_result_path',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^ ^
  +                                 'metavar': '<plugin>',
  ?                                  ^ ^^^^^   ^^^^^^^ ^^
                                    'dest': 'plugin',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': 'plugin',
                                    'is_remainder': False,
  -                                 'kind': 'plugin',
  -                                 'metavar': '<plugin>',
  -                                 'nargs': '?',
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'proc',
  +                 'path': [
  +                     'proc',
  +                 ],
                    'aliases': [
                        'task',
                    ],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': 'b27912a3f3363439',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'proc',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'proc',
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '0bff067a5f5ed7b2',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'kill',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'proc',
                                'kill',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'proc_id',
  -                                 'is_remainder': False,
  -                                 'kind': 'proc',
  -                                 'metavar': 'REF',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '58c1b3ef56f6b4be',
                            'hidden': False,
  +                         'description_digest': '0bff067a5f5ed7b2',
  -                         'mutex_groups': [],
  -                         'name': 'list',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all',
  ?                                          ^ ^
  +                                 'dest': 'help',
  ?                                          ^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'REF',
  +                                 'dest': 'proc_id',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'proc',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'list',
  +                         'path': [
  +                             'proc',
  +                             'list',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '58c1b3ef56f6b4be',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-a',
                                        '--all',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  ?                                          ^^^^
  +                                 'dest': 'all',
  ?                                          ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-j',
                                        '--json',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^^ ^
  +                                 'dest': 'json',
  ?                                  ^  ^   ^^ ^^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-k',
  +                                     '--kind',
  +                                 ],
  +                                 'dest': 'kind',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
                                    'choices': [
                                        'command',
                                        'tui',
                                        'detached',
                                    ],
  -                                 'dest': 'kind',
  ?                                --------
  +                                 'kind': None,
  ?                                       ++++++
                                    'hidden': True,
  -                                 'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-k',
  -                                     '--kind',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'limit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-n',
                                        '--limit',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'shell',
  ?                                          --- ^
  +                                 'dest': 'limit',
  ?                                           ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-N',
                                        '--shell',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  ?                                          ^^^^ ^^
  +                                 'dest': 'shell',
  ?                                          ^^ ^^
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'query',
  ?                                          ^^ ^^
  +                                 'dest': 'project',
  ?                                          ^^^^ ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-q',
                                        '--query',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'running',
  ?                                           ^^^^^^
  +                                 'dest': 'query',
  ?                                          +++ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-r',
                                        '--running',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'session',
  ?                                          ^^^^ -
  +                                 'dest': 'running',
  ?                                          ^^^^  +
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-s',
                                        '--session',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^^^
  +                                 'dest': 'session',
  ?                                  ^  ^   ^^ ++++++
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-S',
  +                                     '--status',
  +                                 ],
  +                                 'dest': 'status',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
                                    'choices': [
                                        'pending',
                                        'running',
                                        'settling',
                                        'success',
                                        'error',
                                        'killed',
                                    ],
  -                                 'dest': 'status',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-S',
  -                                     '--status',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'tag',
  ?                             ^^^^^^^^^^^^^^^^^
  +                             },
  ?                             ^
  +                             {
  -                                 'hidden': False,
  -                                 'kind': 'tag',
  -                                 'repeatable': False,
                                    'strings': [
                                        '-t',
                                        '--tag',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'proc',
  -                             'list',
  ?                              ^^
  +                                 'dest': 'tag',
  ? ++++                             ^^   +++++++
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'tag',
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'abfb3b6096584e15',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'run',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'cwd',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-c',
  -                                     '--cwd',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'label',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-l',
  -                                     '--label',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'shell',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-N',
  -                                     '--shell',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'quiet',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-q',
  -                                     '--quiet',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'session',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--session',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'tag',
  -                                 'hidden': False,
  -                                 'kind': 'tag',
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-t',
  -                                     '--tag',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'wait',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-w',
  -                                     '--wait',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'proc',
                                'run',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'proc_command',
  -                                 'is_remainder': True,
  -                                 'kind': None,
  -                                 'metavar': '-- COMMAND ...',
  -                                 'nargs': '...',
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'b306840da7a9d865',
                            'hidden': False,
  +                         'description_digest': 'abfb3b6096584e15',
  -                         'mutex_groups': [],
  -                         'name': 'show',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all_lines',
  ?                                          ^ ^^^^^^^
  +                                 'dest': 'help',
  ?                                          ^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--cwd',
  +                                 ],
  +                                 'dest': 'cwd',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-l',
  +                                     '--label',
  +                                 ],
  +                                 'dest': 'label',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-N',
  +                                     '--shell',
  +                                 ],
  +                                 'dest': 'shell',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-q',
  +                                     '--quiet',
  +                                 ],
  +                                 'dest': 'quiet',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--session',
  +                                 ],
  +                                 'dest': 'session',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--tag',
  +                                 ],
  +                                 'dest': 'tag',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': 'tag',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-w',
  +                                     '--wait',
  +                                 ],
  +                                 'dest': 'wait',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': '-- COMMAND ...',
  +                                 'dest': 'proc_command',
  +                                 'nargs': '...',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': True,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'show',
  +                         'path': [
  +                             'proc',
  +                             'show',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'b306840da7a9d865',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-A',
                                        '--all-lines',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^  ^  -------
  +                                 'dest': 'all_lines',
  ?                                  ^  ^^^^^  ^^^^^ +
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'markdown',
                                        'json',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'follow',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-F',
                                        '--follow',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'log_lines',
  ?                                            ^^^^^^^
  +                                 'dest': 'follow',
  ?                                          +++  ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-l',
                                        '--log-lines',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'output_only',
  ?                                           ^^^^^ ^ ^^
  +                                 'dest': 'log_lines',
  ?                                          + ^ ^^ ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-o',
                                        '--output-only',
                                    ],
  +                                 'dest': 'output_only',
                                    'takes_value': False,
  +                                 'repeatable': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'proc',
  ?                              ^^
  +                                 'choices': None,
  ? ++++                             ^^ + ++ ++++++
  -                             'show',
  ?                              ^^ ^^
  +                                 'kind': None,
  ? ++++                             ^^^^^^^^ ^^
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^^
  +                                 'metavar': 'REF',
  ?                                  ^ ^^^^^   ^^^^^
                                    'dest': 'proc_id',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'proc',
                                    'is_remainder': False,
  -                                 'kind': 'proc',
  -                                 'metavar': 'REF',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'project',
  +                 'path': [
  +                     'project',
  +                 ],
                    'aliases': [],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': 'b3a1ba2bf3e982c8',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'project',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'project',
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': 'list',
  -                         'description_digest': 'c41cdfb109656147',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'alias',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'project',
                                'alias',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'c41cdfb109656147',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [
                                {
  +                                 'name': 'add',
  +                                 'path': [
  +                                     'project',
  +                                     'alias',
  +                                     'add',
  +                                 ],
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '2d995f475f85a9ab',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'add',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [
  +                                     {
  +                                         'metavar': 'project',
  +                                         'dest': 'project',
  +                                         'nargs': None,
  +                                         'choices': None,
  +                                         'kind': 'project',
  +                                         'is_remainder': False,
  +                                     },
  +                                     {
  +                                         'metavar': 'alias',
  +                                         'dest': 'alias',
  +                                         'nargs': None,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'is_remainder': False,
  +                                     },
  +                                 ],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'clear',
                                    'path': [
                                        'project',
                                        'alias',
  -                                     'add',
  ?                                       ^^
  +                                     'clear',
  ?                                      +++ ^
                                    ],
  -                                 'positionals': [
  -                                     {
  -                                         'choices': None,
  -                                         'dest': 'project',
  -                                         'is_remainder': False,
  -                                         'kind': 'project',
  -                                         'metavar': 'project',
  -                                         'nargs': None,
  -                                     },
  -                                     {
  -                                         'choices': None,
  -                                         'dest': 'alias',
  -                                         'is_remainder': False,
  -                                         'kind': None,
  -                                         'metavar': 'alias',
  -                                         'nargs': None,
  -                                     },
  -                                 ],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '26be362e895f1b12',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'clear',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [
  +                                     {
  +                                         'metavar': 'project',
  +                                         'dest': 'project',
  +                                         'nargs': None,
  +                                         'choices': None,
  +                                         'kind': 'project',
  +                                         'is_remainder': False,
  +                                     },
  +                                 ],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'list',
                                    'path': [
                                        'project',
                                        'alias',
  -                                     'clear',
  ?                                      - ^^^
  +                                     'list',
  ?                                       ^^^
                                    ],
  -                                 'positionals': [
  -                                     {
  -                                         'choices': None,
  -                                         'dest': 'project',
  -                                         'is_remainder': False,
  -                                         'kind': 'project',
  -                                         'metavar': 'project',
  -                                         'nargs': None,
  -                                     },
  -                                 ],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '90f7f869f8db0969',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'list',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'json',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-j',
                                                '--json',
                                            ],
  +                                         'dest': 'json',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                    ],
  +                                 'positionals': [
  +                                     {
  +                                         'metavar': 'project',
  +                                         'dest': 'project',
  +                                         'nargs': '?',
  +                                         'choices': None,
  +                                         'kind': 'project',
  +                                         'is_remainder': False,
  +                                     },
  +                                 ],
  +                                 'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
  +                             },
  +                             {
  +                                 'name': 'remove',
                                    'path': [
                                        'project',
                                        'alias',
  -                                     'list',
  -                                 ],
  -                                 'positionals': [
  -                                     {
  -                                         'choices': None,
  -                                         'dest': 'project',
  -                                         'is_remainder': False,
  -                                         'kind': 'project',
  -                                         'metavar': 'project',
  -                                         'nargs': '?',
  -                                     },
  ?                                     ^
  +                                     'remove',
  ?                                     ^^^^^^^^
                                    ],
  -                                 'subcommands': [],
  -                             },
  -                             {
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': 'b191c59088a01af5',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'remove',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
  -                                 ],
  -                                 'path': [
  -                                     'project',
  -                                     'alias',
  -                                     'remove',
                                    ],
                                    'positionals': [
                                        {
  +                                         'metavar': 'project',
  +                                         'dest': 'project',
  +                                         'nargs': None,
                                            'choices': None,
  -                                         'dest': 'project',
  ?                                           ---
  +                                         'kind': 'project',
  ?                                          +++
                                            'is_remainder': False,
  -                                         'kind': 'project',
  -                                         'metavar': 'project',
  -                                         'nargs': None,
                                        },
                                        {
  +                                         'metavar': 'alias',
  +                                         'dest': 'alias',
  +                                         'nargs': None,
                                            'choices': None,
  -                                         'dest': 'alias',
  ?                                           ---   ^^^^^^^
  +                                         'kind': None,
  ?                                          +++    ^^^^
                                            'is_remainder': False,
  -                                         'kind': None,
  -                                         'metavar': 'alias',
  -                                         'nargs': None,
                                        },
                                    ],
                                    'subcommands': [],
  -                             },
  -                         ],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  +                                 'default_child': None,
  ? ++++++++
  -                         'description_digest': 'b8c7fcfd95632a40',
  +                                 'mutex_groups': [],
  +                             },
  -                         'hidden': False,
  ?                         ^^^^^^^^^^^^^^^
  +                         ],
  ?                         ^
  +                         'default_child': 'list',
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'current',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'project',
                                'current',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'b8c7fcfd95632a40',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'db0ade39277c304d',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'disable',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'force',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-f',
  -                                     '--force',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'project',
                                'disable',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'is_remainder': False,
  -                                 'kind': 'project',
  -                                 'metavar': 'project',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '94421f74eaf5c8f4',
                            'hidden': False,
  +                         'description_digest': 'db0ade39277c304d',
  -                         'mutex_groups': [],
  -                         'name': 'enable',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'force',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^ ++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-f',
                                        '--force',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^  -------
  +                                 'dest': 'force',
  ?                                  ^  ^^^^^^^^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'project',
  +                                 'dest': 'project',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'enable',
                            'path': [
                                'project',
                                'enable',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'is_remainder': False,
  -                                 'kind': 'project',
  -                                 'metavar': 'project',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '425efdf398be1be9',
                            'hidden': False,
  +                         'description_digest': '94421f74eaf5c8f4',
  -                         'mutex_groups': [],
  -                         'name': 'list',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'state',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^ ++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-s',
  -                                     '--state',
  -                                 ],
  -                                 'takes_value': True,
  ?                                    ^^^^^^ -    ^^^
  +                                 'repeatable': False,
  ?                                  +++++  ^     ^^^^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'json',
  ?                             ^^^^^^^^^^^^^^^^^^
  +                             },
  ?                             ^
  -                                 'hidden': False,
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-f',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^^ ^^^^ ^^^
  +                                     '--force',
  ? ++++                                 ^^^^ ^^ ^
  -                                     '-j',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--json',
  ? ----                                 ^^^  ^
  +                                 'dest': 'force',
  ?                                  ^^ ++++++ ^^^
  -                                 ],
  ?                                 ^
  +                                 'takes_value': False,
  ?                                 ^^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'project',
  +                                 'dest': 'project',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'list',
                            'path': [
                                'project',
                                'list',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '425efdf398be1be9',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--state',
  +                                 ],
  +                                 'dest': 'state',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '9b20b3ed5df4ce62',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'set-current',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'project',
                                'set-current',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'is_remainder': False,
  -                                 'kind': 'project',
  -                                 'metavar': 'project',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'fc16c49c85086156',
                            'hidden': False,
  +                         'description_digest': '9b20b3ed5df4ce62',
  -                         'mutex_groups': [],
  -                         'name': 'set-state',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'force',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^ ++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-f',
  -                                     '--force',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'project',
  +                                 'dest': 'project',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'set-state',
                            'path': [
                                'project',
                                'set-state',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'is_remainder': False,
  -                                 'kind': 'project',
  -                                 'metavar': 'project',
  -                                 'nargs': None,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'state',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': '{enabled,disabled,sibling}',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'de71242fa77783cc',
                            'hidden': False,
  +                         'description_digest': 'fc16c49c85086156',
  -                         'mutex_groups': [],
  -                         'name': 'show',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--force',
  +                                 ],
  +                                 'dest': 'force',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'project',
  +                                 'dest': 'project',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'is_remainder': False,
  +                             },
  +                             {
  +                                 'metavar': '{enabled,disabled,sibling}',
  +                                 'dest': 'state',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'show',
                            'path': [
                                'project',
                                'show',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'de71242fa77783cc',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^ ^
  +                                 'metavar': 'project',
  ?                                  ^ ^^^^^   ^^^ ^ +++
                                    'dest': 'project',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'project',
                                    'is_remainder': False,
  -                                 'kind': 'project',
  -                                 'metavar': 'project',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'prompt',
  +                 'path': [
  +                     'prompt',
  +                 ],
                    'aliases': [],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': 'b67d43e9cec720d7',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'prompt',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'prompt',
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '102ba760cbcc70e0',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'copy',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'copy',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'id',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'f7ffd9ad995a0de8',
                            'hidden': False,
  +                         'description_digest': '102ba760cbcc70e0',
  -                         'mutex_groups': [],
  -                         'name': 'delete',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'yes',
  ?                                          ^ ^
  +                                 'dest': 'help',
  ?                                          ^ ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-y',
  -                                     '--yes',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'id',
  +                                 'dest': 'id',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'delete',
                            'path': [
                                'prompt',
                                'delete',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'id',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '0be1bbecd758c297',
                            'hidden': False,
  +                         'description_digest': 'f7ffd9ad995a0de8',
  -                         'mutex_groups': [],
  -                         'name': 'doctor',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                             {
  +                                 'strings': [
  +                                     '-y',
  +                                     '--yes',
  +                                 ],
  +                                 'dest': 'yes',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'id',
  +                                 'dest': 'id',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'doctor',
                            'path': [
                                'prompt',
                                'doctor',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '0be1bbecd758c297',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '4a82c9123ec34ad7',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'edit',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'prefix',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-P',
  -                                     '--prefix',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'edit',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'id',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '05d08359fdcfa908',
                            'hidden': False,
  +                         'description_digest': '4a82c9123ec34ad7',
  -                         'mutex_groups': [],
  -                         'name': 'export',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'force',
  ?                                          ^^^^
  +                                 'dest': 'help',
  ?                                          ^ ++
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-F',
  -                                     '--force',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'metadata',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-P',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^^  ^^^ ^^^
  +                                     '--prefix',
  ? ++++                                 ^^^ ++ ^ ^
  -                                     '-m',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--metadata',
  ? ----                                 ^^^  ^^^^^
  +                                 'dest': 'prefix',
  ?                                  ^ + ^^^^^^^^^^
  -                                 ],
  ?                                 ^
  +                                 'takes_value': True,
  ?                                 ^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'out',
  ?                             ^^^^^^^^^^^^^^^^^
  +                             },
  ?                             ^
  -                                 'hidden': False,
  +                         ],
  +                         'positionals': [
  -                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^^
  +                             {
  ?                             ^
  -                                 'repeatable': False,
  -                                 'strings': [
  ?                                  ^  ----   ^
  +                                 'metavar': 'id',
  ?                                  ^^ +++    ^^^^^
  -                                     '-o',
  ? ----                                 ^^
  +                                 'dest': 'id',
  ?                                  ^^^^^^^^^^
  -                                     '--out',
  ? ----                                 ^^ ^^^
  +                                 'nargs': None,
  ?                                  ^^^^^^^^^ ^^
  -                                 ],
  ?                                 ^
  +                                 'choices': None,
  ?                                 ^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                  -- ^^^^^^^^   ^^^
  +                                 'kind': None,
  ?                                   ^^^   ^^^
  +                                 'is_remainder': False,
                                },
  -                             {
  ?                         ^^^^^
  +                         ],
  ?                         ^^
  +                         'subcommands': [],
  -                                 'choices': None,
  ? --------                           - ^^^
  +                         'default_child': None,
  ?                          ++++++++   ^^
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'export',
  -                                 'dest': 'sdd',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--sdd',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'export',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'id',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '7ee5afd000b4fa1f',
                            'hidden': False,
  +                         'description_digest': '05d08359fdcfa908',
  -                         'mutex_groups': [],
  -                         'name': 'list',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all',
  ?                                          ^ ^
  +                                 'dest': 'help',
  ?                                          ^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-a',
  -                                     '--all',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'cancelled',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-F',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^^ ^^^^ ^^^
  +                                     '--force',
  ? ++++                                 ^^^^ ^^ ^
  -                                     '-c',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--cancelled',
  ? ----                                 ^^^^^  ----
  +                                 'dest': 'force',
  ?                                  ^^^^^^^^^^^
  -                                 ],
  ?                                 ^
  +                                 'takes_value': False,
  ?                                 ^^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'json',
  ?                             ^^^^^^^^^^^^^^^^^^
  +                             },
  ?                             ^
  -                                 'hidden': False,
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-m',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^ ^^^^^ ^^^
  +                                     '--metadata',
  ? ++++                                 ^^^^ ^^^^^ ^
  -                                     '-j',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--json',
  ? ----                                 ^^^ ^^
  +                                 'dest': 'metadata',
  ?                                  ^^ ^^^^^^^^^^^^^
  -                                 ],
  ?                                 ^
  +                                 'takes_value': False,
  ?                                 ^^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'limit',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-o',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^ ----- ^^^
  +                                     '--out',
  ? ++++                                 ^^^^  ^
  -                                     '-l',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--limit',
  ? ----                                 ^^^^^^
  +                                 'dest': 'out',
  ?                                  ^^^^^^^^^^
  -                                 ],
  ?                                 ^
  +                                 'takes_value': True,
  ?                                 ^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                    ^^^^^^ -    ^^^
  +                                 'repeatable': False,
  ?                                  +++++  ^     ^^^^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'query',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-s',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                   ^^^^^^ ^^^
  +                                     '--sdd',
  ? ++++                                 ++ ^^ ^
  -                                     '-q',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--query',
  ? ----                                 ^^^^ ^^
  +                                 'dest': 'sdd',
  ?                                  ^ ^^^^^^^^^
  -                                 ],
  ?                                 ^
  +                                 'takes_value': False,
  ?                                 ^^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                    ^^^^^^ -    ^^^
  +                                 'repeatable': False,
  ?                                  +++++  ^     ^^^^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'id',
  +                                 'dest': 'id',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'list',
                            'path': [
                                'prompt',
                                'list',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '7ee5afd000b4fa1f',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--all',
  +                                 ],
  +                                 'dest': 'all',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--cancelled',
  +                                 ],
  +                                 'dest': 'cancelled',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-l',
  +                                     '--limit',
  +                                 ],
  +                                 'dest': 'limit',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-q',
  +                                     '--query',
  +                                 ],
  +                                 'dest': 'query',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'd421a1d36573fbc2',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'prune',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'before',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-b',
  -                                     '--before',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'cancelled',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-c',
  -                                     '--cancelled',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-d',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'keep',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-k',
  -                                     '--keep',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'yes',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-y',
  -                                     '--yes',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'prune',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'd421a1d36573fbc2',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-b',
  +                                     '--before',
  +                                 ],
  +                                 'dest': 'before',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--cancelled',
  +                                 ],
  +                                 'dest': 'cancelled',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-d',
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-k',
  +                                     '--keep',
  +                                 ],
  +                                 'dest': 'keep',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-y',
  +                                     '--yes',
  +                                 ],
  +                                 'dest': 'yes',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '5559f2599b695591',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'run',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'edit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-e',
  -                                     '--edit',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'prefix',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-P',
  -                                     '--prefix',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'run',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'id',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '92e4018bc97d51c5',
                            'hidden': False,
  +                         'description_digest': '5559f2599b695591',
  -                         'mutex_groups': [],
  -                         'name': 'save',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'description',
  ?                                          ^ ^^^^ ----
  +                                 'dest': 'help',
  ?                                          ^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-D',
  -                                     '--description',
  -                                 ],
  -                                 'takes_value': True,
  ?                                    ^^^^^^ -    ^^^
  +                                 'repeatable': False,
  ?                                  +++++  ^     ^^^^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'force',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^  -------
  +                                     '-e',
  ? ++++                                 ^
  -                                 'strings': [
  ?                                  ^ ----- ^^^
  +                                     '--edit',
  ? ++++                                 ^^^^^  ^
  -                                     '-F',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--force',
  ? ----                                 ^^^^^^
  +                                 'dest': 'edit',
  ?                                  ^ ++++++++++
  -                                 ],
  ?                                 ^
  +                                 'takes_value': False,
  ?                                 ^^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'global_',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-P',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^^  ^^^ ^^^
  +                                     '--prefix',
  ? ++++                                 ^^^ ++ ^ ^
  -                                     '-g',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--global',
  +                                 'dest': 'prefix',
  -                                 ],
  ?                                 ^
  +                                 'takes_value': True,
  ?                                 ^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'name',
  ?                             ^^^^^^^^^^^^^^^^^^
  +                             },
  ?                             ^
  -                                 'hidden': False,
  +                         ],
  +                         'positionals': [
  -                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^^
  +                             {
  ?                             ^
  -                                 'repeatable': False,
  -                                 'strings': [
  ?                                  ^  ----   ^
  +                                 'metavar': 'id',
  ?                                  ^^ +++    ^^^^^
  -                                     '-n',
  ? ----                                 ^^
  +                                 'dest': 'id',
  ?                                  ^^^^^^^^^^
  -                                     '--name',
  ? ----                                 --  ^ -
  +                                 'nargs': None,
  ?                                    ^^^^^^^^^
  -                                 ],
  ?                                 ^
  +                                 'choices': None,
  ?                                 ^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                  -- ^^^^^^^^   ^^^
  +                                 'kind': None,
  ?                                   ^^^   ^^^
  +                                 'is_remainder': False,
                                },
  -                             {
  ?                         ^^^^^
  +                         ],
  ?                         ^^
  +                         'subcommands': [],
  -                                 'choices': None,
  ? --------                           - ^^^
  +                         'default_child': None,
  ?                          ++++++++   ^^
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'save',
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'tag',
  -                                 'hidden': False,
  -                                 'kind': 'tag',
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-t',
  -                                     '--tag',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'save',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'id',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '424785ece3bf4499',
                            'hidden': False,
  +                         'description_digest': '92e4018bc97d51c5',
  -                         'mutex_groups': [],
  -                         'name': 'search',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'after',
  ?                                          ^^^ ^
  +                                 'dest': 'help',
  ?                                          ^ ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-D',
  +                                     '--description',
  +                                 ],
  +                                 'dest': 'description',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-F',
  +                                     '--force',
  +                                 ],
  +                                 'dest': 'force',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-g',
  +                                     '--global',
  +                                 ],
  +                                 'dest': 'global_',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--name',
  +                                 ],
  +                                 'dest': 'name',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--tag',
  +                                 ],
  +                                 'dest': 'tag',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': 'tag',
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'id',
  +                                 'dest': 'id',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'search',
  +                         'path': [
  +                             'prompt',
  +                             'search',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '424785ece3bf4499',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-a',
                                        '--after',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'before',
  ?                                          ^ -- -
  +                                 'dest': 'after',
  ?                                          ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-b',
                                        '--before',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^  ------
  +                                 'dest': 'before',
  ?                                  ^  ^^^^^^^^^^
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--color',
  +                                 ],
  +                                 'dest': 'color',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'auto',
                                        'always',
                                        'never',
                                    ],
  -                                 'dest': 'color',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-c',
  -                                     '--color',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'compact',
                                        'json',
                                        'full',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'limit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-n',
                                        '--limit',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^^^^
  +                                 'dest': 'limit',
  ?                                  ^  ^   ^^^^^^^
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--source',
  +                                 ],
  +                                 'dest': 'source',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'archive',
                                        'local',
                                        'all',
                                        'sdd',
                                    ],
  -                                 'dest': 'source',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-s',
  -                                     '--source',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'tag',
  -                                 'hidden': False,
  -                                 'kind': 'tag',
  -                                 'repeatable': True,
                                    'strings': [
                                        '-t',
                                        '--tag',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'cancelled',
  ?                                          ^ ^^^^^^^
  +                                 'dest': 'tag',
  ?                                          ^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': 'tag',
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-x',
                                        '--cancelled',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^  ^
  +                                 'dest': 'cancelled',
  ?                                  ^  ^   ^^ +++ ^ ++
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'prompt',
  -                             'search',
  ?                              ----
  +                                 'choices': None,
  ? ++++                               +++++ ++++++
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^
  +                                 'metavar': 'query',
  ?                                  ^ ^^^^^   ^^^ +++
                                    'dest': 'query',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
                                    'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'query',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '6d3b1efb3803db3a',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'select',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-a',
  -                                     '--all',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'cancelled',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-c',
  -                                     '--cancelled',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'edit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-e',
  -                                     '--edit',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'prefix',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-P',
  -                                     '--prefix',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'query',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-q',
  -                                     '--query',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'select',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '6d3b1efb3803db3a',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--all',
  +                                 ],
  +                                 'dest': 'all',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--cancelled',
  +                                 ],
  +                                 'dest': 'cancelled',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-e',
  +                                     '--edit',
  +                                 ],
  +                                 'dest': 'edit',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-P',
  +                                     '--prefix',
  +                                 ],
  +                                 'dest': 'prefix',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-q',
  +                                     '--query',
  +                                 ],
  +                                 'dest': 'query',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                        {
  +                         'name': 'show',
  +                         'path': [
  +                             'prompt',
  +                             'show',
  +                         ],
                            'aliases': [],
  -                         'default_child': None,
  +                         'hidden': False,
                            'description_digest': 'd6624ccbc5cbb79e',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'show',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'raw',
                                        'markdown',
                                        'json',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
  -                         ],
  -                         'path': [
  -                             'prompt',
  -                             'show',
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^^
  +                                 'metavar': 'id',
  ?                                  ^ ^^^^^   ^^^^
                                    'dest': 'id',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
                                    'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'id',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '279717294cc14aa5',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'stats',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'prompt',
                                'stats',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '279717294cc14aa5',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'questions',
  +                 'path': [
  +                     'questions',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  +                 'hidden': False,
                    'description_digest': 'd6b4b1e3ce956d7d',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'questions',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'questions',
                    ],
                    'positionals': [
                        {
  +                         'metavar': 'questions_json',
  +                         'dest': 'questions_json',
  +                         'nargs': None,
                            'choices': None,
  -                         'dest': 'questions_json',
  +                         'kind': None,
                            'is_remainder': False,
  -                         'kind': None,
  -                         'metavar': 'questions_json',
  -                         'nargs': None,
                        },
                    ],
                    'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'repo',
  +                 'path': [
  +                     'repo',
  +                 ],
                    'aliases': [],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': '85529381d79bf076',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'repo',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'repo',
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '3db73d01f04b029e',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'init',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'check',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-c',
  -                                     '--check',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'diff',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-d',
  -                                     '--diff',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'no_commit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-C',
  -                                     '--no-commit',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'repo',
                                'init',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '3db73d01f04b029e',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--check',
  +                                 ],
  +                                 'dest': 'check',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-d',
  +                                     '--diff',
  +                                 ],
  +                                 'dest': 'diff',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-C',
  +                                     '--no-commit',
  +                                 ],
  +                                 'dest': 'no_commit',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '8aaeac39b58aabf8',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'list',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all_projects',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-a',
  -                                     '--all',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'workspace',
  -                                 'hidden': False,
  -                                 'kind': 'workspace',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-w',
  -                                     '--workspace',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'repo',
                                'list',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '8aaeac39b58aabf8',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--all',
  +                                 ],
  +                                 'dest': 'all_projects',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-w',
  +                                     '--workspace',
  +                                 ],
  +                                 'dest': 'workspace',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'workspace',
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '9a774aedbe126754',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'log',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'agent',
  -                                 'hidden': False,
  -                                 'kind': 'agent',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-a',
  -                                     '--agent',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-i',
  -                                     '--id',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'repo',
  -                                 'hidden': False,
  -                                 'kind': 'repo',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-r',
  -                                     '--repo',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'workspace',
  -                                 'hidden': False,
  -                                 'kind': 'workspace',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-w',
  -                                     '--workspace',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'repo',
                                'log',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '9a774aedbe126754',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--agent',
  +                                 ],
  +                                 'dest': 'agent',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'agent',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-i',
  +                                     '--id',
  +                                 ],
  +                                 'dest': 'id',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-r',
  +                                     '--repo',
  +                                 ],
  +                                 'dest': 'repo',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'repo',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-w',
  +                                     '--workspace',
  +                                 ],
  +                                 'dest': 'workspace',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'workspace',
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '476d1409a389f41a',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'open',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'reason',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-r',
  -                                     '--reason',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'workspace',
  -                                 'hidden': False,
  -                                 'kind': 'workspace',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-w',
  -                                     '--workspace',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'repo',
                                'open',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'repo',
  -                                 'is_remainder': False,
  -                                 'kind': 'repo',
  -                                 'metavar': 'REPO',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '63e1643eed5af844',
                            'hidden': False,
  +                         'description_digest': '476d1409a389f41a',
  -                         'mutex_groups': [],
  -                         'name': 'path',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'ensure',
  ?                                           ^^^^^
  +                                 'dest': 'help',
  ?                                          + ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-e',
  -                                     '--ensure',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  +                             },
  +                             {
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
                                    'strings': [
                                        '-p',
                                        '--project',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'workspace',
  ?                                          ^ ^^^^^ ^
  +                                 'dest': 'project',
  ?                                          ^^ ^^ ^
  -                                 'hidden': False,
  -                                 'kind': 'workspace',
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-r',
  +                                     '--reason',
  +                                 ],
  +                                 'dest': 'reason',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-w',
                                        '--workspace',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^ ^^  ------
  +                                 'dest': 'workspace',
  ?                                  ^  ^^^^^^^^^^^ ^
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'workspace',
  +                                 'hidden': False,
                                },
                            ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'REPO',
  +                                 'dest': 'repo',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'repo',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'path',
                            'path': [
                                'repo',
                                'path',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '63e1643eed5af844',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-e',
  +                                     '--ensure',
  +                                 ],
  +                                 'dest': 'ensure',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-w',
  +                                     '--workspace',
  +                                 ],
  +                                 'dest': 'workspace',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'workspace',
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^^
  +                                 'metavar': 'REPO',
  ?                                  ^ ^^^^^   ^^^^^^
                                    'dest': 'repo',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'repo',
                                    'is_remainder': False,
  -                                 'kind': 'repo',
  -                                 'metavar': 'REPO',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'repro',
  +                 'path': [
  +                     'repro',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  +                 'hidden': False,
                    'description_digest': '1a8978a39657dfb0',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'repro',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'repro',
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '1e940e0642085652',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'capture',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'repro',
                                'capture',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '1e940e0642085652',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [
                                {
  +                                 'name': 'agents-tab',
  +                                 'path': [
  +                                     'repro',
  +                                     'capture',
  +                                     'agents-tab',
  +                                 ],
                                    'aliases': [],
  -                                 'default_child': None,
  ?                                    ^^^^^^^^^^^   ^^^
  +                                 'hidden': False,
  ?                                  +++  ^   ^^^^
                                    'description_digest': '2e179e92c6d2ba0a',
  -                                 'hidden': False,
  -                                 'mutex_groups': [],
  -                                 'name': 'agents-tab',
                                    'options': [
                                        {
  -                                         'choices': None,
  -                                         'dest': 'help',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '-h',
                                                '--help',
                                            ],
  +                                         'dest': 'help',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'output',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '--output',
                                            ],
  +                                         'dest': 'output',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'commit_safe',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '--commit-safe',
                                            ],
  +                                         'dest': 'commit_safe',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'commit_safe',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '--no-commit-safe',
                                            ],
  +                                         'dest': 'commit_safe',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'size',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '--size',
                                            ],
  +                                         'dest': 'size',
                                            'takes_value': True,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
                                        {
  -                                         'choices': None,
  -                                         'dest': 'json',
  -                                         'hidden': False,
  -                                         'kind': None,
  -                                         'repeatable': False,
                                            'strings': [
                                                '--json',
                                            ],
  +                                         'dest': 'json',
                                            'takes_value': False,
  +                                         'repeatable': False,
  +                                         'choices': None,
  +                                         'kind': None,
  +                                         'hidden': False,
                                        },
  -                                 ],
  -                                 'path': [
  -                                     'repro',
  -                                     'capture',
  -                                     'agents-tab',
                                    ],
                                    'positionals': [],
                                    'subcommands': [],
  +                                 'default_child': None,
  +                                 'mutex_groups': [],
                                },
                            ],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '5c5b3521a85fc6d2',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'replay',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'assert_stable',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '--assert-stable',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'write_artifacts',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '--write-artifacts',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'size',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '--size',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'repro',
                                'replay',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '5c5b3521a85fc6d2',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '--assert-stable',
  +                                 ],
  +                                 'dest': 'assert_stable',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '--write-artifacts',
  +                                 ],
  +                                 'dest': 'write_artifacts',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '--size',
  +                                 ],
  +                                 'dest': 'size',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^^
  +                                 'metavar': 'path',
  ?                                  ^ ^^^^^   ^^^^^^
                                    'dest': 'path',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': None,
                                    'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'path',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'restore',
  +                 'path': [
  +                     'restore',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  +                 'hidden': False,
                    'description_digest': '20957463fc578d25',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'restore',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'list',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-l',
                                '--list',
                            ],
  +                         'dest': 'list',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'restore',
                    ],
                    'positionals': [
                        {
  +                         'metavar': 'name',
  +                         'dest': 'name',
  +                         'nargs': '?',
                            'choices': None,
  -                         'dest': 'name',
  ?                           ---    ^ ^^
  +                         'kind': 'patch',
  ?                          +++     ^ ^^^
                            'is_remainder': False,
  -                         'kind': 'patch',
  -                         'metavar': 'name',
  -                         'nargs': '?',
                        },
                    ],
                    'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'revert',
  +                 'path': [
  +                     'revert',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  +                 'hidden': False,
                    'description_digest': '98ee7a70311c0c3b',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'revert',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'revert',
                    ],
                    'positionals': [
                        {
  +                         'metavar': 'name',
  +                         'dest': 'name',
  +                         'nargs': None,
                            'choices': None,
  -                         'dest': 'name',
  ?                           ---    ^ ^^
  +                         'kind': 'patch',
  ?                          +++     ^ ^^^
                            'is_remainder': False,
  -                         'kind': 'patch',
  -                         'metavar': 'name',
  -                         'nargs': None,
                        },
                    ],
                    'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'revive-log',
  +                 'path': [
  +                     'revive-log',
  +                 ],
                    'aliases': [],
  +                 'hidden': False,
  +                 'description_digest': 'd1b40f43c88b11c9',
  +                 'options': [
  +                     {
  +                         'strings': [
  +                             '-h',
  +                             '--help',
  +                         ],
  +                         'dest': 'help',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '--all',
  +                         ],
  +                         'dest': 'all',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '--limit',
  +                         ],
  +                         'dest': 'limit',
  +                         'takes_value': True,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '--since',
  +                         ],
  +                         'dest': 'since',
  +                         'takes_value': True,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '--outcome',
  +                         ],
  +                         'dest': 'outcome',
  +                         'takes_value': True,
  +                         'repeatable': False,
  +                         'choices': [
  +                             'success',
  +                             'failure',
  +                         ],
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '--json',
  +                         ],
  +                         'dest': 'as_json',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '--jsonl',
  +                         ],
  +                         'dest': 'as_json',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                 ],
  +                 'positionals': [],
  +                 'subcommands': [],
                    'default_child': None,
  -                 'description_digest': 'd1b40f43c88b11c9',
  -                 'hidden': False,
                    'mutex_groups': [
                        [
                            'as_json',
                            'as_json',
                        ],
                    ],
  +             },
  +             {
  -                 'name': 'revive-log',
  ?                           ^^^^^^^^^
  +                 'name': 'run',
  ?                           ^^
  +                 'path': [
  +                     'run',
  +                 ],
  +                 'aliases': [],
  +                 'hidden': False,
  +                 'description_digest': '8e81df2a31e3ce63',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'all',
  -                         'hidden': False,
                            'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '-Q',
  +                             '--request-path',
  +                         ],
  +                         'dest': 'operation_request_path',
  +                         'takes_value': True,
                            'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
                            'strings': [
  -                             '--all',
  ?                               ^^^^
  +                             '-R',
  ?                               ^
  +                             '--result-path',
                            ],
  +                         'dest': 'operation_result_path',
  -                         'takes_value': False,
  ?                                        ^^^^
  +                         'takes_value': True,
  ?                                        ^^^
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'limit',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  -                         'strings': [
  -                             '--limit',
  -                         ],
  -                         'takes_value': True,
                        },
  -                     {
  ?                 ^^^^^
  +                 ],
  ?                 ^^
  +                 'positionals': [
  +                     {
  +                         'metavar': 'PROMPT',
  +                         'dest': 'prompt',
  +                         'nargs': '?',
                            'choices': None,
  -                         'dest': 'since',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                            ^ ^^^^^^
  +                         'is_remainder': False,
  ?                          +++  ^^^^^ ^
  -                         'strings': [
  -                             '--since',
  -                         ],
  -                         'takes_value': True,
  -                     },
  -                     {
  -                         'choices': [
  -                             'success',
  -                             'failure',
  -                         ],
  -                         'dest': 'outcome',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '--outcome',
  -                         ],
  -                         'takes_value': True,
  -                     },
  -                     {
  -                         'choices': None,
  -                         'dest': 'as_json',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '--json',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                     {
  -                         'choices': None,
  -                         'dest': 'as_json',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '--jsonl',
  -                         ],
  -                         'takes_value': False,
                        },
                    ],
  -                 'path': [
  -                     'revive-log',
  -                 ],
  -                 'positionals': [],
                    'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'skill',
  +                 'path': [
  +                     'skill',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  -                 'description_digest': '8e81df2a31e3ce63',
                    'hidden': False,
  +                 'description_digest': '19345301604bc58d',
  -                 'mutex_groups': [],
  -                 'name': 'run',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'operation_request_path',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-Q',
  -                             '--request-path',
  -                         ],
  -                         'takes_value': True,
  -                     },
  -                     {
  -                         'choices': None,
  -                         'dest': 'operation_result_path',
                            'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-R',
  -                             '--result-path',
  -                         ],
  -                         'takes_value': True,
                        },
                    ],
  -                 'path': [
  ?                    ^^
  +                 'positionals': [],
  ?                   +++++++ ^^    ++
  +                 'subcommands': [
  -                     'run',
  ?                     ^^^^^^
  +                     {
  ?                     ^
  +                         'name': 'init',
  +                         'path': [
  +                             'skill',
  +                             'init',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '1169916db1d96e98',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-D',
  +                                     '--allow-dirty',
  +                                 ],
  +                                 'dest': 'allow_dirty',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--check',
  +                                 ],
  +                                 'dest': 'check',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-d',
  +                                     '--diff',
  +                                 ],
  +                                 'dest': 'diff',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--force',
  +                                 ],
  +                                 'dest': 'force',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-A',
  +                                     '--no-apply',
  +                                 ],
  +                                 'dest': 'no_apply',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-C',
  +                                     '--no-commit',
  +                                 ],
  +                                 'dest': 'no_commit',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-P',
  +                                     '--no-push',
  +                                 ],
  +                                 'dest': 'no_push',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--provider',
  +                                 ],
  +                                 'dest': 'provider',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-y',
  +                                     '--yes',
  +                                 ],
  +                                 'dest': 'yes',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'list',
  +                         'path': [
  +                             'skill',
  +                             'list',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '6abdb7995ba879e0',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'log',
  +                         'path': [
  +                             'skill',
  +                             'log',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '0784784eb90009b4',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--agent',
  +                                 ],
  +                                 'dest': 'agent',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'agent',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-i',
  +                                     '--id',
  +                                 ],
  +                                 'dest': 'id',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--runtime',
  +                                 ],
  +                                 'dest': 'runtime',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--skill',
  +                                 ],
  +                                 'dest': 'skill',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'skill',
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'use',
  +                         'path': [
  +                             'skill',
  +                             'use',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'a01b0cb94e1daa0e',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-r',
  +                                     '--reason',
  +                                 ],
  +                                 'dest': 'reason',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'skill-name',
  +                                 'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'skill',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
                    ],
  +                 'default_child': 'list',
  -                 'positionals': [
  -                     {
  -                         'choices': None,
  -                         'dest': 'prompt',
  -                         'is_remainder': False,
  -                         'kind': None,
  -                         'metavar': 'PROMPT',
  -                         'nargs': '?',
  -                     },
  -                 ],
  -                 'subcommands': [],
  ?                  ^ ^^ ^^^^^
  +                 'mutex_groups': [],
  ?                  ^ ^^^^^^ ^^
                },
                {
  +                 'name': 'stitch',
  -                 'aliases': [],
  ?                   ^^^^^^    --
  +                 'path': [
  ?                  + ^^
  -                 'default_child': 'list',
  -                 'description_digest': '19345301604bc58d',
  +                     'stitch',
  +                 ],
  +                 'aliases': [
  +                     'vcs',
  +                 ],
                    'hidden': False,
  +                 'description_digest': '5e068494b4e6409d',
  -                 'mutex_groups': [],
  -                 'name': 'skill',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  -                     },
  -                 ],
  -                 'path': [
  -                     'skill',
  ?                      -  ^^
  +                         'kind': None,
  ? ++++                       ^^ ++++++
  +                         'hidden': False,
  +                     },
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  +                         'name': 'create',
  +                         'path': [
  +                             'stitch',
  +                             'create',
  +                         ],
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '1169916db1d96e98',
                            'hidden': False,
  +                         'description_digest': '0ca5493099850810',
  -                         'mutex_groups': [],
  -                         'name': 'init',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'allow_dirty',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-D',
  -                                     '--allow-dirty',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'check',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-c',
  -                                     '--check',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'diff',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-d',
  -                                     '--diff',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-n',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'force',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-f',
  -                                     '--force',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'no_apply',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-A',
  -                                     '--no-apply',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'no_commit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-C',
  -                                     '--no-commit',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'no_push',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-P',
  -                                     '--no-push',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'provider',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--provider',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'yes',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-y',
  -                                     '--yes',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'skill',
  -                             'init',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '6abdb7995ba879e0',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'list',
  -                         'options': [
  -                             {
  -                                 'choices': None,
                                    'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
                                    'takes_value': False,
  +                                 'repeatable': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'skill',
  -                             'list',
  ?                              ^  -
  +                                 'choices': None,
  ? ++++                             ^^^ ++  ++++++
  +                                 'kind': None,
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  ?                     ^^
  +                             {
  ?                     ^^^^^^^^^
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '0784784eb90009b4',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'log',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'agent',
  -                                 'hidden': False,
  -                                 'kind': 'agent',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-a',
  -                                     '--agent',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'id',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-i',
  -                                     '--id',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'runtime',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-R',
  -                                     '--runtime',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'skill',
  -                                 'hidden': False,
  -                                 'kind': 'skill',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--skill',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'skill',
  -                             'log',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'a01b0cb94e1daa0e',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'use',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'reason',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-r',
  -                                     '--reason',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'skill',
  -                             'use',
  -                         ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'is_remainder': False,
  -                                 'kind': 'skill',
  -                                 'metavar': 'skill-name',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                 ],
  -             },
  -             {
  -                 'aliases': [
  -                     'vcs',
  -                 ],
  -                 'default_child': 'list',
  -                 'description_digest': '5e068494b4e6409d',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'stitch',
  -                 'options': [
  -                     {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-h',
  -                             '--help',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                 ],
  -                 'path': [
  -                     'stitch',
  -                 ],
  -                 'positionals': [],
  -                 'subcommands': [
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '0ca5493099850810',
  -                         'hidden': False,
  -                         'mutex_groups': [
  -                             [
  -                                 'message',
  -                                 'message_file',
  -                             ],
  -                         ],
  -                         'name': 'create',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'message',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-m',
                                        '--message',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'message_file',
  ?                                                 -----
  +                                 'dest': 'message',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-M',
                                        '--message-file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'file',
  +                                 'dest': 'message_file',
  ?                                          ++++++++
  -                                 'hidden': True,
  ?                                  ^^^^ ^
  +                                 'takes_value': True,
  ?                                  ^^^ ^^^^^^^
  -                                 'kind': None,
                                    'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-f',
                                        '--file',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'exclude',
  ?                                          ^^^ --
  +                                 'dest': 'file',
  ?                                          ^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': True,
  ?                                  -----  ^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': True,
  +                             },
  +                             {
                                    'strings': [
                                        '-x',
                                        '--exclude',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  ?                                  ^^^^^     ^^^
  +                                 'dest': 'exclude',
  ?                                  ^  +   ^ +++++++
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '--only-file',
  +                                 ],
                                    'dest': 'only_files',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
                                    'hidden': True,
  -                                 'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '--only-file',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'name',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-n',
                                        '--name',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'bug_id',
  ?                                          ^^^^^^
  +                                 'dest': 'name',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-b',
                                        '--bug-id',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'do_not_close_bead',
  ?                                          ^^ ^^^^^^^^^^^^^
  +                                 'dest': 'bug_id',
  ?                                          ^^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-B',
                                        '--do-not-close-bead',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'checkout_target',
  ?                                          ^^^^^ ^  ^ ^^^^
  +                                 'dest': 'do_not_close_bead',
  ?                                          ^ ^^^  ^^^^^^^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-c',
                                        '--checkout-target',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'parent',
  ?                                          ^   -
  +                                 'dest': 'checkout_target',
  ?                                          ^^^^^^^^^^  +
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--parent',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^ -
  +                                 'dest': 'parent',
  ?                                  ^  ^   ^^^  +++
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--status',
  +                                 ],
  +                                 'dest': 'status',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'wip',
                                        'draft',
                                        'ready',
                                    ],
  -                                 'dest': 'status',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-s',
  -                                     '--status',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--type',
  +                                 ],
  +                                 'dest': 'method',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'create_commit',
                                        'create_proposal',
                                        'create_pull_request',
                                        'commit',
                                        'propose',
                                        'pr',
                                    ],
  -                                 'dest': 'method',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-t',
  -                                     '--type',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'resume',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-r',
                                        '--resume',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^   -------
  +                                 'dest': 'resume',
  ?                                  ^  ^^^^^^^^ +
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  ?                         ^
  +                             },
  ?                         ^^^^^
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [
  +                             [
  +                                 'message',
  +                                 'message_file',
  +                             ],
  +                         ],
  +                     },
  +                     {
  +                         'name': 'list',
                            'path': [
                                'stitch',
  -                             'create',
  ?                              ^^^^ -
  +                             'list',
  ?                              ^^^
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'a60bfb1f8a646269',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--all',
  +                                 ],
  +                                 'dest': 'all',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-A',
  +                                     '--author',
  +                                 ],
  +                                 'dest': 'authors',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-b',
  +                                     '--branch',
  +                                     '--ref',
  +                                 ],
  +                                 'dest': 'remote_ref',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--color',
  +                                 ],
  +                                 'dest': 'color',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'auto',
  +                                     'always',
  +                                     'never',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-o',
  +                                     '--current-only',
  +                                 ],
  +                                 'dest': 'current_only',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-F',
  +                                     '--fetch',
  +                                 ],
  +                                 'dest': 'force_fetch',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'pretty',
  +                                     'full',
  +                                     'oneline',
  +                                     'json',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--limit',
  +                                 ],
  +                                 'dest': 'limit',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-m',
  +                                     '--merges',
  +                                 ],
  +                                 'dest': 'merges',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'hide',
  +                                     'show',
  +                                     'only',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-N',
  +                                     '--no-fetch',
  +                                 ],
  +                                 'dest': 'no_fetch',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-T',
  +                                     '--no-tags',
  +                                 ],
  +                                 'dest': 'show_tags',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '--origin',
  +                                 ],
  +                                 'dest': 'origins',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': [
  +                                     'stitch',
  +                                     'auto',
  +                                     'manual',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-r',
  +                                     '--repo',
  +                                 ],
  +                                 'dest': 'repos',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-R',
  +                                     '--reverse',
  +                                 ],
  +                                 'dest': 'reverse',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-S',
  +                                     '--sdd',
  +                                 ],
  +                                 'dest': 'sdd',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--since',
  +                                     '--after',
  +                                 ],
  +                                 'dest': 'since',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--tags',
  +                                 ],
  +                                 'dest': 'show_tags',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': True,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-u',
  +                                     '--until',
  +                                     '--before',
  +                                 ],
  +                                 'dest': 'until',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'a60bfb1f8a646269',
  -                         'hidden': False,
                            'mutex_groups': [
                                [
                                    'all',
                                    'current_only',
                                ],
                                [
                                    'force_fetch',
                                    'no_fetch',
                                ],
                            ],
  +                     },
  +                 ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
  +             },
  +             {
  -                         'name': 'list',
  ? --------                          ^^
  +                 'name': 'telemetry',
  ?                          ++ ^^^ ++
  +                 'path': [
  +                     'telemetry',
  +                 ],
  +                 'aliases': [],
  +                 'hidden': False,
  +                 'description_digest': '1bdffe5c36996796',
  +                 'options': [
  +                     {
  +                         'strings': [
  +                             '-h',
  +                             '--help',
  +                         ],
  +                         'dest': 'help',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                 ],
  +                 'positionals': [],
  +                 'subcommands': [
  +                     {
  +                         'name': 'cleanup-test-data',
  +                         'path': [
  +                             'telemetry',
  +                             'cleanup-test-data',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '55a5a83a28ac3455',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all',
  ?                                          ^ ^
  +                                 'dest': 'help',
  ?                                          ^^ ^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-a',
  -                                     '--all',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'authors',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': True,
  ?                                  ^^^^^^^^^^ ------
  +                                     '-n',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^^ ^ -- ^^^
  +                                     '--dry-run',
  ? ++++                                 ^^^ ^^^^  ^
  -                                     '-A',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--author',
  +                                 'dest': 'dry_run',
  -                                 ],
  ?                                 ^
  +                                 'takes_value': False,
  ?                                 ^^^^^^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                    ^^^^^^ -    ^^^
  +                                 'repeatable': False,
  ?                                  +++++  ^     ^^^^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  -                             {
  -                                 'choices': None,
  ?                                  - - ^ ^   ^^^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^
  -                                 'dest': 'remote_ref',
  -                                 'hidden': False,
  +                             },
  +                             {
  -                                 'kind': None,
  ?                                  ^  ^   ^^^^^
  +                                 'strings': [
  ?                                  ^^^  ^^   ^
  -                                 'repeatable': False,
  ?                                  ^^^^^^^^^^ -------
  +                                     '-y',
  ? ++++                                 ^^
  -                                 'strings': [
  ?                                  ^^^^^^  ^^^
  +                                     '--yes',
  ? ++++                                 ^^^^  ^
  -                                     '-b',
  ?                                 ^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                     '--branch',
  ? ----                                 ^^^^^^^^
  +                                 'dest': 'yes',
  ?                                  ^^^^^^^^^^^
  +                                 'takes_value': False,
  -                                     '--ref',
  ? ----                                 --  ^
  +                                 'repeatable': False,
  ?                                    ^^^^^^^^ +++++++
  -                                 ],
  ?                                 ^
  +                                 'choices': None,
  ?                                 ^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                  -- ^^^^^^^^   ^^^
  +                                 'kind': None,
  ?                                   ^^^   ^^^
  +                                 'hidden': False,
                                },
  -                             {
  ?                         ^^^^^
  +                         ],
  ?                         ^^
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'health',
  +                         'path': [
  +                             'telemetry',
  +                             'health',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'b4202720db03a622',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'list',
  +                         'path': [
  +                             'telemetry',
  +                             'list',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '40b68c75d0282a90',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--subsystem',
  +                                 ],
  +                                 'dest': 'subsystem',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--type',
  +                                 ],
  +                                 'dest': 'type',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'counter',
  +                                     'gauge',
  +                                     'histogram',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'snapshot',
  +                         'path': [
  +                             'telemetry',
  +                             'snapshot',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'acb506d4b79b3f56',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'json',
  +                                     'rich',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--subsystem',
  +                                 ],
  +                                 'dest': 'subsystem',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'status',
  +                         'path': [
  +                             'telemetry',
  +                             'status',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '1af6544e75fa61f1',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                 ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
  +             },
  +             {
  +                 'name': 'update',
  +                 'path': [
  +                     'update',
  +                 ],
  +                 'aliases': [],
  +                 'hidden': False,
  +                 'description_digest': '45e94691d6fe1ec0',
  +                 'options': [
  +                     {
  +                         'strings': [
  +                             '-h',
  +                             '--help',
  +                         ],
  +                         'dest': 'help',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '-j',
  +                             '--json',
  +                         ],
  +                         'dest': 'json',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '-n',
  +                             '--dry-run',
  +                         ],
  +                         'dest': 'dry_run',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '-q',
  +                             '--quiet',
  +                         ],
  +                         'dest': 'quiet',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '-t',
  +                             '--to',
  +                         ],
  +                         'dest': 'to',
  +                         'takes_value': True,
  +                         'repeatable': False,
  +                         'choices': [
  +                             'dev',
  +                             'pypi',
  +                         ],
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                     {
  +                         'strings': [
  +                             '-y',
  +                             '--yes',
  +                         ],
  +                         'dest': 'yes',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                 ],
  +                 'positionals': [],
  +                 'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
  +             },
  +             {
  +                 'name': 'validate',
  +                 'path': [
  +                     'validate',
  +                 ],
  +                 'aliases': [],
  +                 'hidden': False,
  +                 'description_digest': 'bc512bb3e6eb9104',
  +                 'options': [
  +                     {
  +                         'strings': [
  +                             '-h',
  +                             '--help',
  +                         ],
  +                         'dest': 'help',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                 ],
  +                 'positionals': [],
  +                 'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
  +             },
  +             {
  +                 'name': 'var',
  +                 'path': [
  +                     'var',
  +                 ],
  +                 'aliases': [],
  +                 'hidden': False,
  +                 'description_digest': 'dc164d89ea6f01e1',
  +                 'options': [
  +                     {
  +                         'strings': [
  +                             '-h',
  +                             '--help',
  +                         ],
  +                         'dest': 'help',
  +                         'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
  +                     },
  +                 ],
  +                 'positionals': [],
  +                 'subcommands': [
  +                     {
  +                         'name': 'get',
  +                         'path': [
  +                             'var',
  +                             'get',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '2f76f5ef93a5a3d8',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--color',
  +                                 ],
  +                                 'dest': 'color',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'auto',
                                        'always',
                                        'never',
                                    ],
  -                                 'dest': 'color',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-c',
  -                                     '--color',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'current_only',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-o',
  -                                     '--current-only',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'force_fetch',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-F',
  -                                     '--fetch',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': [
  -                                     'pretty',
  -                                     'full',
  -                                     'oneline',
  -                                     'json',
  -                                 ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-f',
                                        '--format',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'limit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-n',
  -                                     '--limit',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': [
  -                                     'hide',
  -                                     'show',
  -                                     'only',
  -                                 ],
  -                                 'dest': 'merges',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-m',
  -                                     '--merges',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'no_fetch',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-N',
  -                                     '--no-fetch',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'show_tags',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-T',
  -                                     '--no-tags',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': [
  -                                     'stitch',
  -                                     'auto',
  -                                     'manual',
  -                                 ],
  -                                 'dest': 'origins',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '--origin',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'repos',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-r',
  -                                     '--repo',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'reverse',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-R',
  -                                     '--reverse',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'sdd',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-S',
  -                                     '--sdd',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'since',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--since',
  -                                     '--after',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'show_tags',
  -                                 'hidden': True,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-t',
  -                                     '--tags',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'until',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-u',
  -                                     '--until',
  -                                     '--before',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'stitch',
  -                             'list',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                 ],
  -             },
  -             {
  -                 'aliases': [],
  -                 'default_child': 'list',
  -                 'description_digest': '1bdffe5c36996796',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'telemetry',
  -                 'options': [
  -                     {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-h',
  -                             '--help',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                 ],
  -                 'path': [
  -                     'telemetry',
  -                 ],
  -                 'positionals': [],
  -                 'subcommands': [
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '55a5a83a28ac3455',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'cleanup-test-data',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-n',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'yes',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-y',
  -                                     '--yes',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'telemetry',
  -                             'cleanup-test-data',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'b4202720db03a622',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'health',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'telemetry',
  -                             'health',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '40b68c75d0282a90',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'list',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'subsystem',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--subsystem',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': [
  -                                     'counter',
  -                                     'gauge',
  -                                     'histogram',
  -                                 ],
  -                                 'dest': 'type',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-t',
  -                                     '--type',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'telemetry',
  -                             'list',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'acb506d4b79b3f56',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'snapshot',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': [
  -                                     'json',
  -                                     'rich',
  -                                 ],
                                    'dest': 'format',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
                                    'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'subsystem',
  ?                                  ^ ^    ^ ------ --
  +                                 'repeatable': False,
  ?                                  ^ ^^^ ++++   ^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--subsystem',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'telemetry',
  -                             'snapshot',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '1af6544e75fa61f1',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'status',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'telemetry',
  -                             'status',
  -                         ],
  -                         'positionals': [],
  -                         'subcommands': [],
  -                     },
  -                 ],
  -             },
  -             {
  -                 'aliases': [],
  -                 'default_child': None,
  -                 'description_digest': '45e94691d6fe1ec0',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'update',
  -                 'options': [
  -                     {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-h',
  -                             '--help',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                     {
  -                         'choices': None,
  -                         'dest': 'json',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-j',
  -                             '--json',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                     {
  -                         'choices': None,
  -                         'dest': 'dry_run',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-n',
  -                             '--dry-run',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                     {
  -                         'choices': None,
  -                         'dest': 'quiet',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-q',
  -                             '--quiet',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                     {
  -                         'choices': [
  -                             'dev',
  -                             'pypi',
  -                         ],
  -                         'dest': 'to',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-t',
  -                             '--to',
  -                         ],
  -                         'takes_value': True,
  -                     },
  -                     {
  -                         'choices': None,
  -                         'dest': 'yes',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-y',
  -                             '--yes',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                 ],
  -                 'path': [
  -                     'update',
  -                 ],
  -                 'positionals': [],
  -                 'subcommands': [],
  -             },
  -             {
  -                 'aliases': [],
  -                 'default_child': None,
  -                 'description_digest': 'bc512bb3e6eb9104',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'validate',
  -                 'options': [
  -                     {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-h',
  -                             '--help',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                 ],
  -                 'path': [
  -                     'validate',
  -                 ],
  -                 'positionals': [],
  -                 'subcommands': [],
  -             },
  -             {
  -                 'aliases': [],
  -                 'default_child': 'list',
  -                 'description_digest': 'dc164d89ea6f01e1',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'var',
  -                 'options': [
  -                     {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
  -                         'strings': [
  -                             '-h',
  -                             '--help',
  -                         ],
  -                         'takes_value': False,
  -                     },
  -                 ],
  -                 'path': [
  -                     'var',
  -                 ],
  -                 'positionals': [],
  -                 'subcommands': [
  -                     {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '2f76f5ef93a5a3d8',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'get',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': [
  -                                     'auto',
  -                                     'always',
  -                                     'never',
  -                                 ],
  -                                 'dest': 'color',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-c',
  -                                     '--color',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
                                    'choices': [
                                        'pretty',
                                        'raw',
                                        'json',
                                        'jsonl',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-H',
  +                                     '--hidden',
  +                                 ],
  +                                 'dest': 'hidden',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--limit',
  +                                 ],
  +                                 'dest': 'limit',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'projects',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'TARGET',
  +                                 'dest': 'targets',
  +                                 'nargs': '*',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'list',
  +                         'path': [
  +                             'var',
  +                             'list',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'c8a246aa63a955f4',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--agent',
  +                                 ],
  +                                 'dest': 'agents',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--color',
  +                                 ],
  +                                 'dest': 'color',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'auto',
  +                                     'always',
  +                                     'never',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-f',
                                        '--format',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'hidden',
  ?                                          ^^^^^^
  +                                 'dest': 'format',
  ?                                          ^^^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'pretty',
  +                                     'json',
  +                                     'jsonl',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-H',
                                        '--hidden',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'limit',
  ?                                          ^ ^^^
  +                                 'dest': 'hidden',
  ?                                          ^ ^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-k',
  +                                     '--key',
  +                                 ],
  +                                 'dest': 'keys',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-n',
                                        '--limit',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'projects',
  ?                                          ^^^^^^ -
  +                                 'dest': 'limit',
  ?                                          ^^^^
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': True,
  ?                                  -----  ^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'var',
  -                             'get',
  -                         ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'targets',
  ?                                          ^^ ^
  +                                 'dest': 'projects',
  ?                                          ^ ^^ +
  -                                 'is_remainder': False,
  ?                                  ^  ^ -------   ^^^^
  +                                 'takes_value': True,
  ?                                  ^^^^  ^^^^    ^^^
  -                                 'kind': None,
  ?                                  ^^^^   ^^^
  +                                 'repeatable': True,
  ?                                  ^^^^^^^^^^   ^^^
  -                                 'metavar': 'TARGET',
  ?                                  ^ ^^^^^   ^^^^^^^^
  +                                 'choices': None,
  ?                                  ^^^^^ ^   ^^^^
  -                                 'nargs': '*',
  ?                                   ^^^^    ^
  +                                 'kind': 'project',
  ?                                  ++ ^    ^^^^^^^
  +                                 'hidden': False,
                                },
  -                         ],
  ?                         ^^
  +                             {
  ?                         ^^^^^
  +                                 'strings': [
  +                                     '-r',
  +                                     '--reverse',
  +                                 ],
  +                                 'dest': 'reverse',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--since',
  +                                 ],
  +                                 'dest': 'since',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-u',
  +                                     '--until',
  +                                 ],
  +                                 'dest': 'until',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-v',
  +                                     '--value',
  +                                 ],
  +                                 'dest': 'values',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-V',
  +                                     '--value-json',
  +                                 ],
  +                                 'dest': 'value_json',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'c8a246aa63a955f4',
  -                         'hidden': False,
                            'mutex_groups': [
                                [
                                    'values',
                                    'value_json',
                                ],
                            ],
  +                     },
  +                     {
  -                         'name': 'list',
  ?                                  --
  +                         'name': 'set',
  ?                                   +
  +                         'path': [
  +                             'var',
  +                             'set',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '5c76efb872621652',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'agents',
  ?                                          ^^ ^^^
  +                                 'dest': 'help',
  ?                                          ^ ^^
  -                                 'hidden': False,
  ?                                  ^^^^ ^
  +                                 'takes_value': False,
  ?                                  ^^^ ^^^^^^^
  -                                 'kind': None,
  -                                 'repeatable': True,
  ?                                               ^^^
  +                                 'repeatable': False,
  ?                                               ^^^^
  -                                 'strings': [
  ?                                  ^^^ ^^    ^
  +                                 'choices': None,
  ?                                  ^^^ ^^    ^^^^^
  -                                     '-a',
  -                                     '--agent',
  -                                 ],
  ?                                 ^
  +                                 'kind': None,
  ?                                 ^^^^^^^^^^^^
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': [
  ?                                  - - ^ ^   ^
  +                                 'hidden': False,
  ?                                    ^^ ^   ^^^^^^
  -                                     'auto',
  ?                             ^^^^^^^^^^^^^^
  +                             },
  ?                             ^
  -                                     'always',
  ?                             ^^^^^^^^^^^^^^^^^
  +                             {
  ?                             ^
  -                                     'never',
  ? ----                                  ^^^^ ^
  +                                 'strings': [
  ?                                  ++++ ^^ ^^^
  -                                 ],
  ?                                 ^
  +                                     '-j',
  ?                                 ^^^^^^^^
  -                                 'dest': 'color',
  ?                                  ^^ ------ ^^^
  +                                     '--json',
  ? ++++                                 ^^^  ^
  -                                 'hidden': False,
  ?                                 ^^^^^^^^^^^^^^^
  +                                 ],
  ?                                 ^
  -                                 'kind': None,
  ?                                  ---    ^  ^
  +                                 'dest': 'json',
  ?                                   +++   ^^^  ^
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  ?                                  ^ ^^^^^   ^
  +                                 'repeatable': False,
  ?                                  ^^^^^ ^^^^   ^^^^^^
  -                                     '-c',
  ? ----                                 -
  +                                 'choices': None,
  ?                                   ++++++ ++++++
  -                                     '--color',
  ? ----                                 ^^^ ^^^^
  +                                 'kind': None,
  ?                                  ^^^^^^^^ ^^
  -                                 ],
  ?                                 ^
  +                                 'hidden': False,
  ?                                 ^^^^^^^^^^^^^^^
  -                                 'takes_value': True,
  +                             },
  -                             },
  ?                             ^^
  +                             {
  ?                             ^
  -                             {
  -                                 'choices': [
  -                                     'pretty',
  -                                     'json',
  -                                     'jsonl',
  -                                 ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'hidden',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-H',
  -                                     '--hidden',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'keys',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-k',
  -                                     '--key',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'limit',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-n',
  -                                     '--limit',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'projects',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': True,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'reverse',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-r',
  -                                     '--reverse',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'since',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--since',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'until',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-u',
  -                                     '--until',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'values',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': True,
                                    'strings': [
                                        '-v',
                                        '--value',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'value_json',
  ?                                               -----
  +                                 'dest': 'value',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': True,
  ?                                  -----  ^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +
  -                                 'strings': [
  -                                     '-V',
  -                                     '--value-json',
  -                                 ],
  -                                 'takes_value': True,
  ?                                    ^^^^^^ -    ^^^
  +                                 'repeatable': False,
  ?                                  +++++  ^     ^^^^
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                         ],
  -                         'path': [
  -                             'var',
  ?                             ^^^^^
  +                             },
  ?                             ^
  -                             'list',
  ?                             ^^^^^^^
  +                             {
  ?                             ^
  +                                 'strings': [
  +                                     '-f',
  +                                     '--value-file',
  -                         ],
  +                                 ],
  ? ++++++++
  +                                 'dest': 'value_file',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  -                         'positionals': [],
  ?                         ----------------
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'KEY[=VALUE]',
  +                                 'dest': 'assignments',
  +                                 'nargs': '+',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '5c76efb872621652',
  -                         'hidden': False,
                            'mutex_groups': [
                                [
                                    'value',
                                    'value_file',
                                ],
                            ],
  -                         'name': 'set',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'value',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-v',
  -                                     '--value',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'value_file',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-f',
  -                                     '--value-file',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
  -                         'path': [
  -                             'var',
  -                             'set',
  -                         ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'assignments',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'KEY[=VALUE]',
  -                                 'nargs': '+',
  -                             },
  -                         ],
  -                         'subcommands': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'version',
  +                 'path': [
  +                     'version',
  +                 ],
                    'aliases': [],
  -                 'default_child': None,
  +                 'hidden': False,
                    'description_digest': '51d444d829e86b5b',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'version',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'json',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-j',
                                '--json',
                            ],
  +                         'dest': 'json',
                            'takes_value': False,
  +                         'repeatable': False,
  -                     },
  -                     {
                            'choices': None,
  -                         'dest': 'verbose',
  -                         'hidden': False,
                            'kind': None,
  -                         'repeatable': False,
  ?                          ^ ^^^^^^^^
  +                         'hidden': False,
  ?                          ^^^^ ^
  +                     },
  +                     {
                            'strings': [
                                '-v',
                                '--verbose',
                            ],
  +                         'dest': 'verbose',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'version',
                    ],
                    'positionals': [],
                    'subcommands': [],
  +                 'default_child': None,
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'workspace',
  +                 'path': [
  +                     'workspace',
  +                 ],
                    'aliases': [],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': '86726e171a979f8d',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'workspace',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'workspace',
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'b3f8748609e33ac7',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'cleanup',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'stale',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--stale',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'include_shares',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-i',
  -                                     '--include-shares',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-n',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'workspace',
                                'cleanup',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'b3f8748609e33ac7',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--stale',
  +                                 ],
  +                                 'dest': 'stale',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-i',
  +                                     '--include-shares',
  +                                 ],
  +                                 'dest': 'include_shares',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '7d2b63c30543f3b5',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'list',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'all_projects',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-a',
  -                                     '--all',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'json',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-j',
  -                                     '--json',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'workspace',
                                'list',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '7d2b63c30543f3b5',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--all',
  +                                 ],
  +                                 'dest': 'all_projects',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-j',
  +                                     '--json',
  +                                 ],
  +                                 'dest': 'json',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'f728d8ba4c734f80',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'migrate',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': [
  -                                     'xdg-state',
  -                                 ],
  -                                 'dest': 'to',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-t',
  -                                     '--to',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'symlink_transition',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-s',
  -                                     '--symlink-transition',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'finalize',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-f',
  -                                     '--finalize',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-n',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'workspace',
                                'migrate',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': 'f728d8ba4c734f80',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-t',
  +                                     '--to',
  +                                 ],
  +                                 'dest': 'to',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': [
  +                                     'xdg-state',
  +                                 ],
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-s',
  +                                     '--symlink-transition',
  +                                 ],
  +                                 'dest': 'symlink_transition',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--finalize',
  +                                 ],
  +                                 'dest': 'finalize',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '747bf3db53419f09',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'path',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-p',
  -                                     '--project',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'workspace',
                                'path',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'workspace_num',
  -                                 'is_remainder': False,
  -                                 'kind': 'workspace',
  -                                 'metavar': 'workspace_num',
  -                                 'nargs': None,
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '9b70441413727070',
                            'hidden': False,
  +                         'description_digest': '747bf3db53419f09',
  -                         'mutex_groups': [],
  -                         'name': 'repair',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'project',
  ?                                           ------
  +                                 'dest': 'help',
  ?                                          +++
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
  ?                                  -----  ^
  +                                 'takes_value': False,
  ?                                    ^^^^^^ +
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
                                    'strings': [
                                        '-p',
                                        '--project',
                                    ],
  -                                 'takes_value': True,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'dry_run',
  ?                                          ^ ^^^^^
  +                                 'dest': 'project',
  ?                                          ^ ^^^^^
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  ?                                  -----  ^     ^^^^
  +                                 'takes_value': True,
  ?                                    ^^^^^^ +    ^^^
  -                                 'strings': [
  -                                     '-n',
  -                                     '--dry-run',
  -                                 ],
  -                                 'takes_value': False,
  ?                                    ^^^^^^ -
  +                                 'repeatable': False,
  ?                                  +++++  ^
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
                                },
                            ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'workspace_num',
  +                                 'dest': 'workspace_num',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'workspace',
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'repair',
                            'path': [
                                'workspace',
                                'repair',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '9b70441413727070',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-p',
  +                                     '--project',
  +                                 ],
  +                                 'dest': 'project',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-n',
  +                                     '--dry-run',
  +                                 ],
  +                                 'dest': 'dry_run',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
                {
  +                 'name': 'xprompt',
  +                 'path': [
  +                     'xprompt',
  +                 ],
                    'aliases': [],
  -                 'default_child': 'list',
  +                 'hidden': False,
                    'description_digest': 'db5e0d689c55f907',
  -                 'hidden': False,
  -                 'mutex_groups': [],
  -                 'name': 'xprompt',
                    'options': [
                        {
  -                         'choices': None,
  -                         'dest': 'help',
  -                         'hidden': False,
  -                         'kind': None,
  -                         'repeatable': False,
                            'strings': [
                                '-h',
                                '--help',
                            ],
  +                         'dest': 'help',
                            'takes_value': False,
  +                         'repeatable': False,
  +                         'choices': None,
  +                         'kind': None,
  +                         'hidden': False,
                        },
  -                 ],
  -                 'path': [
  -                     'xprompt',
                    ],
                    'positionals': [],
                    'subcommands': [
                        {
  -                         'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '9c39e5590cb042ab',
  -                         'hidden': False,
  -                         'mutex_groups': [],
                            'name': 'catalog',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'out_dir',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-o',
  -                                     '--out',
  -                                 ],
  -                                 'takes_value': True,
  -                             },
  -                         ],
                            'path': [
                                'xprompt',
                                'catalog',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '9c39e5590cb042ab',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-o',
  +                                     '--out',
  +                                 ],
  +                                 'dest': 'out_dir',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': 'a4f489c54a36c0be',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'expand',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'trace',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-t',
  -                                     '--trace',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'xprompt',
                                'expand',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'prompt',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'prompt',
  -                                 'nargs': '?',
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': 'e69f842a09d1f68a',
                            'hidden': False,
  +                         'description_digest': 'a4f489c54a36c0be',
  -                         'mutex_groups': [],
  -                         'name': 'explain',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'named_args',
  ?                                          ^^^ ^^^^^^
  +                                 'dest': 'help',
  ?                                          ^ ^^
  -                                 'hidden': False,
  ?                                  ^^^^ ^
  +                                 'takes_value': False,
  ?                                  ^^^ ^^^^^^^
  -                                 'kind': None,
  -                                 'repeatable': True,
  ?                                               ^^^
  +                                 'repeatable': False,
  ?                                               ^^^^
  -                                 'strings': [
  ?                                  ^^^ ^^    ^
  +                                 'choices': None,
  ?                                  ^^^ ^^    ^^^^^
  -                                     '-a',
  -                                     '--arg',
  -                                 ],
  ?                                 ^
  +                                 'kind': None,
  ?                                 ^^^^^^^^^^^^
  -                                 'takes_value': True,
  ?                                  ^^^ ^^^  ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^^^^^  ^
                                },
  -                         ],
  ?                         ^^
  +                             {
  ?                         ^^^^^
  +                                 'strings': [
  +                                     '-t',
  +                                     '--trace',
  +                                 ],
  +                                 'dest': 'trace',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'prompt',
  +                                 'dest': 'prompt',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'explain',
                            'path': [
                                'xprompt',
                                'explain',
                            ],
  -                         'positionals': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'workflow_name',
  -                                 'is_remainder': False,
  -                                 'kind': 'xprompt',
  -                                 'metavar': 'workflow_name',
  -                                 'nargs': None,
  -                             },
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'args',
  -                                 'is_remainder': False,
  -                                 'kind': None,
  -                                 'metavar': 'args',
  -                                 'nargs': '*',
  -                             },
  -                         ],
  -                         'subcommands': [],
  -                     },
  -                     {
                            'aliases': [],
  -                         'default_child': None,
  -                         'description_digest': '6218d6bf0b221c68',
                            'hidden': False,
  +                         'description_digest': 'e69f842a09d1f68a',
  -                         'mutex_groups': [],
  -                         'name': 'graph',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-a',
  +                                     '--arg',
  +                                 ],
  +                                 'dest': 'named_args',
  +                                 'takes_value': True,
  +                                 'repeatable': True,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
  +                         'positionals': [
  +                             {
  +                                 'metavar': 'workflow_name',
  +                                 'dest': 'workflow_name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'xprompt',
  +                                 'is_remainder': False,
  +                             },
  +                             {
  +                                 'metavar': 'args',
  +                                 'dest': 'args',
  +                                 'nargs': '*',
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'is_remainder': False,
  +                             },
  +                         ],
  +                         'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
  +                     },
  +                     {
  +                         'name': 'graph',
  +                         'path': [
  +                             'xprompt',
  +                             'graph',
  +                         ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '6218d6bf0b221c68',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                             {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'mermaid',
                                        'text',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
  -                         ],
  -                         'path': [
  -                             'xprompt',
  -                             'graph',
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^   ^
  +                                 'metavar': 'workflow_name',
  ?                                  ^ ^^^^^   ^^ +++++++ ++ +
                                    'dest': 'workflow_name',
  +                                 'nargs': '?',
  +                                 'choices': None,
  +                                 'kind': 'xprompt',
                                    'is_remainder': False,
  -                                 'kind': 'xprompt',
  -                                 'metavar': 'workflow_name',
  -                                 'nargs': '?',
                                },
                            ],
                            'subcommands': [],
  -                     },
  -                     {
  -                         'aliases': [],
                            'default_child': None,
  -                         'description_digest': '309696ea2a9da945',
  -                         'hidden': False,
                            'mutex_groups': [],
  +                     },
  +                     {
                            'name': 'list',
  -                         'options': [
  -                             {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
  -                                 'strings': [
  -                                     '-h',
  -                                     '--help',
  -                                 ],
  -                                 'takes_value': False,
  -                             },
  -                         ],
                            'path': [
                                'xprompt',
                                'list',
                            ],
  +                         'aliases': [],
  +                         'hidden': False,
  +                         'description_digest': '309696ea2a9da945',
  +                         'options': [
  +                             {
  +                                 'strings': [
  +                                     '-h',
  +                                     '--help',
  +                                 ],
  +                                 'dest': 'help',
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  +                                 'kind': None,
  +                                 'hidden': False,
  +                             },
  +                         ],
                            'positionals': [],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                        {
  +                         'name': 'show',
  +                         'path': [
  +                             'xprompt',
  +                             'show',
  +                         ],
                            'aliases': [],
  -                         'default_child': None,
  +                         'hidden': False,
                            'description_digest': '1c9fe97c3ae1c6d7',
  -                         'hidden': False,
  -                         'mutex_groups': [],
  -                         'name': 'show',
                            'options': [
                                {
  -                                 'choices': None,
  -                                 'dest': 'help',
  -                                 'hidden': False,
  -                                 'kind': None,
  -                                 'repeatable': False,
                                    'strings': [
                                        '-h',
                                        '--help',
                                    ],
  -                                 'takes_value': False,
  ?                                  ^^^  ^^^^^^   ^^ ^^
  +                                 'dest': 'help',
  ?                                  ^  ^   ^^^ ^^
  +                                 'takes_value': False,
  +                                 'repeatable': False,
  +                                 'choices': None,
  -                             },
  ?                             ^
  +                                 'kind': None,
  ?                             ^^^^^^^^^^^^^^^^
  +                                 'hidden': False,
  -                             {
  ?                             ^
  +                             },
  ?                             ^^
  +                             {
  +                                 'strings': [
  +                                     '-c',
  +                                     '--color',
  +                                 ],
  +                                 'dest': 'color',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'auto',
                                        'always',
                                        'never',
                                    ],
  -                                 'dest': 'color',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-c',
  -                                     '--color',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  +                                 'strings': [
  +                                     '-f',
  +                                     '--format',
  +                                 ],
  +                                 'dest': 'format',
  +                                 'takes_value': True,
  +                                 'repeatable': False,
                                    'choices': [
                                        'full',
                                        'json',
                                        'raw',
                                    ],
  -                                 'dest': 'format',
  -                                 'hidden': False,
                                    'kind': None,
  -                                 'repeatable': False,
  ?                                  ^ ^^^^^^^^
  +                                 'hidden': False,
  ?                                  ^^^^ ^
  -                                 'strings': [
  -                                     '-f',
  -                                     '--format',
  -                                 ],
  -                                 'takes_value': True,
                                },
                                {
  -                                 'choices': None,
  -                                 'dest': 'project',
  -                                 'hidden': False,
  -                                 'kind': 'project',
  -                                 'repeatable': False,
                                    'strings': [
                                        '-p',
                                        '--project',
                                    ],
  -                                 'takes_value': True,
  ?                                  ^^^  ^^^^^^   ^ ^
  +                                 'dest': 'project',
  ?                                  ^  ^   ^^ ^^ +++
  +                                 'takes_value': True,
  +                                 'repeatable': False,
  -                             },
  -                         ],
  -                         'path': [
  -                             'xprompt',
  -                             'show',
  ?                              ^  ^
  +                                 'choices': None,
  ? ++++                             ^  ^^^^ ++++++
  +                                 'kind': 'project',
  +                                 'hidden': False,
  +                             },
                            ],
                            'positionals': [
                                {
  -                                 'choices': None,
  ?                                  ^^^^^ ^    ^^^
  +                                 'metavar': 'NAME',
  ?                                  ^ ^^^^^   + ^^^^
                                    'dest': 'name',
  +                                 'nargs': None,
  +                                 'choices': None,
  +                                 'kind': 'xprompt',
                                    'is_remainder': False,
  -                                 'kind': 'xprompt',
  -                                 'metavar': 'NAME',
  -                                 'nargs': None,
                                },
                            ],
                            'subcommands': [],
  +                         'default_child': None,
  +                         'mutex_groups': [],
                        },
                    ],
  +                 'default_child': 'list',
  +                 'mutex_groups': [],
                },
            ],
  +         'default_child': None,
  +         'mutex_groups': [],
        },
    }
==== 2 failed, 34538 passed, 12 skipped, 73 warnings in 1509.14s (0:25:09) =====
error: recipe `test-cost` failed on line 415 with exit code 1
error: recipe `check-full` failed on line 661 with exit code 1

