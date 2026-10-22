# Chat History - ace-run (research.2w.gem)

- **TIMESTAMP:** 2026-09-29 07:02:58 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2w.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260929_065034.md`

## Prompt

%id(gem, clan=research.2w)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.2w.cdx`, `research.2w.cld`, `research.2w.grk`, `research.2w.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to add
excellent support for bead file attachments.

- We already support leaving notes of the form `@<path_to_file>` as long as
  `@<path_to_file>` is the only contents of the note.
- We should add support for `@<path_to_file>` references anywhere in a note and require
  that `@@` be used if a literal `@` is needed.
- We should have robust (but optional--not all users will necessarily run the
  `sase bead show` command using a terminal that supports viewing images, for
  example--also I'm not sure that sase agents will want this enabled since it might be
  easier for them to use image file paths to read images directly) support for viewing
  images
- Finally, make sure that large and arbitrary binary files are supported. Think hard
  about the best way to add support for these.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

# SASE Bead File Attachments: Research, Critique, and Recommended Architecture

**Author:** researcher gem (`research.2w.gem`)  
**Report File:** [`bead_file_attachments_architecture_and_critique__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202609/bead_file_attachments_architecture_and_critique__gem.md)  
**Registered Artifact:** `research:202609/bead_file_attachments_architecture_and_critique__gem.md` (`file:explicit:843bf3cf2b7c5cc9612407f4`)

---

## 1. Executive Summary & Synthesis

The proposal to introduce first-class file attachment support for SASE beads addresses an essential requirement in modern agentic software engineering: software tasks frequently depend on non-textual or out-of-band evidence—including UI regression screenshots, compiler logs, memory profiler flamegraphs, core dumps, and test database fixtures.

However, an in-depth architectural analysis reveals critical tensions in the initial implementation concept that would severely compromise system stability, git scalability, and developer ergonomics if built naively.

### Core Architectural Conclusions:
1. **Conflating Transclusion with Attachment:** The current `@<path>` implementation in `src/sase/cli_file_values.py` (`read_at_path_value`) performs *textual transclusion*—it reads UTF-8 text from disk and inlines it directly into `BeadNote.text`. Extending this to binary files causes immediate UTF-8 decode crashes, and extending it to large files causes severe git repository bloat.
2. **Usability Hazards of Universal `@@`:** Forcing `@@` for any literal `@` across freeform note prose severely damages developer UX, colliding with Python decorators (`@dataclass`, `@pytest.mark`), Java annotations, email addresses, git reflog references (`HEAD@{1}`), and mentions (`@agent`).
3. **Git Scalability & Workspace Impact:** SASE spins up parallel ephemeral numbered workspaces (`sase_<N>`). In-band storage of binary attachments in `beads/events/**` would permanently bloat git packfiles, dramatically slowing clone and checkout times. Binary payloads must reside out-of-band in a Content-Addressed Storage (CAS) tier.
4. **Human vs. Agent Presentation Bifurcation:** Humans using `sase bead show` want rich, auto-scaling visual previews (via Kitty graphics or TrueColor ANSI half-blocks). AI agents using `sase bead read` must *never* receive terminal escape noise or huge raw byte dumps; they require structured file paths and artifact references to inspect with their own tools.

---

## 2. Critique of the Initial Plan & Necessary Adjustments

### 2.1 Adjustment 1: Separate Text Transclusion from Asset Attachment
* **The Problem:** When a note contains `@<path>`, does it mean *"paste the text of this file right here"* (transclusion), or *"attach this file as a durable asset and link to it"* (attachment)?
* **The Solution:** 
  - For **attachments** (images, logs, binaries, archives): the file is streamed into SASE's Content-Addressed Storage (CAS), assigned a canonical artifact reference (`file:explicit:<sha256>`), and registered in the note's typed attachment table.
  - For **transclusion** (inserting text snippets into prose): provide explicit flags/syntax (e.g. `--transclude <file>` or `@transclude:path`).

### 2.2 Adjustment 2: Refined Path Syntax Instead of Mandatory `@@`
* **The Problem:** Mandating `@@` for any literal `@` will cause constant syntax errors when users paste stack traces, code snippets with decorators (`@dataclass`, `@property`), or emails.
* **The Solution:** Adopt **qualified path recognition**:
  1. A token starting with `@` is treated as an attachment candidate *only* if it looks like a path (starts with `@./`, `@../`, `@/`, `@~/`, contains a `/`, or ends with a recognized file extension) AND resolves on disk.
  2. Markdown image and link syntax (`![alt](@path)` and `[label](@path)`) is natively supported.
  3. `@@` is supported as an escape sequence for ambiguous edge cases, but standard code decorators and mentions remain unescaped.
  4. Provide an explicit CLI flag: `sase bead note <id> -a <path>` (the cleanest, most reliable input method).

### 2.3 Adjustment 3: Out-of-Band Content-Addressed Storage (CAS)
* **The Problem:** Storing raw binary files or base64 strings in `events/**.jsonl` commits binary blobs into git, permanently degrading repository performance.
* **The Solution:** Leverage SASE's existing artifact CAS (`~/.sase/projects/<proj>/artifacts/beads/`). The bead event stream in `sase-core` records only lightweight `BeadAttachmentWire` metadata (~200 bytes per attachment).

---

## 3. Recommended Architecture & Design of Record

### 3.1 Dual-Tier Storage Engine

```
┌────────────────────────────────────────────────────────┐
│                      sase bead note                    │
└──────────────┬──────────────────────────┬──────────────┘
               │                          │
       (1. Stream Payload)        (2. Append Event)
               ▼                          ▼
┌──────────────────────────────┐ ┌──────────────────────────────┐
│  Content-Addressed Storage   │ │  Rust Core Event Stream      │
│  (CAS / Artifact Subsystem)  │ │  (sase-core: beads/events/)  │
├──────────────────────────────┤ ├──────────────────────────────┤
│ ~/.sase/artifacts/beads/     │ │ BeadNoteWire {               │
│ - Chunked SHA-256 ingestion  │ │   id: "note_123",            │
│ - Content deduplication      │ │   text: "Prose context...",  │
│ - GC protected via links     │ │   attachments: [             │
│ - Canonical file:explicit:...│ │     BeadAttachmentWire { ... }│
│                              │ │   ]                          │
│                              │ │ }                            │
└──────────────────────────────┘ └──────────────────────────────┘
```

#### Rust Core Wire Schema (`crates/sase_core/src/bead/wire.rs`):
```rust
#[derive(Debug, Clone, PartialEq, Eq, Serialize, Deserialize)]
pub struct BeadAttachmentWire {
    pub id: String,              // e.g. "att_01h8..."
    pub filename: String,        // original filename (e.g. "ui_error.png")
    pub artifact_ref: String,    // "file:explicit:e3b0c442..."
    pub mime_type: String,       // "image/png", "application/x-coredump"
    pub size_bytes: u64,         // exact byte size
    pub sha256: String,          // full SHA-256 hash
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub caption: Option<String>, // optional caption
}
```

### 3.2 Ingestion Interfaces
1. **Primary CLI Option (Explicit & Scriptable):**
   ```bash
   sase bead note sase-1 "Reproduction trace and screenshot" -a ./screen.png -a ./core.dmp
   ```
2. **In-Prose Syntax (Natural & Disambiguated):**
   ```markdown
   sase bead note sase-1 "UI crash in @dataclass parser; see @./screen.png and ![Trace](@./trace.log)"
   ```
3. **Explicit Transclusion:**
   ```bash
   sase bead note sase-1 --transclude ./short_error.txt "Failed with above error"
   ```

### 3.3 Visual Presentation Layer ("Intuitive, Reliable, Beautiful")

#### 1. Interactive Human Surface (`sase bead show`):
An adaptive three-tier visual rendering pipeline:
* **Tier 1 (Kitty Graphics Protocol):** Detects Kitty, Ghostty, WezTerm, or tmux passthrough (`kitten icat`) for true-pixel, sharp inline previews bounded to max column/row limits.
* **Tier 2 (ANSI Cell Half-Blocks):** Fallback using SASE's built-in `CellImageRenderable` (`src/sase/ace/tui/graphics/cell.py`) with 24-bit TrueColor or 256-color half-blocks (`▀`, `▄`).
* **Tier 3 (Unicode Attachment Cards):** Clean border cards for non-image binaries (core dumps, tarballs, sqlite DBs) or non-graphical terminals:
  ```text
  ┌─ [IMG 1] ui_crash.png ──────────────────────────────────────────┐
  │  [Inline Graphic Preview via Kitty or ANSI Half-Blocks]         │
  │  Format: image/png · Dimensions: 1280x720 · Size: 245.8 KB      │
  │  Ref: file:explicit:9b2a7c41 · Path: ~/.sase/artifacts/...      │
  │  Action: sase artifact open file:explicit:9b2a7c41              │
  └─────────────────────────────────────────────────────────────────┘
  ┌─ [BIN 2] core.88412 ────────────────────────────────────────────┐
  │  Type: application/x-coredump (ELF 64-bit LSB core file)        │
  │  Size: 48.6 MB · SHA256: 3a91f4c7b8e10293...                   │
  │  Ref: file:explicit:3a91f4c7 · Path: ~/.sase/artifacts/...      │
  │  Action: gdb target/debug/worker ~/.sase/artifacts/.../core.88412 │
  └─────────────────────────────────────────────────────────────────┘
  ```

#### 2. AI Agent Surface (`sase bead read`):
* Terminal graphics and ANSI escape sequences are **strictly disabled**.
* Emits clean, audited Markdown specifying exact local paths, MIME types, sizes, and artifact refs:
  ```markdown
  - **Attachment #1 (image):** `ui_crash.png`
    - MIME: `image/png` | Size: 245.8 KB | Ref: `file:explicit:9b2a7c41...`
    - Local Path: `/home/bryan/.sase/artifacts/beads/9b/ui_crash.png`
  ```
* Agents can inspect the file using native multimodal tools (`view_file`), run external analysis commands, or invoke subagents without token waste or visual noise.

---

## 4. Verification and Deliverables

* **Research Report Location:**
  [`sase/repos/research/202609/bead_file_attachments_architecture_and_critique__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202609/bead_file_attachments_architecture_and_critique__gem.md)
* **Durable Snapshot Registered:**
  ```bash
  sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/sase/repos/research/202609/bead_file_attachments_architecture_and_critique__gem.md" -l "research:202609/bead_file_attachments_architecture_and_critique__gem.md"
  ```
  - Artifact Reference: `file:explicit:843bf3cf2b7c5cc9612407f4`
* **Finalizer Declaration:**
  - Finalizer manifest submitted and accepted for repository `sdd:research` (`repo-e029ea166d96`).
  - Working tree clean.
