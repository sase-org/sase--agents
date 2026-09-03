# Chat History - ace-run (research.4.cld)

- **TIMESTAMP:** 2026-09-03 16:56:25 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260903_163453.md`

## Prompt

%id(cld, clan=research.4) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I would like to add the ability for users to add new projects
in bulk from the "Projects" tab on the "SASE Admin Center" panel.

- This will be useful, for example, when users are onboarding a new machine and want to
  enable the set of projects they are currently working on for that machine.
- We should provide excellent completion for the organizations/repos that the user is
  most likely to select.
- See how we do this for the `#gh` VCS xprompt workflow's argument for inspiration.
- We need to make sure to do this in a VCS-agnostic way so future VCS plugins are
  supported automatically.
- As a part of this change we should stop auto-enabling new projects that are created
  when an argument is passed to a VCS xprompt workflow that is associated with a new
  (i.e. currently unknown to this machine's sase) project.

Can you do some research with the goal of helping me decide the best way to implement
this? In particular, think very hard about what the best UX for this functionality looks
like. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current state of the code.

Found the key file. Let me read the VCS ref completion machinery.

Now let me look at how the GitHub plugin's `ws_resolve_ref` creates a project (the auto-enable path).

I have what I need. Writing the research document now.

Research written to `sase/repos/research/202609/bulk_project_add.md` (630 lines, every structural claim cited to source at `9e2d95bb0`).

## What I found

**The feature is mostly assembly.** SASE already has a provider-agnostic, cached, ranked, error-classified repo catalog — it's the `#gh:sase-org/` completion menu — plus a multi-select project list whose `a` (enable) key already operates on the marked set, plus a canonical "browse remote catalog → mark many → preview → one tracked proc" pane in the Updates tab. Bulk add is the join of those three.

**"Add a project" is really "adopt a project."** Every discovery surface (`+` catalog, launch pickers, `sase project list`) keys off `PROJECT_STATE: enabled`. So bulk add *is* bulk enable over a row set that mixes local records with catalog entries — no new verb needed.

**The auto-enable behavior is an absence, not a statement.** Nothing calls "enable"; the GitHub provider writes a ProjectSpec containing only `WORKSPACE_DIR`, and missing `PROJECT_STATE` means enabled. Fixing it is one host-side write, but it collides with the workspace claim gate (blocks disabled specs) and with launch-time re-adoption (which would silently undo it on the second launch).

## Recommendation

A **fourth Projects sub-tab, `Add`**, whose single input is a provider ref minus the `#` (`gh:sase-org/`) driven by the *identical* completion helpers the prompt bar uses, and whose rows are a **three-state reconciliation** — `enabled` / `disabled` / `new` — committed with the pane's existing `m`/`u`/`a` gesture through a new `sase project add` CLI run as one tracked proc.

Two things I'd flag as the load-bearing decisions:

- **One optional field, `VcsRepoEntry.workspace_dir`,** is the reconciliation join key. It turns per-row `peek_ref` (O(N·M)) into one dict lookup, and it lets you retire a hardcoded `~/projects/github/<owner>/<repo>` guess currently sitting in a supposedly provider-agnostic host module. Bare-git, which implements neither catalog hook, degrades to a plain ref box with no special case — that's the VCS-agnosticism test.

- **The two halves compose.** After the auto-enable change, every one-off `#gh:owner/repo` launch deposits a `disabled` record — which is exactly the zero-cost, highest-intent band at the top of the new `Add` sub-tab. The change that stops the clutter and the change that lets you adopt in bulk are the same feature from two sides.

The auto-enable change needs four coordinated edits plus a `sunset` flag (it's user-reaching deprecation), and it touches four docs pages. §5 works through why each of the tempting shortcuts — a new lifecycle state, a second ProjectSpec axis, routing to the external-repo path — doesn't hold up.

Two open questions I left for you in §7: whether the empty-input root should show all workflows' namespaces or default to one provider, and whether adopting a `new` row should also run `sase init` (which the concurrent `projects_tab_init_ux` work is putting on `i`/`I` in the same pane).
