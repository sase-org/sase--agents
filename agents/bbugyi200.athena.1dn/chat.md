# Chat History - ace-run (1dn)

- **TIMESTAMP:** 2026-11-17 16:00:46 EST
- **MODEL:** claude/opus
- **AGENT:** 1dn

## Prompt

#gh:gh_sase-org__sase I launched a macro swarm using the prompt shown in the ~/tmp/research_prompt.txt
file, but only 6 agents were launched in the research swarm. I was expecting 8 (the
image and linker agents were not launched). Can you dig into why this happened? Make
sure your report is concise, easy to understand, and contains great visuals. 
Write this research to a new markdown file under the /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/repos/research/202611/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.
%m:@xlarge

## Response

Found the `#research_swarm` macro definition; now checking how `image`/`linker` gating evaluated in your actual launch.

Locating the actual swarm run (launched ~15:44 under the `bob-cli` project) to see which agents were created.

Found an earlier swarm (`research.63`, Nov 16) that launched all 8 — now hunting for the run matching your prompt to compare.

Still looking for the actual 6-agent run — widening the search to the last couple of days.

Swarm isn't recorded on athena (latest clan is `research.64`, all 8 agents), so I'll reproduce the expansion of your exact prompt locally to find what drops the segments.

Key lead: commit `efc66a420` ("evaluate authored commands before interpolating data") landed at 15:12 today, and the installed editable `sase` runs it. Reading that diff now.

Now let me see what `expand_single_macro` does with the guard after the commit.

The commit includes `_unwrap_condition_tokens` for exactly this case, so the cause may be subtler. Running the real swarm expansion on your prompt to see the output directly.

Reproduced: the expansion yields exactly 6 segments — `image` and `linker` are dropped at expansion time. Now pinning down which step drops them.

The `%if` filter itself keeps image+linker (9→8, only audio dropped correctly), so something *after* filtering loses them. Dumping the post-filter text.

Found it: the text has 7 `---` separators (8 segments) but the fence-aware splitter only returns 6. Checking whether a broken code fence is swallowing the last two separators.

Bisected: parent commit `71f0060927` → 8 segments; `efc66a420b` → 6. Quickly checking whether the `sase macro expand` failure I hit earlier is the same commit.

Both symptoms trace to `efc66a420b`. Let me quickly check whether your actual run lives on another tailnet machine, since it isn't on athena.

Apollo has today's swarms. Viewing the rest of the list.

research.59's lead is running now, and research.58's lead is waiting. One last check: how the splitter treats the fence lines, so the report describes it accurately.

Root cause fully confirmed. Loading the Mermaid skill for the report's diagrams and opening the research repo.

Research repo path matches yours. Before writing, I'll quickly validate a candidate fix in a scratch copy (not the repo) so the report's recommendation is tested.

The one-line fix restores all 8 segments with zero stray markers. Checking whether it also fixes the separate `sase macro expand` failure.

Separate bug confirmed (unaffected by the fence fix). Pulling the exact lines from your real `research.58` lead prompt on apollo for the report.

Now drafting the two Mermaid figures and rendering them to check fit.

Global `mmdc` can't find Chrome; trying the pinned CLI / a system Chromium.

Two fixes needed: the `␀` glyph renders as a box in fig 1, and fig 2's subgraph titles are truncated and stacked in the wrong order. Revising.

Subgraph titles still clip their last word (a Mermaid label-width quirk). Trying markdown-string titles.

Figures pass (82.7% and 92.3% fit). Checking an existing report's conventions before writing.

Writing the report now.

Making one table cell more robust (triple backticks inside an inline code span render inconsistently).

Figures render cleanly. Registering the report as a durable snapshot.

Registered (`file:explicit:c1798ebb9b8fdad85a57743d`). This regression is worth tracking, so I'll file it as a bug task bead using the required duplicate-check flow.

No duplicate task. The regressing commit came from phase `sase-1tc.1.1.2`, and epic `sase-1tc.1.1` is still in progress, so checking in-progress epics (step 6).

The regression was caused directly by this active epic's phase `sase-1tc.1.1.2`, so per policy it belongs on epic `sase-1tc.1.1` as a `DISCOVERED ISSUE:` note, not as a new task.

The note is recorded on the epic. Now finalizing the turn.

Your prompt was fine. A bug added to sase's macro engine today stopped the image and linker agents from launching. Their prompts were glued onto the end of the lead researcher's (`.final`) prompt instead of becoming separate agents.

**Cause:** commit `efc66a420b` ("evaluate authored commands before interpolating data"). It now wraps every `{{ }}` value in the macro template with hidden marker characters. `#research_swarm` prints its file tree through a Jinja macro inside `{{ }}`, so that text got wrapped twice, and the cleanup step left two markers behind. One sits in front of the code block's opening fence, so the parser no longer sees it as an opening fence and instead treats the closing fence as one that never closes. That "open" code block hides the last two `---` separators, so 8 segments split into 6. The `%if(should_run=…)` check was not the problem: I traced it and it kept image and linker.

**What happened on apollo** (the run isn't on athena):

| Time | Event | Agents |
|---|---|---|
| 14:27 | `research.57` (a different prompt) | 8 |
| 15:23 | apollo's sase checkout updates to `efc66a420b` | – |
| 15:30 | `research.58`, your prompt | 6 |
| 15:37 | `research.59`, your prompt again | 6 |

**Evidence:**
- Expanding your exact prompt gives 8 segments with the commit before (`71f0060927`) and 6 with `efc66a420b`.
- Both real `.final` prompts on apollo contain the linker and image instructions plus 4 leftover markers.

**What this means for your current runs:**
- `research.58` and `research.59` are duplicate swarms for the same prompt. `.59`'s lead was running when I checked; `.58`'s was still waiting on its researchers.
- Neither will produce an infographic or a published `<name>.md`, because the lead leaves that to a linker that never launched. You may want to kill one of the duplicates.

**Fix:** a one-line change to `_marking_finalize` in `src/sase/macro/_jinja.py` that strips the inner markers before wrapping. I tested it on a scratch copy only (the repo is unchanged): your prompt expands to all 8 segments with no leftover markers.

**A second bug from the same commit:** `sase macro expand` now fails on this prompt, because `#research(suffix=…)`'s argument check sees a hidden placeholder instead of the real value. The one-line fix doesn't cover it.

I filed both bugs, with the repro and the proposed fix, as a `DISCOVERED ISSUE` note on the in-progress epic `sase-1tc.1.1`, which made the commit, rather than as a new task bead (bead policy for issues an active epic caused).

The report has two rendered Mermaid diagrams, plus the timeline and evidence tables. It is registered as `research:202611/research_swarm_missing_image_linker_agents.md` (`file:explicit:c1798ebb9b8fdad85a57743d`), and the research repo commit is declared.

Report: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_32/sase/repos/research/202611/research_swarm_missing_image_linker_agents.md`
