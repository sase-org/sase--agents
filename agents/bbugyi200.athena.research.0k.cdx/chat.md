# Chat History - ace-run (research.0k.cdx)

- **TIMESTAMP:** 2026-08-14 18:24:54 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0k.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260814_180548.md`

## Prompt

%clan(research.0k, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I want to eliminate procs that run inside the ACE TUI
process, make every proc supervisor-owned and detached, and remove the `-d|--detached`
option from the `sase proc run` command.

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
%wait(priority=20) %model:@research_a 
#gh:gh_sase-org__sase I want to eliminate procs that run inside the ACE TUI
process, make every proc supervisor-owned and detached, and remove the `-d|--detached`
option from the `sase proc run` command.

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
all of this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll trace the current proc/monitor architecture, read the existing research, and map the proposed shell taxonomy onto the service, CLI, supervisor, and ACE boundaries. I’m using the SASE repo skill because the research sidecar is a separate repository, plus the audited memory-read skill for the glossary and xprompt semantics this design touches.

The current glossary confirms why this is more than a rename: today `Proc` has three persisted kinds (`command`, `tui`, `detached`), while “agent lane” deliberately mixes a family container with a singleton. I’m now checking where those concepts are structural versus merely presentation labels, so the recommendation can avoid baking the future standalone-shell direction into the wrong layer.

The earlier reports’ broad direction still holds, but one recommendation is now clearly obsolete: a new top-level `sase shell` CLI would fight the taxonomy you’ve proposed. The cleaner boundary is shaping up as “Proc is the execution record; `shell` is an optional identity/attachment capability; monitor is a compatibility and family-lifecycle facade over the same service.” I’m validating that against the current TUI callback/dedup machinery and Rust wire before locking it in.

The key design distinction is now firm: `shell_name` should identify one execution leaf, while family attachment and concurrency exclusion stay separate. That avoids repeating today’s `kind` mistake, where ownership and attribution are fused, and it keeps a clean path to future standalone proc shells without forcing xprompt/wait semantics into this change.

The report is drafted. I’m doing a final consistency check on the taxonomy, CLI proposal, and the closing recommendation, then I’ll hand you the file and the key decision points.

Research completed and written to [proc_shell_convergence.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202608/proc_shell_convergence.md).

The recommendation is to:

- Establish one supervisor-owned Proc control plane.
- Add `-S|--shell NAME` as optional Proc-shell identity—not a new Proc kind.
- Make monitors family-attached proc shells implemented as a service-level facade over Procs.
- Migrate ACE’s 53 in-process Proc producers to command-backed Procs or ordinary untracked UI workers.
- Introduce the SASE agent / agent shell / proc shell / SASE shell taxonomy while staging the deeper `lane_*` code rename separately.
- Preserve legacy Proc and monitor records through a compatibility window.

The report also covers schema changes, concurrency, lifecycle settlement, logging, compatibility, phased migration, and acceptance criteria. Markdown validation passed; no runtime tests were necessary because only the research document was added.

The finalizer confirms the research report is the change from this session, so I’m completing the required external-repository commit now. I’m using the SASE repository and commit skills to validate the sidecar checkout, commit through the mandated stitch workflow, and confirm the worktree is clean.

The sidecar contains only the new report, and the reviewed content matches the requested research scope. I’m committing it as a documentation-only change; no exclusions are needed.

Committed the research report:

- Commit: `7991c73 docs: research proc-shell convergence architecture`
- File: [proc_shell_convergence.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/research/202608/proc_shell_convergence.md)
- Repository is clean and synchronized with `origin/main`.
- No runtime tests were needed for this documentation-only change.
