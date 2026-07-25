# Chat History - ace-run

- **TIMESTAMP:** 2026-07-16 22:27:45 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** refresh_docs.sase.78eaa34f9dfc.polish
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260716_123347.md`

## Prompt

%wait:refresh_docs.sase.78eaa34f9dfc.update
%name:refresh_docs.sase.78eaa34f9dfc.polish
%w(runners=0)
#gh:gh_sase-org__sase %g:chop #fork:refresh_docs.sase.78eaa34f9dfc.update

Inspect the documentation changes made by the first refresh-docs agent.
Verify descriptions against the current system behavior rather than assuming they are true.
Improve clarity for a new user, especially where terminology or workflow ordering could be misunderstood.
Keep edits scoped to documentation unless a tiny sidecar correction is required.
If you change files, run the appropriate documentation checks for this repository.

## Response

I’ll review the prior `docs: refresh guides for current SASE behavior` diff against the actual CLI, configuration schema, and TUI implementation. I’ll focus on workflow order and terminology a newcomer could misread, make documentation-only corrections, then run the repository’s documentation checks and required full check if files change.

The lifecycle rename is the largest cross-cutting edit, so I’m validating it first at three layers: accepted on-disk values, public CLI vocabulary, and filtering behavior. After that I’ll verify the new ACE/family and Telegram descriptions directly against their implementations.

I found three concrete drift points already: the Admin Center docs describe a nonexistent enabled-only/state filter, the launch docs say explicit disabled-project refs are rejected even though launch preparation re-enables them, and the Telegram article says the update worker stops AXE even though it runs `sase update` and only ensures AXE is running afterward. I’m also checking the linked Telegram implementation so the newly added custom-command section reflects execution behavior, not just the core schema. I’ll use the `sase_repo` skill because repository instructions require it for that linked checkout.

The launch behavior is intentional and covered by launch tests: broad completion/catalog discovery excludes disabled projects, but a prompt that explicitly names a registered disabled project re-enables it before claiming a workspace. I’m going to document that distinction and separate it from `is_sase_managed`, ChangeSpec status, and “active agent” terminology. Because this touches xprompt/launch documentation, the project instructions also require the audited `sase_memory_read` workflow for the xprompt memory before I edit.

The main issue is now clear: the prior refresh reversed one important lifecycle rule. Disabled projects are hidden from broad discovery, but an explicitly typed known-project launch ref intentionally re-enables the project; only context-only launches remain blocked. I’m tightening that distinction across the lifecycle, workspace, xprompt, mobile, and architecture pages, and I’m correcting two smaller workflow-ordering descriptions in initialization and Telegram updates.

The corrections are applied across the existing canonical pages; no new guide or sidecar change is warranted. I’ve also made the lifecycle terms explicitly distinct from ChangeSpec status, “active” agents, and `is_sase_managed`, since those were easy for a first-time reader to conflate. I’m now reviewing the exact diff for overstatement and internal consistency before running the documentation build.

A second source-level check caught an important nuance before validation: a project checkout or mobile `project` value is only prompt-resolution context. It does not itself select that project’s workspace—bare prompts still default to `#git:home`. I’m correcting my initial wording and the mobile example so the docs distinguish context, explicit workspace refs, and low-level claim guards accurately.

The consistency scan is now clean, including one older onboarding article that still called initialization “memory, SDD, skills”; the current coordinator is memory, repositories, skills and plans all three before applying them. I’m moving to validation now: repository bootstrap first, then the strict documentation build and the required full check.

The strict MkDocs build passes. I’m starting the repository’s required full check now; the bootstrap is using the published-core fallback because this workspace’s optional linked `sase-core` directory is incomplete, the same supported fallback condition encountered in the earlier refresh.

The full check reached and passed formatting plus every lint/static stage, then stopped at SASE validation because the published `sase-core-rs` wheel lacks the checkout’s newer `sase_content_layout` binding. That is an environment/version mismatch, not a documentation failure. I’m doing a final diff audit and a couple of focused behavior tests that do not require that missing binding, then I’ll report the validation boundary precisely.

Reviewed the first refresh against current code, tests, and the linked Telegram integration. Updated 12 documentation files.

Key corrections:

- Clarified project lifecycle behavior: discovery is enabled-only, but an explicit known-project VCS ref automatically re-enables a disabled project. Context alone does not select a workspace; bare prompts default to `#git:home`. See [README.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/README.md:137), [project_spec.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/project_spec.md:157), and [mobile_gateway.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/mobile_gateway.md:486).
- Corrected ACE’s Projects inventory: enabled and disabled true projects appear together, enabled first, with one text filter—not separate lifecycle filters. See [ace.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/ace.md:1009).
- Clarified launch ordering and atomic workspace claims in [architecture.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/architecture.md:30).
- Corrected initialization ordering to memory → repositories → skills, and explained that `--yes` cannot approve missing sidecar creation. See [init.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/init.md:17).
- Documented actual Telegram custom-command isolation, reserved names, argument handling, and update-worker behavior in [configuration.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/configuration.md:1159) and [telegram-mobile-agents.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/docs/blog/posts/telegram-mobile-agents.md:140).

Validation:

- `just docs-check`: passed, including strict MkDocs build.
- Three focused behavior tests: passed.
- `just check`: formatting and all lint/static stages passed; SASE validation stopped because the installed published `sase_core_rs` lacks the newer `sase_content_layout` binding. This is an environment/version mismatch, unrelated to the documentation edits.

Changes remain uncommitted.

The 12 listed documentation edits are mine from this review, so I’m following the required `sase_git_commit` workflow now. I’ll commit only those files with a message scoped to the lifecycle and workflow clarifications.

The final diff is documentation-only and matches the verified corrections: explicit disabled-project refs re-enable at launch, project context is not workspace selection, Admin Center inventory semantics are corrected, and initialization/Telegram ordering now matches implementation. I’m committing this exact file set.

The commit hook is still running `just fix`; it has not reported errors or changed the reviewed scope. I’m waiting for the commit/push workflow to finish, then I’ll verify the branch and working tree.

Completed and committed the documentation review.

- Corrected lifecycle, launch-context, ACE inventory, initialization, and Telegram workflow descriptions across 12 documentation files.
- `just docs-check` and focused behavior tests passed.
- `just check` reached SASE validation but was blocked by the installed `sase_core_rs` missing `sase_content_layout`.
- No code or sidecar changes were needed.

Commit: `ea1db4f4b docs: clarify lifecycle and launch workflows`

The working tree is clean and synchronized with `origin/master`.
