# Chat History - ace-run (research.5s.cld)

- **TIMESTAMP:** 2026-11-21 17:36:10 EST
- **MODEL:** claude/opus
- **AGENT:** research.5s.cld
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261121_172603.md`

## Prompt

%id(cld, clan=research.5s)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.5s.cdx`, `research.5s.grk`, `research.5s.mus`, `research.5s.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to think of the best possible name for what I now call the "prompt input widget".
This name should be added as a new glossary term that describes the widget, the way the
prompt input widget stacks work, and how the prompt input widget property panel. I want
to keep this new term concise and useful for future agents.

Can you do some research with the goal of helping me think of the best possible name?
End your analysis with a ranked list of names you think I should consider and a
recommended new glossary term entry for your #1 pick. 
First run `sase repo open research -r "Write this research report"` and use the path it prints as `<research checkout>`. Write this research to a new markdown file under `<research checkout>/202611/`.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path under the opened research checkout and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Still reading: I'm going through the frontmatter/properties panel docs and code so the proposed term matches how the widget really behaves.

Now mapping name collisions: I'm checking which "prompt *" names are already taken in the TUI (Prompts overlay, prompt_panel, and so on).

I have what I need from the code and docs. One last measurement: how often each candidate word already appears in the repo, as a collision check.

Research is done. Writing the report now; my top pick is **Prompt Composer**.

I fixed one word count after registering, so I'm re-registering so the stored snapshot matches the final file.

Now finalizing the turn.

My top pick is **Prompt Composer** (alias *composer*). The report is written and registered as an artifact under the label `research:202611/prompt_input_widget_naming__cld.md`.

**Why Prompt Composer:**
- **Industry fit:** "composer" is the usual name for a writing area plus the controls around it. OpenAI's Codex CLI calls its input `ChatComposer`, Zulip has a "compose box", and chat SDKs ship "message composer" components. Future agents will guess the meaning without looking it up.
- **No clashes:** "composer" appears only 9 times in sase, none of them user-facing. sase-core has a single hit in a test fixture.
- **Covers every mode:** the widget also writes Plan Feedback, Coder Prompt replies, hijack text and macro definitions, not just launch prompts.
- **Clean structure:** composer → prompt stack → pane, with the properties panel above the stack, the same way deck → card → block works.

**Ranked list:**
1. **Prompt Composer**: best overall.
2. **Prompt Bar**: keep the current name and just define it. Nothing has to change, but "bar" suggests a thin strip, and the widget is now a stack of panes with a panel above it.
3. **Prompt Workbench**: accurate but wordy.
4. **Prompt Slate**: the best SASE-style made-up name; it's unique in the repo, but an agent wouldn't guess its meaning.
5. **Prompt Dock**: fine, but says little about editing.
6. **Prompt Pad**: good stack-of-sheets metaphor, but searching for "pad" mostly hits CSS padding.

**Names to avoid:**
- **Prompt Stack** was the strongest from the code's side, but it's one letter from **Prompt Stash**, and the stash keys live in this same widget.
- **Prompt Input** clashes with macro inputs (`ace.prompt_inputs`).
- **Prompt Editor** clashes with `$EDITOR`.
- **Prompt Panel** clashes with the agent prompt panel on the Agents tab.
- **Prompt Deck** clashes with Agent Data Deck.
- **Launchpad** clashes with Launch Control and doesn't fit the modes that don't launch anything.

**Property panel:** it currently has four names. I'd make "properties panel" canonical (it matches the commit history and the "No properties yet." empty state) and list "frontmatter panel" as an alias for the code and border title.

**Recommended glossary entry** (`sase/memory/glossary/prompt-composer.md`, about 150 words):

```markdown
---
keyword: Prompt Composer
aliases:
  - composer
  - prompt bar
  - prompt input widget
---

The prompt composer is the TUI's bottom-docked prompt-writing widget (`PromptInputBar`)
for agent prompts, Plan Feedback, Coder Prompt replies, and bound macro definitions. It
holds a prompt stack: one or more vim-mode panes, one per agent, in top-to-bottom launch
order. Loaded text splits into panes at top-level `---`, but a typed `---` stays literal;
`g-` adds a pane, `gj`/`gk` focus, `gJ`/`gK` reorder, and the title reads
`Prompt · N agents`. `Enter` launches all panes or the current one; order alone never
sequences them — a bare `%wait` waits on the pane above. `gs` stashes the whole stack as
one [[glossary:prompt-stash]] row. One snippet or mini-macro pane may sit pinned at the
bottom and never launches. Above the stack, the properties panel (`FrontmatterPanel`,
titled `frontmatter`, toggled with `g=`) edits the stack's shared frontmatter with a
macro file's fields; `_` local macros declared there complete in every pane, and a
single-pane launch re-attaches it.
```

The aliases mean nothing in the code has to be renamed, the same way Macro still answers to "xprompt". Adding the entry is a memory change, so it should go through `/sase_memory_write`.

**Housekeeping:**
- I registered the artifact twice: after the first registration I corrected one word count in the report. The second registration (`file:explicit:79f84864ad7e8c4c6e921d6a`) matches the final file; the first one (`file:explicit:9a6862f02d1bf8034cc58a00`) is slightly out of date.
- `sase repo open research` warned that it refused to replace a mismatched plans sidecar clone under the primary checkout. It still printed the research path and everything worked.
- The report will be committed to the research repo when this turn ends.

Files are in `202611` of the research checkout:
- prompt_input_widget_naming__cld.md
