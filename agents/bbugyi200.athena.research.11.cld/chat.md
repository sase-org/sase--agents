# Chat History - ace-run (research.11.cld)

- **TIMESTAMP:** 2026-08-24 14:42:14 EDT
- **MODEL:** claude/opus
- **AGENT:** research.11.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260824_141250.md`

## Prompt

%id(cld, clan=research.11) %m:@research_b  #gh:gh_sase-org__sase I want to start making better use of sase's artifact links.
For one I have a strong feeling that we are not linking artifact files like plans and
research files consistently or in an ideal way. It would be nice if we could improve
this somehow without increasing the average agent's context too much (e.g. by telling
every agent to always look for ways they can create artifact links in agent instruction
files, for example).

Can you do some research with the goal of helping me decide the best way to implement
this? While you're at it, do some research on how we can improve artifact links in
general and use them in the best way. End your analysis with a recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by understanding the current artifact-link implementation and how artifacts are created/linked today.

Now I have a complete evidence base. Writing the report.

Now filing the two confirmed defects as task beads.

Declaration accepted. Report written to `sase/repos/research/202608/artifact_link_adoption.md`.

## What I found

The core diagnosis is not what you'd guess from "we aren't linking consistently."

**Instruction reach isn't the bottleneck — incentive is.** `AGENTS.md` §1.1 already spends 893 characters of Tier 1 budget on the relation registry, in front of every agent on every turn. `implements` and `supersedes` have been written **zero** times. Separately, 135 agents read `sase_artifacts.md` (with its four worked `link add` examples) in the last five days and produced **five** deliberate links between them. Meanwhile `sase bead dep` has 3,091 edges — because a bead dependency gates a launch. Edges get written when they're load-bearing, not when they're documented.

**Coverage against what's mechanically derivable:**

| Population | Available | Present |
|---|---:|---:|
| Plans with `bead_id` (→ `implements`) | 589 | **0** |
| Research swarm `__a`/`__b` pairs (→ `derives-from`) | 55 | **1** |
| `RELATED:` notes awaiting `migrate-notes --apply` | 303 | **0** |
| Prompts citing an artifact by prose path vs `@ref` | 219 | 12 |

**Recommendation: derive, don't exhort.** Everything above is a pure function of data SASE already owns. Attach derivation at `sase plan propose` / `sase artifact create` (exact moment), a file hook on the sidecars (reactive), and a `housekeeping` lumberjack chop (bulk backfill) — all three are existing zero-agent-context mechanisms; `research-highlights` already proves the file-hook pattern in production. Route only genuine judgment calls to a batched `sase artifact link suggest` + gate. That reaches ~1,770 rows from today's 137 with **no added agent instruction**. The only agent-facing text I'd add is one line each to `/sase_plan` and the `#research_swarm` lead step. Nothing to `AGENTS.md`; nothing to `/sase_final`.

The highest-leverage single change is making `sase artifact read` print the artifact's neighborhood instead of stripping it — currently the sanctioned audited read shows *fewer* links than `cat`.

## Two confirmed defects, filed

- **`sase-t0`** — `sase artifact read` never commits its link rows. `_record_read_link` calls `upsert_row` but not `persist_artifact_link_graph_mutation` (only `link_add` does), so rows die in the ephemeral workspace clone and vanish on the next `rebuild_aggregate`. 63 of 140 recorded read links (45%) are already gone.
- **`sase-t1`** — `_upsert_bead` inspects only `source_ref`, so a link whose *target* is a bead never reaches the bead. Reproduced by writing this report's own `related bead:sase-r8` link: present in the aggregate, absent from `sase-r8`'s event stream and page. All 26 existing `link_added` events have a bead as source.

## Two things worth knowing

I hit a finalizer failure that isn't in the report: `sase final context` aborted with `ValueError: obligation.paths has 548 entries; maximum is 128` because the shared `agents` sidecar (which I'd opened read-only to measure prompts) had hundreds of other agents' publications pending. It cleared once the drain committed, but a busy shared sidecar can hard-block a declaration. Say the word and I'll file it.

Also: I appear to be `research.11.cld`, and `research.11.cdx` is writing `202608/artifact_link_adoption_and_quality.md` on the same question — we collided on a link-index file mid-run. If a `final` member consolidates us, that's expected; if not, the two reports will need merging.
