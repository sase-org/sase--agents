#gh:gh_sase-org__sase Can you help me migrate the artifact ref expansion for all artifact ref types to a simple reference like the `@research` ref does?

- Also, no more `@` prefixes for file path references.
- For example, `@plan:202608/foobar.md` should now resolve to `the 202608/foobar.md file in the plans sidecar repo`.
- Make sure you review and simplify the ref expansion for all known artifact ref types.

#plan %w(runners=100)