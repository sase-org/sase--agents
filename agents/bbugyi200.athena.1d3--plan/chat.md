# Chat History - ace-run (1d3--plan)

- **TIMESTAMP:** 2026-11-16 16:00:36 EST
- **MODEL:** claude/opus
- **AGENT:** 1d3--plan

**Plan:** /home/bryan/.sase/plans/202611/py312_slice_annotation_crash.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/py312_slice_annotation_crash.md`

> # Fix the Python 3.12 `slice[...]` import crash in `sase tui`
> ## Problem
> `sase tui` (and anything else that imports `sase.ace.tui.models`) crashes at import on
> Python 3.12:
> ```
> File "src/sase/ace/tui/models/_loaders/_done_common.py", line 158, in _LazyInstructionBundleFiles
>     index: slice[
> TypeError: type 'slice' is not subscriptable
> ```
> ## Root cause

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Why am I getting this error on my apollo machine? See the command output below for
context. Can you help me diagnose the root cause of this issue and fix it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

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

## Response

Root cause confirmed, and it's the only such site in `src/`. Timing a possible guard check, then writing the plan.

Writing the plan next: the one-line fix plus an optional lint guard so this kind of crash shows up locally on 3.14. First I'm checking how new `tools/` lint scripts get registered.

Plan drafted; fixing one validation error in the decision callout, then I'll propose it.

The crash comes from one type annotation that Python 3.12 can't handle. I've proposed a plan to fix it; no files are changed yet, because the plan has to be approved first.

## Why it happens
1. Commit `fadbfdc497` ("feat(ace): memoize per-load agent loader work", landed today) added a `__getitem__` method to `_LazyInstructionBundleFiles` in `src/sase/ace/tui/models/_loaders/_done_common.py`. Its parameter is typed as `slice[SupportsIndex | None, ...]`.
2. `slice[...]` is only valid for type checkers. In real Python, `slice` can't be subscripted on any version: 3.12, 3.13 and 3.14 all raise `TypeError: type 'slice' is not subscriptable`. It only works if Python never actually evaluates the annotation.
3. That file is one of about 790 in `src/` (out of ~6,500) without `from __future__ import annotations`. Python 3.12 evaluates function annotations as soon as it reads the class, so importing the module crashes. Python 3.14 postpones evaluating annotations, so the bad one is never touched.
4. On athena, both the dev venvs and your installed `sase` use Python 3.14, so the authoring agent's tests, mypy and ruff all passed. apollo's `sase` runs on the system Python 3.12, which is also the project's minimum (`requires-python = ">=3.12"`).
5. CI did catch it, but only after it landed. Master Gate run 43951346220 for `fadbfdc497` failed in `lint` and all 8 test shards with this exact `TypeError`. Master Gate was already failing on earlier commits for unrelated reasons, so one more failed run didn't stand out.

I scanned every `src/sase` module without the future import on 3.14, forcing annotations to be evaluated the way 3.12 does. The only failures were this method (two hits: its overload and its implementation), so nothing else is currently broken this way.

## The plan (small, single-agent)
- **The fix:** add `from __future__ import annotations` to `_done_common.py`. That matches the convention most of the repo already follows, and the precise type annotations stay as they are.
- **A guard (one decision for you, default yes):** a new `tools/check_eager_annotations` lint step in `lint`, `check` and `check-full`. It imports every module lacking the future import and, on 3.14, evaluates annotations the way 3.12 does, so this kind of crash shows up locally before landing. A test wouldn't work here because `just check`'s test selection follows static imports and would skip a sweep like this. The step adds about 4–5s per run; the plan includes tool tests and updates the Justfile wiring tests.

## On apollo
apollo's `sase` is an editable install of `~/projects/github/sase-org/sase`, so once the fix is on master, a `git pull` there fixes `sase tui` with no reinstall. Until then you could check out `fadbfdc497^` there, or run `sase` from a Python 3.14 environment.
