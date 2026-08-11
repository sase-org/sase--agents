# Chat History - ace-run (research.09.final)

- **TIMESTAMP:** 2026-08-11 10:28:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.09.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260811_093801.md`

## Prompt

%id(final, clan=research.09) %wait(priority=20) %m:@research_lead
%wait:research.09.cdx %wait:research.09.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

We currently support 8 different types of artifact references
(referred to as "refs" for the rest of this prompt)--the 6 builtin ones   `@plan` and
`@research`. These are all supposedly defined using xprompts (see the sase-ho epic bead
for context). I want to revert most of (all of?) the work associated with the sase-ho
epic bead and re-design refs.

- Let's stop using xprompts to define refs.
- Instead, let's use a ref contract that is fulfilled by a few builtin refs, the special
  `@file` ref, and sidecar repo (which we might rename to artifact repos in the future)
  configurations.
- We should support the following builtin refs:
  - `@stitch`: Should accept an argument of the form `<short_hash>` for the primary
    project repo (determine what project is in context by checking what VCS xprompt
    workflow is used in the prompt) or `<repo>@<short_hash>` for some other `<repo>`.
  - `@patch`: Should accept a Patch name as an argument.
  - `@bead`: Should accept either `<short_id>` (defaults to searching the current
    project's--i.e. the project in context--bead store) or `<full_bead_id>`.
- Sidecar repo ref configurations should be able to be defined either inline (i.e. by
  defining all of the proper configuration fields explicitly in a project's
  sase/sase.yml file) or via the special `use: <ref_provider>` field.
  - When the `use: <ref_provider>` field is provided, it should be one of the only
    fields needed since we should infer the ref's configuration from `<ref_provider>`,
    which should specify a ref provider name that was registered as a plugin. This way
    users can define and share their own artifact reference types. See how we do this
    with other pluggable functionality (e.g. with pluggy hooks) in sase for inspiration.
  - We should define a builtin `<ref_provider>` for the `@plan` ref, which should be
    added to the project-local sase/sase.yml file via the `use: <ref_provider>` field
    when the `plan` sidecar repo is initialized by the `sase init` command.
  - Similarly, we should define a new plugin hook that allows `file_hooks` config
    entries to set the `use: <file_hook_provider>` field.
  - My custom `research` sidecar repo and its associated file hook (defined in my
    chezmoi repo) is the perfect first use-case for these plugin hooks:
    - Let's define all of the necessary configuration for that repo (including the ref
      provider and file hook provider) in the new sase-org/sase-research GitHub repo.
    - Configure this repo as a linked repo in this project's sase/sase.yml file. Make
      sure it is clear from this repo's description the distinction between this repo
      and the `sase--research` sidecar repo (since they are so similarly named).
    - Make sure the `command` field of the file hook is still customizable by users of
      the research file hook provider (we should still define
      `command: bob highlights create --include-id` in my chezmoi repo's sase.yml file's
      configuration).
    - Also, move all `#research` related xprompts into this new repo (including the
      `#research_swarm` xprompt workflow).
    - Make sure this new repo has excellent linting, tests, CI, and documentation. Don't
      skimp on this!
- The special `@file` ref will allow the user to reference local files that are then
  tracked/published (to the `agents` sidecar repo--see related bullets below) by sase.
  - The user will need to define which files are supported via a new sase config field.
    Make sure they are able to specify directories and file types (e.g. only markdown
    files in the ~/bob/ directory, recursively--which should be the configuration you
    add for me in the sase.yml file in my chezmoi repo).
  - When a `@file` reference is found in the prompt, the file should be added as a sase
    artifact file which gets associated with the sase agent that gets launched by that
    prompt.
  - When publishing that agent's data files to the `agents` sidecar repo, we should
    replace `@<ref>:<file>` (in the prompt) with a `[@<ref>:<file>][<N>]` link, where
    `<N>` is the first available positive integer not taken by a different link in that
    file, that links to that file, which should be contained in a files/ directory
    somewhere in the `agents` sidecar repo (make sure we use hashes to track file
    content duplicates and store each new instance--i.e. new contents--of a ref file to
    this repo in exactly one location).
- Every ref type will need to configure the following behaviors:
  - What text should expand in place of the `@<ref>:<arg>` text?
  - Which files (or generic entries, in the case of builtin refs) should be tracked and
    supported (e.g. for completion, validation, etc...)?
  - Which properties are supported and how are they parsed (this will likely be via
    frontmatter properties in markdown files for most ref types, but builtin refs will
    need to do something different)? These will be used to support filtering the
    corresponding "Artifacts" sub-tab (see related bullet below) entries and may be used
    (use your best judgement here) to support some kind of custom/pretty rendering when
    that entry is selected on that sub-tab.
- As a part of this feature, we should also change the sub-tabs on the "Artifacts" tab.
  - Each sidecar repo with a configured artifact ref type should cause a new sub-tab of
    the "Artifacts" tab to be rendered (e.g. if any enabled sase projects configure the
    research sidecar repo, for example, then a `Research` sub-tab should be available on
    the "Artifacts" tab).
  - Let's get rid of the current version of the "Files" sub-tab:
    - The "Plans" sub-sub-tab is obsolete, since this should be replaced with the new
      "Plans" sub-tab that gets rendered automatically (assuming the builtin `plans`
      sidecar repo is configured for at least one enabled sase project).
    - The "Chats" and "Files" sub-sub-tabs can both be deleted (neither was providing
      much value).
    - The "Files" sub-tab should remain, but should be completely re-designed. Namely,
      this tab will be used to display all `@file` refs that were used in sase agent
      prompts. Make sure that every version of a referenced file ref is viewable from
      this tab but only show one entry per unique file path (e.g. if `@file` was used
      multiple times with ~/bob/gtd.md as its argument in multiple prompts and the
      ~/bob/gtd.md file contained different contents when those refs were used, then
      there should only be one entry corresponding with ~/bob/gtd.md, but I should be
      able to toggle through all known versions of that file's contents when that entry
      is selected).
    - The "Files" sub-tab should also show any files that were added as artifacts by
      sase agents using the `sase artifact create` command. Make sure each file's origin
      (i.e. reason for being shown on this sub-tab) is made clear somehow.
- Also, as a part of this feature, we should start doing a much better job of tracking
  which refs were used by which sase agents.
  - In addition to the linkage that occurs for `@file` refs, other refs found in prompts
    should also be converted to an appropriate `[@<ref>:<arg>][<N>]` link.
  - Use your best judgement about what destination to link to from these links (for
    sidecar repo refs, we should link to the corresponding artifact file--at the
    appropriate commit using some kind of permalink--in that sidecar's GitHub repo).
  - Also, for sidecar repo refs, these should trigger corresponding commits (only when
    the sase agents who used that ref is published to the `agents` sidecar repo) to
    those sidecar repos to add an appropriate entry to a new `Referenced By` table that
    we start rendering at the bottom of these artifact files (only when there are known
    references). Make sure this table contains useful information, including a link to
    the corresponding sase agent's page.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

IMPORTANT: Your goal is research only. Do NOT attempt to implement any of this.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.09.cdx` -> `__a`, `research.09.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading both researchers' transcripts to identify their report files.

Both researchers wrote to the *same* filename — I need to check whether one overwrote the other. Let me open the research repo properly first.

Both wrote to the same path — `d4a2117` (cdx) rebased on top of `9a45b3b` (cld). Let me recover both versions.

cdx's commit overwrote cld's report during the rebase — both are recoverable from git history. Let me set up the directory and recover both.

No collision (nullglob made `ls` list the whole dir). Creating the layout and recovering both reports:

Both reports preserved. Now let me read them in full.

Both reports are strong and largely agree, but they conflict on several load-bearing points. Let me verify the disputed claims myself.

Confirmed the disputed Rust claims. Now checking the plugin/config/UI surfaces and bead history.

Both reports listed the research xprompt inventory differently. Let me get the actual set.

I have everything I need. Writing the consolidated report.

Prettier isn't converging — likely a broken emphasis span. Let me find it.

Prettier now passes. Let me verify it didn't mangle the `**/*.md` glob inside a bold span at line 99.

Prettier corrupted that bullet's glob patterns. Let me fix it and check for similar damage elsewhere.

Done. Consolidated report written.

## What I found first

**The two reports were written to the same path and one overwrote the other.** `research.09.cdx` hit a rebase conflict against `research.09.cld`'s already-pushed commit and resolved it by keeping only its own version. Both are recoverable from git — I extracted `9a45b3b` (cld) as `__b` and moved the working-tree file (`d4a2117`, cdx) to `__a`. Nothing was lost.

## Final layout

```
202608/ref_provider_contract/
├── ref_provider_contract__a.md    (cdx, 1188 lines)
├── ref_provider_contract__b.md    (cld,  809 lines — recovered from git)
└── ref_provider_contract.md       (consolidated, 1237 lines)
```

## What my own pass added

Both reports agreed on the big call — **surgical retirement of the xprompt adapter, not a `git revert`** — so I spent my effort on their eleven disagreements and on claims neither had verified. Reading the code settled them:

- **`artifact_pool_filename` has *two* duplication vectors, not one.** It's `{12-hex-prefix}-{basename}`, *and* `relative_artifact_link` publishes to `artifacts/<yyyymm>/`. So identical bytes duplicate across both basenames and months. `__a`'s full-SHA-256 store is required; `__b`'s "reuse the existing pool" cannot satisfy your "exactly one location" requirement.
- **The link allocator is 90% there, not 100%.** `assign_reference_id` really does allocate the first free integer and reuse one `[N]` per destination — but `reference_ids_in_body` scans definition lines only, not numeric *uses*, and has no fence awareness. `__b` called it done; it needs a specific extension.
- **The authored plans ref is `@plans`, plural** (the kind defaults to the sidecar role). Your `@plan` is a rename needing an alias — `__a` caught this, `__b` missed it.
- **The research xprompt inventory:** four of the five (`#research`, `/image`, `/more`, `/prompt`) live in chezmoi's `xprompts:` YAML block, not as `.md` files. `__b` assumed all five were files, which would mis-scope the migration.
- **`sase-hv` is already closed as `canceled`** — `__a` recommended dealing with it; it's done.
- The research ref's globs today are the default `**/*.md`, so adopting the file hook's tighter globs is a visible behavior change, not a port.

The main architectural conflict — declarative specs only (`__a`) vs. optional per-use pluggy callbacks (`__b`) — I resolved for `__a`, on the grounds that callbacks make config validation impossible without importing plugin code and put shared semantics on the wrong side of the Rust-core boundary. I kept `__b`'s naming (`sase_artifact`) and its `@file` two-payload grammar, which the scanner's existing two-colon special case backs up.

The report ends with five open decisions flagged for you rather than assumed — chiefly whether `@chat`/`@bug`/`@agent` survive, since their strings are persisted in bead refs and manifests, making removal a data migration rather than a deletion.

The three files are in the research repo but **uncommitted** (the `git mv` is staged, the two new files untracked) — I didn't commit since you didn't ask.

I'll commit the three report files in the research repo.

These are my changes from this session. Committing them with the commit skill.

Committed. Working tree is clean and `main` is level with `origin/main`.

**Commit `e3f7aad`** — `docs: add consolidated ref provider contract research`

All three files are in the tree at `202608/ref_provider_contract/`:

| File | Lines | Source |
|---|---|---|
| `ref_provider_contract__a.md` | 1188 | cdx (`research.09.cdx`) — the surviving working-tree report |
| `ref_provider_contract__b.md` | 809 | cld (`research.09.cld`) — recovered from `9a45b3b` |
| `ref_provider_contract.md` | 1237 | consolidated |

Both researchers wrote to the same path (`202608/artifact_ref_contract_redesign.md`), and cdx's rebase onto cld's already-pushed commit resolved the collision by discarding cld's version. I recovered it from git history, so nothing was lost — the commit message records this so the recovery is traceable later.

One non-blocking warning from the commit hook: the project has 3 quarantined agent-hood publication requests, so the agent link written into this commit may not resolve until you run `sase agent sync --retry-quarantined`. That's pre-existing and unrelated to these files.
