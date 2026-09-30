- **PLAN:**
  [202609/bead_show_attachment_span_offsets.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_show_attachment_span_offsets.md)
- **AGENTS:**
  - [bbugyi200.athena.0ub--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ub.md)

Did the `sase-1d6.2` sase agent use bead attachments correctly (see the command output
below for context)? Is this something we can/should fix? If so, please do so. First
though, fix these beads so they can be read.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.

```
❯ sase bead show sase-1d5.1
Traceback (most recent call last):
  File "/home/bryan/.local/bin/sase", line 10, in <module>
    sys.exit(main())
             ~~~~^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/main/entry.py", line 187, in main
    handler(args)
    ~~~~~~~^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_query.py", line 276, in handle_bead_show
    _run_bead_view(args, audited_reason=None)
    ~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_query.py", line 334, in _run_bead_view
    _run_bead_view_inner(args, audited_reason=audited_reason)
    ~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_query.py", line 397, in _run_bead_view_inner
    document = build_show_batch_document(
        batch,
    ...<3 lines>...
        images_mode=images_mode,
    )
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_show_batch.py", line 489, in build_show_batch_document
    sections = _show_batch_sections(
        batch,
    ...<3 lines>...
        images_mode=images_mode,
    )
  File "/home/bryan/projects/github/sase-org/sase/src/sase/bead/cli_show_batch.py", line 646, in _show_batch_sections
    PagerSection(
    ~~~~~~~~~~~~^
        identity=subject_ref,
        ^^^^^^^^^^^^^^^^^^^^^
    ...<10 lines>...
        known_kinds=known_kinds_from_artifact_context(reference_context),
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    )
    ^
  File "<string>", line 14, in __init__
  File "/home/bryan/projects/github/sase-org/sase/src/sase/pager/document.py", line 94, in __post_init__
    _validate_attached_targets(
    ~~~~~~~~~~~~~~~~~~~~~~~~~~^
        targets,
        ^^^^^^^^
        body_length=len(body_text.plain),
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
        section_identity=self.identity,
        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    )
    ^
  File "/home/bryan/projects/github/sase-org/sase/src/sase/pager/document.py", line 375, in _validate_attached_targets
    raise ValueError(
    ...<2 lines>...
    )
ValueError: attached target span 5472:5493 exceeds body length 4821 for section bead:sase-1d5.1
```
