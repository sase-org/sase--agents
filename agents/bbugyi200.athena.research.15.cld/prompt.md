%id(cld, clan=research.15) %m:@research_b  #gh:gh_sase-org__sase I want to give sase gates representation as named family
shells ("gate shells"--which should be added as a glossary term / memory strand for this
project) that are added to the agent family that created them (gates should create an
agent family if the gate was created by an agent shell that was previously not
associated with an agent family).

- Sase agents should never wait for a human to respond to a sase gate because that could
  take a very long time potentially. This is a bug in our current architecture for
  gates.
- Instead every sase gate should kill the sase agent that created it. This functionality
  already exists for some gates like the ones used by the /sase_plan and /sase_questions
  skills. We should make sure to migrate these skills / commands over to this new way of
  doing things so we don't have two separate systems.
- In order to make this work we will need to add support to gates for specifying an
  optional prompt for the next agent that should be run in the same family as the gate
  shell.
- Make sure this is highly configurable so we can support existing use cases (like the
  coder agents launched to implement plans or the agents that are launched after a human
  answers an agent's questions, for example) and support giving the next agent the
  status and/or output of the gate commands that were run (see the bob-cli-15 epic bead
  in the bob-cli sase project for some context on why these types of gates are
  necessary). We should also support using the `#fork` xprompt to fork the entire agent
  family transcript (i.e. any shells that ran before the agent shell, the agent shell,
  and the gate shell).
- Gate shells should have an icon that is rendered to the left of them (like we do with
  the gear icon for monitor shells). Make sure the icon we use for this is appropriate
  and distinct to gate shells.
- Gate shells, when selected, should show the live output of whatever command was
  selected by the user as they run. This same output should be shown by the agent family
  node in a new `GATE` sub-section of the `AGENT REPLY` section. In general, make sure
  gates have excellent and full support in the agent metadata panel when the
  corresponding agent family is selected (see how this is done for monitor shells for
  inspiration).
- This change is also expected to simplify the way we handle family shell statuses.
  Namely, the gate shell should take over the `TALE/EPIC` and `PLAN/TALE/EPIC APPROVED`
  shell statuses. The agent that proposed the tale/epic should just have a status of
  `DONE` (which is more appropriate I think since we often seem to assume this agent
  created/implemented a plan--by showing `TALE DONE`, for example--when all the agent
  did was ask some questions or run a sase monitor). This should NOT have any impact on
  the status shown for the agent family node since it should still show the status of
  the most recently run shell in that family (after this feature is implemented, this
  should be the gate shell, which should support the same statuses that we expect the
  agent family node to show now).
- This change brings sase gates much closer in functionality to sase monitors. We should
  therefore try our best to unify these concepts and the code/logic that corresponds
  with them as much as possible/desirable (based on what functionality is actually
  shared--don't just take my word for it).
- #beau

Can you do some research with a goal of helping me understand the best way to implement
this? End your analysis with a recommended solution. #research(report_target=research.15.cld.md)