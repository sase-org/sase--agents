# Chat History - ace-run (research.1.cld)

- **TIMESTAMP:** 2026-09-02 14:28:21 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260902_141538.md`

## Prompt

%id(cld, clan=research.1) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase Very often when using the new Artifacts Links panel to jump
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
this? End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the Artifacts Links panel, the Patch tab's search-query fallback pattern, and the `^` keymap.

I have the full picture. Writing the report now.

Research written to `sase/repos/research/202609/artifact_links_panel_jump_reliability.md`.

## What I found

Your instinct is right, but the diagnosis has a twist: **query filtering is only half the problem, and probably the smaller half.**

**Cause 1 — identity mismatch (dominant).** The chips the links panel hands to the follow path carry a *synthesized* `ArtifactEntryTarget` built by guessing (`relations/link_index.py:213` → `target_for_ref_kind`, `relations/artifact_links.py:227`). Selection is an exact tuple lookup in a dict. The guesses hard-code `"task"` for beads (real kinds are `task|flag|epic|phase`) and `"archive"` for documents (real kinds are `proposal|active|archive`), assume full 40-char shas for stitches, and assume the aggregate's project *key* equals the row's project spelling. So a link to **any epic bead, phase bead, active plan, or abbreviated stitch fails even when the row is on screen.** Given how much SASE leans on epic/phase beads and auto-projected `implements`/`produced-by` edges, that matches "very often" better than filtering does. The reconciliation code already exists (`_known_target_for_ref`) — the in-pane relations panel uses it; the rail and links panel skip it.

**Cause 2 — genuinely filtered out.** Real and worth your fix: Stitches ships `sidecar:false merges:hide since:24h`, Beads ships `-status:closed`, everything ships a `limit:` head slice.

**Cause 3 — the reveal ladder is a stub.** `reveal_entry_target` is implemented only by the Patches pane; the other five inherit `return False`. And link-follow calls it with `role=FAMILY`, which rewrites the query to the *currently selected* patch's revert family (not the link target), warns, and then returns `True` anyway — so a failed jump clobbers your Patch query and still gets recorded as a link-trail hop.

Also confirmed: `^` already works on every Artifacts sub-tab (`ArtifactsQueryHistoryActionsMixin` shadows the Patches-only version via MRO), and every pane's `apply_host_limit_query` already records history — so a rewrite committed through that seam is `^`-reversible for free. That's the seam to build on.

## Recommendation (detailed in §6)

**R1 first:** add `entry_target_for_ref()` to the pane navigator contract so the destination pane resolves the ref against its *own unfiltered* rows. Canonical rules belong in `sase-core` per the backend-boundary memory. This alone removes most of the toasts and needs no query rewriting.

**R2:** then a generic reveal ladder — drop `limit:` → targeted identity query → *minimal widening* (drop only the terms that exclude the row, possible because R1 hands you the actual row) → neutral `limit:all` as the guaranteed last rung → only then an honest toast that distinguishes "dangling" from "not in inventory". Each rewrite commits through the pane's query seam and is wrapped in a `RelationReveal`-shaped lens, which already self-retires when the query moves.

Plus R3 (Patches-pane fixes, including the `return True`-on-failure bug), R4 (stop giving up while a pane is loading — the pending-target machinery would have landed it), R5 (add a filterable `sha:` to the Stitches dialect; Stitches currently cannot address a commit at all), and R6 (say "press `^` to restore" when a reveal fires).
