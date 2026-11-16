#gh:gh_sase-org__sase Why am I getting this error on my apollo machine? See the command output below for
context. Can you help me diagnose the root cause of this issue and fix it?

#plan %m:@xlarge

```
❯ sase tui
Traceback (most recent call last):
  File "/home/bryan/.local/bin/sase", line 10, in <module>
    sys.exit(main())
             ^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/main/entry.py", line 19, in main
    _main(hit)
  File "/home/bryan/projects/github/sase-org/sase/src/sase/main/entry.py", line 117, in _main
    dispatch_initial_commands(args, parser)
  File "/home/bryan/projects/github/sase-org/sase/src/sase/main/_dispatch_initial.py", line 14, in dispatch_initial_commands
    handle_ace_command(args)
  File "/home/bryan/projects/github/sase-org/sase/src/sase/main/ace_handler.py", line 216, in handle_ace_command
    from sase.ace.tui import AceApp
  File "<frozen importlib._bootstrap>", line 1412, in _handle_fromlist
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/__init__.py", line 23, in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.12/importlib/__init__.py", line 90, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/app.py", line 30, in <module>
    from .actions import (
  File "<frozen importlib._bootstrap>", line 1412, in _handle_fromlist
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/actions/__init__.py", line 89, in __getattr__
    module = import_module(module_name, __name__)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.12/importlib/__init__.py", line 90, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/actions/agents/__init__.py", line 3, in <module>
    from ._core import DISMISSABLE_STATUSES, AgentsMixinCore
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/actions/agents/_core.py", line 7, in <module>
    from ._agent_enter_action import AgentEnterActionMixin
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/actions/agents/_agent_enter_action.py", line 18, in <module>
    from ._agent_enter_targets import (
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/actions/agents/_agent_enter_targets.py", line 23, in <module>
    from ._agent_enter_resolver import (
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/actions/agents/_agent_enter_resolver.py", line 10, in <module>
    from ...models._agent_clan import clan_lone_stopped_member
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/models/__init__.py", line 5, in <module>
    from .agent_loader import load_all_agents, load_all_workflows
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/models/agent_loader.py", line 54, in <module>
    from ._loaders import (
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/models/_loaders/__init__.py", line 8, in <module>
    from ._done_loaders import (
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/models/_loaders/_done_loaders.py", line 11, in <module>
    from . import _done_filesystem_loaders as _filesystem_loaders
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/models/_loaders/_done_filesystem_loaders.py", line 17, in <module>
    from ._done_common import (
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/models/_loaders/_done_common.py", line 115, in <module>
    class _LazyInstructionBundleFiles(list[str]):
  File "/home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/models/_loaders/_done_common.py", line 158, in _LazyInstructionBundleFiles
    index: slice[
           ^^^^^^
TypeError: type 'slice' is not subscriptable
```