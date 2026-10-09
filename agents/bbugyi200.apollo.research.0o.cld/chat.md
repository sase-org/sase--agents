# Chat History - ace-run (research.0o.cld)

- **TIMESTAMP:** 2026-10-08 21:56:19 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0o.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_202653.md`

## Prompt

%id(cld, clan=research.0o)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0o.cdx`, `research.0o.grk`, `research.0o.mus`, `research.0o.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to make the case that Hermes can do everything that sase can and that the
smart move (for just about any user except for many me) would be to not bother with
sase.

Can you do some research with the goal of supporting/refuting that claim? Make sure that
this analysis / comparison is based on the feature sets of each product. Do not consider
popularity / adoption. End your analysis with a recommendation. If you think sase
realistically might have a role to play (as a tool used by many, not just me), justify
why and describe what that role is. 
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

Reading prior Sept 2026 comparison as a baseline; next I'll verify what's changed in Hermes and sase since then.

Both surveys are back; I'm spot-checking the claims that decide the verdict (subscriptions, vendor-CLI lanes, catalog plugins) before writing.

Verification done; I'm confirming two last Hermes details (headless mode, the reverted durable-approval commit), then writing the report.

Report written and tally corrected; now registering it as a durable artifact.

Registration succeeded. Now the final declaration.

The report is written and registered. Its conclusion splits your claim in two:

- **"Hermes can do everything sase can" is false.** I checked 20 sase capabilities against the current Hermes code (HEAD `1e0c7730d7`, 2026-10-08, release v0.21.6). Hermes's core product matches 5 of them. Another 4 need an opt-in setting or an experimental plugin, 6 are only possible through community plugins or by the Hermes model improvising in its shell, and 5 have no equivalent at all.
- **"Most users should not bother with sase" holds up.** It's the better claim to make.

**Where Hermes falls short.** These are design differences, not missing features Hermes will add next month:
1. **Other vendors' coding tools as workers.** Hermes can't run Claude Code, Codex, Grok Build and the rest as supervised workers on one task board. Its own docs still say adding external coding tools to its task board is "not yet a paved path." Only Codex is supported, as an opt-in setting.
2. **Who commits.** In Hermes the agent runs `git` and `gh` itself. sase does the commits, tags each one with which agent and plan produced it, and fails a run that leaves uncommitted work.
3. **Approvals.** Hermes approvals block the agent and are denied after 300 seconds with no answer. Hermes added approvals that wait until answered on 2026-10-01 and reverted the change the same day. sase's approvals end the agent's turn and can be answered days later.
4. **Project memory.** Hermes's memory is per user and written by the agent. sase's is stored in the repo, edited by people, delivered the same way to every vendor's tool, and logs every read.

**Where Hermes is ahead.** Hermes's task board is a real coding pipeline, and some of it sase lacks: a review step for each task, a gate that waits for required CI checks, and goal loops checked by a judge model. Hermes also offers sandboxing, Windows support and 28 chat platforms. sase costs every user something:
- Linux and macOS only, and still alpha.
- Every agent runs with its permission checks turned off and no sandbox.
- A lot of concepts to learn.
- No release since 0.17.1 (2026-08-29), so everything newer exists only on the main branch.

**Subscription pricing, which is easy to get wrong.**
- **Claude:** Anthropic's support page (updated 2026-10-07) says `claude -p`, which is how sase runs Claude, still counts against your normal plan limits. Hermes's built-in Claude login only works on Max with purchased extra-usage credits, and it presents itself to Anthropic as Claude Code. Hermes reaches the normal plan cleanly only through an experimental plugin.
- **Codex:** both tools can use a ChatGPT subscription through Codex's own login.

**Recommendation:** Make the practical argument and drop the "everything" claim. sase does have a role beyond you: a control layer for any developer who runs many frontier coding tools from several vendors at once on their own trusted code. That user supervises from a distance and needs every change traceable and landed through a controlled path. To reach that group, sase would need:
- a new release;
- an opt-in sandbox mode;
- a smaller starting set of features for new users;
- a review step for each task and a gate that waits for required CI checks.

It should also work alongside Hermes rather than compete with it. Hermes has a headless mode that sase could drive like any other agent tool.

The comparison would flip if Hermes added three things: support for other vendors' coding tools on its task board, approvals that wait until answered, and commits made by Hermes itself rather than by the agent.

One harness note: a helper's report triggered a warning because it quoted the permission-bypass flags sase passes to each vendor tool, as documented in sase's `docs/llms.md`. That was documentation text, not an instruction.

Registered as `file:explicit:c59826925f906fbe1118e52a` (label `research:202610/hermes_instead_of_sase_feature_test__cld.md`). The commit is declared and the host will make it after this turn.

Sources:
- [Use the Claude Agent SDK with your Claude plan](https://support.claude.com/en/articles/15036540-use-the-claude-agent-sdk-with-your-claude-plan)
- [Monthly API credits for Max and Team plans](https://support.claude.com/en/articles/17154008-monthly-api-credits-for-max-and-team-plans)
- [Zed blog: Anthropic subscription changes](https://zed.dev/blog/anthropic-subscription-changes)
- [Runtimewire: Hermes Agent v0.20.0 voice/A2A](https://runtimewire.com/article/nous-research-hermes-agent-v0200-voice-a2a)

Report: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/hermes_instead_of_sase_feature_test__cld.md`
