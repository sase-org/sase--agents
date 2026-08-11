# Chat History - ace-run (research.09.cld)

- **TIMESTAMP:** 2026-08-11 09:57:28 EDT
- **MODEL:** claude/opus
- **AGENT:** research.09.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260811_093801.md`

## Prompt

%id(cld, clan=research.09) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase We currently support 8 different types of artifact references
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

IMPORTANT: Your goal is research only. Do NOT attempt to implement any of this. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding the current state of the codebase.

I have a full picture now. Writing the research document.

Research written to `sase/repos/research/202608/artifact_ref_contract_redesign.md` (the sase repo itself is untouched, so no `just check` needed).

## What I found

I read the `sase-ho` epic's actual diff (Python: 3,488 insertions / 132 deletions across 83 files; Rust `4071bf0`: +2,040 across 24 files, already released as `sase-core-rs` v0.21.0), the current `artifact_ref/` Rust module, the Python `artifact_ref_*` / `sidecar_ref_config` / `loader_refs` layer, the pluggy patterns in `vcs_provider`/`workspace_provider`, `config/file_hooks.py`, the ACE `widgets/artifacts/` tree, the agents-sidecar prompt-archive publisher, your chezmoi `sase.yml` + `research_swarm.md`, and the (empty, 0-byte-README) `sase-org/sase-research` repo.

## The four load-bearing conclusions

**1. Don't `git revert` sase-ho.** It's three separable layers and only one is the thing you dislike. The *path-filter contract* (`filter_artifact_ref_path_payloads`, `path_globs`, the `filtered` status) and the *document-root plumbing* are exactly what the new ref contract needs — reverting them means rebuilding them. I list a surgical delete set (~1,200–1,600 LOC) and an explicit keep set.

**2. Make the provider contract declarative-first, with pluggy as an override.** Copying the `sase_vcs`/`sase_workspace` pure-pluggy shape would force `sase-research` to ship ~300 lines of Python for behavior that's entirely describable as data, and would make config validation impossible without importing plugin code. A `RefProviderMetadata` literal + optional hooks makes the research provider ~60 lines and no custom resolution code.

**3. Three things you asked for already exist.** `commit_footer.rs::allocate_numeric_id` is *literally* "first available positive integer not taken by another link in that file," including one-`[N]`-per-destination reuse. `rewrite_prompt_artifact_links` already rewrites live refs idempotently while skipping fenced blocks and existing links — it just emits inline instead of reference-style. And `refresh_plan_links` already does locked, batched, cross-repo section reconciliation — that's your `Referenced By` writer.

**4. The biggest risk isn't any new feature — it's persisted data.** `commit:` and `file:` reference strings live in bead `refs:` lists, `consumption.jsonl`, prompt manifests, and Patch files. `@stitch` needs a permanent parse alias, not a rename.

## Two decisions I flagged rather than assumed

- **`@chat` / `@bug` / `@agent`**: your list of builtins names only `stitch`/`patch`/`bead`(+`file`). I recommend keeping those three as builtin *providers* (they satisfy the contract with no special-casing, and removal is a data migration), but called it out as your call.
- **`@file` grammar**: I recommend one kind with two payload shapes (path *or* `explicit:<digest>`) rather than splitting off `@artifact` — `scanner.rs::trim_candidate_end` already special-cases `kind == "file"` with two colons, so the grammar was built anticipating this.

The doc ends with a 7-phase epic graph (ACE tab redesign last, `sase-research` after the provider hook), a risk table, five rejected alternatives with reasons, and the `sase-research` vs `sase--research` disambiguation — including that the linked-repo `description:` is what `sase memory init` renders into `AGENTS.md`, so that's where the distinction has to land.

The research document I wrote is untracked. Committing it via the required skill.

Committed. The research repo is clean and in sync with `origin/main`.

**What I did:** the only uncommitted change was the research document I wrote earlier in this session — `202608/artifact_ref_contract_redesign.md` (809 lines) in the research repo. The finalizer listed it twice (once as linked repo, once as SDD sidecar) because both resolve to the same checkout, so one commit covers both.

- Commit `9a45b3b` — `docs(research): design an artifact-ref contract to replace ref xprompts`
- Staged only that file via `-f`; tag `docs(research)` matches the repo's existing history
- `git status --short --branch` → clean, not ahead of upstream (pushed)

The sase workspace repo itself was never modified, so no `just check` was needed.

One thing worth your attention, unrelated to this commit: `sase commit` warned that the project has **3 quarantined agent-hood publication requests**, so the agent link written into this commit may not resolve until the outbox is cleared. It suggests `sase agent sync --retry-quarantined`. I did not run it — clearing a publication outbox is outward-facing and pre-existing, so it's your call.
