# Chat History - ace-run (research.2q.cld)

- **TIMESTAMP:** 2026-09-27 09:10:30 EDT
- **MODEL:** claude/opus
- **AGENT:** research.2q.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260927_083447.md`

## Prompt

%id(cld, clan=research.2q)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.2q.cdx`, `research.2q.grk`, `research.2q.mus`, `research.2q.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add
support for dynamic sub-tabs to the "Agents" tab.

- We should add the `%tab:<tab_name>` directive to support this.
- If the `%tab` directive is not used explicitly in the prompt used to launch a sase
  agent, then we should default to launching that agent on a special "main" tab.
- If there is only one tab that has agents on it, then we should not show any tabs at
  all (i.e. keep the current behavior).
- Machine Tabs
  - We should add a new "machine tabs" glossary memory web term that describes this
    concept.
  - When remote machines are configured on the current machine, we should automatically
    show `local` instead of `main` for the main tab for agents that were launched on the
    current machine. For remote agents, we should automatically replace `main` with
    `<machine_name>` where `<machine_name>` is that machine's configured name.
  - A good icon should be rendered next to the machine tabs in the sub-tab title bar on
    the "Agents" tab (this includes "local").
  - Any agents that are launched with the `%tab:<tab_name>` directive should always use
    `<tab_name>` as their tab (on all machines). This will allow us to, for example,
    group all agents related to a particular project on a single tab regardless of which
    machine each agent ran on.
- We should not support an "ALL" sub-tab that shows all agents. Instead, we should
  modify the `o` option in the panel that is shown when the `o` keymap is used on the
  "Agents" tab. Namely, we should add support for a 3rd view that merges all tribes and
  all tabs (instead of just all tribes) into a single panel. This option should also
  support its current behavior (merge all tribes--but do not merge tabs) by cycling
  through the 3 views. We should also add a new `O` option that does the same thing as
  the `o` option but in the opposite direction.
- Some previous research can be found in the agent_machine_tabs_and_cluster_semantics.md
  file in the research sidecar repo. This research file should be reviewed before
  performing your own research. Note, however, that this research file focuses too much
  on the specific case of machine tabs, does not prioritize dynamic tabs, and is not
  ambitious enough overall.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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

I've read the earlier machine-tabs research. Next I'm loading the related SASE memory notes and glossary terms, then I'll look at the Agents-tab code.

Codebase map is back. Now I'm reading the key files directly: the grouping modal, the tab strip, the Artifacts dynamic sub-tabs, and why the old `%tribe` directive was retired.

Still gathering evidence. Next: checking whether the earlier machine-tabs research already became beads or plans, and reading the tab-strip and launch-context code.

Reading the tab-strip widget and the Artifacts dynamic-tab code, which is the closest existing model for dynamic sub-tabs.

Checking how the `'` jump-hint system works, since it could give direct tab jumps without a new key.

Checking in sase-core whether the remote fleet feed would carry a new tab field the same way it carries tribe today.

Now testing which candidate machine and tab icons the TUI's bundled fonts can actually render.

Next: the CLI rules note (a `sase agent tab` command is likely part of the design) and the existing tribe-assignment flow, which a "move to tab" action would mirror.

I have enough code context. Verifying a few precedents I plan to cite (env-based tribe inheritance, the palette hash, the dispatch conflict list), then I'll write the report.

Last check before writing: which `g`-prefix keys the prompt bar already uses, so a proposed "pick launch tab" key doesn't collide.

I've verified the facts I need. Writing the report now.

`gT` is already taken in the prompt bar (it opens the snippets panel). Fixing the report to use a free key.

Report fixed. Registering it as a durable artifact snapshot.

Registration succeeded. Now the final declaration.

I wrote the report and registered it as an artifact; the host will commit it to the research repo. My recommendation is to build this feature, with a few changes to the requirements that are listed below.

- **Report:** `sase/repos/research/202609/agents_dynamic_sub_tabs__cld.md`
- **Artifact:** registered as `research:202609/agents_dynamic_sub_tabs__cld.md` (`file:explicit:8322f11f4bf601ff66079e47`).

**Recommended design:**
- **`%tab` sets a stored label for display only.** It goes into the agent's own record and into the feed other machines read, so every machine puts the agent on the same tab. The tab applies to the whole clan, session or workflow, so none of them is ever split across tabs. Tabs are never targets for `%wait` or `%hold`, which keeps them safe to rename or move.
- **The default tab is worked out when displayed, never saved.** An agent without `%tab` shows on `main`, or on `local` / the machine's configured name when remote machines are set up. Enrolling or renaming a machine therefore never needs a data migration.
- **The tab bar is dynamic.** It appears only when two or more tabs have agents. It sits in the existing, normally hidden header row above the agent list. Each tab shows a count and a "needs you" badge. Machine tabs use a `⌨` icon (unused elsewhere and supported by the TUI's bundled fonts); `main` uses `⌂`; named tabs use `◇` and get the same color on every machine without any config.
- **`o` becomes a three-step zoom: Tribes → Tab → Everything.** `O` goes the other way. With only one tab it stays today's two-way toggle, so there's no step that does nothing.
- **Shared logic belongs in sase-core.** Tab-name checks, resolving which tab an agent is on, the `%tab` directive definition and the new feed field all go there. Without the core change, `%tab` would be silently dropped for some launches, including remote ones.

**Changes to your requirements (each is labelled A1–A11 in the report):**
- **Inherit the current tab when launching (A1).** If you launch from a named tab, the new agent goes there too. The prompt bar shows the tab, and it is written into the prompt as `%tab`. You can override it with `%tab:main` or a new `gb` picker. Without this, a new agent vanishes from the tab you're looking at.
- **Agents launched by other agents inherit their launcher's tab (A2).** This keeps epics and helper agents with the work that started them.
- **`[` / `]` switch tabs (A8).** This matches the Artifacts tab. Card-block stepping moves to `(` / `)`.
- **Agents can be moved between tabs after launch (A10).** This is through the `N` dialog and a new `sase agent tab` command.
- **Use `local` everywhere for "this machine" (A6).** The TUI currently says `here` in four places, which would clash with the new tab name.
- **Smaller rules:**
  - `%tab:main` is allowed and means "default tab", while `%tab:local` is reserved.
  - Tab names are lowercased.
  - A search query changes tab counts but never makes the tab bar appear or disappear.
  - A dispatch to a remote machine whose sase is too old to understand `%tab` is refused with an upgrade message. Without that check, the literal text `%tab:foo` would end up in the agent's prompt.

The report closes with a six-phase implementation plan and five open questions for you. The main one is whether launch-from-tab inheritance (A1) should be on by default.
