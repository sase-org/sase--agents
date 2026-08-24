# Chat History - ace-run (0cy--plan)

- **TIMESTAMP:** 2026-08-24 17:27:39 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 0cy--plan

**Plan:** /home/bryan/.sase/plans/202608/preserve_legacy_bead_event_prefixes.md


## Prompt

#gh:gh_sase-org__sase Why did the `sase-t2.2` sase agent fail? Is this something we should consider fixing? If so, use your /sase_plan skill to plan the appropriate changes.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/preserve_legacy_bead_event_prefixes.md`

> # Preserve legacy bead event prefixes during mutations
> ## Problem
> The structured-note rollout made legacy note data readable but not mutation-safe.
> `IssueWire` now deserializes an `issue_created` payload's legacy `notes` string into
> `Vec<BeadNoteWire>` and serializes the current structured form. Meanwhile,
> `MutableStore::save` calls `write_event_store_changed`, which serializes every event in
> a changed stream, including the already-published prefix.
> As a result, the first mutation of a legacy stream rewrites historical JSON: an empty
> `payload.issue.notes` field is omitted, and a non-empty string becomes structured note
> records. The Python append-only guard correctly rejects that as an ancestor rewrite.

*See full plan file for details.*

