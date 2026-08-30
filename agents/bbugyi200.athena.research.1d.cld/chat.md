# Chat History - ace-run (research.1d.cld)

- **TIMESTAMP:** 2026-08-30 07:03:54 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1d.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260830_064821.md`

## Prompt

%id(cld, clan=research.1d) %m:@research_b  #gh:gh_sase-org__sase I've been thinking about renaming the sase project for a
while now. I just realized that one thing that sase does that is unique is attempts to
provide a UI that compacts a lot of information from multiple sources onto one surface
(the 3 tabs in the TUI each do this in one way or another). I am also unlikely to choose
a name that is longer than seven characters (bonus points for shorter names).

Can you do some research with the goal of coming up with some great potential new names
for this project? End your analysis with a ranked list of names that you think I should
consider. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this properly. Let me first understand what SASE actually is and does, then explore the naming space.

Let me dig into the TUI's three tabs (the core of the user's insight) and check the prior naming research for house style.

Good — I have the house style. Now let me gather the hard facts: what the three tabs actually compact, the rename cost surface, and internal vocabulary collisions.

Network is available. Let me bulk-check name availability and refine the rename cost surface.

PyPI is nearly saturated for short English nouns — an important finding. Let me check a second wave of rarer candidates and start collision checks on GitHub.

Key finding: `weft` (2026-08-28) and `quoin` (2026-08-15) are *live agent-tooling* packages — the naming space in this niche is actively closing. Let me check a third wave plus GitHub org availability.

Let me check GitHub org availability and test one idea that falls directly out of your insight.

Let me validate the domain signal differently and pin down the exact rename cost and per-tab evidence.

I have what I need. Writing the report.

Report written to `sase/repos/research/202608/renaming_the_project.md`.

**Top of the ranked list: `andon`, then `mosaic`, then `docket`.**

Three findings did most of the work:

**Your thesis checks out, and it's sharper than "SASE has a nice TUI."** The Artifacts tab's unification is *architecturally enforced* — `docs/artifacts_pane_visual_grammar.md:3` says every pane, including a provider that failed to load, renders through one contract-driven shell. That gave me a real naming constraint: the metaphor must preserve *individual legibility* of the sources. A mosaic keeps its tesserae distinguishable; a blend doesn't. So `fuse`, `merge`, `blend` are wrong on the merits, not just uninspiring.

**This naming space is closing in real time.** I checked ~120 candidates on PyPI. Four of my strongest independently-derived names were taken by directly competing projects *within the last three weeks*: `weft` ("The durable task substrate for agent systems", released 2026-08-28 — two days ago), `quoin` ("Workflow state for stateless coding agents", 08-15), `abax` (08-11), `tessella` (08-09). `weft` was my best metaphor before verification. That's why I weighted availability at 25/100 and why the report says its clearances have a shelf life of about four weeks.

**The rename cost is ~10× the ChangeSpec rename, and unlike that one it's a data migration.** 99,459 occurrences across 83% of tracked files — but the number that matters is **319 distinct `SASE_*` environment variables**, plus `~/.sase` as every install's state directory and `.sase` as the ProjectSpec extension. That's a compatibility problem needing a deprecation window, not a `sed`. It doesn't argue against renaming; it argues for doing it once, which is itself a reason to weight durable availability heavily.

Two things worth flagging directly:

- **`ace` (3 chars) is in the list at #6 and I'd rather you rejected it deliberately than by omission.** Your insight is that the compaction surface is the differentiator — and that surface already has a name, a flagship command, and a docs section. Its acronym is *already* stale ("Agentic Change Explorer" still encodes ChangeSpec, in five doc locations). It scores lower linguistically, but §8 argues the brand question is *prior* to the name question: decide whether ACE stays the TUI's name first, because that reframes everything else.
- **I could not verify domain registration.** RDAP isn't exposed for `.sh` — `rdap.org` returned 404 for `sase.sh`, which you demonstrably own. I fell back to DNS resolution, which is a sound one-way signal only: `andon.sh` and `docket.sh` don't resolve; `mosaic.sh`, `radar.sh`, `plat.sh`, `comb.sh` do. Confirm at a registrar. If `andon.sh` turns out to be parked at a high price, `docket` moves to first.

I also skipped trademark searches entirely — worth an hour on `mosaic` and `radar` specifically before you commit.
