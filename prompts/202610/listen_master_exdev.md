- **PLAN:**
  [202610/listen_master_exdev.md](https://github.com/sase-org/sase--plans/blob/main/202610/listen_master_exdev.md)
- **AGENTS:**
  - [bbugyi200.athena.0ws.f0--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ws.f0.md)

%macros_enabled:false

# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first
projections of exact continuation nodes; any historical source without recoverable node
provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:68537388221930c449fecf14c8a6e1ee`

- **Node:** `agent-delta:20261005095141:47f9b35f03054d63`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:**
  `local:continuation/records/agent_delta/agent-delta:20261005095141:47f9b35f03054d63.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update
supersedes it.

We recently added support to sase-listen for transcribing articles / research papers and
publishing them to the feed that I subscribe to from the AntennaPod app on my phone (see
the sase-1g7 epic bead for context). Can you help me write a concise report describing
how this functionality works? Say I wanted to transcribe the
https://openai.com/index/open-source-codex-orchestration-symphony/ article, for example,
and listen to it from AntennaPod. How would I do that? Write this research to a new
markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.

After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l
"research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete. %m:@xlarge

### Assistant

I'm reading the sase-listen docs and code to see how URL renders and multi-machine
publishing work.

Next I'm checking the installed sase-listen and its config on this machine.

I'm doing a free, no-API fetch-and-extract test of the Symphony article in a temp
directory, so it doesn't touch the real library.

I've confirmed the Symphony article fetches cleanly; now I'm reading the rollout field
notes to get real timing and cost numbers.

I have everything I need. Writing the report now.

Now I'll file the H3-heading issue as a task bead and put its real ID into the report.

No existing bead covers this, so I'm filing a new small bug bead for the H3-section
chaptering issue.

The typed link command fails with the same bead-id validation error that forced
`--no-links` earlier, so I'll record the relations as a bead note and move on to
registering the report.

Registration succeeded. I'll clean up my temp probe files and finalize.

I wrote the report and registered it as a durable snapshot. It's at
`sase/repos/research/202610/sase_listen_article_to_antennapod.md`, registered as
`research:202610/sase_listen_article_to_antennapod.md` (artifact
`file:explicit:7f72665a5f5b9264690a2d84`). The research repo commit will happen when
this turn ends.

**To listen to the Symphony article:** from athena (or apollo), run

```bash
sase-listen doctor   # expect: ok: feed:host (apollo via apollo · …)
sase-listen render https://openai.com/index/open-source-codex-orchestration-symphony/ -e full
```

Then pull to refresh the SASE Listen feed in AntennaPod. Nothing else needs setting up:
I ran `sase-listen doctor` on athena and every check passed, including reaching apollo
(11 episodes in the feed).

**How it works:**

1. **Fetch:** the page is downloaded on your machine with a browser-like client, which
   gets past openai.com's Cloudflare check.
2. **Extract:** a library called Trafilatura turns the page into Markdown and pulls out
   the title, author and date. The result is saved and reused on later runs.
3. **Write:** for `brief` or `full`, Gemini writes the narration script. It's checked
   against the article (every number must appear in the source) and rewritten up to 3
   times if it fails.
4. **Render:** Gemini text-to-speech produces an MP3 with chapters and a cover.
5. **Publish:** because athena's config names apollo as the feed host, the episode is
   sent to apollo over SSH. apollo adds it to `feed.xml`, which it serves only on your
   tailnet. The feed token never leaves apollo.

**The three editions:**

- **`brief`** (the default): about 600 words, around 4 minutes.
- **`full`:** a rewrite of every section in order, capped at 2,400 words. It is not a
  word-for-word transcript.
- **`verbatim`:** the article text read as-is, with no AI involved.

The report also covers how to review the script before paying for audio, and what to do
when something fails.

**What I checked against the actual article** (in a scratch directory, with no paid API
calls and nothing published):

- It downloads fine: 2,364 words, by Alex Kotliarskyi, dated 2026-04-27.
- **Use `full`, not `verbatim`, for this one.** The article's section headings are one
  level lower than the ones sase-listen turns into chapters. A verbatim reading would be
  a single 16-minute chapter with no chapter skipping. `brief` and `full` aren't
  affected because Gemini writes its own chapters. I filed this as bug bead `sase-1gl`
  (size small).
- **Cost:** about $0.19 of text-to-speech for roughly 14 minutes, plus a few Gemini
  calls to write the script. That's an estimate: it's scaled from a dry run that priced
  a verbatim reading at $0.22.
- The episode title will read "…Symphony. (Full)" with a stray period, because the
  page's own title ends in one.

**Other things I noticed:**

- athena's sase-listen was installed from a SASE workspace copy rather than from git, so
  it's slightly behind the latest code (it lacks `render -g`). The report includes the
  upgrade command; upgrade apollo first.
- I couldn't attach typed "related" links from `sase-1gl` to `sase-1g7` and `sase-1e3`.
  The link command failed with the same bead-ID validation error that also made
  `sase bead read sase-1g7` fail unless I passed `--no-links`. I recorded the relations
  as a note on `sase-1gl` instead.

---

%macros_enabled:true

# New Query

This didn't work (see the command output below for context). Can you help me diagnose
the root cause of this issue and fix it? Think this through thoroughly and create a plan
using your `/sase_plan` skill. Choose and author the appropriate tier, validate and
revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.

```
❯ sase-listen render https://openai.com/index/open-source-codex-orchestration-symphony/ -e full
stage: synthesize
[1/10] chunk 0 synthesized
[4/10] chunk 3 synthesized
[2/10] chunk 1 synthesized
[3/10] chunk 2 synthesized
[5/10] chunk 4 synthesized
[6/10] chunk 5 synthesized
[7/10] chunk 6 synthesized
[8/10] chunk 7 synthesized
[10/10] chunk 9 synthesized
[9/10] chunk 8 synthesized
stage: gates
stage: master
sase-listen render: unexpected error: [Errno 18] Invalid cross-device link: '/tmp/sase-listen-master-io0rm4x_/episode.mp3' -> '/home/bryan/.local/share/sase-listen/library/.staging/an-open-source-spec-for-codex-orchestration-symphony-808675/master.mp3'
```
