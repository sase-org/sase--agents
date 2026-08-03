# Chat History - ace-run (chop.refresh_docs.sase.0_753955.2)

- **TIMESTAMP:** 2026-08-02 19:23:53 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** chop.refresh_docs.sase.0_753955.2

<!-- sase:section:xprompt -->

## Agent XPrompt

[#gh:sase-org/sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(chop.refresh_docs.sase.0_753955.2, tribe=chop)
%wait:chop.refresh_docs.sase.0_753955.1
%wait(runners=0)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

<!-- /sase:section:xprompt -->

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 961 B</summary>

```markdown
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where
terminology or workflow ordering could be misunderstood. You may only create,
modify, or delete documentation files, such as Markdown or other docs-tree
content, READMEs, and doc-adjacent assets. You MUST NOT create, modify, or
delete source code, tests, build configuration, or any other non-documentation
file, even to fix a bug you are confident about.

When documentation and code disagree, document the actual current behavior;
never change the code to match the prose. If you identify a suspected code bug,
describe it in your final response so a human or separately scoped agent can
pick it up (and you may also note it in the commit message body), but do not fix
it. Run the repository's documentation checks when you change files.
```

</details>

<!-- /sase:section:rendered -->

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.0_753955.2, tribe=chop)
%wait:chop.refresh_docs.sase.0_753955.1
%wait(runners=0)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I’ll audit the update agent’s documentation diff against the implementation and command behavior, then edit only documentation and run the repository’s documentation checks. I’ll call out any code defects I find without touching code.

The commit is cleanly isolated at `HEAD` and changes 11 documentation files. I’ve narrowed the substantive claims to three areas: ACE’s Artifacts hierarchy, the two stored prompt representations and their size/search semantics, and the related CLI/configuration behavior. I’m now tracing each claim to command definitions, rendering/storage code, and tests.

One important mismatch has surfaced: an archive’s default body is not always the pre-expansion XPrompt. Ordinary commit publication uses `raw_xprompt.md`, but an approved planner run deliberately supplies a dry-expanded, directive-stripped plan snapshot and names it after the plan. Also, the “rendered prompt” is the final preprocessed text SASE hands to the provider—not the provider’s complete model context. I’m correcting those distinctions throughout the changed docs and the linked prompt-rendering reference.

The prose now distinguishes the two real publication paths and removes the misleading “exact model input” claim. I also verified the ACE labels and nesting directly from the canonical tab-order constants and widget composition: Commits, Beads, Bugs, PRs, Files; then Plans, Chats, Other under Files. Next I’m validating the documented CLI flags and prompt behavior with focused tests, followed by the strict docs build and required repository check.

The strict site build passed. The required repository check then stopped at Markdown formatting for three edited docs; I’m applying the repository’s Prettier settings only to those documentation files, then I’ll rerun both checks.

The strict docs build now passes after formatting, and the full repository check has cleared formatting, all linters, SASE validation, and committed-plan validation. The full test suite is still running; the focused behavior audit already passed 99 tests covering prompt storage/search, archive commands, configuration, and the ACE hierarchy.

The full repository check has completed successfully, including the complete test suite. I’m doing the remaining documentation CI path now—the PDF handbook build/validation and deploy-artifact assertions—so the review covers the same documentation surfaces users receive, not just the HTML site.

Audited and corrected the documentation. Only documentation files changed.

Key fixes:

- Distinguished commit-backed prompt archives from approved-plan archives and documented their actual ordering.
- Clarified that “rendered prompt” means the preprocessed prompt SASE hands to the provider, not the provider’s complete model context.
- Documented truncation, identical-prompt handling, search exclusions, and CLI output accurately.
- Confirmed the ACE hierarchy: Commits, Beads, Bugs, PRs, Files; with Plans, Chats, Other under Files.

Updated: [agents_sidecar.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/agents_sidecar.md:68), [sdd.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/sdd.md:59), [xprompt.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/xprompt.md:1933), [configuration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/configuration.md:2140), [prompt.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/prompt.md:57), and [cli.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/cli.md:287).

Checks passed:

- `just docs-check`
- `just docs-pdf-check` — validated 592-page handbook
- `just docs-deploy-artifact-check`
- `just check`
- 99 focused behavior tests

Suspected code issues left untouched:

- `sase agent prompts show` help and JSON still label the default output as `xprompt`, although approved-plan entries contain a dry-expanded primary body.
- Prompt archives duplicate an identical provider prompt, while chat history uses an identity marker to avoid duplication. This may be an implementation inconsistency.

The listed documentation edits are the changes from this audit, so I’m using the required SASE commit workflow to commit exactly those six files.

The commit is scoped to the audited docs and describes only the corrected prompt-publication, storage, search, and ACE/CLI documentation. I’m committing it now and will verify the branch is clean and synchronized afterward.

Committed the six audited documentation files as:

`fe0d71e09 docs: clarify archived prompt representations`

The working tree is clean and synchronized with `origin/master`. Documentation checks and the full repository check passed. No source or non-documentation files were changed.
