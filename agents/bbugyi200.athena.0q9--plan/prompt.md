#gh:gh_sase-org__sase Can you help me start using the same style for the row that contains sase's
notification indicators on the top-right of the TUI as we do for the load/model/project
text indicators beneath it by using dots to separate the different types of indicators
and using `<type>: ` prefixes?

- The following types should be supported and should be used to display `<type>: `
  before each section:
  - `provider`: hard/soft disabled LLM provider indicator
  - `inbox`: Sase notification indicators
  - `procs`: Sase procs.
  - `prompts`: Stashed prompts. Let's just start using the `prompts: <N>` text for this
    (i.e. remove the little snowflake icon), where `<N>` should be highlighted the same
    as before.
  - `updates`: The indicator that shows when sase updates are available.
- If I forgot any indicator groups, name them using your best judgement.
- #beau

#plan %m:@xlarge