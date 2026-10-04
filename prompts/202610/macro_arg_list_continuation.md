- **PLAN:**
  [202610/macro_arg_list_continuation.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_arg_list_continuation.md)
- **AGENTS:**
  - [bbugyi200.apollo.51--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.51.md)

In the prompt input widget and external editors (via LSP support), we already support
removing the space before the `(` when pressing `(` after a `#foo` macro and we insert
`()` before the first colon when `(` is pressed after a `#foo::` macro. Can you now help
me add support for adding a comma before the `)`, placing the cursor after the comma,
and then triggering macro input completion when `(` is pressed before a macro with
arguments like `#foo(bar=1)` or `#foo(bar=1)::`? For example, consider the following
prompt input widget state:

```
#foo(bar=1):: <cursor>Some text for the first positional input.
```

If the user were to press `(` while in insert-mode, that should result in the following
state:

```
#foo(bar=1,<cursor>):: Some text for the first positional input.
```

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
