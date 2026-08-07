# Chat History - ace-run (ux--plan)

- **TIMESTAMP:** 2026-08-07 14:28:22 EDT
- **MODEL:** claude/opus
- **AGENT:** ux--plan

**Plan:** /home/bryan/.sase/plans/202608/ace_byte_free_artifact_view_crash.md


## Prompt

#gh:gh_sase-org__sase The `sase ace` TUI crashes when I try to view an image file from the artifact panel that shows when the `a` keymap is used on the agents tab (e.g. this crash would occur if the user hit `<enter>` in #sshot). See the partial stacktrace below for context. Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus 
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

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/ace_byte_free_artifact_view_crash.md`

> # Plan: Fix the ACE crash when opening a byte-free (VCS-backed) artifact file
> ## Symptom
> `sase ace` hard-crashes (unhandled `TypeError`, Textual tears the app down) when the
> user presses `<enter>` on an image row in the artifact-file picker opened with the `a`
> keymap on the Agents tab:
> ```
> TypeError: argument should be a str or an os.PathLike object where __fspath__ returns a
> str, not 'NoneType'
> ```
> with these locals at the top frame:

*See full plan file for details.*

