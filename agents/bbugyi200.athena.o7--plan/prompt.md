#gh:gh_sase-org__sase Pressing `<ctrl+j>` from the prompt input widget twice when at the
start of an empty bullet deletes the bullet created by the first `<ctrl+j>`
press and adds a blank line beneith that line. This only works when the line the
cursor is on looks like this `- ` (i.e. an empty bullet line). Can you help me
make it so this works any time the cursor is after the space in `- `? For
example, consider the following prompt, where `<cursor>` is meant to denote the
user's cursor position:

```
Some prompt here..

- foo bar
- <cursor>#plan
```

If the user presses `<ctrl+j>` after this change, I would expect to see the
following prompt afterwards:

```
Some prompt here..

- foo bar

<cursor>#plan
```

#plan