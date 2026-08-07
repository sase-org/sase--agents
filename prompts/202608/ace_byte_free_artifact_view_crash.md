- **PLAN:**
  [202608/ace_byte_free_artifact_view_crash.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_byte_free_artifact_view_crash.md)
- **AGENTS:**
  - [bbugyi200.athena.ux--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.ux.md)

The `sase ace` TUI crashes when I try to view an image file from the artifact panel that
shows when the `a` keymap is used on the agents tab (e.g. this crash would occur if the
user hit `<enter>` in #sshot). See the partial stacktrace below for context. Can you
help me diagnose the root cause of this issue and fix it? Think this through thoroughly
and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.

```
│ ╭────────────────────────────────────────────────────────── locals ───────────────────────────────────────────────────────────╮                                                  │
│ │ artifacts = (ArtifactFileViewSpec(path=None, kind='image'),)                                                                │                                                  │
│ │   command = ['/home/bryan/.local/share/uv/tools/sase/bin/python3', '-m', 'sase.ace.tui.graphics.viewer', '--kind', 'image'] │                                                  │
│ │      kind = None                                                                                                            │                                                  │
│ │     specs = (ArtifactFileViewSpec(path=None, kind='image'),)                                                                │                                                  │
│ ╰─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯                                                  │
│                                                                                                                                                                                  │
│ /home/bryan/projects/github/sase-org/sase/src/sase/ace/tui/graphics/_viewer_tmux.py:315 in <genexpr>                                                                             │
│                                                                                                                                                                                  │
│   312 │   else:                                                                                ╭─────────────────────── locals ───────────────────────╮                          │
│   313 │   │   for spec in specs:                                                               │   .0 = <tuple_iterator object at 0x7fcbb534a290>     │                          │
│   314 │   │   │   command.extend(["--kind", "" if spec.kind is None else str(spec.kind)])      │ spec = ArtifactFileViewSpec(path=None, kind='image') │                          │
│ ❱ 315 │   command.extend(str(Path(spec.path).expanduser()) for spec in specs)                  ╰──────────────────────────────────────────────────────╯                          │
│   316 │   return command                                                                                                                                                         │
│   317                                                                                                                                                                            │
│                                                                                                                                                                                  │
│ /home/bryan/.local/share/uv/python/cpython-3.14.3-linux-x86_64-gnu/lib/python3.14/pathlib/__init__.py:150 in __init__                                                            │
│                                                                                                                                                                                  │
│    147 │   │   │   │   except TypeError:                                                                                                                                         │
│    148 │   │   │   │   │   path = arg                                                                                                                                            │
│    149 │   │   │   │   if not isinstance(path, str):                                                                                                                             │
│ ❱  150 │   │   │   │   │   raise TypeError(                                                                                                                                      │
│    151 │   │   │   │   │   │   "argument should be a str or an os.PathLike "                                                                                                     │
│    152 │   │   │   │   │   │   "object where __fspath__ returns a str, "                                                                                                         │
│    153 │   │   │   │   │   │   f"not {type(path).__name__!r}")                                                                                                                   │
│                                                                                                                                                                                  │
│ ╭──────────────────────────────────── locals ─────────────────────────────────────╮                                                                                              │
│ │   arg = None                                                                    │                                                                                              │
│ │  args = (None,)                                                                 │                                                                                              │
│ │  path = None                                                                    │                                                                                              │
│ │ paths = []                                                                      │                                                                                              │
│ │  self = <repr-error "'pathlib.PosixPath' object has no attribute '_raw_paths'"> │                                                                                              │
│ ╰─────────────────────────────────────────────────────────────────────────────────╯                                                                                              │
╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
TypeError: argument should be a str or an os.PathLike object where __fspath__ returns a str, not 'NoneType'
```
