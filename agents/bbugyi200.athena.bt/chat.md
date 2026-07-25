# Chat History - ace-run

- **TIMESTAMP:** 2026-07-17 09:05:54 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** bt
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260717_090140.md`

## Prompt

#gh:gh_sase-org__sase Can you provide a constructive critique of the infographic stored in the docs/images/sase_overview.png file with a goal of making it more accurate, useful, and beautiful? %m:claude/claude-fable-5

## Response

I'll take a look at the infographic first.

The crops confirm several suspicions. Two more spot-checks — the fan-out's origin and a possible leftover artifact near Workspace 3's right edge.

I've reviewed the image at full resolution (with close-up crops), the sidecar prompt file, the previous final-review critique, the style brief, and the README context it's embedded in. Here's my critique.

## Overall verdict

The concept is right — the five-beat story (you → one prompt → parallel agents → durable state → outcomes) is the correct hero narrative, the dark terminal palette matches the demo GIFs, and the restraint (no planner sub-diagram, no plugin strip) is a real improvement over the old asset. But the execution has one broken narrative link, one factual arrow, and several label-placement defects that the previous `sase_overview.critique.md` review missed despite claiming "uncropped panels" and "clear fan-out." Details below, ranked by impact.

## Accuracy and story problems

**1. The central fan-out is visually disconnected — the headline beat doesn't work.** The teal arrow from the prompt card feeds *only Workspace 1's left edge*, while the light-blue "PARALLEL AGENTS" bracket that fans into all three workspaces floats in space, unconnected to the prompt — it even has an orphan stub rising from its center toward the subtitle box, as if fed by the title. A reader tracing the flow sees "prompt → Workspace 1, and three arrows from nowhere." Since "one prompt fans out to parallel agents" is the product's core claim, this is the most important fix: route a single edge from the prompt card up into the bracket (and delete the direct prompt→Workspace 1 arrow), so the fan-out has an unambiguous source.

**2. "Scheduled work" is sourced from the wrong place.** All three outcome cards hang off the durable-state rail's spine. "Reviewed PRs" ← ChangeSpecs is right, "Tracked runs" ← durable state is defensible, but "Scheduled work" is *produced by AXE*, not derived from durable state — the coral color already links it to the AXE chip, and the arrow contradicts that link. Either route a coral edge from AXE to that card, or replace the outcome with something durable-state actually yields (e.g. "Resumable runs" or "Auditable history").

**3. ACE TUI and AXE are dead ends, so "supervise" is never drawn.** The two chips hang under "You" with no outgoing edges, while the README's tagline is that one developer *supervises* parallel agents through ACE. A light return edge (outcomes → ACE/You, or ACE ↔ workspaces) would close the loop and turn a one-way pipeline into the supervision story. This is optional for a hero, but right now the two chips read as decorative.

**4. The three workspace icons imply false differentiation.** Terminal, folder, and branch icons suggest the workspaces differ in kind, when the point is they're *identical* isolated clones distinguished only by which agent CLI runs inside. Use one consistent workspace glyph (the branch icon is the best fit for "clone") in all three cards.

## Craft defects (label overlay misregistration)

**5. All three outcome labels miss their label zones.** Close inspection shows "Reviewed PRs," "Tracked runs," and "Scheduled work" each straddle the *top-left corner* of their inner blank chip instead of sitting centered inside it — the text collides with the chip's stroke, "Scheduled work" additionally spills left toward its icon, and every chip sits mostly empty beneath its label. At 830 px README width this reads as a rendering bug. This is a pure SVG-overlay coordinate fix.

**6. "Antigravity CLI" overflows its pill.** The text is set smaller than "Claude Code"/"Codex" yet still breaks through both ends of its capsule border. Widen the pill or shorten the label to "Antigravity" (the README's own table calls it "Antigravity CLI (`agy`)", so plain "Antigravity" stays accurate).

**7. The outcome spine hugs Workspace 3.** The vertical teal spine runs ~40 px off Workspace 3's right border for its full height, which at README scale can read as a direct workspace→outcomes edge — exactly the edge the post-processing pass deliberately removed. Push the spine right or shorten it to rise only from the rail's end.

## Beauty and brand polish

**8. The dashed title boxes read as placeholders.** Dashed rectangles around "SASE" and the subtitle are the visual language of wireframes and crop marks, and they're the only dashed strokes in the piece besides the rail separators. The subtitle also sits cramped against its border. Drop both boxes — the type is strong enough alone — or use solid hairlines. Also note the README displays this image directly beneath an H1 that already says "sase," so the giant in-image title is redundant in that context (it earns its place on the docs homepage, though).

**9. Casing: the brand is lowercase "sase," the image shouts "SASE."** Every surface — README, PyPI, sase.sh — styles it lowercase, and uppercase invites confusion with the networking acronym (Secure Access Service Edge). A lowercase wordmark would be both more on-brand and more distinctive.

**10. The accent-color system is half accidental.** Coral deliberately links AXE ↔ Scheduled work (good), but amber accidentally links "ONE PROMPT" ↔ "Tracked runs," and green appears exactly once. Colored *label text* in the outcomes also reads as status semantics (green = pass, red = error — "Scheduled work" in coral with a stop-square icon actively reads as "stopped/failed"). Recommendation: keep outcome text off-white, carry color only in the icons, and swap the stop-square for the calendar-clock already used on AXE.

**11. Typography.** DejaVu Sans is serviceable but generic, and the repo literally pins Fira Code for its visual identity. Setting labels (or at least the wordmark and section headers) in Fira Code would tie the hero to the demo GIFs right below it. Minor: "ONE PROMPT" as a header over a card listing *three* things (Prompt/XPrompt/Workflow) causes a beat of confusion — separating them with "·" or styling them as alternative chips would clarify "one prompt, of any of these kinds."

**12. Mechanical: the PNG is 1.0 MiB.** For the first asset every README visitor loads, run it through `oxipng`/`pngquant` — this class of flat dark image typically compresses 40–60% with no visible loss.

## What to keep

The five-beat left-to-right composition, the durable-state rail as the single source of the outcome spine, the near-black `#0d1117` GitHub-dark match, workspace numbering that mirrors the "numbered workspace clone" model, and the deterministic-label-overlay pipeline itself — all correct calls worth preserving in a regeneration.

The highest-leverage fixes are #1 (connect the fan-out), #5–6 (label registration), and #2 (Scheduled-work sourcing) — most are overlay-SVG edits that don't require regenerating the base image. Happy to draft the revised label/edge overlay and update the sidecar prompt file if you'd like.
