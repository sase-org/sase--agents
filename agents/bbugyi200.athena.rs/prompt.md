#gh:gh_sase-org__sase Can you help me improve the prompts that we store in sase agent chat
markdown files and in prompt markdown files?

- Let's start always storing the unrendered and the rendered agent prompt (see
  how the difference in the contents that we render in the `AGENT XPROMPT` and
  `AGENT PROMPT` sections of the agent metadata panel on the agents tab for
  context) in every sase agent chat markdown file and every prompt markdown
  file?
- We currently seem to only store the unrendered version I think (you should
  verify this).
- For any xprompt reference found in an unrendered prompt (regardless of whether
  in a sase agent chat file or in a prompt file) that has been published to the
  `<project>--agents` sidecar repo, we should start tranforming this reference
  (e.g. `#foo`) into a markdown hyperlink that links to the file (via a GitHub
  URL) containing that xprompt definition.
- Make sure that this feature has good support for chezmoi repos by linking to
  the appropriate files in the appropriate chezmoi repo when the
  `use_chezmoi: true` sase config field is set.
- #beau

#plan #m_opus