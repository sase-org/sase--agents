# Chat History - ace-run (research.38.final)

- **TIMESTAMP:** 2026-10-01 15:22:04 EDT
- **MODEL:** claude/opus
- **AGENT:** research.38.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_145619.md`

## Prompt

%clan(research.38, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you help me
understand what the new sase-listen repo will actually provide to users that install it?
See the sase-1e3 epic bead for context. Make sure the report you produce is useful,
concise, and beautiful.]]) %id:research.38.final %m:@xlarge
%wait:research.38.cdx %wait:research.38.cld %wait:research.38.grk %wait:research.38.mus %wait:research.38.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you help me
understand what the new sase-listen repo will actually provide to users that install it?
See the sase-1e3 epic bead for context. Make sure the report you produce is useful,
concise, and beautiful.

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.38.cdx`, `research.38.cld`, `research.38.grk`, `research.38.mus`, `research.38.gem` dependencies, matching by `wait_name` and the canonical research
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
4. Write the consolidated report to `<name>/<name>__final.md`: merge the strongest findings
   from every report above and your own research, resolve conflicts, cut duplication,
   and add missing critical context without unnecessary length.

   Do not create `<name>/<name>.md`, not even as a placeholder, because the linker
   agent `research.38.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.38.linker`, can find it:

   sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

   Use the consolidated report's actual absolute path and its path relative to the
   research repo root, for example `research:202609/<name>/<name>__final.md`. Register
   only the consolidated report, and do not pass `--move`. If registration fails,
   report that failure; do not report the task as fully complete.

Final layout:

```text
<month-dir>/<name>/
├── <name>__cdx.md
├── <name>__cld.md
├── <name>__grk.md
├── <name>__mus.md
├── <name>__gem.md
└── <name>__final.md
```

## Response

I've read all five reports. Next I'll check the points where they disagree (what works today, costs, the `--json` scope, Kokoro, Telegram chapters) against the epic, the plan, and the live repo.

Checking which commands actually work today by running the scaffold's CLI.

Neither sibling plugin has the audio work yet; the docs site is live, but only as stubs. Last, I'll verify the corpus numbers that cld cited from the originating research.

I have what I need. Now I'll set up the layout in my research checkout.

The report is written and registered, and the other checkouts are clean. Now submitting the final declaration.

The consolidated report is written and registered as `research:202610/sase_listen_what_you_get/sase_listen_what_you_get__final.md` (ref `file:explicit:029a8d3188e400ba9a7ff4c9`). The five researcher reports are now in the same directory under their original suffixes. The host will commit everything once this turn ends.

**What sase-listen gives someone who installs it:**

- **It's a standalone command-line tool, not a SASE plugin.** `uv tool install sase-listen` turns any Markdown file into an MP3 that is narrated, split into chapters, volume-normalized, tagged and has cover art. It can also publish episodes to a private podcast feed for AntennaPod. It never imports `sase` and brings its own ffmpeg, so the only thing you have to supply is a text-to-speech API key.
- **It reads what it's given; it doesn't write or summarize.** On its own it cleans up the Markdown and reads the whole thing. A typical research report comes out at about 19 minutes. The shorter 16-minute "audio edition" needs a script written by a SASE agent (`#research/audio`) or by you following `sase-listen guide`.
- **The agent-written edition exists for accuracy, not length.** About half the time (52%), research reports put their recommendation in a table, and the plain reading drops large tables. So a plain reading would often skip the recommendation itself.
- **Listening to research on a walk takes three packages:** sase-listen makes the MP3, sase-research-artifacts has the agent write the edition, and sase-telegram delivers it as a playable track.
- **Cost:** about $0.22 for a 16-minute episode with Gemini, rising to about $0.43 after 2027-01-01. That's roughly $2 a month for 10 episodes, not counting what the agent spends writing the scripts.

**What I found by checking the live repo myself:**

- **You can't install it yet.** PyPI returns 404, and only `doctor` (offline checks) and `config` work. `render` and the other 9 commands exit with "not implemented yet".
- **Releases are blocked.** The automated release step failed because a GitHub repo setting still stops Actions from opening pull requests, so there is no 0.1.0 release PR to merge. The scaffold phase was meant to fix that setting, and that phase is already closed. Flipping the setting or adding a `SASE_RELEASE_TOKEN` secret unblocks it.
- **Neither sibling plugin has its audio work yet** (Telegram audio sending, the `#research/audio` command).
- **Private notes have no protection.** The feed is protected only by an unguessable URL on a public Tailscale Funnel, and every real render sends the text to Google or OpenAI. The original research said private notes must stay off both, but scripts have no `private:` marker to enforce that.

The report ends with a table resolving where the researchers disagreed. The main corrections:
- **What works today:** `doctor` already works, which two reports missed.
- **Cost:** the "$0.16" figure some reports used is for a 12-minute script, not a full 16-minute edition.
- **gem's overstatements:**
  - Kokoro is not a built-in local voice; you'd point the tool at your own Kokoro server.
  - Telegram's player shows no chapters.
  - Research swarms don't publish to the feed automatically.
