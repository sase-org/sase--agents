#gh:gh_sase-org__sase Can you help me add a new `sase glossary` command?

- This command should have the following sub-commands, which should act against the
  current sase project (add a CLI option to the `sase glossary` command to allow the
  user to select the project explicitly):
  - `list`: List all of the currently configured glossary terms. Make sure this command
    supports multiple output formats and supports filtering somehow.
  - `log`: Show a log of all of the times that agents have read terms from the glossary
    using the `read` sub-command.
  - `read`: Should be a wrapper around the `show` sub-command. The only difference
    between this sub-command and the `show` sub-command is that this command should
    require a reason (from the agent) and will log the read (with the reason) somewhere.
  - `show`: Print the targeted glossary terms' definition. By default this command
    should also print the definitions of any glossary terms that are referenced by this
    term's definition. This should be done recursively so all of the glossary terms that
    you need to know to understand the target term are displayed. Make sure we clearly
    indicate (in a visually appealing way) why each glossary term was printed.
- The primary goal of this command is to allow agents to fetch glossary terms in a way
  that consumes as few tokens as possible (by only showing that term and related terms).
  This will also allow us to scale up the glossary and add new entries whenever
  appropriate without worrying about adding too many tokens to context.
- To accomplish that goal, we should have the `sase init` command stop generating the
  sase/memory/glossary.md long-term memory file.
- Instead, if any glossary terms are configured for a project, we should add
  instructions to the Tier 2 section (after a blank line and right before a blank line
  that preceeds the long-term memory file sub-sections) for agents to use the
  `sase glossary read <term>` command for any of the listed terms.
- These new glossary instructions that you add to the Tier 2 section should start with
  the text `**GLOSSARY TERMS:** `. Use your best judgement for the rest, but make sure
  to include a list of all configured glossary terms and keep it concise (remember that
  every token in context either helps or hurts us).
- We should start showing a new `GLOSSARY` sub-section in the `SASE CONTEXT` section of
  the agent metadata panel when agents run the `sase glossary read` command. See how we
  do this for the `MEMORY` section and the `sase memory read` command for inspiration.
  Make sure we show the reason for the read (here and in the `sase glossary log`
  command's output).
- #beau

#plan