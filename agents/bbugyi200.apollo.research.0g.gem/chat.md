# Chat History - ace-run (research.0g.gem)

- **TIMESTAMP:** 2026-10-07 16:51:47 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0g.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_163926.md`

## Prompt

%id(gem, clan=research.0g)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0g.cdx`, `research.0g.cld`, `research.0g.grk`, `research.0g.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to give sase plans (i.e. tales and epics) the ability to embed sase gate
options within their frontmatter somehow.

- This will be useful, for example, to start requiring that all memory file changes be
  planned in plan files with explicit human gates (that should default to on iff the
  user explicitly requested those memory changes).
- This will also be useful if, for example, a sase agent has a question for the user
  that effects the plan but the agent has enough information to write a good plan
  without an immediate answer (i.e. the coder agent can implement the plan based on what
  gate selections the user made).
- I have already done some research on this, which can be found in the
  plan_frontmatter_decisions.md file in the research sidecar repo. Review that research
  before performing your own. I agree with all of the recommendations made in that
  research file (though your judgement should take priority when it comes to UX
  decisions).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide what the best possible UX
looks like (across the TUI, Telegram, and the CLI) for this functionality? 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
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

I have completed the independent UX research investigation and authored the detailed design specification for **Plan Decisions across the TUI, Telegram, and CLI**.

### Summary of Research & UX Design

The report has been written to:
[`plan_decision_ux_across_surfaces__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/plan_decision_ux_across_surfaces__gem.md)

And registered as a durable artifact:
- **Ref:** `file:explicit:2c8ab46dc6c042db7ef3071c`
- **Label:** `research:202610/plan_decision_ux_across_surfaces__gem.md`
- **Stored Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261007163931/plan_decision_ux_across_surfaces__gem-9142f9475d79.md`

---

### Core UX Highlights

#### 1. The Three Golden Tenets of the Design
1. **Single-Key Default Path ("Enter to Approve"):** Default velocity must not be slowed down. If the planner provided sensible defaults, approving a plan remains **one keystroke (`Enter`)** in ACE, **one tap** in Telegram, and **zero extra flags** in the CLI.
2. **Zero Hidden State:** Replaces buried sub-dialogs (such as the legacy `c` modal, which saw zero usage across 54 human reviews). Decisions live front and center in the primary review interface across all surfaces.
3. **Live Outcome Projection (The "Contract" Line):** Toggling an option immediately updates a dynamic, plain-language summary line (`→ Tale coder · grouping=mode · Authorized: edit tui.md`) before submission, eliminating guesswork and rubber-stamping hazards.

---

#### 2. Surface 1: ACE Terminal User Interface (TUI)
- **Modal Reorganization:**
  - Renames the existing branch button group from "Decision" to **"Verdict"** (`1 ✅ Tale`, `2 ❌ Reject`, `3 💬 Feedback`) to avoid namespace confusion.
  - Adds a dedicated, scannable **Decisions** column above the Verdict section.
- **Visual Controls:**
  - **Toggles:** Native `☑️` / `⬜` toggles for boolean decisions, toggled via `Space`.
  - **Choices (Enum):** Stepper control `‹ choice ›` cycling forward on `Space` and backward on `Shift+Space`, with consequence text displayed beneath.
  - **Memory Rows:** Prominent `🧠` icon, target note scope (`tui.md`), and provenance chips (`✓ requested` in green, `not requested` dimmed, `⚠ unverified` in orange warning).
  - **Deviations from Default:** Marked with an accent dot (`•`). `r` resets the focused decision to its default; `R` resets all decisions.
- **In-Gate Plan Editing (`e`):** The decision definition schema is frozen during review. If the user edits markdown prose, it updates live; if they attempt to change decision IDs or choices in the file, ACE provides clear guidance to toggle via the UI or request a replan via Feedback.

---

#### 3. Surface 2: Telegram Bot
- **Tier 1 (High-Density Review Card):**
  - Displays the plan goal, size, and an embedded `🎛 Decisions` block listing each decision and its default value.
  - Primary inline button: **`[✅ Approve as shown]`** — allows instantaneous, one-tap approval accepting all defaults without wizard fatigue.
- **Tier 2 (The Interactive Switchboard):**
  - Tapping **`[🎛 Change Decisions]`** does not spam the chat with sequential question prompts; instead, it updates the inline keyboard in-place via `editMessageReplyMarkup` into a live switchboard.
  - Tapping toggle buttons (`[🧠 tui.md: ☑️ YES]`) flips them in place (`[🧠 tui.md: ⬜ NO •]`).
  - Tapping choice buttons cycles options.
  - Completed with a single `[✅ Submit with choices]` button.
- **Tier 3 (Durable Receipt):** Post-approval message updates into a permanent audit record showing selected decisions, timestamp, and launched coder.

---

#### 4. Surface 3: Command Line Interface (CLI)
- **`sase plan show`:**
  - Emits a dedicated Rich table for `DECISIONS (N)` displaying ID, Kind, Default, Current Value / Answer, Provenance, and Consequences.
  - Shows the live **Outcome Preview** block summarizing downstream agent authorization.
- **`sase plan approve`:**
  - Adds `-D, --decide KEY=VALUE` (repeatable) to override specific decisions:
    ```bash
    sase plan approve keymap_help_overlay -D grouping=mode -D tui_note=no
    ```
  - Added `-r, --reset-decisions` for automated scripts forcing all defaults.
  - Dry-run (`--dry-run` / `-n`) renders the exact execution manifest and authorized memory scope without executing.
  - Clear, user-friendly diagnostics for unknown decision keys, invalid choices, or ill-formed boolean values.
- **Interactive TTY Wizard:** When run interactively in a raw terminal without `-D`, provides a prompt menu before executing.

---

#### 5. Downstream Lifecycle & Policy Enforcement
- **Dual Persistence:** Gate responses record the authoritative decision receipt; the approve command stamps `answer:`, `decided_by:`, and `decided_surface:` into the archived plan frontmatter.
- **Tale Coder Turn:** Automatically injects a sealed `Reviewer Decisions (Final)` block into the initial coder agent prompt.
- **Epic Beads:** Rendered in `sase bead read` under `DECISIONS` for phase workers.
- **Phased Enforcement:** Supports a beta-flagged finalizer guard that starts advisory and later enforces that all memory file diffs map to an approved memory decision answered `true`.

The finalizer declaration for the `commit` payload has been submitted and accepted:

- **Repository**: `sdd:research` (`repo-8caa19a02d02`)
- **Action**: `commit`
- **Message**: `docs(research): research plan decision UX across ACE, Telegram, and CLI surfaces`
