#gh:gh_sase-org__sase Can you help me add excellent support for filtering procs on the "Procs" tab of
the "SASE Admin Center" panel?

- When a new `/` keymap is used, I want a search/query bar to pop-up at the top. See the
  similar keymap on the "XPrompts" tab of the "SASE Admin Center" panel for inspiration.
- We should support a new query syntax with a new set of query filters dedicated to
  filtering procs.
- Any normal quoted text (i.e. quoted text that is not in the form `<key>:<value>`,
  where `<value>` can be quoted text with spaces or non-quoted text without spaces)
  should be used to filter the command string and/or the command output. Negate this
  type of filter (normal text) by prefixing the first quotation symbol with a `-`.
- You should think hard about which query filters to support but we should at least
  support the following:
  - `monitor:<bool>`: Only show monitor / non-monitor procs (add a new `m` keymap to
    automatically toggle this filter on/off--when toggling off, remove the query bar if
    this is the last remaining filter).
  - `min:<N>`: Only show procs that had a runtime of at least `<N>` seconds.
  - `before:<datetime>`: Only show procs that completed before `<datetime>`.
  - `running:<bool>`: Only show procs that are running/complete.
- Any filter that accepts a `<bool>` value should be able to be specified as `<key>` as
  a short-hand for `<key>:true`
- Make sure we support negativating any filter by prefixing it with `-`.
- For example, the query `"just check" -monitor -min:300` should show all non-monitor
  procs that ran in under 5 minutes and contain the text "just check" in either their
  command string or in their command's output.
- I think we may have some shared logic in this codebase for query filters/query engines
  like this. Try to reuse and/or extend that code if possible.
- #beau

#plan #m_opus