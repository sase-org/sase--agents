# Chat History - ace-run (research.1v.final)

- **TIMESTAMP:** 2026-10-16 22:14:26 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1v.final
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_213202.md`

## Prompt

%clan(research.1v, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] Can you do some research on gascity (see the https://github.com/gastownhall/gascity
GitHub repo)? What is it used for? What is the long-term vision (if any) for this
project?]]) %id:research.1v.final %m:@xlarge
%wait:research.1v.cdx %wait:research.1v.cld %wait:research.1v.grk %wait:research.1v.mus %wait:research.1v.gem %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are the lead researcher: 5 independent researchers have reported on the request
below, and you will add your own research and merge every perspective into one
consolidated report.

SASE derives your plan's links from the artifacts you read this turn; use
`sase artifact read` for context you actually used.

Research request:

Can you do some research on gascity (see the https://github.com/gastownhall/gascity
GitHub repo)? What is it used for? What is the long-term vision (if any) for this
project?

The researchers' registered reports:

{% for a in wait.artifacts if a.kind == "markdown" and a.label and a.label.startswith("research:") %}
- wait_name={{ a.wait_name }} label={{ a.label }} source_path={{ a.source_path }} path={{ a.path }} ref={{ a.ref }}
{% endfor %}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. From the registered reports above, identify exactly one report per expected suffix
   in cdx, cld, grk, mus, gem, belonging to this
   dispatch's `research.1v.cdx`, `research.1v.cld`, `research.1v.grk`, `research.1v.mus`, `research.1v.gem` dependencies, matching by `wait_name` and the canonical research
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
   agent `research.1v.linker` publishes it from your report.

5. After the write succeeds, register the consolidated report as a durable snapshot so
   the linker agent, `research.1v.linker`, can find it:

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

I've read the first of five reports (cdx). Now I'm reading the other four.

Now I'm checking the points where the reports disagree, starting with the gascity checkout: commit counts, tags, and the design docs.

Now I'm checking claims on the web that only one report made: Yegge's August pivot, the Every review, and the Gasworks page.

Claims are verified. Now I'm moving the five reports into a new folder, then writing the consolidated report.

All cited files exist. Now I'm registering the consolidated report as an artifact.

I've written the consolidated Gas City report and registered it for the linker as `research:202610/gascity_software_factory_purpose_and_vision/gascity_software_factory_purpose_and_vision__final.md`. All five researcher reports (cdx, cld, grk, mus, gem) now sit beside it in that folder, and the host commits the research repo after this turn.

**What it's for.** Gas City (`gc`) is a free, MIT-licensed Go tool that runs groups of existing CLI coding agents as a "software factory". It works with Claude Code, Codex, Gemini, Cursor and about a dozen others.
- You write how a job gets done once, as a TOML file called a formula.
- A controller breaks the job into durable work records ("beads"), runs ready steps on many agents in parallel, and waits on dependencies.
- It runs review and check loops, retries failures, and finishes the job without anyone sitting in a chat session.

It generalizes Steve Yegge's Gas Town project. Its core rule is that no agent roles are hardcoded: Gas Town's Mayor, Polecat and the others become swappable configuration. The maintainers mostly use it to build Gas City itself; the throughput numbers they publish are their own.

**Long-term vision.** There is a clear one, but no dated plan. It has three layers:
1. **Product thesis (CEO Chris Sells):** engineers stop building the software and instead build and improve the factory that builds it. The bet is that better models make factories better, not unnecessary.
2. **Commercial direction:** an open-core ladder. Beads and Gas City are free. Beads Team Server (a shared, governed work graph) is open to design partners now. Gasworks (one factory shared by several operators, hosted or inside your own cloud) opens design partnerships in December 2026. The open-source client already speaks a vendor-neutral hosting protocol, but only login has shipped.
3. **Next release (1.6):** reliable recovery after crashes and restarts, moving bookkeeping off the Dolt database to SQLite for speed, and easier onboarding for contributors, human or agent.

**Biggest caveat.** In April Yegge called Gas City "our official new direction". By August Yegge wrote that Gas Town "fell apart at the seams" and "I have given up on building reusable harnesses", and now runs a private orchestrator instead. That undercuts the premise of a reusable toolkit. An independent review by Every in May reached a similar verdict: "sharp ideas… not yet ready for prime time."

**Corrections I made to the researchers' claims:**
- **Commit share:** project CTO Julian Knutsen wrote 62% of the commits on `main` (4,457 of 7,161). cld said 57% by mixing counting methods; grk said ~8,500 commits by counting every branch.
- **gem's errors:** gem got the definition of the project's "Primitive Test" wrong, and misnamed one of its principles ("NDI" stands for "Nondeterministic Idempotence").
- **Reconciler v2:** the new crash-recovery logic is still opt-in, not the default.
- **Skills and MCP:** the repo's rules say it will never include skills or MCP tool registration, yet the code now delivers both to agents.

I couldn't confirm the cld report's claim that an autonomous agent pushed the accidental Beads 1.2.1 release. I could only confirm the release went out untested.

Sources:
- [Yegge, "Welcome to Gas City"](https://yegge.ai/essays/welcome-to-gas-city/)
- [Yegge, "The Continuous Thunderdome"](https://yegge.ai/essays/the-shape-of-things-to-come/)
- [Every review](https://every.to/context-window/inside-the-100-agent-software-factory)
- [Gasworks](https://gascity.com/gasworks/)
- [Beads Team Server](https://gascity.com/beads-team-server/)
- [gascity.com/about](https://gascity.com/about/)
- [Beads v1.2.2 release notes](https://newreleases.io/project/github/gastownhall/beads/release/v1.2.2)
- [Built In listing](https://builtin.com/company/gas-city)
