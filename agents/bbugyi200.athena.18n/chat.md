# Chat History - ace-run (18n)

- **TIMESTAMP:** 2026-11-05 12:04:33 EST
- **MODEL:** claude/opus
- **AGENT:** 18n

## Prompt

#gh:gh_sase-org__sase Can you explain to me, from a user's perspective, how the new "agent hijack"
functionality will work once its implementation is complete? See the sase-1qz epic bead
for context. Make sure your report is concise, easy to understand, and contains
excellent visuals. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete. %m:@xlarge

## Response

I'll start by reading the epic bead and its children.

Status: I've read the epic bead and its full plan; now checking the in-progress phase beads and landed code so the report reflects what actually shipped.

Status: loaded the diagram guidelines; next I'll draft the report's figures and render them to check.

Let me look at the rendered golden PNG to keep the row mockups faithful.

Status: confirmed the landed row rendering against the real TUI golden screenshot. Now drafting and rendering the two Mermaid figures.

Figure 1 fits (84%); figure 2 is too wide at 45%. Restructuring it left-to-right with merged questions.

Still too wide (53%). One more compaction pass — shorter hexagon and leaf labels — before falling back to a table.

Report written. Verifying a few claims (kill's status label, flag-enable syntax) before registering.

The figure renders cleanly at 84% fit. Registering the report as a durable artifact.

Registration succeeded. Finishing the turn through the SASE finalizer.

I wrote the report on how agent hijack will work for users and registered it as an artifact.

**Report:** `sase/repos/research/202611/agent_hijack_user_guide/agent_hijack_user_guide.md`
**Artifact:** label `research:202611/agent_hijack_user_guide/agent_hijack_user_guide.md`, ref `file:explicit:8bc2cd38111fc3ddef360e16`

**How it will work for you:**
- **Hijacking an agent.** When an agent stalls, press `,k`, or press `h` in the kill dialog, or run `sase agent hijack NAME`. The agent's processes stop, but its workspace, uncommitted changes and Agents-tab row are kept. The row changes to `⏏ HIJACKED`.
- **Recovering it.** Press `⏎` on that row to open a recovery panel. Its options are grouped by what happens to your changes:
  - **Keep the changes:** escalate to a bigger model (`u`), continue with the same model (`c`), or add guidance first (`i`).
  - **Start over:** restart with the same prompt (`r`) or edit the prompt (`e`), in a fresh workspace.
  - **Look or leave:** view the diff (`v`), open a shell (`t`), or dismiss (`d`).
- **Shortcut.** Pressing `⏎⏎` escalates.
- **No lost work.** Nothing is released until a snapshot of the changes exists, and each hijacked agent can only be resolved once.

**Visuals in the report:**
- The real TUI screenshot of every hijack row state, taken from the visual-snapshot test. It's copied next to the report.
- A lifecycle diagram from RUNNING to HIJACKED to the final outcomes. I rendered it and checked that it reads correctly.
- A text mockup of the recovery panel, including how it looks when an action is unavailable.
- Tables comparing kill with hijack, showing which key to press when, and which model escalation picks.
- Sample CLI usage and the session tree after an escalation.

**Things to know:**
- The recovery side isn't built yet: the panel, `sase agent recover`, and Instruct/Edit are still in progress. Those visuals come from the epic plan, not from real screenshots, and the report says so.
- `sase agent recover` doesn't exist in the current CLI yet.
- Hijacking itself is in the code but behind a beta flag that is off by default; turn it on with `sase flag enable agent_hijack`.
- I dropped a second diagram (a "which key should I press" flowchart) because it was too wide to read at page size. A table covers the same thing.

The host will commit the report and screenshot to the research repo now that this turn has ended.
