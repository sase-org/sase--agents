# Chat History - ace-run (research.1u.cld)

- **TIMESTAMP:** 2026-10-16 18:37:06 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1u.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_175332.md`

## Prompt

%id(cld, clan=research.1u)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.1u.cdx`, `research.1u.grk`, `research.1u.mus`, `research.1u.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of comparing sase with gastown (see the
https://github.com/gastownhall/gastown GitHub repo), with a particular focus on the
things that gastown does better than sase? End your analysis with a ranked list of ways
that gastown is superior to sase along with a (not necessarily one-to-one) ranked list
of recommended changes you think I should consider making to sase based on your report's
findings. 
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

I've opened the gastown repo and am surveying its docs and code; next I'll map them onto sase.

I'm sending parallel deep dives into gastown's subsystems and checking the project's current status on the web.

Gas Town research is done (it's in maintenance mode; Gas City is the successor). Now I'm mapping sase's own docs to find where its equivalents line up.

Checking a few more claims in the code before I write the report.

Grounding the merge-queue recommendation in sase's current green-master work.

Starting the write-up. First, a quick check of the counts I'll cite.

Report written. Checking two remaining citations, then registering the artifact.

I've written the report and registered it as an artifact. I also submitted the commit declaration; the host commits the research repo after this turn ends.

**Report:** `sase/repos/research/202610/gastown_vs_sase_where_gastown_leads__cld.md`
**Artifact:** `explicit:36736e9a70fffb9f965ce290`, label `research:202610/gastown_vs_sase_where_gastown_leads__cld.md`

**Gas Town's current state**
- Its last commit was 2026-07-23, at v1.2.1.
- Yegge wrote in August that it "fell apart at the seams with Opus 4.7." He moved his own work to a private harness, and Gas City, an SDK rewrite with no hard-coded roles, is the active successor.
- Several advertised features don't run: the batch-then-bisect merge queue exists in code but nothing calls it, and per-step model selection and capability-based routing exist only in docs. I checked each headline claim in the source and tagged it as code, doc-only or unwired.

**Where Gas Town is better, top five of fifteen**
1. **Landing:** it tests each change on the merged result before landing and proves the merged commit is on the target branch. SASE pushes straight to `master` and only finds out afterwards. The Oct 1 research found `master` red for 13 days, and the green-master epics keep recurring.
2. **Failed work:** it retries automatically on a stronger model, caps retries, and skips work that fails three times. In SASE a failed phase waits for you, and the retry fallback steps *down* to sonnet.
3. **Live agents:** it detects stalled, hung and zombie agents and lists them in a Problems view. SASE doesn't watch a turn that wedges before the agent submits its final declaration.
4. **Coordination:** the Mayor agent can dispatch work, and agents can message each other. In SASE, a launch an agent requests never goes ahead without your approval.
5. **Escalation:** blockers are routed by severity to email, SMS or Slack, and unanswered ones are raised again.

The rest are telemetry export and cost tracking, keeping a session through quota limits, saving work through crashes, per-repo workflow patches and resume, asking a past agent questions, more providers, more doctor auto-fixes, credential fencing, a model-downgrade eval suite, and reach (Homebrew, Docker, community).

**Top recommendations, out of fifteen**
1. **Landing lane:** hold a lock per repo while landing, and refuse any landing that adds failures relative to the current `master` tip, checked on the rebased tree. This works even while `master` is red. Then confirm the push actually reached the remote. Batch only when the queue gets deep, and skip bisection.
2. **Failure policy for beads:** retry on a stronger model, cap attempts, then skip or escalate.
3. **Live-turn monitoring:** classify running agents from the stream-JSON events SASE already parses, and add a Problems view.
4. **Re-raise stale gates** on a louder channel, with severity levels.
5. **Coordinator session:** a chain of single turns woken by events, with a capped number of launches it may approve itself. This keeps SASE's one-turn-per-agent rule intact.

Two quick wins: freeze and thaw agents (an emergency stop) using their existing systemd scopes, and save snapshots of work during long turns.

The report also lists what not to copy (driving agents by typing into tmux, LLM patrol agents for mechanical checks, an always-on Mayor process, rotating between several accounts), and the areas where SASE is already ahead.

**Caveats**
- The Medium originals returned 403, so the Yegge material comes from the yegge.ai and blog.gascity.com copies.
- The cost and throughput figures in his essays are his own reports and don't agree from one post to the next.
