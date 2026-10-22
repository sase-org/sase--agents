# Chat History - ace-run (research.37.cld)

- **TIMESTAMP:** 2026-10-01 13:33:07 EDT
- **MODEL:** claude/opus
- **AGENT:** research.37.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_130220.md`

## Prompt

%id(cld, clan=research.37)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.37.cdx`, `research.37.grk`, `research.37.mus`, `research.37.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some
research with the goal of helping me come up with ideas to improve the `#research_swarm`
xprompt swarm? Think hard about how this swarm can produce better research (e.g. by
digging into what it means to build a good research agent swarm) and think hard about
how this xprompt swarm can take better advantage of existing features provided by sase
(you can also recommend new sase features if they are truly justified). End your
analysis with a ranked list of improvements you think I should consider making. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
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

Reading the `#research_swarm` xprompt and its sibling research xprompts in the plugin repo.

Surveying the research sidecar now: past swarm outputs and any earlier research about research swarms.

Reading prior SASE research on the linker agent and multi-agent collaboration (unrelated to this swarm) through audited artifact reads.

Gathering empirical data on past research-swarm runs (timings, outcomes) from the local run archive.

Subagent stats are back. Now I'll check two surprising claims myself: lead prompts showing `**` where `__` belongs, and codex researchers never searching the web.

Confirmed the `**` corruption and that a backtick fix works. Now checking whether codex researchers are launched with web search enabled.

Stats and the two bugs are verified. Next I'll pull in outside evidence on what makes multi-agent research systems work.

Outside evidence is gathered. Now checking which SASE features exist today (wait failure semantics, research search, goals, lineage deriver) before I recommend anything.

Checking how `sase var` output keys resolve for keyed swarm names, since several ideas depend on it.

Evidence gathering is done. One more check: whether the prettier `__`→`**` rewrite also hits ordinary prose prompts, not just the rendered handoff list.

Confirmed: this is a general SASE launch-time bug. Any prompt paragraph with two `__` tokens outside code spans gets rewritten. Writing the report now.

Report written. Registering it as a durable artifact.

Registration succeeded. With my report finalized, I'll file the general prettier `__`→`**` bug as a task bead, as the bead-capture rule requires.

No duplicate or causal epic found. Creating the bug bead for the prettier `__`→`**` rewrite now.

I wrote and registered my report. Registration returned `ref: file:explicit:eb1bb7818089210892be755d`. The host commits the research repo after this turn.

- **Report:** `sase/repos/research/202610/research_swarm_quality_and_sase_leverage__cld.md`
- **Label:** `research:202610/research_swarm_quality_and_sase_leverage__cld.md`

**Bottom line:** keep the swarm's basic design. Independent researchers that never talk, plus one central lead, is what the evidence supports:
- Majority voting explains most of the gain usually credited to multi-agent debate.
- In a Google study, a central coordinator kept error amplification to 4.4×, against 17.2× for agents with no coordinator.

The weak points are what passes through that design. Researchers get only the raw prompt. The lead is told to merge, not to check claims. And nothing measures quality.

**Two confirmed bugs:**
- **Corrupted lead input.** SASE runs prettier over every agent prompt at launch. It rewrites paired `__` to `**`, so all 39 lead prompts and all 4 linker prompts since 2026-09-21 got report labels and paths that don't exist (e.g. `topic**cdx.md`). I reproduced it, and it hits any prompt with two `__` tokens in one paragraph. Wrapping the fields in backticks avoids it; I tested that. I filed it as bug bead `sase-1dx`.
- **No web access for codex researchers.** `codex exec` is launched without its `--search` flag. None of the 105 past codex researcher runs made a web call.

**Ranked improvements:**
1. Backtick the report fields in the lead and linker prompts now, then fix the prettier rewrite in SASE.
2. Give researchers a proper brief:
   - how to research: search prior research with `sase plan search --kind research`, cite a checked source for each key claim, use the web for outside topics;
   - a fixed report structure ending in a table of the claims the recommendation rests on;
   - a `kind` input (decide / critique / survey / debug).

   First merge the five copied researcher sections into one shared xprompt; the copies have already drifted apart.
3. Make the lead check rather than merge: list its own questions before reading any report, map where reports agree and disagree, treat agreement as weak evidence, verify key and minority claims against sources, and drop numbered headings.
4. Turn on codex web search and log it; also log Gemini's tool calls, which are invisible today.
5. Have the lead record what each researcher uniquely contributed (`sase var set`), and build a 15–20-prompt blind test set. Nothing yet shows the five-researcher `rsa` setup beats the two-researcher `rs` one.
6. Opt-in "lenses": every researcher answers the whole question, but each goes deeper on one angle. Test before making it a default.
7. An opt-in `%wait` mode that lets the lead proceed when a researcher fails. Four of 138 swarms never got a lead because of this. It's the only new SASE feature on the list.
8. Fix the stale lineage code (existing bead `sase-15r`).
9. Finish rolling out the linker once item 1 is fixed.
10. When goals reach swarms, make sure the lead or linker claims the goal, never the image agent.

**Not recommended for now:**
- **Debate rounds:** they add little over voting.
- **A scoping agent before the researchers:** it adds a serial step and gives every researcher the same framing.
- **Starting the lead before the slowest researcher finishes:** the straggler is usually claude, which may be a top contributor.
- **Bringing back the critique agent:** its output never reached the PDF you read.
- **More default researchers:** wait for item 5's data.

The statistics come from a read-only scan of 634 past research-agent runs (138 swarms, 2026-07-09 to 2026-10-01), excluding this swarm. Three caveats:
- Some failure counts were rebuilt from notifications, because the retried runs' directories were deleted.
- Codex and Gemini record no token usage.
- Gemini's research activity isn't logged at all.

I didn't open any peer report from this swarm.
