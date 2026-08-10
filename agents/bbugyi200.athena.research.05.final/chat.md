# Chat History - ace-run (research.05.final)

- **TIMESTAMP:** 2026-08-10 15:16:24 EDT
- **MODEL:** claude/opus
- **AGENT:** research.05.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260810_144802.md`

## Prompt

%id(final, clan=research.05) %wait(priority=20) %m:@research_lead
%wait:research.05.cdx %wait:research.05.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to start creating a corresponding bead for every
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
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.05.cdx` -> `__a`, `research.05.cld` -> `__b`), then read both reports.
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

I'll start by reading both transcripts to identify which report each researcher wrote.

Mapping confirmed: `research.05.cdx` → `external_issue_patch_reconciliation.md` (`__a`), `research.05.cld` → `external_bug_and_pr_mirroring.md` (`__b`). Reading both reports now.

Both reports are substantive and disagree on the single most important design decision. Let me verify the contested claims myself.

Report B's `external_ref` claim checks out. Let me read the original plan's reasoning and verify the remaining contested points.

Report B's schema constraint claims are confirmed verbatim, including that the original plan listed `external_ref` as an explicit non-goal. Now the other contested points.

This is important — let me check the central filter point, which both reports missed.

Major finding: the patch-chop exclusion is a **query config** problem, not a code change. Let me verify.

Found something both reports missed. Let me verify the bug-id normalization collision.

Confirmed: `#42` in `sase` and `#42` in `sase-github` normalize identically. Now checking parser round-trip safety for a new field.

Verification complete. Both reports' core claims hold up, and I found three things neither caught. Creating the consolidated layout now.

Now writing the consolidated report.

The sase repo is untouched — all writes went to the research sidecar. Final layout is in place.

## What I did

**Transcript mapping** (from the chat headers, not filesystem order): `research.05.cdx` → `external_issue_patch_reconciliation.md` → `__a`; `research.05.cld` → `external_bug_and_pr_mirroring.md` → `__b`.

```
202608/external_artifact_ingestion/
├── external_artifact_ingestion__a.md   (30k, codex)
├── external_artifact_ingestion__b.md   (21k, claude)
└── external_artifact_ingestion.md      (34k, consolidated)
```

## The four disagreements, resolved

Both reports were strong and split on every substantive decision. I verified the contested claims against the code rather than picking a side by plausibility:

- **Bug↔bead link** — `__b`'s `external_ref` core column wins on identity, but `__a`'s `bug:` ref stays for resolution. **Write both.** `__b`'s blocking constraint is real (`CHECK(issue_type = 'plan' OR ...)` at `_db_schema.py:57-61`), and the original epic plan names `external_ref` verbatim as the designed follow-up — listed under *Non-goals* at `artifacts_tab.md:391`. The decisive argument is idempotency: `refs` has no uniqueness, so a human adding a second `bug:` ref silently mints a duplicate bead on the next pass.
- **PR provenance** — `__a`'s tri-state `PR_ORIGIN`, absent ⇒ `unknown`. `__b`'s absent ⇒ `sase` would assert provenance for the entire Patch history without evidence, permanently and undetectably.
- **Chop design** — split decision: `__a`'s `for_each: {source: projects}` fan-out (verified real) over `__b`'s manual loop, but `__b`'s core-builtin location over `__a`'s plugin registration, since reconciliation semantics must not live behind a repo boundary.
- **UI** — complementary, merged.

## Three hazards neither report found

1. **`_normalize_bug_id` collapses project identity.** I ran it: `bug:sase#42` and `bug:sase-github#42` both normalize to `'42'`. With four related repos on this machine, that's a live collision, and `__b`'s plan to extend `bug_links.py` walks straight into it.
2. **The patch-chop hazard has one choke point, not four scan sites.** `runtime.filtered_patches` feeds *six* chops from a single computation at `chop_runner_context.py:49` — but `pr_submitted_checks` (which `__b` listed) uses a different path entirely. Critically, the obvious fix of expressing the exclusion as an Axe query is unsafe: `axe_config.query` is user-overridable, so the exclusion must be structural.
3. **`__a`'s `SASE_PATCH=` stamp can't live where the agent footer lives.** `build_pr_body()` early-returns without `SASE_ARTIFACTS_DIR`, so a human running `sase commit pr` produces a tracked PR with no marker. It has to go in `append_pr_tags`.

One judgment call I made against both reports' framing: mirrored beads should have **unset** size, not `__a`'s `large` default — the schema permits NULL, and a fabricated estimate reads like a judgment no chop is entitled to make.

Committed. The research sidecar is clean and in sync with `origin/main`.

## Commit

`40a8cf8 docs(research): consolidate external artifact ingestion research` — git recorded the two source reports as pure renames (0 content change) plus the 585-line consolidated report, confirming both originals were preserved intact rather than rewritten.

```
202608/external_artifact_ingestion/
├── external_artifact_ingestion__a.md   (587 lines, codex — external_issue_patch_reconciliation)
├── external_artifact_ingestion__b.md   (349 lines, claude — external_bug_and_pr_mirroring)
└── external_artifact_ingestion.md      (585 lines, consolidated)
```

The `sase` workspace repo is untouched and clean — all writes went to the research sidecar.

One non-blocking warning from the commit: the project has **2 quarantined agent-hood publication requests**, so the chat link written into this commit may not resolve until you run `sase agent sync --retry-quarantined`. That predates this commit and doesn't affect the commit itself.

## What the consolidated report concludes

Both researchers split on all four substantive decisions, so I verified the contested claims against the code rather than picking by plausibility:

- **Bug↔bead link** — write *both* an `external_ref` core column (identity) and a `bug:` ref (resolution). The deciding argument is idempotency: `refs` has no uniqueness constraint, so a human adding a second `bug:` ref silently mints a duplicate bead on the next reconciliation pass.
- **PR provenance** — tri-state `PR_ORIGIN` where absent means *unknown*, not *sase*. Defaulting to `sase` would assert provenance over the entire existing Patch history without evidence.
- **Chop design** — split decision: the `for_each: {source: projects}` fan-out (verified to exist), but located as a core builtin rather than behind a plugin boundary.
- **Three hazards neither report found** — `_normalize_bug_id` collapses project identity (`sase#42` and `sase-github#42` both normalize to `'42'`, a live collision given four related repos here); the patch-chop exclusion has one choke point in the runtime's filtered-patch computation and must be structural because `axe_config.query` is user-overridable; and the `SASE_PATCH=` stamp must go in `append_pr_tags`, since `build_pr_body` early-returns when a human runs `sase commit pr` outside an agent run.

The report closes with four open questions for you, of which only one has no clear default: whether to adopt *all* PRs on a repo or only those authored by your own GitHub identity. That choice is what makes the chop exclusion load-bearing.
