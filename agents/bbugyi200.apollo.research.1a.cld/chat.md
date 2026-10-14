# Chat History - ace-run (research.1a.cld)

- **TIMESTAMP:** 2026-10-14 09:39:48 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1a.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261014_091543.md`

## Prompt

%id(cld, clan=research.1a)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.1a.cdx`, `research.1a.grk`, `research.1a.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure about our recent migration from agent instruction files to instruction
bundles (see the sase-1ko epic bead for context).

- The thing I am worried about is that an agent's core instructions are no longer
  transparent.
- I used to be able to just read the AGENTS.md file to understand what initial /
  project-level instructions a sase agent was given, for example. But now new users
  and/or non-sase agents need to generate it using a `sase` command I'm assuming?
- Also, it is not clear to me what the benefits are of this new solution? Your report
  should iterate over all of the immediate and long-term benefits.

Can you do some research with the goal of helping me decide whether or not I should
proceed with this work or revert it? 
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

Reading the E3 plan and the earlier research behind the instruction-bundle migration; next I'll check the code and the current state of the repo.

Still gathering evidence: reading the original design report to list the benefits it claimed, then I'll check the code and the latest acceptance results.

Comparing what agents actually receive now with the committed AGENTS.md; next I'll check the acceptance record and the post-cutover data.

Checking the code size and cost of the migration, and how a human or non-SASE tool would see the instructions today.

Prior research never weighed transparency as a cost, which is worth noting. Reading the fresh-clone report next, since it covers new users and non-SASE tools.

Confirmed my own run has its delivered bundle archived. Checking that the inspection command works on this run, then I'll write the report.

Last evidence check: the pre-E3 readiness review's bottom line. Then writing the report.

I have enough evidence. Writing the report now.

The report is written and registered. Submitting the final declaration so the host commits it.

I recommend keeping E3, the change that's now live, and changing E4 instead. Your transparency concern is valid, but the loss you're worried about hasn't happened yet. It's scheduled for E4, which isn't planned or approved.

**Where things stand today:**
- **`AGENTS.md` is still committed and still regenerated.** All 20 instruction files are still in git, and a test checks that the committed `AGENTS.md` matches what agents now receive.
- **It still covers nearly everything an agent gets.** I compared it with the bundle I received for this run. It's missing only your home-layer notes and one per-provider section. Otherwise the differences are heading numbers, line wrapping and a marker comment.
- **New users and non-SASE tools don't need a `sase` command yet.** E3 changed only agents that SASE launches. A fresh clone, GitHub, or a plain `claude` or `codex` session in a checkout sees exactly what it saw before.
- **E4 is where the loss would come from.** It plans to replace `AGENTS.md` with a stub of at most 80 lines and move the full text into gitignored files you'd have to generate with `sase`.
- **The reason E4 removes the file no longer holds.** It was that Codex couldn't ignore a committed `AGENTS.md`. That turned out to be wrong, and E3 already tells Codex to ignore it. Claude, Grok and Muse runs also ignore it now, so keeping it costs nothing at runtime. It's also what agents fall back to when a bundle can't be delivered.
- **Reading `AGENTS.md` was never the full picture.** Before E3, Claude and Codex got the SASE rules twice and Grok got nothing for four weeks. Grok and Muse never got your home notes, and the per-provider instructions were hidden in Python code. Now `sase instructions show NAME` prints the exact text a given agent received.

**One thing did get worse.** The Agents tab row "AGENTS.md as launched" now points at a file explicit-delivery agents didn't load, and no part of the TUI can open the bundle yet. Two smaller wording issues are stale too. It's a small fix; I didn't file a task for it because this research may change E4.

The report lists 22 benefits. Only one actually requires dropping the full committed file: no more regeneration churn in commits. That's the smallest one. `AGENTS.md` changed in 88 commits over 60 days, and 83 of those were already editing memory or the generator. The main immediate benefits are:
- the SASE rules arrive once instead of twice for Claude and Codex, about 0.8k tokens saved per call;
- Grok and Muse now get your home notes;
- the per-provider instructions are visible with `sase instructions render`;
- Claude helpers get proper helper instructions;
- context no longer varies with which workspace an agent landed in;
- you can see exactly what each agent was given.

There's no evidence yet that agents behave better or worse. Codex, Grok and Claude switched over today, there are only about 20 finished runs, and Muse can't run until its quota resets on Oct 19.

**Options:**

| Option | Result |
| --- | --- |
| A. Turn the four per-provider flags off | Back to the old delivery. No transparency gain, since `AGENTS.md` never went away. |
| B. Run E4 as planned | Full instructions disappear from GitHub and fresh clones. |
| **C. Keep E3 and re-scope E4 (recommended)** | Keep a full, checked `AGENTS.md`. Delete the `GEMINI.md`, `QWEN.md` and `OPENCODE.md` copies (20 files → 8). Skip the stub and the generate-it-yourself machinery. |

**Next steps:**
1. Make sure the decision record from the final E3 phase says the committed `AGENTS.md` stays.
2. Let the 7-day trial run, with Muse starting after Oct 19.
3. Turn a provider's flag off only if its missed final declarations rise more than 2 points above the baseline.
4. Be skeptical of E7. Instructions that vary by agent are the one change that makes "read one file" impossible by design.

The report is registered as an artifact (`file:explicit:75a55feddaacdfe0612a308f`), and the host will commit it to the research repo.

Files are in `sase/repos/research/202610`:
- instruction_bundles_transparency_proceed_or_revert__cld.md
