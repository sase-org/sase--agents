# Chat History - ace-run (0pw--code)

- **TIMESTAMP:** 2026-09-23 10:59:37 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** 0pw--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202609/tribe_panel_prompts.md

The above plan has been reviewed and approved. Implement it now.


## Response

Implemented the approved `202609/tribe_panel_prompts.md` plan: tribe panels now show a fold-aware PROMPTS section after TRIBE MEMBERS.

What was built (all in the main checkout; plans sidecar only read):
- `split_prompt_preamble` in `_agent_completion_prompt.py`, with `prompt_snippet` refactored onto it (behavior unchanged).
- `xprompt_overlay_spans` in `util/xprompt_syntax.py`, with `apply_xprompt_overlays` delegating (verified span-identical).
- New `_agent_tribe_prompts.py`: worker-side prompt digests (headline/body/launch/spans/chips/project), first-appearance grouping with `×N` coalescing, and a 1024-entry content-hash LRU.
- Aggregation wiring: `prompts` is now a required tribe enrichment section alongside replies/slow-tool-calls, reusing cached clan snapshots.
- New `_agent_display_tribe_prompts.py` renderer: 8/24/24/all entry ladder, roster-digit chips (3 cap, `•` fallback), `›`/`×N` attribution, gutter previews, 500-line Forensics cap with launch line, per-entry `za`/`zA` anchors.
- `docs/ace.md` tribe table and enrichment paragraph updated.

Verification observed:
- 67 targeted unit tests pass (20 digest/grouping, 18 renderer incl. the no-tokenize render guard, plus aggregation/section/contract updates); full `tests/ace/tui/widgets/` suite: 4785 passed.
- `just fix`, ruff, mypy clean. `sase tool run check` passes every gate except symvision, which flags only `ExpandedLaunchSegments` in `src/sase/agent/launch_cwd_segments.py` — a file this change never touches (pre-existing finding, left alone per scope rules).
- Visuals: 2 new goldens created and inspected (glance and inspect both read cleanly); the 8 existing tribe goldens are byte-identical.

One test-design note: the new visual test waits on panel-document state before Ctrl+J scrolling, since the narrow prompt panel keeps PROMPTS below the fold until scrolled — an initial SVG-only wait timed out for that reason, not because enrichment was missing.

Final declaration accepted for commit of the main checkout.
