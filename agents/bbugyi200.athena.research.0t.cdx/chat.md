# Chat History - ace-run (research.0t.cdx)

- **TIMESTAMP:** 2026-08-21 09:40:21 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0t.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260821_092709.md`

## Prompt

%clan(research.0t, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I want to investigate and close out all of the remaining open sase feature flags, which represent deprecations and/or new features (some of which have been enabled already and others which are off by default). I already have some agents working on the `artifact_links` and `pluggable_finalizers` feature flags, so those are being handled. Can you do some research with the goal of helping me understand what needs to be done to get rid of the rest of the feature flags? End your analysis with a list of next steps associated with each open feature flag (except for the two that are already being worked). Keep your report concise and practical.]]) %id:research.0t.cdx
%wait(priority=20) %model:@research_a 
#gh:gh_sase-org__sase I want to investigate and close out all of the remaining open sase feature flags, which represent deprecations and/or new features (some of which have been enabled already and others which are off by default). I already have some agents working on the `artifact_links` and `pluggable_finalizers` feature flags, so those are being handled. Can you do some research with the goal of helping me understand what needs to be done to get rid of the rest of the feature flags? End your analysis with a list of next steps associated with each open feature flag (except for the two that are already being worked). Keep your report concise and practical. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’m using the SASE memory, repository, and artifact skills because this investigation touches feature-flag lifecycle rules and writes into the durable research repository. I’ll inventory every live flag, exclude `artifact_links` and `pluggable_finalizers`, trace each remaining flag through code/tests/history/task metadata, and finish with a compact per-flag action list. The requested `/sase_final` skill is not available in this session, so at the end I’ll use its stated `sase final context` / `sase final submit` command workflow directly as the closest supported fallback.

The lifecycle rules are clear: both beta and sunset flags are removed by deleting the Off branch and making the On branch unconditional; the flag bead closes in the same change. I’ve also opened the `research` sidecar through SASE’s audited repository workflow, so the requested path is now the authorized write target. Next I’m correlating registry entries with their dedicated beads and actual call sites.

The evidence now separates the flags into three buckets:

- Strong immediate candidates: `prettier_enabled` (the deprecated escape hatch is absent from your env and chezmoi config) and `plugin_catalog_scoped_latest` (the Off path is the documented O(catalog) PyPI storm; the On path already has scale guards).
- Needs deliberate soak: `coder_inherits_planner_chat`, `completion_refresh_on_update`, `epic_resume_gate`, and `commit_finalizer_shared_clone_exempt`. The first and third are currently off; your chezmoi-owned completion stamps mean the enabled completion flag skips all three installed shells; and I found no genuine persisted warning showing the shared-clone exemption has handled a real race yet.
- Release-gated: `ref_sync_gesture` is only two days old and its own removal criterion requires two minor releases, so it should remain unconditional-on through 0.16/0.17 and retire around 0.18 if no colon-consumption reports appear.

I’m turning that into the requested short report, with exact code/test cleanup and validation steps per flag.

The report is written and Markdown-formatted. It ends with seven flag-specific next-step sequences, omitting the two flags already assigned. I’m now registering the report as a durable SASE artifact and then I’ll run the requested final-declaration fallback; after that declaration I will not alter any files.

The host selected its built-in commit finalizer for the new research-sidecar file, so the final declaration requires a repository action. I’m consulting the SASE commit skill now because a post-completion finalizer has triggered it; this is part of the requested final-declaration workflow, not an extra source change.

Completed the research report: [feature_flag_closeout.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202608/feature_flag_closeout.md).

Key conclusion: remove `prettier_enabled` and `plugin_catalog_scoped_latest` soon; operationally soak four flags; retain `ref_sync_gesture` through 0.17.

Durable artifact:

- ID/ref: `file:explicit:021341d990702387222befba`
- [Stored snapshot](/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20260821092709/feature_flag_closeout-82bb25ddf5fb.md)

Markdown formatting and diff checks passed. The `/sase_final` skill was unavailable, so I ran its prescribed commands directly; the final declaration was accepted.
