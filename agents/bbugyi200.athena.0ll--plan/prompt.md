#gh:gh_sase-org__sase We recently added support to the prompt input widget and external editors (via
LSP support) for converting the single-colon xprompt/directive syntax to the
parentheses-syntax by inputting the `(` character. Can you now help me add similar
support for the double-colon syntax? Namely, when the `(` character is input as the
first character after `::` (and some optional space characters), we should add `()`
before the first `:` and then move the cursor to the right of the `(` character (this
way the user can start typing an xprompt `foo=bar` style input).

#plan %m:gpt-6-astra