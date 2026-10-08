# Chat History - ace-run (research.0l.gem)

- **TIMESTAMP:** 2026-10-08 10:39:18 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0l.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261008_101923.md`

## Prompt

%id(gem, clan=research.0l)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0l.cdx`, `research.0l.cld`, `research.0l.grk`, `research.0l.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

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
want to make the `%auto` directive much more configurable, intuitive, and more powerful
in general.

- I agree with all of the recommendations made by the auto_directive_autonomy_policy.md
  file in the research sidecar repo, which you should review before performing your own
  research.
- This research did not focus on the UX (e.g. the TUI, CLI, and Telegram) much though,
  which is what I would like you to focus on.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of figuring out what the best possible user
experience looks like for this functionality? It is possible that there isn't much to do
here, but you should think hard about whether or not that is the case or if additional
UX integrations would be genuinely helpful to users. End your analysis with a
recommended UX design. 
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

# Independent Research Report: `%auto` Directive & Autonomy Policy UX Design

**Researcher:** `research.0l.gem`  
**Report File:** [`auto_directive_ux_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/auto_directive_ux_design__gem.md)  
**Registered Artifact:** `explicit:c3832114bced7b001a5bd4fa` (`research:202610/auto_directive_ux_design__gem.md`)  
**Baseline Policy:** [`auto_directive_autonomy_policy.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/auto_directive_autonomy_policy/auto_directive_autonomy_policy.md)

---

## Executive Summary & Core Design Thesis

The policy analysis in `auto_directive_autonomy_policy.md` demonstrated that `%auto` must not be expanded into an ad-hoc permission DSL typed into prompts, but must instead select config-defined, Rust-owned autonomy profiles (`autonomy:`). However, **a robust policy engine will still fail if the user experience treats autonomy as an invisible background automaton.**

Today's UX suffers from:
1. **Total Invisibility:** Today's `%auto` executes 70% of prompt turns in complete silence. When gates auto-resolve, no notifications are published, no TUI cards update, and Telegram remains completely silent.
2. **Blunt Force Controls:** The only live control in ACE today is the `A` key, which attempts a crude boolean toggle (and fails to stick for live bare-`%auto` runs due to Defect D5).
3. **Semantic Conflation:** The single cyan lightning glyph `⚡` conflates four radically different operating postures: pair programming, unattended overnight runs, routine background coding, and constrained epic workers.

Our proposed design introduces **Symmetric Autonomy UX** across ACE (TUI), the CLI, Telegram/mobile, and prompt authoring.

---

## The Four Human Operational Postures

Instead of confronting users with an abstract matrix of gate rules, the design centers around four intuitive **Operational Postures**:

| Posture | Profile | Intent | Tale Plan | Epic Plan | Questions | On Ask | TUI Badge |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Attended** | `attended` | "Pair programming: automate boilerplate plans, but stop to ask questions before making design assumptions." | `approve_archive` | `ask` | `ask` | `park` | `⚡ att` (Gold `#E5C07B`) |
| **Standard** | `standard` | "Routine flow: approve tale plans, answer questions if recommended, but stop at major epics." | `approve_archive` | `approve` | `recommended` | `park` | `⚡ std` (Cyan `#5FD7FF`) |
| **Overnight** | `overnight` | "Walking away: do not park on minor questions or launch runaway epics; keep moving or cleanly report." | `approve_archive` | `deny` (or `ask`) | `decide` | `deny` | `⚡ ngt` (Purple `#AF87FF`) |
| **Supervised** | `manual` | "Supervised run: human reviews every plan, epic, and question checkpoint." | `ask` | `ask` | `ask` | `park` | *(dim / omitted)* |
| **Worker** | `epic_worker`| "Phase/land worker: hard-bounded to parent epic scope; nested epics forbidden." | `approve_archive` | `ask` | `recommended` | `park` | `⚡ wrk` (Blue `#61AFEF`) |

---

## Key Cross-Surface UX Deliverables

### 1. ACE (TUI) Experience
- **Glanceable Row Badges:** Replaces the generic `⚡` with responsive posture badges: `⚡std` (cyan), `⚡att` (gold), `⚡ngt` (purple), `⚡wrk` (blue). In narrow columns (<100 cols), gracefully collapses to `⚡`, `⚡?`, `⚡🌙`, `⚡w`.
- **Interactive Header Pill:** Row 1 of the agent identity header features an actionable pill:  
  `⚡ overnight [plan:archive · epic:deny · q:decide]`
- **The `A` Key & `Shift+A` Modal:**
  - Quick tap `A` toggles **Pause / Resume Autonomy** (instantly switching between active profile and `manual`).
  - `Shift+A` (or Leader `, a`) opens the **Autonomy Profile Modal**, displaying all configured profiles, effective gate rules, and live single-key toggles (`1`-`4` to pick posture, `q` to toggle question behavior, `e` to toggle epic behavior).
- **The Dedicated `⚡ AUTONOMY` Deck View:**
  - **Active Posture Card:** Displays active profile, config layer provenance (`builtin` → `user` → `project` → `prompt`), effective gate rules, and confirmation of injected context.
  - **Decision Ledger & Audit Timeline:** Chronological, scrollable ledger of every gate encountered during the run (`[14:02:11] tale:plan · approve_archive · policy: overnight [📄]`), with `Enter` to inspect gate bundles/receipts.
- **Low-Noise Toasts & Inbox Receipts:** Auto-resolutions trigger subtle, non-stealing 3.5s toasts and log to a dedicated, quiet `Receipts (Auto)` inbox drawer category.

### 2. CLI Experience (`sase autonomy`)
Adheres strictly to [`sase/memory/cli_rules.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/memory/cli_rules.md):
- `sase autonomy` defaults to `sase autonomy list`, displaying configured profiles, inheritance hierarchy, and default markers (`★`).
- `sase autonomy explain [PROMPT|AGENT]`: Simulates prompt directives (e.g. `sase autonomy explain "%auto(overnight, q=ask)"`) or audits live running agents, rendering the full gate matrix and the exact agent awareness text injected into prompt context.
- `sase autonomy set <AGENT> <PROFILE|OVERRIDE>`: Dynamically adjusts a running agent's autonomy from another terminal via atomic `agent_meta.autonomy` writes.
- `sase autonomy history [AGENT]`: Inspects the audit ledger of automated decisions across sessions.
- `sase run -a [PROFILE]` / `--auto [PROFILE]` / `--autonomy-explain`: First-class CLI launch flags matching directive syntax.

### 3. Telegram & Mobile Experience
- **Silent Autonomous Decision Receipts:** When gates auto-resolve, Telegram receives a quiet message (`disable_notification=True` to prevent audible alerts / vibrations) detailing the action taken, the plan summary, and the matched policy rule.
- **The "Take the Wheel" Flow:**
  - Every auto-receipt includes an inline callback button: `[ ⏸️ Pause Autonomy ]`.
  - Tapping it from mobile immediately downgrades the live agent to `manual` on the host, editing the Telegram card in-place (`⏸️ Autonomy Paused`). Subsequent gates notify as standard urgent interactive cards.
- **Bot Commands:** `/auto`, `/auto <agent>`, `/auto <agent> pause`, `/auto <agent> resume`, `/auto <agent> <profile>`.

### 4. Prompt Authoring, LSP & Agent Awareness
- **Grammar:** Clean, uniform syntax: `%auto`, `%a:attended`, `%auto(overnight, epic=deny)`, `%auto(q=ask)`.
- **LSP / Neovim Integration:** Autocomplete popups with profile descriptions on `%auto:`, argument completions on `%auto(`, and red diagnostic squigglies on illegal privilege escalations or unrecognized profiles.
- **Injected Context Awareness:** Rust core injects an authoritative 5-line instruction block informing the agent of its exact posture (e.g. telling it whether questions will be auto-decided, so it flags recommended choices and avoids stalling).

---

## Artifact Registration & Finalizer Status

1. **Research Report Written:**  
   [`auto_directive_ux_design__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202610/auto_directive_ux_design__gem.md)
2. **Artifact Created:**  
   `sase artifact create -p "/home/bryan/.../202610/auto_directive_ux_design__gem.md" -l "research:202610/auto_directive_ux_design__gem.md"`  
   - Ref: `file:explicit:c3832114bced7b001a5bd4fa`  
   - ID: `explicit:c3832114bced7b001a5bd4fa`
3. **Turn Finalizer Declared:**  
   Finalizer manifest submitted via `sase final submit -` and accepted by the host.
