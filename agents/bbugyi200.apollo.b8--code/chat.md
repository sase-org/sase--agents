# Chat History - ace-run (b8--code)

- **TIMESTAMP:** 2026-10-30 12:41:43 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** b8--code

## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202610/research_highlights_non_report_captures.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- topic_dir_scope = canonical (planner default: canonical). Implement the "topic_dir_scope = canonical" branch; ignore "topic_dir_scope = depth_only". Context: "Should bob_research_capture also skip topic-dir Markdown other than <name>/<name>.md?".
- vault_cleanup = gate (planner default: report). Implement the "vault_cleanup = gate" branch; ignore "vault_cleanup = report". Context: "Should the implementer propose removing the junk refs already in the Bob vault?".
Implement only the branches selected above.


## Response

I'll start by reading the implement skill and opening the approved plan in the plans sidecar.

The research open landed on a mismatched clone. I'll locate the plans sidecar and read the approved plan from there.

I'll open both linked repos and inspect the hook template, capture script, and tests.

I have the intended filter, capture guard, and junk-ref paths. Next I’ll land those code changes and tests.

Asset-folder junk is filtered; topic-dir notes still match the hook and the capture command skips them. Next I’ll run the guarded check in `sase-research-artifacts`.

The research-highlights leak is stopped at both layers: hook globs now only admit report-depth Markdown, and `bob_research_capture` skips anything that is not `<YYYYMM>/<stem>.md` or `<YYYYMM>/<name>/<name>.md`.

### Code
- **sase-research-artifacts:** hook `path_globs` are `20*/*.md`, `20*/*/*.md`, plus `!20*/**/*_assets/**`. Inventory globs are unchanged. Docs/tests updated.
- **chezmoi:** `bob_research_capture` skips non-canonical month-dir Markdown with exit 0 and no `bob` call.

### Verification
- Research-artifacts: `sase tool run check` succeeded (162 tests passed).
- Chezmoi: `bashunit ./tests/bash/bob_research_capture_test.sh` — 16 passed.
- Matcher replay of the incident: the three `_assets` junk ADDs are `False`; the two wanted linker reports are `True`. `acceptance.md` and `pdfkit_table_selection_report_drafts.md` still match the hook (depth-2 topic-dir Markdown); the capture command skips them.

### Live hook
`sase file-hook list --json` still shows `20*/**/*.md`. Apollo’s plugin is the primary `sase-research-artifacts` checkout; it needs a fast-forward after the commit lands. Do not hand-edit it. Athena picks up the template from its install or the patch release.

### Vault cleanup
Gate `custom-862617ba-fe55-4b74-a37c-8e51f9c1aafe` is waiting. Preview with `p`, then **Remove junk refs and vault-sync** or leave them.

| Ref | Task | Status |
|---|---|---|
| `README_2` | `done/bob_done.md` `^ref-readme-2` | abandoned |
| `README_3` | `bob.md` `^ref-readme-3` | queued |
| `test` | `bob.md` `^ref-test` | queued |
| `pdfkit_table_selection_report_drafts` | `bob.md` `^ref-pdfkit-table-selection-report-drafts` | queued |
| `acceptance` | `bob.md` `^ref-acceptance` | queued |
| `README` (Oct 7) | on the note | abandoned |
| `demo` (Oct 7) | on the note | abandoned |

After the chezmoi commit lands, deploy with `chezmoi update -a --force`. I could not run that this turn.
