# Chat History - ace-run (research.3n.cld)

- **TIMESTAMP:** 2026-10-05 07:37:02 EDT
- **MODEL:** claude/opus
- **AGENT:** research.3n.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_065248.md`

## Prompt

%id(cld, clan=research.3n)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.3n.cdx`, `research.3n.grk`, `research.3n.mus`, `research.3n.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to a single SASE.md file
that defines a spec for the agent instruction file that gets used to contruct the
appropirate agent instruction file dynamically in ephemeral workspaces before launching
sase agents in those workspaces.

- I think that this architecture change will allow us to fix a few bugs identified in
  the agent_instructions_budgeted_router.md file in the research sidecar repo (e.g. Grok
  reads both AGENTS.md and CLAUDE.md and codex doesn't read the ~/AGENTS.md file at
  all).
- Also, this would unlock the ability to specify that parts of the agent instruction
  file should only be rendered for certain agents. I'm not sure how we should identify
  these agents, but my first thought would be to use a new `%tag` directive to tag
  certain agents and then only render some parts of the agent instruction file for
  agents with certain tags. This is just my first instinct though. You should think hard
  about the best way to implement this.
- I think I'm probably forgetting a few other high-value use-cases (see if you can
  identify any that I missed).

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
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Reading the prior router research done; now surveying how SASE generates instruction files, how providers load them, and the directive system.

Verifying empirically whether Codex and Grok actually receive the home/project files, using recent session logs.

Key finding: providers load instruction files very inconsistently. Verifying Grok's actual rule-file loading with `grok inspect`.

Still verifying Grok: checking where it records loaded project instructions in its session files.

Major finding: since ~2026-09-10 Grok SASE runs load **zero** instruction files (not two). Checking the likely cause (Grok folder-trust gating).

Verified: Codex *does* get `~/AGENTS.md` via the shadow-home bridge (so that claimed bug is stale), but Claude and Codex both receive the shared SASE contract twice. Quantifying that overlap now.

Checking how Muse (29% of recent runs) actually loads instruction files.

Testing whether Grok's instruction loss shows up in behavior: comparing `/sase_final` declaration rates by provider before and after 2026-09-10.

I have enough evidence. Writing the report now.

Report written. Registering it as a durable artifact.

Artifact registered. The Grok zero-load is a discovered bug worth a task bead — running the new-task flow.

No duplicate (closed `sase-lq` is the opposite symptom) and no causally related epic. Creating the bug bead.

Bead filed. Now the final declaration.

I've written the report at `sase/repos/research/202610/sase_md_instruction_bundles__cld.md` and registered it as `research:202610/sase_md_instruction_bundles__cld.md` (artifact `file:explicit:4df3015614b12471a4cdc48e`). My verdict: build this, but change four things about how.

## The bugs are different from what you described
I checked each provider's own session logs to see what agents actually loaded:
- **Grok has loaded no instruction files at all since about 2026-09-10.** Before that it loaded both `AGENTS.md` and `CLAUDE.md`. Since then, 568 of 568 Grok sessions in SASE workspaces loaded nothing. In a workspace, `grok inspect` reports `Project trusted: no` and zero instructions; the root cause isn't confirmed. Grok is 13% of runs. Over the same window, the share of non-research Grok runs that submitted a final declaration fell from 60% to 26%; Claude and Codex moved 6 points or less. That's a correlation, not proof.
- **Codex does read `~/AGENTS.md`.** The shadow-`CODEX_HOME` bridge has supplied it since 2026-05-31, and recent Codex sessions show it. The real problem goes the other way: Claude and Codex both get the shared SASE contract twice, from the home file and the project file. That's about 790 tokens on every call, plus two conflicting "linked repos" lists.
- **Muse (29% of runs) never sees the home layer.** That means no tailnet, Obsidian or chezmoi context.
- **According to their docs, OpenCode never reads `OPENCODE.md`, and Qwen loads both `QWEN.md` and `AGENTS.md`.**

## What I'd change
1. **Deliver the instructions instead of writing them into the workspace.** Each provider adapter should pass a fresh render on every call: Claude via `--append-system-prompt-file`, Grok via `--rules`, Codex via its shadow-home `AGENTS.md`, and Muse and Antigravity via a prompt prefix. Writing files into the workspace fails in seven ways. The worst: the files are tracked, so the host would commit them, and Grok skips gitignored and untrusted files anyway.
2. **Make `SASE.md` the layout and conditions, not the content.** The memory notes stay the content and gain a `when:` frontmatter key. Putting all the text in one file would undo the core/reference/web split and the audited reads.
3. **Don't add `%tag`.** You already had a `%tag` directive; it was renamed `%group` and then replaced by tribes. Old `tag` metadata is still read as a tribe, so a new `tag` field would collide with that. Every conditional section I found can be keyed on facts SASE already knows at launch: provider, session role, phase worker, tribe, macros used, commit method and host. If free-form labels are ever needed, declare them as `traits` in macro frontmatter.
4. **Add a check that each provider received the instructions exactly once.** It would read the provider's own session logs and run in `sase doctor` and on a schedule. The Grok regression went unnoticed for about four weeks.

## Use cases you may have missed
- Moving the four provider-specific "single-turn" directives, now hidden in adapter Python, into the reviewable spec.
- Lean renders for monitor and gate turns, which are 12.5% of runs.
- Accurate records of what each agent actually saw; today's snapshot records files the provider may never have read.
- Rules that depend on role, such as the epic phase-worker bead rule.
- Host-specific home layers, replacing the chezmoi hostname template hack.
- Instruction sections contributed by plugins.
- Delivering the SASE contract in other people's repos without touching their files.
- A/B tests of instruction variants, measured with the existing audit logs.

The report ends with a five-phase plan. Phase 0 is a quick Grok fix using `--rules`, plus dropping the dead and double-loaded copies.

## Other things I did
- **Bug bead:** I filed `sase-1gj` (type bug, size large, status ready) for the Grok problem. The closed bead `sase-lq` covers the old double-load, so it isn't a duplicate.
- **Missing typed link:** I couldn't add the typed link between the two beads. `sase artifact link add` failed with a "bead id segment" validation error, the same one `sase bead read sase-lq` raises unless you pass `--no-links`. I recorded the relationship as a note on `sase-1gj` instead.
- **Possible CI gap:** CI appears to regenerate the instruction files before it checks them for drift, which would hide drift. I didn't run CI to confirm this.

The final declaration was accepted; the host will commit the report to the research repo.
