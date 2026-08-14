- **AGENTS:**
  - [bbugyi200.athena.research.0k.cdx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.0k.cdx/README.md)

%clan(research.0k, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to
eliminate procs that run inside the ACE TUI process, make every proc supervisor-owned
and detached, and remove the `-d|--detached` option from the `sase proc run` command.

- I also want to merge sase monitors into sase procs by adding a new `--shell <name>`
  option on the `sase proc` command and making `sase monitor` wrap this functionality
  (at the service-level).
- I have thought of a good new glossary term that is related to this feature and
  improves sase's agent taxonomy (i.e. tribes, clans, families, etc...):
  - We currently have the term "agent lane" to refer to either an agent family or a
    single agent.
  - One problem with that term is that it is confusing. I'd like to refer to agent lanes
    as "sase agents" (or just agents) instead, but that creates a problem: We would then
    have no way of referring to a single agent, which may or may not belong to an agent
    family.
  - I think we can solve this by introducing a new term, "agent shell", which will be
    used to refer to a single agent which may or may not belong to an agent family.
  - We can then generalize this term with a new term, "sase shell", which can refer to
    either an agent shell or a "proc shell" (this is what we referred to as "named
    procs" in one of the research files references below, but I think "proc shell" is
    going to work better).
  - A "proc shell" is what we currently (and should continue to) refer to as "sase
    monitors" (though I think we might make monitors only refer to proc shells that live
    in agent families at some point--see the FUTURE DIRECTION bullet below for context).
- See the detached_proc_convergence.md and sase_shell_named_procs.md files (which
  contain some obsolete assumptions, but should be worth reviewing) in the research
  sidecar repo for context and inspiration.
- FUTURE DIRECTION: My plan is to eventually allow stand-alone proc shells that are not
  a part of any agent family. There are several benefits to this change. It will allow
  us to make use of xprompt directives to have procs wait for agents to complete (or
  vice-versa), for example. This change is out of scope for your research, but it might
  be useful to keep this future direction in mind.

Can you do some research with the goal of helping me decide the best way to implement
all of this? End your analysis with a recommended solution.]]) %id:research.0k.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I want to eliminate procs
that run inside the ACE TUI process, make every proc supervisor-owned and detached, and
remove the `-d|--detached` option from the `sase proc run` command.

- I also want to merge sase monitors into sase procs by adding a new `--shell <name>`
  option on the `sase proc` command and making `sase monitor` wrap this functionality
  (at the service-level).
- I have thought of a good new glossary term that is related to this feature and
  improves sase's agent taxonomy (i.e. tribes, clans, families, etc...):
  - We currently have the term "agent lane" to refer to either an agent family or a
    single agent.
  - One problem with that term is that it is confusing. I'd like to refer to agent lanes
    as "sase agents" (or just agents) instead, but that creates a problem: We would then
    have no way of referring to a single agent, which may or may not belong to an agent
    family.
  - I think we can solve this by introducing a new term, "agent shell", which will be
    used to refer to a single agent which may or may not belong to an agent family.
  - We can then generalize this term with a new term, "sase shell", which can refer to
    either an agent shell or a "proc shell" (this is what we referred to as "named
    procs" in one of the research files references below, but I think "proc shell" is
    going to work better).
  - A "proc shell" is what we currently (and should continue to) refer to as "sase
    monitors" (though I think we might make monitors only refer to proc shells that live
    in agent families at some point--see the FUTURE DIRECTION bullet below for context).
- See the detached_proc_convergence.md and sase_shell_named_procs.md files (which
  contain some obsolete assumptions, but should be worth reviewing) in the research
  sidecar repo for context and inspiration.
- FUTURE DIRECTION: My plan is to eventually allow stand-alone proc shells that are not
  a part of any agent family. There are several benefits to this change. It will allow
  us to make use of xprompt directives to have procs wait for agents to complete (or
  vice-versa), for example. This change is out of scope for your research, but it might
  be useful to keep this future direction in mind.

Can you do some research with the goal of helping me decide the best way to implement
all of this? End your analysis with a recommended solution. #research
