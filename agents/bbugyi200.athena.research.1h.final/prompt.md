%id(final, clan=research.1h) %m:@xlarge
%wait:research.1h.cdx %wait:research.1h.cld 
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

I want to add support to sase for dispatching to remote
machines.

- I've already done some research related to this topic. Review the
  tailnet_agent_fleet.md, sase_collaboration_architecture.md, and
  tailnet_fleet_federation.md files (which were created in that order) in the research
  sidecar repo for context and inspiration before starting your own research.
- I like the idea of using a Tailnet to auto-discover (its fine if auto-discovery is
  handled by the `sase init` command, which can then configure the appropriate machines
  explicitly--this way we don't need to pay the cost of auto-discovery at runtime) which
  machines are available but I don't think that Tailscale should be a hard dependency
  for this functionality.
- Instead I think we should use sase's existing plugin architecture to generalize this
  and allow remote device discovery and dispatch (and related functionality) to be
  specified via one or more new plugin hooks. The Tailnet plugin should be built in and
  enabled by default (we might need a new sase config field to support specifying which
  dispatch provider should be used?).
- Also we need to make sure this functionality is as lazy and performant as possible. To
  support this requirement, I was thinking that we should split the Agents tab in the
  TUI into two subtabs: a Local sub-tab and a Remote sub-tab, both of which should show
  a count of the running sase agents in the subtab title bar.
- On the new Remote sub-tab we should show all remote agents (make sure that remote
  agents which the local machine is subscribed to are visually distinct somehow) that
  would be shown on all of the configured remote machines in their TUIs (we should show
  all of them on this one sub-tab--don't create sub-sub-tabs), but these should only
  show enough information to allow the user to decide whether or not they want to
  subscribe to that agent on this local machine.
- The new Local sub-tab should show all of the sase agents that we currently show, but
  should also show any remote agents that the local machine is subscribed to (either by
  explicitly subscribing to a remote agent from the new Remote sub-tab or by launching
  the remote machine from this machine using the new `%dispatch` directive). We should
  try our best to allow users to manage remote agents that the local machine is
  subscribed to in the exact same ways that they can manage local agents; however, make
  sure remote agent managements (e.g. viewing, killing, creating, forking, etc...) is as
  performant as possible.
- We should add a new `%dispatch:<machine>` directive that allows the user to specify
  that an agent should be launched on the `<machine>` remote machine instead of the
  local machine. sase agents launched on remote machines using the `%dispatch` directive
  should be auto-subscribed to by the local machine that ran them.

Can you do some research with the goal of helping me decide the best way to implement
this? I would also like you to critique this idea (in general) and (in particular) the
proposed UX requirements by asking and answering questions like "Is there a better way
to achieve the same goal?". Think hard when it comes to designing the appropriate UX.
#beau End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify the one distinct A report and the one
   distinct B report belonging to this dispatch's `research.1h.cdx` and
   `research.1h.cld` dependencies, matching by `wait_name` and the canonical research
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