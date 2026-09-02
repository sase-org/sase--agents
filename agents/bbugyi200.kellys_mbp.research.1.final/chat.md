# Chat History - ace-run (research.1.final)

- **TIMESTAMP:** 2026-09-02 14:49:32 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** research.1.final

## Prompt

%id(final, clan=research.1)
%wait(priority=20) %m:@xlarge
%wait:research.1.cdx %wait:research.1.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

Very often when using the new Artifacts Links panel to jump
to a linked artifact, I receive an error toast saying that that artifact is no longer
available on that tab. For the Patch tab what we used to do for situations like this
(for the `<enter>` keymap on the "Agents" tab, for example) is change the current search
query on that tab to an appropriate query that matches the missing PR in the case of
that tab (this way we could then jump to that PR/patch entry). The user would then be
able to switch back to the query that they were using previously by using the `^` keymap
(which should be supported on all sub-tabs of the "Artifacts" tab). I want to make the
links panel significantly more reliable, to the point where these types of errors
virtually never happen, using a similar strategy.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.1.cdx` -> `__a`, `research.1.cld` -> `__b`), then read both reports.
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

I'll start by reading the two researcher transcripts to find which report file each one wrote.

Both reports are already synced into my workspace's month directory. Now I'll read both reports.

Cause 1 (synthesized target guesses) is confirmed in the code. Now I'll verify the follow ladder, the Patch reveal bug, and the direct filter-mutation claim that only report A makes.

All claims verified. Now I'll set up the consolidated report directory. First, let me check the existing consolidated-report convention in the sibling directory.

Now I'll write the consolidated report, merging both reports with my verification results and resolving their disagreements.

The consolidation is complete. Per SASE requirements, I'll submit the final declaration before ending my turn.

The consolidated report is written and the declaration submitted. Final layout in `sase/repos/research/202609/artifact_link_follow_reliability/`:

- `artifact_link_follow_reliability__a.md` — codex researcher (was `artifact_links_navigation_recovery_design.md`)
- `artifact_link_follow_reliability__b.md` — claude researcher (was `artifact_links_panel_jump_reliability.md`)
- `artifact_link_follow_reliability.md` — the consolidated report

**What the research found.** Both researchers independently converged on the same reframing, and I verified every load-bearing claim in the code: query filtering is only half the problem, and probably the smaller half. The "no longer available" toast collapses four distinct failures: (1) **identity mismatch** — link chips carry a *guessed* row target (`target_for_ref_kind` hard-codes bead kind `"task"` and document kind `"archive"`, keeps abbreviated SHAs, and uses project keys that diverge from row spellings), so epic/phase/flag beads, active/proposed plans, and short stitch SHAs fail *even when the row is on screen*; (2) genuinely filtered-out rows (`since:24h`, `-status:closed`, `limit:` caps); (3) loading treated as absence (Boolean APIs, a silent give-up while panes load, premature "missing" toasts); and (4) genuinely dangling refs, which should fail but with an honest message.

**Notable verified findings each researcher contributed alone:** codex caught that four panes' pending-target fallbacks clear filters by direct state mutation, bypassing the history seam — so today's partial recovery already breaks the `^` way-back you want to rely on. Claude caught that the Patches pane doesn't implement the host limit-query protocol (so `Ctrl+O` can't restore a Patch query), that the one existing reveal builds its query from the *currently selected* patch rather than the link target and reports success even on failure, and that the Stitches dialect can't address a commit at all. Good news both confirmed: `^` already works on every Artifacts sub-tab, and every pane's query-commit path already records history — so a rewrite committed through that seam is `^`-reversible for free.

**Where they disagreed, and how I resolved it:** optimistic trail hops while loading vs. finalize-on-select (resolved: finalize-on-select, since the panes' existing pending-clear points make a completion hook cheap); `limit:all` as a guaranteed rung vs. avoiding broad loads (resolved: keep it as a rarely-firing last resort, with targeted hydration later for rows not in inventory at all).

**Recommended solution:** fix addressing before filtering. Phase 1 adds pane-side ref resolution (canonical rules in `sase-core` per the backend-boundary memory) — this alone removes most toasts with no query rewriting. Then a host-owned reveal ladder (folds → narrow identity query → minimal widening → neutral fallback), every rewrite committed exactly once through the existing history seam and wrapped in a self-retiring `LinkReveal` lens, tri-state `SELECTED/PENDING/MISSING/FAILED` completion, small dialect additions (`sha:` on Stitches, filterable `id:` on Beads/Files), and a toast that advertises `^` when a reveal fires.
