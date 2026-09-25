#gh:gh_sase-org__sase %w:0pw We just added the new `PROMPTS` section to the agent metadata panel, that
shows when an agent tribe panel is selected. Can you now help me add support for showing
the same agent clan summaries shown when an agent clan is selected (the agent clan
summaries for the agent clans used to launch epic beads are the most complex example of
this) for all of the agent clans contained in an agent tribe when that agent tribe panel
is selected?

- These summaries can get quite large so make sure you think hard about the best way to
  support progressive disclosure while maintaining TUI performance and providing a good
  default view (that users still find useful).
- Also, it seems that agent clan summaries seem to get lost sometimes (if I kill certain
  phases in an epic agent clan, for example). Can you help me dig into this as well,
  diagnose why agent clan summaries might get lost / not be displayed (once set, they
  should be persisted somehow to prevent loss and to be used as the default if the clan
  is created again without specifying the summary--we should do the same to make sure
  that we remember an agent clan's chosen tribe), and fix any issues you find?
- #beau

#plan %m:@xlarge