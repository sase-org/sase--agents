# Chat History - ace-run (research.0k.final)

- **TIMESTAMP:** 2026-08-14 18:44:33 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0k.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260814_180548.md`

## Prompt

%id(final, clan=research.0k) %wait(priority=20) %m:@research_lead
%wait:research.0k.cdx %wait:research.0k.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to eliminate procs that run inside the ACE TUI
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
all of this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0k.cdx` -> `__a`, `research.0k.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
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

## Response

I'll start by reading both transcripts to identify which report each researcher wrote.

Both transcripts identified. `research.0k.cdx` wrote `proc_shell_convergence.md` (→ `__a`), `research.0k.cld` wrote `sase_shells_and_proc_convergence/` (→ `__b`). Now let me open the research sidecar repo properly.

Both reports are read. Now let me verify the disputed facts myself, starting with the producer inventory and CLI option availability.

B's recount is confirmed (41 refs / 30 files); A's "53 producers / 37 files" was carried forward without recounting. Now the CLI option collision question.

`-S` is already `--status` on `sase proc list` — that settles the short-alias dispute. Now the Rust wire.

Let me read the authoritative CLI rules and glossary via the memory-read skill.

Found something both reports missed — a third ACE submission method. Let me get the true producer inventory.

Evidence gathered. Now let me set up the directory structure.

Both reports are preserved with git history. Now writing the consolidated report.

Verified. The read path at `procs/store.rs:224` silently `continue`s past rows that fail validation, counting them only in `invalid_record_lines` — so my §6.4 claim holds exactly.

## Done

```
sase/repos/research/202608/proc_ownership_and_shell_taxonomy/
├── proc_ownership_and_shell_taxonomy__a.md   (research.0k.cdx, 935 lines, git-mv'd)
├── proc_ownership_and_shell_taxonomy__b.md   (research.0k.cld, 743 lines, git-mv'd)
└── proc_ownership_and_shell_taxonomy.md      (consolidated, 1042 lines)
```

Both reports moved with history preserved; `__a`'s three sibling links got a `../` prefix so they still resolve one level down. Nothing was overwritten.

**Where the two reports agreed** (and I confirmed): promote `monitor/supervise.py` to the proc kernel and delete `procs/supervisor.py`; keep `sase monitor` as a direct service-level facade — not a CLI wrapper, not a wrapper process; taxonomy first as its own behavior-preserving epic; no top-level `sase shell` command; `__b`'s `--` resolution rule for `--shell`.

**Five things I corrected, each with evidence:**

1. **The producer inventory is wrong in both.** `__a` says 53/37 (never recounted), `__b` says 41/30 but greps `_submit_background_proc`, which **doesn't exist**. Both miss `_submit_proc` — 17 call sites across 7 files. True figure: **56 call sites / 36 files**.

2. **`-S|--shell` collides.** `__a` checked it against `sase monitor -S|--stop-status` and missed that `-S` is `--status` on `sase proc list` (`parser_proc.py:146`). `__b`'s `-N` is correct.

3. **The dedup conflict resolves in `__a`'s favor, and that changes the plan.** `__b` argues the shell name *is* the store-wide dedup key. It can't be: ACE's exclusion is set-overlap (`requested & info.exclusive_scopes`) with a live call site claiming three scopes at once. Keep `shell_name` and `concurrency_keys` separate, with a name implying one key. **Consequence:** `__b`'s claim that standalone proc shells are a prerequisite for the ACE migration is false — Epic C depends on Epic B phases 1–4 only, removing a hard serialization from the sequence.

4. **`__b`'s `timeout_seconds: Option<f64>` won't compile.** `ProcWire` derives `Eq`. `AgentMetaWire`, which already holds those f64 fields, derives only `PartialEq` for exactly this reason. `__a`'s integer-ms is right.

5. **A silent-data-loss hazard neither report states:** `validate_kind` runs on **read**, not just append, and invalid rows are dropped into `invalid_record_lines`. All 101 live rows are `kind="tui"` — so removing `"tui"` from `PROC_KINDS` makes the store read as empty. Same shape for the log pruner: `__a`'s "every reader follows `Proc.log_path`", if applied to `delete_proc_logs`, would start deleting artifacts-owned logs on nearly every append.

Also new: `-a/--agent` is free on `sase monitor start` but is `--all` on `sase monitor list`, so `__b`'s rename is only half-clean; `cli_rules.md` forbids required options while `sase monitor start` has three; and the `Proc` glossary entry itself hardcodes the three kinds this work deletes.

The research sidecar has the two moves staged and the new report untracked — I haven't committed. Say the word and I'll run it through `/sase_git_commit`.

Layout is correct and nothing was left behind. Committing now.

Committed and pushed. `## main...origin/main` with no ahead-marker confirms the push landed as part of `create_commit`.

## Summary

Committed the consolidated research as `d2d0671 docs(research): consolidate the proc ownership and shell taxonomy reports` in the research sidecar. The finalizer listed the repo twice (as linked repo and as SDD sidecar), but both entries point at the same checkout, so one commit covers them; `git status --short --branch` is clean.

Final layout in the tree:

```
202608/proc_ownership_and_shell_taxonomy/
├── proc_ownership_and_shell_taxonomy__a.md   (research.0k.cdx, 935 lines)
├── proc_ownership_and_shell_taxonomy__b.md   (research.0k.cld, 743 lines)
└── proc_ownership_and_shell_taxonomy.md      (consolidated, 1042 lines)
```

Both source reports moved with `git mv`, so history is preserved and neither was overwritten. The only content edit to a source report was prefixing `__a`'s three sibling-report links with `../` so they still resolve from one directory down.

The commit message records what the consolidation concluded: the points both researchers reached independently (promote the monitor supervisor to the proc kernel and delete the ACE-owned one, keep `sase monitor` as a service-level facade, land the taxonomy rename as its own behavior-preserving epic, no top-level `sase shell` command), plus the five claims I corrected against the current tree — the producer inventory (56 call sites / 36 files), the `-S` alias collision with `sase proc list --status`, the shell-name-as-dedup-key proposal that ACE's set-overlap exclusion rules out, the `Option<f64>` field that won't compile against the `Eq`-deriving wire type, and the read-path kind validation that would make the whole store read as empty if the `tui` kind were dropped.
