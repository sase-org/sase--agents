# Chat History - ace-run (research.2y.final)

- **TIMESTAMP:** 2026-09-30 07:14:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2y.final
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_062946.md`

## Prompt

%clan(research.2y, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] We currently store
too many prompts in prompt history (see the ~/tmp/screenshots/20260930_062115.png
screenshot for an example of a prompt that likely shouldn't have been stored).

- Namely, prompt history is meant to be used to store user prompts, each of which is
  supposed to correlate with a specific request made by a human being (by using the
  prompt input widget in the TUI or the `sase run` command to launch a sase agent, for
  example).
- Any prompt used to launch agents that belong to an xprompt swarm should not be saved
  to prompt history, but the prompt containing the xprompt swarm invokation
  (`#research_swarm`, for example) which was used by the user to launch the swarm should
  be saved to prompt history.
- Any prompt used to launch agents from routines should not be saved to prompt history.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.]]) %id:research.2y.final %m:@xlarge
%wait:research.2y.cdx %wait:research.2y.cld %wait:research.2y.grk %wait:research.2y.mus %wait:research.2y.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

We currently store
too many prompts in prompt history (see the ~/tmp/screenshots/20260930_062115.png
screenshot for an example of a prompt that likely shouldn't have been stored).

- Namely, prompt history is meant to be used to store user prompts, each of which is
  supposed to correlate with a specific request made by a human being (by using the
  prompt input widget in the TUI or the `sase run` command to launch a sase agent, for
  example).
- Any prompt used to launch agents that belong to an xprompt swarm should not be saved
  to prompt history, but the prompt containing the xprompt swarm invokation
  (`#research_swarm`, for example) which was used by the user to launch the swarm should
  be saved to prompt history.
- Any prompt used to launch agents from routines should not be saved to prompt history.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.2y.cdx`, `research.2y.cld`, `research.2y.grk`, `research.2y.mus`, `research.2y.gem` dependencies, matching by `wait_name` and the canonical research
   label's existing `__<suffix>.md` suffix. Never reassign suffixes from list order.
   Open the research repo with `/sase_repo`, then read each report through its canonical
   research reference (or the `ref` field's `file:<id>` reference if the original has
   moved) using `sase artifact read`. Do not read predecessor chat transcripts. If the
   records above do not identify exactly one report per expected suffix, stop and report
   the missing or ambiguous input instead of guessing.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move each report
   inside it as `<name>__<suffix>.md`, preserving its existing suffix. Each report's
   `source_path` is provenance for where it lives in your own opened research checkout;
   resolve its canonical repo-relative path there before moving it. Never modify the
   other agents' checkouts or the stored snapshot recorded at `ref` — only the copy in
   your own checkout moves. Preserve every file and never overwrite: on any collision,
   pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>.md
```

## Response

I've opened the research repo and read the first report (cdx); now reading the other four.

I've verified the core write path and the `sase run` entry point. Next I'm checking the provider guard, typed admission, and remote-dispatch paths.

`looks_generated` isn't exposed to Python yet, so a heuristic prune needs a new binding plus a `sase-core-revision.txt` pin move. Now looking at the screenshot directly.

Remaining checks: whether generated templates leave placeholder tags behind in a separate store after pruning, and what the documented history contract says today.

Research is complete. Now organizing the research repo: picking a collision-free stem and moving the five reports into their folder.

Reports moved. Collecting exact line numbers for the citations in the consolidated report.

Now writing the consolidated report.

Checking two claims before finalizing: what "if active" means for direct typed admission, and whether `launch_agent_from_cwd` forwards `origin`.

Both claims check out. Applying a few accuracy corrections to the report.

The layout matches the spec. The only repo I changed is the research sidecar; sase-core was only read. Submitting the final declaration.

I'd go ahead with this: history should hold only prompts a human submitted. But I'd state it as one rule — record the text a human submitted, once, and nothing a machine launched — instead of two exclusions for swarms and routines.

**What your screenshot actually shows** (I checked the rows against the live history store):
- **Epic phase launches:** the highlighted row and all the `+2`/`+3`/`+4` bursts come from `sase bead work` launching epic phases. That is neither a swarm nor a routine, so your two rules wouldn't catch it. Each epic writes one row for the whole bundle plus one per phase. That's 65 of the 79 machine rows in the 100 newest.
- **Routine rows are there too:** the 05:39 and 18:36–18:37 rows are `toobig` split jobs (14 rows).
- **The swarm rule already works:** both of today's `#research_swarm` submissions are stored as a single row each, with no member rows.
- **Across the whole store,** about 71% of the 11,587 rows are machine-generated, rising from 59% in July to 80% in September.
- **The groundwork exists:** every launch is already tagged `typed` or `generated`, but only next-word prediction uses the tag. Generated prompts are still saved to history, and their `<placeholder>` tags are learned. When a generated launch fails, its prompt also lands in your Stash.

**Requirement changes I'd make:**
1. Define it by who started the launch, not by which command was used. Agents, monitors and gate shells also call `sase run`.
2. Store your exact submitted text once, even when the launcher rewrites or splits it. Today, `%r:N` stores the rewritten per-copy prompts but never your original. When a disabled provider forces you to drop swarm members, the expanded member prompts are stored as if you typed them.
3. Relaunching a member of a swarm, epic or routine isn't a new request. Your 06:52 edit-and-relaunch of `sase-1d6.3` (with `%w:0ub` added) was stored as typed.
4. Keep storing the segments of `---` multi-prompts you type yourself.
5. Clean up the existing rows. Blocking new writes doesn't remove what's already there.

**Recommended solution:**
- **Phase 1 (one small PR):**
  - Skip storage entirely for machine launches, before placeholder learning and Stash.
  - Also treat `sase run` from routine jobs, monitors and gate shells as machine launches. Monitor and proc environments drop the "inside an agent" marker, so those are currently stored as typed.
  - Make "not recorded" the default for launch calls that don't say where they came from.
  - In the same PR, save your prompt for `%if`/`%proc` launches and `%dispatch` launches. Today they never record it, and after the gate they would leave no trace at all.
- **Phase 2:** the entry point (`sase run` or mobile) decides the text to store and it's saved once, which fixes the `%r:N`, disabled-provider, name-reuse and one-member-swarm cases. Add the relaunch rule.
- **Phase 3:** a `sase prompt prune --generated` command that previews first, backs up, and never removes anything you typed. It would delete the 79 explicitly tagged rows, plus about 8,100 older untagged rows matched by a pattern check in sase-core. That check needs markers added for routine jobs, and a random sample of what it flags found only machine templates.
- **Not doing:** a show/hide toggle, a separate launch log, or a feature flag. Cleaning the store makes a toggle unnecessary.

**Where the five reports disagreed:** mus's claim that swarm member prompts are stored on the normal launch path is wrong; the code and the live store both show one row per swarm. The claim in two other reports (cld, grk) that the screenshot has no routine rows is also wrong.

**Questions for you:**
1. Should an edited relaunch of an epic phase agent (like your `%w:0ub` edit) stay out of history? I recommend yes.
2. Should agent-proposed launches you edit before approving count as yours?
3. Are you OK deleting the ~8,100 older pattern-matched rows after a preview and backup, or should only the 79 tagged rows go?

I moved the five reports into the new folder and wrote the merged report there. The host will commit the research repo after this turn. Nothing in sase itself was changed.

Files are in `202609/prompt_history_human_submissions_only/` in the research repo:
- `prompt_history_human_submissions_only.md` (the merged report)
- `prompt_history_human_submissions_only__cdx.md`
- `prompt_history_human_submissions_only__cld.md`
- `prompt_history_human_submissions_only__grk.md`
- `prompt_history_human_submissions_only__mus.md`
- `prompt_history_human_submissions_only__gem.md`
