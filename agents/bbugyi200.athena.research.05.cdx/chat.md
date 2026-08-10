# Chat History - ace-run (research.05.cdx)

- **TIMESTAMP:** 2026-08-10 15:04:50 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.05.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260810_144802.md`

## Prompt

%clan(research.05, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I want to start creating a corresponding bead for every
external bug (e.g. GitHub issue--but this should use our plugin system I think) created
for sase projects that are enabled on the given machine (I'm assuming we will use one or
more chops for this, but I am open to suggestions).

- I also want to do the same thing for Patches (i.e. create a new patch for each PR on
  enabled projects that was not created by a sase agent).
- I then want to merge the "Beads" and "Bugs" sub-tabs on the "Artifacts" tab in an
  elegant way that displays only beads but makes it very clear which beads are
  associated with bugs (and provides useful operations for editing/viewing those bugs).
- Again, we should do something similar for patches: Rename the "PRs" sub-tab of the
  "Artifacts" tab to "Patches" and start making it clear which Patches have PRs that
  were created externally associated with them. Keep in mind that, in the case of
  patches, sase agents do something create PRs and associate them with patches (so the
  existnce of a corresponding PR does not mean that the Patch was triggered by an
  external PR).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.]]) %id:research.05.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase I want to start creating a corresponding bead for every
external bug (e.g. GitHub issue--but this should use our plugin system I think) created
for sase projects that are enabled on the given machine (I'm assuming we will use one or
more chops for this, but I am open to suggestions).

- I also want to do the same thing for Patches (i.e. create a new patch for each PR on
  enabled projects that was not created by a sase agent).
- I then want to merge the "Beads" and "Bugs" sub-tabs on the "Artifacts" tab in an
  elegant way that displays only beads but makes it very clear which beads are
  associated with bugs (and provides useful operations for editing/viewing those bugs).
- Again, we should do something similar for patches: Rename the "PRs" sub-tab of the
  "Artifacts" tab to "Patches" and start making it clear which Patches have PRs that
  were created externally associated with them. Keep in mind that, in the case of
  patches, sase agents do something create PRs and associate them with patches (so the
  existnce of a corresponding PR does not mean that the Patch was triggered by an
  external PR).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll trace the current bead, Patch, Artifacts-tab, chop, and plugin boundaries, then compare feasible ingestion/synchronization designs. I’m using the SASE repo skill to inspect the research sidecar and linked plugin correctly, the memory-read skill for bead/xprompt rules, and the Patches skill for the existing Patch model. I’ll write the final recommendation as a new August 2026 research note.

The initial model confirms an important asymmetry: beads already have an event-sourced identity and artifact refs, while Patches already permit a `PR:` association but do not encode why that association exists. I’m now following the actual UI and provider code to find the cleanest place to add provenance and idempotent import, especially how “created externally” can be detected without guessing from the mere existence of a PR.

Axe already has the right scheduling primitive: a plugin can contribute an installed chop plus config that expands one stable instance per enabled project (`for_each: {source: projects, vcs: [gh]}`). That gives each project independent cadence/state and removes the need for a core loop that knows GitHub. The remaining design question is the durable identity model—URLs alone are good UI links, but too weak as the sole idempotency/provenance key.

I’ve finished mapping the current bead, Patch, provider, Axe/chop, and Artifacts-tab architecture. I’m now consolidating the tradeoffs into the research report, including the provenance and idempotency rules needed to avoid misclassifying SASE-created PRs as external.

The design is converging on two important invariants: external issues are linked through the existing canonical `bug:` artifact refs, while PR provenance needs a new explicit field because a `PR:` URL alone cannot distinguish an imported PR from one created by SASE. I’m writing the report around those two seams rather than introducing parallel “bug” or “external Patch” record types.

Research is complete: [external_issue_patch_reconciliation.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/external_issue_patch_reconciliation.md).

The recommendation is:

- Two provider-plugin Axe chops, one for issues and one for PRs.
- Reuse canonical `bug:` refs for bead associations.
- Add explicit `PR_ORIGIN: sase|external|unknown` Patch provenance.
- Stamp SASE-created PRs with `SASE_PATCH=<name>`.
- Merge Bugs into Beads and rename PRs to Patches, exposing remote records as facets rather than separate inventories.

The report covers polling/backfill, idempotency, lifecycle mapping, crash recovery, UI operations, ownership boundaries, alternatives, and a phased delivery sequence. `git diff --check` passes; no code tests were needed for this research-only sidecar addition.

The research note is already complete; this pass is the required publication finalizer. I’m using the SASE git-commit skill because it is the mandated commit path, then I’ll verify the research sidecar is clean.

The finalizer’s file is exactly the completed research report and no unrelated changes are present. I’ll commit only that note with a documentation-scoped message.

Research completed and committed as `2288093`.

Report: [external_issue_patch_reconciliation.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/sase/repos/research/202608/external_issue_patch_reconciliation.md)

The research sidecar is clean and synchronized with `origin/main`.
