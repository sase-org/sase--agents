# Chat History - ace-run (research.4w.cld)

- **TIMESTAMP:** 2026-10-19 07:54:05 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4w.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071704.md`

## Prompt

%id(cld, clan=research.4w)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 5-researcher swarm.
The other researchers, `research.4w.cdx`, `research.4w.grk`, `research.4w.mus`, `research.4w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add hermes (see the https://github.com/nousresearch/hermes-agent GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to hermes that you should review if you
can find it. End your analysis with a recommended solution. 
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

I found the prior "Can Hermes Replace SASE?" research and am now reading it alongside SASE's provider architecture and the hermes-agent repo.

Status: I've finished mapping the Hermes side. I'm now checking how SASE handles open-ended model names and session resume, then I'll write the report.

Status: research is essentially complete. I'm checking Hermes's Nous Portal model catalog for sensible default tiers, then writing the report.

Status: all the evidence is gathered. I'm checking existing provider short names to propose a unique one for Hermes, then writing the report.

Status: the report is written and its links are cleaned up. Next I'm registering it as a durable artifact.

The artifact is registered. Now I'm submitting the final declaration.

I've written the report and registered it as an artifact. My recommendation: add Hermes as a bundled, opt-in provider that runs Hermes's documented JSON output mode (`hermes chat --format stream-json`), with each SASE workspace getting its own private Hermes home directory. All Hermes findings come from reading its source at `8f5693af41` (2026-10-19); I never ran Hermes, so the behaviours listed under "Unverified items" in the report still need a short hands-on check.

**Prior research.** The earlier report, `can_hermes_replace_sase`, already recommended making Hermes "the eighth SASE provider" via its JSON output mode. It was pinned six days before Hermes v0.22.0 (2026-10-14), which changed how that mode works.

**What changed in v0.22.0.** `hermes chat` no longer does the work itself. Every turn now runs inside a background daemon, one per Hermes home directory (`HERMES_HOME`). If SASE agents simply used your `~/.hermes`:
- **Wrong agent identity:** each agent's tools would see the environment of whichever agent started the daemon, so `SASE_*` variables would point at the wrong agent.
- **No cancellation:** SASE's interrupt signal only disconnects the CLI; the turn keeps running in the daemon, while SASE starts a second turn in the same workspace.
- **Broken cleanup:** the daemon sits inside the process scope of the agent that started it. When that agent's runner exits, SASE's cleanup kills the daemon and every other Hermes agent's turn with it.
- **Personal leakage:** runs would pick up your personal Hermes memory, persona and session history.

**The fix.** Give each workspace its own Hermes profile under `~/.hermes/profiles/`, created from a `sase` profile you set up once with `hermes profile create sase --clone`.
- Each agent then owns its daemon, which inherits the agent's environment and is cleaned up with it.
- SASE stops the daemon at the end of every turn, and an interrupt becomes "stop the daemon".
- Your existing Hermes subscription logins are reused automatically.
- Each running Hermes agent costs about 270 MB of RAM.

**The rest of the design:**
- **Instructions:** SASE's instructions go in through `HERMES_EPHEMERAL_SYSTEM_PROMPT` with `--ignore-rules`.
- **Disabled features:** Hermes's scheduler, memory, session search and ask-the-user tools are turned off.
- **New code:** a dedicated parser, because Hermes's output events are flat and don't fit SASE's existing Claude-style reader.
- **Remaining wiring:** the provider registration and other SASE changes follow the Grok template.

**Where Hermes is worth using:** Nous Portal, OpenRouter and local models. Routing Claude through Hermes only bills Max extra-usage credits, never your base allowance. Codex through Hermes draws on the same ChatGPT quota SASE's `codex` provider already uses.

**Biggest risk:** Hermes landed about 16,700 commits in 30 days and releases almost daily, so the report recommends:
- a minimum supported version (v0.22.2)
- test fixtures recorded per Hermes version
- five small upstream patches; the most useful would let a one-off run skip the daemon, which would make the per-workspace homes unnecessary.

**Alternatives held in reserve:** Hermes's ACP protocol (Agent Client Protocol, the editor-integration interface) costs more to build and is only worth it if SASE wants one adapter for several ACP agents. Driving Hermes as a Python library avoids the daemon but ties SASE to its most volatile internals.

**Files:**
- Report: `sase/repos/research/202610/hermes_sase_provider_integration__cld.md`
- Artifact: registered as `research:202610/hermes_sase_provider_integration__cld.md` (`file:explicit:01e6d62655054dc6c01d1786`)
- Commit: accepted for the research repo; the host makes it after this turn ends.
