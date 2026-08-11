# Chat History - ace-run (research.09.cdx)

- **TIMESTAMP:** 2026-08-11 10:13:37 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.09.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260811_093801.md`

## Prompt

%clan(research.09, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] We currently support 8 different types of artifact references
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

IMPORTANT: Your goal is research only. Do NOT attempt to implement any of this.]]) %id:research.09.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase We currently support 8 different types of artifact references
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

I’m using the SASE memory, patch/bead, and repository-access skills because this research crosses xprompt internals, bead history, and configuration/code in linked sidecar and chezmoi repositories. I’ll trace the current implementation and `sase-ho` rationale, compare it with the plugin/config and publishing architecture, then write only the requested research report—no implementation changes.

The completed `sase-ho` epic confirms the coupling the redesign is trying to remove: it synthesized sidecar refs as hidden `#ref/*` xprompts and reused xprompt discovery, editing, and completion paths. I’m now separating the genuinely reusable pieces (filtering/resolution contracts) from that xprompt-specific transport, while tracing publication and provenance as a distinct lifecycle.

A useful discovery is that SASE already has most of the publication substrate: launch-time ref manifests, content hashing, agent prompt archives, and prompt-link rewriting. The redesign should extend that pipeline rather than rebuild it. The main gaps are immutable revision capture, true digest-only storage, reference-style link numbering, a versioned per-run usage manifest, and post-publication backreference outboxes.

I’ve finished tracing the existing ref pipeline through launch, resolution, staging, publication, and the Artifacts UI. The key finding is that the `sase-ho` work mixed reusable infrastructure with xprompt-specific coupling, so the report will recommend a surgical redesign rather than reverting its commits wholesale. I’m now checking the research-repo conventions and a few primary specifications before writing the report.

The evidence supports a narrower, cleaner boundary than the previous design: plugins should register versioned, declarative provider specifications once, while Rust owns parsing, validation, inventory semantics, and normalized results. That keeps `@` completion, prompt launch, publication, and the TUI on one contract without running arbitrary plugin code in each frontend or on every reference.

The report is written. It includes a concrete provider schema, exact proposed configuration for the plan/research providers and Bryan’s `@file` allowlist, the publication/link-number algorithm, a content-addressed file layout, a retryable back-reference protocol, the dynamic TUI model, a migration map for `sase-ho`, and a phased verification strategy. I’m doing a final consistency and Markdown validation pass now.

Research is complete in [artifact_ref_contract_redesign.md](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research/202608/artifact_ref_contract_redesign.md>).

The central recommendation is a surgical replacement of `sase-ho`’s xprompt coupling—not a wholesale revert—using a Rust-owned declarative provider contract, immutable per-agent ref-use manifests, SHA-256 content-addressed storage, and retryable post-publication backrefs.

No implementation, configuration, repo, or bead changes were made. The report passes Prettier validation.

The research report is already complete; this finalizer pass requires committing that new file in the research sidecar. I’m using the mandated SASE commit skill now, then I’ll verify the repository is clean.

The commit encountered an upstream rebase conflict because the same report path was independently committed on `origin/main`. I’m comparing the two versions now; I’ll retain the complete report, continue the paused rebase, and finish the SASE commit bookkeeping as required.

Committed and pushed the research report:

- Report: [artifact_ref_contract_redesign.md](</home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research/202608/artifact_ref_contract_redesign.md>)
- Commit: `d4a2117` (`docs: research artifact reference provider redesign`)
- Repository is clean and synchronized with `origin/main`.
- No implementation changes were made.
