# Chat History - ace-run (research.0k.cld)

- **TIMESTAMP:** 2026-08-14 18:22:59 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0k.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260814_180548.md`

## Prompt

%id(cld, clan=research.0k) %wait(priority=20) %m:@research_b  #gh:gh_sase-org__sase I want to eliminate procs that run inside the ACE TUI
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

I'll research this. Let me start by exploring the current implementation and the referenced research files.

Both prior notes are rich. Now let me verify the current state of the code, since those notes were written against 2026-08-13 snapshots.

Let me verify two load-bearing claims from the prior notes before I rely on them.

I have everything I need. Writing the research note.

Research written to `sase/repos/research/202608/sase_shells_and_proc_convergence/sase_shells_and_proc_convergence.md`. The sase repo itself is untouched, so no `just check` was needed.

## What I found

I re-verified both prior notes against HEAD (`191e9f219`) rather than trusting them — §0 of the report is a correction table. The most useful corrections: `sase.tasks` is gone (`sase.procs` landed), both `sase-lh` and `sase-kp` have every phase closed and sit on their land beads, and **Python no longer checks the proc wire schema for exact equality** (`SUPPORTED_PROC_WIRE_SCHEMA_VERSIONS = {1, 2}`), so a v3 field addition is now a set entry, not a coordinated cutover. The producer count is also lower than reported (41 references / 30 files, not 54 / 37).

## The three headline conclusions

**1. Your taxonomy is already implemented — it just has no name.** `sase agent list -a` returns 75 rows, of which **33 carry `agent_family_role="monitor"`**. That command already lists sase shells (agent shells *and* proc shells). The taxonomy is a documentation-and-identifier change, not an architectural one. The sentence I'd anchor the glossary on: **a sase agent is a sequence of sase shells.**

**2. Keeping `sase monitor` is better than the prior note's plan to replace it with a `sase shell` command.** Under your taxonomy that command name is taken by the *concept* — a `sase shell` command listing only proc shells would be wrong, and one listing both would duplicate `sase agent list`. Your version also avoids renaming the `/sase_monitor` skill and rewriting `build_and_run.md`.

**3. A key design idea for `--shell`:** make the family separator carry the resolution rule. `--shell pc--check` fully qualifies; `--shell check` is a suffix under the calling agent. That single rule spells today's behavior and your future direction *identically*, so standalone shells become a capability addition with no syntax change.

## Two things you should weigh

- **Your "future direction" is on the critical path.** Eliminating TUI procs needs store-wide dedup; dedup is the shell name; a name makes a proc a shell; a shell belongs to a sase agent — and ACE is not an agent. So ACE's procs need to be shells without a starting agent. The good news is it's cheap: a standalone proc shell is a sase agent whose only shell is a proc shell, structurally identical to a solo agent. I recommend pulling the no-agent case into the merge epic.
- **`--shell` has one wart:** no good short alias. `-s` is `--session` on both `proc run` and `proc list`, so making it `--shell` on `run` only would let `sase proc list -s deploy` silently filter by session. I recommend `-N/--shell` uniformly. Separately, `--shell` conventionally means "which interpreter" — worth reserving `--interpreter` for that now and rejecting values containing `/`.

Fresh data supporting the TUI-proc removal: the live store is **101 rows, all `kind=tui`, 99 with empty command**, and the `kill` proc now runs to a **1679 s max** (up from 1232 s) while `sase proc kill` refuses to touch it.

The research file is mine from this session. Committing it via the commit skill.

Committed.

**`6409247 docs(research): design sase shells and detached-proc convergence`** — research sidecar repo, clean and in sync with `origin/main`. The finalizer listed the repo twice (as linked repo and as SDD sidecar) but both point at the same path, so the single commit covers both entries. The sase workspace repo itself is untouched and clean, so no `just check` was required.

The commit adds `202608/sase_shells_and_proc_convergence/sase_shells_and_proc_convergence.md` (743 lines), which covers:

- **§0 corrections** to the two prior notes, re-verified against HEAD `191e9f219` — `sase.procs` replaced `sase.tasks`, the proc wire schema now validates against `SUPPORTED_PROC_WIRE_SCHEMA_VERSIONS = {1, 2}` rather than exact equality (so a v3 field is a set entry, not a cutover), and the producer inventory is 41 references / 30 files rather than the reported 54 / 37.
- **Part I — the taxonomy**, anchored on *a sase agent is a sequence of sase shells*. `sase agent list -a` already returns 75 rows of which 33 carry `agent_family_role="monitor"`, so it already lists sase shells; this is a naming change, not an architectural one.
- **Part II — `--shell <name>`**, with the family separator carrying the resolution rule (`--shell pc--check` fully qualifies, `--shell check` is a suffix under the calling agent), plus the recommendation to keep `sase monitor` as a service-level facade and to use `-N/--shell` uniformly since `-s` is already `--session`.
- **Part III — removing TUI procs and `--detached`**, with the store evidence: 101 rows, all `kind=tui`, 99 with empty command, and the `kill` proc at a 1679 s max that `sase proc kill` refuses to touch.
- **Sequencing, risks, open decisions, and a recommended solution**, including the argument for pulling standalone agent-less proc shells into the merge epic rather than deferring them.
