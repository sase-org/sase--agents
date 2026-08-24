# Chat History - ace-run (research.10.cld)

- **TIMESTAMP:** 2026-08-24 08:49:37 EDT
- **MODEL:** claude/opus
- **AGENT:** research.10.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260824_083442.md`

## Prompt

%id(cld, clan=research.10) %m:@research_b  #gh:gh_sase-org__sase Can you do some research to help me decide what architectural decision records would be most useful to add to this project? See the glossary_to_memory_webs.md file in the research sidecar repo for context. End your analysis with a ranked list of recommended decisions I should add to the decision web proposed by the glossary_to_memory_webs.md research file. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by finding and reading the research file for context.

I have the evidence I need. Writing the report.

The report is complete. Now the required SASE finalizer declaration.

Report written to `sase/repos/research/202608/decisions_web_seed_adrs.md` (625 lines).

## What I did

Read the companion research, then measured the decision surface directly rather than working from the report's own framing: 13,217 commits (208 breaking), 829K Python LOC / 930K test LOC, the linked `sase-core` checkout (213,719 Rust LOC, 859 commits since 2026-04-28), the 307-topic research sidecar, and live CLI state for flags, projects, and repos.

## The core finding

The seed set should come from **decisions agents are currently getting wrong**, not decisions that were hardest to make — those are different sets. SASE already has three surfaces that each carry part of a decision and none that carry the whole thing: research reports hold deliberation but are addressed by topic+month and never say whether a recommendation was adopted; memory notes hold the rule but deliberately omit rationale to stay inside a 2,273-word core budget; commit messages are unreachable without knowing the commit. The ADR-shaped gap is *adopted rationale, addressed by name* — a stronger justification for the web than the Zettelkasten framing.

Two things fell out that I didn't expect going in:

- **Three of the ten strongest candidates are decisions the project reversed.** Reversal records are the highest-value ADRs available here, because a reversed decision leaves no artifact in the tree at all. The "no retrieval mechanism before its corpus" record covers dynamic memory (removed after seven weeks), episodes (three weeks, plus a removal commit that deleted a command family, a package, an ACE modal, a doctor check, and a docs page), and `keywords:` metadata — and that lesson is *already* load-bearing, since `glossary_to_memory_webs.md` §3.4 rests on it to justify shipping with no closure engine.
- **The best naming ADR is one where the research lost.** `naming_the_change_unit` recommended `rivet`; the project shipped `Patch`. A record of a recommendation not taken, with the reason, is worth more than five recording agreement.

## Ranked list (§7)

Top ten, cut line after #10 (~3,900 words of strand bodies):

1. Agents are single-turn; continuation is mechanical
2. The Rust core is required and has no Python fallback
3. Verification is two-speed because host capacity is the constraint
4. No retrieval mechanism ships before its corpus
5. SASE invents domain nouns instead of reusing industry terms
6. Bead state is an append-only event log; JSONL is a projection
7. Memory is flat, tiered, and file-backed
8. Completion is a host-owned finalizer declaration
9. Agents work in ephemeral numbered workspace clones
10. Durable non-code state lives in consent-gated sidecar repos

Then 11–16 as a second wave, and §5 lists four I recommend *not* writing yet — including the memory-webs decision itself, which is still a recommendation rather than a decision, and the agent family/clan/tribe taxonomy, which is still moving as of your most recent commit.

§6 proposes the record format against the web's constraints (numbering is compatible with slug-as-identity and gets prefix resolution free; lifecycle fields go in the opaque `metadata:` mapping; 250–450 words per strand, citing rather than restating the research report).

One judgment call worth flagging: #5 and #12 are conventions rather than architecture in the narrow sense. I included them under Nygard's "construction techniques" clause and said so explicitly — if you'd rather keep the web strictly structural, they're the two to drop.
