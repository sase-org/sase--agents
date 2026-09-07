# Chat History - ace-run (research.1j.cld)

- **TIMESTAMP:** 2026-09-06 22:31:41 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1j.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260906_220719.md`

## Prompt

%id(cld, clan=research.1j) %m:@research_b 
#gh:gh_sase-org__sase You are researcher B in a two-researcher swarm. The other researcher,
`research.1j.cdx`, is independently investigating the same request and will write its
own self-named report ending in `__a.md`. Your report will end in `__b.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read both reports and synthesize their
findings after you have both finished.

I've been experimenting with ways to create a more powerful
type of "message board" for sase agents to communicate with one another and for humans
to communicate with a running sequence of agent shells in an agent family.

- See the /sase_pipe and /sase_monitor skills for context on how sequences of agents can
  be created via agent families.
- See the `016` sase agent for an example of a recent attempt to prototype / prove the
  value of this type of functionality.
- The best/most recent idea I've come up with so far to implement this is to create a
  new, dedicated "message" sase bead type that serves as a message board that agents can
  subscribe to somehow.
- I'm not sure if this is a good idea or not. Part of your research task is to critique
  this idea in general and either approve it and help me flesh it out or recommend an
  alternative approach.

Can you do some research with the goal of helping me decide the best way to implement
this, if I should implement it at all? End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__b` suffix, i.e. `<stem>__b.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'll start by getting oriented in the repo and understanding the relevant systems.

Research complete and registered.

## Report

**`research:202609/agent_message_board_and_family_channels__b.md`** → artifact `file:explicit:ac09e6cfc52c2e48b306db0a`

## Verdict

**Don't add a `message` bead type. Do build the board — but the part that matters is the delivery hook, and it already exists.**

**Six findings:**

1. **The board worked; the chain died — twice.** Epochs `00a` and `00b` both ended at a `LaunchApproval` gate that killed the turn before the next monitor was scheduled. Both times the board preserved enough state for a fresh family to recover. The message board is the component with a track record here.

2. **The prototype had to defeat bead machinery to work**: stay `open` forever to dodge `TaskTriage`, fill the memory type's required fields with "honest sentinels," declare `size: large` as meaningless, dodge `BeadStaleCleanup`. Its own note #1 records this as observed friction.

3. **The read path is the killer, and a bead type doesn't fix it.** `sase bead show` has no `--since`/`--tail`. `sase bead show sase-xs` = 110,533 bytes (~27k tokens); its first note alone is 69,559 chars. Traffic is trivial (~3.2 msgs/hr) — payloads are enormous. That inverts the usual design concern: **cursors and bounded reads are the whole feature.**

4. **Cost, and the precedent runs the other way.** `IssueType` = 300 Rust refs / 226 Python refs. And `sase_flags.md` already settled this exact question: *"A flag bead is a task bead of type `flag`, not a fourth issue type."*

5. **"Subscribe" has one buildable meaning, and it's enough.** SASE can't deliver to a *running* agent — only to one that hasn't started. But I verified xprompt expansion happens at **dispatch, not queue time** (`sase-xr.3`: artifacts dir stamped 19:00, prompt composed 21:33 when its wait cleared). So a message you post at 03:00 reaches every subscriber starting after 03:00, including agents queued for hours. That *is* subscription.

6. **The hook is 37 lines.** `#fork` already does host-composed launch-time injection with trust framing and marker-escaped disabled-region wrapping: `fork.yml` (25 lines) + `fork_history.py` (12 lines).

## Recommendation (phased)

- **Phase 0, today, zero code** — payload/pointer discipline; a machine-parseable cursor header per message; split the ~9 KB charter out of the board (three epochs re-authored it in 3 hours); schedule the continuation monitor *before* risky work.
- **Phase 1 — `#board:<id>` xprompt** modeled on `fork.yml`: byte-bounded, cursor-aware, author-classified (operator entries outrank agent entries), disabled-region wrapped. No Rust, no new type. Trial it as a project xprompt first; if it doesn't feel powerful in two cycles, delete one file.
- **Phase 2, only if Phase 1 earns it** — `sase board` as a sibling primitive over append-only JSONL (the existing `~/.sase/projects/*/​*.jsonl` + `.lock` pattern), project-*optional* so machine-wide boards work, linked to beads via a new `board:` ref kind rather than a new issue type.
- **Phase 3, only on demand** — `%if`/`%wait` board gating via the existing admission coordinator.
- **In parallel, independently** — move the supervision loop onto durable execution (an AXE chop under a lumberjack, or `sase proc`). A chop can't die at a gate. **Fixing the message board will not fix the chain, and fixing the chain is worth more.**

Also flagged: the board is a shared write surface read into many agents' prompts — copy `#fork`'s `wrap_disabled_region` escaping exactly, and make provenance structural rather than prose.
