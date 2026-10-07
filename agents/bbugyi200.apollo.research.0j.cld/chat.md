# Chat History - ace-run (research.0j.cld)

- **TIMESTAMP:** 2026-10-07 17:45:09 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0j.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_173144.md`

## Prompt

%id(cld, clan=research.0j)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.0j.cdx`, `research.0j.grk`, `research.0j.mus`, `research.0j.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you help me write the very first 2-3 paragraphs for the first sase blog post? This
content is meant to serve as the introduction for the rest of the post. Review related
notes and tasks in my Obsidian vault (i.e. the ~/bob/ directory) before performing your
own research. End your analysis with a fully written introduction. 
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

I'm reading through the blog notes in your Bob vault (`sase_blog`, `sase_blog_0`, `why_sase`, and the earlier review and strategy notes) before I draft the intro.

I've read the July Fable draft. Next I'm going through the authorship-gap and zettelkasten research the vault links to.

Still going through the vault history. I'm looking for your original WisprFlow brain-dump on the first post.

I've finished the core vault notes. Now I'm skimming the older launch-strategy research for advice about the opening specifically.

I've verified a few outside facts (the SASE paper, Shumer's essay, Boris Cherny's setup). Now I'm working out the date of the Boris tweet and pulling sase's current stats.

Your vault shows sase started out as `gai` inside your dotfiles. I'm checking when `gai` first appeared so the intro gets the origin date right.

The origin story is clear now: sase began on 2025-10-20 as a 98-line LangGraph toy called `gai`. I'm checking when Claude Code itself showed up in your dotfiles.

I have enough to write. Before drafting, I'm checking two facts the draft relies on: what the first `tmux_ai_window` actually launched, and what share of the Python is tests.

Research is done. I'm writing the report now; first I'm making sure the filename is free.

Report written. Now registering it as an artifact.

Registration succeeded. Now the final declaration.

The intro is written and saved, and the report is registered as an artifact (`explicit:859dcb17b92c0de885197a58`).

**Report:** `sase/repos/research/202610/sase_blog_0_introduction__cld.md`

## Where it comes from

- **Paragraph 1 is your own sentences.** The opening of `why_sase.md` ("Maybe it was my pride…") answers the unfinished line in `sase_blog_0_legacy_notes.md` ("I could say… Google… but the truth is…"). I joined them and turned the "[insert dolla dolla bills]" placeholder into the joke.
- **Paragraphs 2 and 3 follow your own notes.** They fill in the bullets from `why_sase.md` ("It started with Claude Code", "Something big is happening", stats with "Motion isn't progress") and the outline step "Boris method → tmux_ai_window". The "I've tried a lot" passage in the `sase_blog_0` Contents section is used almost word for word.
- **The specific details come from the git history in your dotfiles.** sase started on 2025-10-20 as `gai`, a 98-line LangGraph script whose only tools were a fake weather lookup and a calculator. The first `tmux_ai_window` (2026-01-14) was 19 lines that opened a tmux window running `claude --dangerously-skip-permissions`. That was 12 days after Boris Cherny's setup thread. The sase repo's first commit was on Valentine's Day 2026.

## Fix before publishing

- **Stats:** the commit and line counts are from today. The report has the commands to re-run them on publish day.
- **"Motion isn't progress":** I couldn't trace it to any Codex podcast episode, so the intro doesn't attribute it.
- **Google:** the intro keeps your phrase "while working at Google". Whether to name the employer is your call.
- **Overlap with the published post:** the current post opens with a Boris paragraph that this intro now repeats. The report suggests a replacement first sentence for the next section.

The report also has a two-paragraph alternate, a brief for the timeline infographic, and a source for every sentence.

## The introduction

> I've always been proud to call myself a Software Engineer. It's always been an easy thing to take pride in (the dolla dolla bills didn't hurt). I could tell you that I started working on sase because of the obvious need for structure I saw while working at Google, or because I saw an opportunity to add some value, but the truth is, maybe it was just my pride. sase is my attempt to take back some control from this thing that seemed like it was coming for a core part of my identity.
>
> And it was coming fast. The first commit in my dotfiles that credits Claude Code is from April 30, 2025, two weeks after OpenAI released Codex CLI, and all it did was move some Lua files from one directory to another. Eight months later, Steve Yegge released Gas Town to run a whole town of coding agents at once, and the next day Boris Cherny, the creator of Claude Code, shared a setup that kept five Claudes busy in five numbered terminal tabs. By February, Matt Shumer's "Something Big Is Happening" was comparing the moment to February 2020 and racking up tens of millions of views.
>
> I responded the only way I know how: I started trying things. sase began on October 20, 2025 as `gai`, a 98-line LangGraph script in my dotfiles whose only tools were a fake weather lookup and a calculator. Twelve days after Boris's post, I bound `prefix + A` to a 19-line script that opened a new tmux window running `claude --dangerously-skip-permissions`. On Valentine's Day 2026, `gai` got its own repo and a new name, borrowed from a paper by Ahmed E. Hassan and colleagues that proposed something called Structured Agentic Software Engineering. That repo now holds 15,755 commits and over two million lines of Python, more than half of it tests. Motion isn't progress, though. I've tried a lot. I've kept trying because, even after all this time, I'm still not quite sure what I want, which frustrates me. This post is about the parts that stuck, starting with that tmux keybinding.

Sources:
- [Anthropic Claude Code release notes](https://docs.anthropic.com/en/release-notes/claude-code)
- [Gigazine: Codex CLI](https://www.gigazine.net/gsc_news/en/20250417-openai-codex-cli)
- [arXiv 2509.06216](https://arxiv.org/abs/2509.06216v1)
- [heise: Gas Town](https://heise.de/-11178824)
- [VentureBeat: Boris Cherny's workflow](https://venturebeat.com/technology/the-creator-of-claude-code-just-revealed-his-workflow-and-developers-are)
- [Wikipedia: Something Big Is Happening](https://en.wikipedia.org/wiki/Something_Big_Is_Happening)
- [Fortune on the Shumer essay](https://www.fortune.com/2026/02/20/something-big-is-happening-in-ai-but-thats-the-only-thing-matt-shumer-got-right)
