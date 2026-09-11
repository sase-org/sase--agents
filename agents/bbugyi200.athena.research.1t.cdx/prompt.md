#gh:gh_sase-org__sase %clan(research.1t, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] We recently migrated from using a configured maximum number
of agents allowed to run to a configured maximum capacity/weight that a given machine
can handle. I would like to make several improvements to the way this functionality
works currently.

- See the sase-z4 epic bead for more context on this recent change.
- We should replace the machine/fleet info that is currently shown on the top-right of
  the "Agents" tab (e.g. `here: athena · 7 active · 1 machine · apollo unknown`) with
  `<L>/<C>`, where `<L>` is the "current load" and `<C>` is the "machine capacity". This
  should replace the other `<L>/<C>` indicator that we show to the left of agent status
  counts at the top of that tab. Make sure this new indicator is much more visually
  appealing and easier to read at a glance (think hard about the best UX for this).
- We will start requiring that every fleet specify its capacity when the `sase init`
  command is run. The athena machine (i.e. this machine) will use 32, the apollo machine
  will use 8, and the mac (my macbook) machine will use 4. See how we satisfy the
  similar requirement for machine names for inspiration.
- We will continue to support floating point / decimal weights, but will prefer to
  render the load (sum of active weights) / capacity as integers for `<L>` and `<C>`
  when possible. For example, we will show `8/32` for a current load of `8` and a
  machine capacity of `32`, but `6.75/32` if the load is `6.75`.
- THE LARGEST AND MOST IMPORTANT CHANGE WE SHOULD MAKE:
  - We will add a new `sase tool` command that is used to wrap slow commands / commands
    that require a lot of resources.
  - This command will allow us to dynamically increase (when the command starts) and
    decrease (when the command completes) the weight of the agent that runs the command.
  - As a part of this change, we should remove the explicit weights that are currently
    set by the `#research_swarm` xprompt swarm (0.25) and by epic lander agents (2).
  - As our first use case, we should wrap all of the `just` commands listed at the top
    of the sase/memory/lint_and_test.md file using the `sase tool` command.
  - I'm thinking that when the `just check-full` command is run, for example, we should
    increase that agent's weight by 15, which would result in a weight of 16 for that
    agent (so at most two agents would be able to run the `just check-full` command at
    once, for example).
  - An agent will need to have some ability to queue itself when a command that is
    wrapped by the `sase tool` command requires more capacity than is currently
    available. In this case, the command should fail with a useful error message and the
    agent should be presented with two choices: 1) Queue itself until the required
    capacity is available. 2) Force the command to run using a `-f|--force` option
    (which may need a `--` before it so it is not confused with the wrapped command's
    CLI options).
  - One of the most important research questions for you to answer is what weights we
    should associate with the other `just` commands. In particular, the `just check`
    command would probably benefit from the ability to dynamically decide what weight to
    assign based on how much work the command anticipates it will need to do.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
all of this? One of your research goals should be to critique this idea itself and
evaluate whether I should pursue it at all. Don't be afraid to guide the research
towards a stronger interface/architecture but clearly call out when you do so. End your
analysis with a recommended solution.]]) %id:research.1t.cdx
%model:@sol_or_grok %q(w=0.25)
You are researcher A in a two-researcher swarm. The other researcher,
`research.1t.cld`, is independently investigating the same request and will write its
own self-named report ending in `__b.md`. Your report will end in `__a.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

We recently migrated from using a configured maximum number
of agents allowed to run to a configured maximum capacity/weight that a given machine
can handle. I would like to make several improvements to the way this functionality
works currently.

- See the sase-z4 epic bead for more context on this recent change.
- We should replace the machine/fleet info that is currently shown on the top-right of
  the "Agents" tab (e.g. `here: athena · 7 active · 1 machine · apollo unknown`) with
  `<L>/<C>`, where `<L>` is the "current load" and `<C>` is the "machine capacity". This
  should replace the other `<L>/<C>` indicator that we show to the left of agent status
  counts at the top of that tab. Make sure this new indicator is much more visually
  appealing and easier to read at a glance (think hard about the best UX for this).
- We will start requiring that every fleet specify its capacity when the `sase init`
  command is run. The athena machine (i.e. this machine) will use 32, the apollo machine
  will use 8, and the mac (my macbook) machine will use 4. See how we satisfy the
  similar requirement for machine names for inspiration.
- We will continue to support floating point / decimal weights, but will prefer to
  render the load (sum of active weights) / capacity as integers for `<L>` and `<C>`
  when possible. For example, we will show `8/32` for a current load of `8` and a
  machine capacity of `32`, but `6.75/32` if the load is `6.75`.
- THE LARGEST AND MOST IMPORTANT CHANGE WE SHOULD MAKE:
  - We will add a new `sase tool` command that is used to wrap slow commands / commands
    that require a lot of resources.
  - This command will allow us to dynamically increase (when the command starts) and
    decrease (when the command completes) the weight of the agent that runs the command.
  - As a part of this change, we should remove the explicit weights that are currently
    set by the `#research_swarm` xprompt swarm (0.25) and by epic lander agents (2).
  - As our first use case, we should wrap all of the `just` commands listed at the top
    of the sase/memory/lint_and_test.md file using the `sase tool` command.
  - I'm thinking that when the `just check-full` command is run, for example, we should
    increase that agent's weight by 15, which would result in a weight of 16 for that
    agent (so at most two agents would be able to run the `just check-full` command at
    once, for example).
  - An agent will need to have some ability to queue itself when a command that is
    wrapped by the `sase tool` command requires more capacity than is currently
    available. In this case, the command should fail with a useful error message and the
    agent should be presented with two choices: 1) Queue itself until the required
    capacity is available. 2) Force the command to run using a `-f|--force` option
    (which may need a `--` before it so it is not confused with the wrapped command's
    CLI options).
  - One of the most important research questions for you to answer is what weights we
    should associate with the other `just` commands. In particular, the `just check`
    command would probably benefit from the ability to dynamically decide what weight to
    assign based on how much work the command anticipates it will need to do.
- #beau

Can you do some research with the goal of helping me decide the best way to implement
all of this? One of your research goals should be to critique this idea itself and
evaluate whether I should pursue it at all. Don't be afraid to guide the research
towards a stronger interface/architecture but clearly call out when you do so. End your
analysis with a recommended solution. #research(suffix=a)