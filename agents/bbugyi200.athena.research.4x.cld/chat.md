# Chat History - ace-run (research.4x.cld)

- **TIMESTAMP:** 2026-10-19 08:26:05 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4x.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_075815.md`

## Prompt

%id(cld, clan=research.4x)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4x.cdx`, `research.4x.grk`, `research.4x.mus`, `research.4x.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We currently show the selected sase agent's instruction bundle in the file deck.

- I would like to start showing the agent's instruction bundle in a new memory deck
  instead.
- This deck would also include cards for other types of memory (and maybe macros?) that
  the agent used.
- Think hard about what other cards/blocks should be included and whether or not these
  cards actually belong in a different existing deck (the record deck maybe?).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

I'm mapping the existing deck system (MAIN, FILES, TOOLS, FINAL, RECORD) and how the instruction bundle reaches the Files deck today. Next I'll look at the record deck and the memory-reads code.

Status: no empty manifests (that was a bug in my one-off script). Retrying the drift check on an older agent.

I have what I need: data on disk, deck architecture costs, RECORD's charter, usage measurements, and prior art. Writing the report now.

Report written. Registering it as a durable artifact.

Registered. One follow-up is worth capturing: the `glossary:agent-data-deck` strand is already stale (it omits RECORD). I'll check whether a task already covers it before filing anything.

Status: the stale-glossary issue is already tracked as `sase-1kc` (its item 4 adds RECORD to `glossary:agent-data-deck`). I'll add a +1 with my independent evidence rather than filing a duplicate.

Report is written and registered, and the side finding was added to an existing task. Submitting the final declaration.

I've written the report and registered it. It's a good idea, with one change of emphasis: the deck should open on what the agent knew and used, not on the bundle text.

**Report:** `sase/repos/research/202610/memory_deck_for_agent_instructions_and_memory__cld.md`, registered as `research:202610/memory_deck_for_agent_instructions_and_memory__cld.md` (`file:explicit:f77bd08e6bba23b0e655e039`). The research repo commit is declared and the host will make it after this turn.

**Main findings**
- **Moving the bundle out of FILES is right.** Since commit `552b38f7ed`, bundle pages count toward the `files N` total. For an agent with no diffs, the bundle also becomes the default FILES page. So a research agent that touched nothing shows `files 2` and opens on 350 lines of boilerplate.
- **The bundle alone would make a weak deck.** Over five days, 401 manifests produced only 27 distinct bundles, and one bundle variant alone covered 160 runs. What differs per agent is:
  - which memory it got, and in what form (inlined, listed, or excluded);
  - what it actually read, and why;
  - at which version;
  - whether a retry today would see different text.

  `sase instructions render -a <agent>` already answers that last question in 35–78 ms ("changed sections: …"). The TUI never shows it.
- **The cards don't belong in RECORD.** RECORD holds short identity fact sheets and is the "Record only" fallback for unreadable archive entries. RECORD's `Bundle:` field also already means the archive bundle, which would be confusing next to instruction bundles.
- **Macros mostly stay out.** They're already shown twice, and only top-level macros are recorded. The exception is `#memory/<note>`: it injects memory through the prompt, and no read log or version pin sees it today.

**Changes I made to your requirements** (each is called out in the report):
- The deck opens on a **Sources** card; the bundle is the second card, titled **Instructions**. "Ledger" was avoided because the goal domain already uses that term.
- Skills are included.
- Artifact reads and opened workspaces are left where they are.
- The MAIN Context card's MEMORY section stays as the quick summary, with a link into the new deck.
- The drift check ships in the first version.
- The logic that combines manifests, reads, and skills goes in `sase-core`, with a matching CLI option.
- Adding the sixth deck is the moment to factor out a small shared structure for RECORD and MEMORY. Adding RECORD touched about 20 files and regenerated 278 screenshot images.

**Recommendation:** a new `❖ MEMORY` deck, opened with `p y`, placed after TOOLS and never chosen automatically for a new split. It has three cards:
- **Sources** (default): every memory source with its version, plus delivery status and drift since launch.
- **Instructions**: the exact bundle, broken into its sections, with one block per model call (root, helper, recovery).
- **Members**: on clans and tribes, whether every member got the same instructions.

Remove the FILES bundle pages in the same phase that ships the Instructions card. The report gives a five-phase plan and five open questions for you, such as `y` vs `e` and where the deck sits in the cycle.

**Side finding:** the glossary entry for decks still lists only four decks and omits RECORD. Task `sase-1kc` already covers this, so I added a +1 with my evidence instead of filing a duplicate.
