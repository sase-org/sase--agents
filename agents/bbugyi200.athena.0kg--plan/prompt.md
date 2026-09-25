#gh:gh_sase-org__sase When the user presses `(` after a `:` character which was placed after an
xprompt or directive (i.e. the single-argument form supported by xprompts / directives)
in the prompt input widget or in external editors (via LSP support), I would like to
start auto-deleting the `:` (it is assumed that the user would like to switch from the
colon argument syntax to the parentheses syntax). For example, assume the following
state:

```
Some prompt here. %q:<cursor>
```

Then, if the user presses `(` at this point when in insert-mode, the prompt input widget
contents should be transformed to the following:

```
Some prompt here. %q(<cursor>)
```

Can you help me implement this? #plan %m:gpt-6-astra