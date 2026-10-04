# Chat History - ace-run (research.n.gem)

- **TIMESTAMP:** 2026-09-29 09:01:26 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.n.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260929_085114.md`

## Prompt

%id(gem, clan=research.n)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.n.cdx`, `research.n.cld`, `research.n.grk`, `research.n.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want all users
working on a sase project to have access to all (non-sensitive) bead attachments by
default.

- Review the attachment_storage_and_access.md file in the research sidecar repo and the
  sase-1ck epic bead for context before performing your research.
- I plan on launching another epic after the sase-1ck epic bead is closed to make these
  changes.
- I think we can implement this by moving non-sensitive attachments from the
  sase--attachments sidecar repo to the public sase--beads repo.
- It's fine if large files are only ever supported via sase's remote machine support.
- I'm not sure how we should identify whether or not a file is sensitive or not. I'm
  thinking that agents should have the ability to specify that an attachment be private
  somehow, but they should default to using public attachments. I'm not sure how they
  should decide when to use a private attachment though.

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

# Research Report: Public Bead Note Attachments & Sensitivity Governance

**Researcher ID:** `research.n.gem` (5-Researcher Swarm)  
**Deliverable File:** [`public_bead_note_attachments__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/public_bead_note_attachments__gem.md)  
**Registered Artifact Ref:** `file:explicit:93bced3c72c9eb6c30aef8f1` (`research:202609/public_bead_note_attachments__gem.md`)  
**Context Evaluated:** Approved epic `sase-1ck` (`plan:202609/bead_note_attachments.md`) & `research:202609/bead_note_attachments/attachment_storage_and_access.md`

---

## Executive Summary & High-Level Critique

### 1. The Core Idea: Is It Good?
- **The Goal (Public by Default for Collaborators):** **Strongly Approved.** In `sase-1ck`, non-collaborators see only prose and a `🔒` chip or `✕ unavailable offline` badge because `sase-org/sase--attachments` is a private repository. Removing this barrier so that any project collaborator or open-source contributor can access non-sensitive diagnostics (screenshots, visual diffs, repro traces) by default is a major usability and productivity improvement.
- **The Mechanism (Moving Bytes to `sase--beads`):** **Strongly Rejected (Architectural Anti-Pattern).** Storing binary attachments directly in `sase--beads` degrades ephemeral workspace cloning (`sase_<N>`), mixes working-tree JSONL projections with CAS blobs, and fatally breaks `sase bead attachment purge` because rewriting history with `git filter-repo` to erase an attachment would rewrite all commit SHAs across the entire bead issue tracker.
- **The Sensitivity Policy (Agent Discretion with Default Public):** **Rejected as a Security Risk.** LLMs are non-deterministic and context-blind to embedded credentials in large files. Relying on an agent to "decide" when a file is sensitive under a default-public policy guarantees that API tokens, internal hostnames, Authorization headers, and environment variables will eventually be leaked to public Git history.
- **Large Files via Remote Machine Support:** **Strongly Approved.** Restricting files $> 50\text{ MiB}$ to enrolled remote machines (e.g. `athena` via SFTP over Tailscale) avoids public cloud egress billing risks, complies with GitHub repository thresholds, and leverages SASE's authenticated peer-to-peer fleet.

---

## Key Findings & Recommended Adjustments

| Original Requirement / Idea | Critique & Assessment | Recommended Adjustment |
| :--- | :--- | :--- |
| **Move non-sensitive attachments to `sase--beads`.** | **High Risk:** Bloats the issue tracker, degrades ephemeral workspace instantiation, and makes GDPR / attachment purging rewrite all bead commit SHAs. | **Keep a dedicated `sase--attachments` sidecar, but set default visibility to PUBLIC** with a bare partial clone (`--filter=blob:none`). |
| **Default all attachments to public via agent discretion.** | **High Security Risk:** LLMs cannot act as reliable Data Loss Prevention (DLP) filters. Accidental leaks in public Git history are instantaneous and permanent. | **Implement a 3-tier Defense-in-Depth framework:** (1) Deterministic refusal + automated regex/entropy DLP scanning, (2) Media-type safe defaults (visual images = public; logs/dumps = scan or private), (3) Explicit agent/human tagging (`@private:./path` / `-P`). |
| **Unspecified private storage location.** | Ambiguous routing for sensitive attachments when the default tier is public. | **Route private attachments to the Authenticated Remote Machine Store (`athena` SFTP)** or an optional `sase--attachments-private` sidecar. |
| **Support large files only via remote machine support.** | **Economically and technically sound:** Avoids public CDN egress costs and GitHub file size blocks. | **Adopted as specified.** Retain Phase 6 rclone SFTP tier over Tailscale for files $> 50\text{ MiB}$. |

---

## Recommended Architecture: Dedicated Public Sidecar + 3-Tier Sensitivity

### 1. Storage & Transport Architecture
Instead of merging binary files into `sase--beads`:
1. **Public Sidecar Repository:** For public projects, create `sase--attachments` as a **public** repository on GitHub.
2. **Git Promisor Partial Clone:** Collaborators clone the repository with `--bare --filter=blob:none` at `~/.sase/projects/<key>/repos/attachments`.
   - **Zero initial download:** Cloning takes milliseconds and transfers 0 blob bytes.
   - **Anonymous HTTPS fetch:** Any collaborator can fetch blobs on demand without GitHub tokens or organization permissions.
   - **Workspace safety:** Ephemeral workspaces never clone the attachments repo.
   - **Isolated history:** Running `git filter-repo` on `sase--attachments` to purge a file does not alter commit hashes in `sase--beads`.

### 2. The 3-Tier Sensitivity Defense
1. **Tier 1: Deterministic Refusal & Automated DLP Scanner (`sase-core`)**
   - Refuse blacklisted paths (`~/.ssh/*`, `*.pem`, `*.key`, `.env*`, `*credentials*`, `id_*`).
   - Run an in-process regex/entropy scanner on text attachments before staging (detecting AWS keys, GitHub PATs, JWTs, Bearer tokens, private keys). Matching files are strictly refused from public storage.
2. **Tier 2: Media Classification**
   - Visual images (`.png`, `.jpg`, `.svg`, `.webp`) and in-tree tracked Git files default to **Public**.
   - Logs (`*.log`), memory dumps, database fixtures, and network captures default to **Private** unless explicitly cleared by the scanner.
3. **Tier 3: Explicit Agent & Human Syntax**
   - Grammar: `@./path` (evaluates via DLP), `@private:./path` (forces private tier), `@public:./path`.
   - CLI: `sase bead note <id> "..." -P/--private`.
   - Wire descriptor: Add `"visibility": "public" | "private"`.

---

## Follow-up Epic Blueprint: `sase-pubatt`

When `sase-1ck` closes, launch the follow-up epic across 5 focused phases:
1. **Phase 1: Wire & Grammar (`sase-core`):** Add `visibility` to attachment descriptors and parse `@private:<path>` notation.
2. **Phase 2: In-Process DLP Secret Scanner (`sase-core`):** Deterministic pattern and entropy checks preventing credential exposure.
3. **Phase 3: Public Attachments Sidecar Init (`sase`):** Update `sase repo init` to provision `sase--attachments` as a public bare partial clone with anonymous HTTPS promisor remotes.
4. **Phase 4: Store Routing & Remote Machine Tier:** Dynamic routing of public blobs $\le 50\text{ MiB}$ to `sase--attachments` and private/large blobs to remote machine SFTP (`athena`).
5. **Phase 5: Agent Skills, Diagnostic Doctor, and TUI Badges:** Update skill templates with unambiguous attachment rules, add doctor reachability checks, and render distinct `🔒 private (athena)` badges.

---

The full research report has been committed to the research repository and registered as a durable artifact snapshot.
