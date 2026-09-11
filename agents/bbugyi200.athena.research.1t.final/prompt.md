%id(final, clan=research.1t) %m:@xlarge
%wait:research.1t.cdx %wait:research.1t.cld %q(w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

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
analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.1t.cdx` and
   `research.1t.cld` dependencies, matching by `wait_name` and the canonical research
   label's existing `__a.md`/`__b.md` suffix. Never reassign `__a`/`__b` from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one A report and one B report, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports inside it as `<name>__a.md` and `<name>__b.md`, preserving each report's
   existing `__a`/`__b` suffix. Each report's `source_path` is provenance for where it
   lives in your own opened research checkout; resolve its canonical repo-relative path
   there before moving it. Never modify the other agents' checkouts or the stored
   snapshot recorded at `ref` — only the copy in your own checkout moves. Preserve both
   files and never overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```