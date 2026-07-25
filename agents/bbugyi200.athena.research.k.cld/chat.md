# Chat History - ace-run (research.k.cld)

- **TIMESTAMP:** 2026-07-25 09:49:08 EDT
- **MODEL:** claude/opus
- **AGENT:** research.k.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260725_092246.md`

## Prompt

%id(cld, clan=research.@) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I have a feeling that I'm not using sase beads to their full potential. Can you do some research to help me think of new and useful ways that I can use beads? End your analysis with a ranked list of recommended improvements you think I should consider making. There should be an existing sase_beads_full_potential_consolidated.md research file somewhere I think, so review that before finalizing your own research. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by getting oriented — the beads reference, the existing consolidated research file, and how beads are actually being used in this repo today.

Let me check the current state of the store and CLI — the consolidated report is 11 days old, so some of it may already be stale.

The store has changed substantially since that report (0 open → 21 open, 8 in progress). Let me dig into what's actually true today.

Found something significant already. Let me verify the store's integrity numbers and check what's changed in the codebase.

I have enough verified data. Writing the report.

Written to `sase/repos/research/202607/sase_beads_next_moves_20260725.md`.

I reviewed the existing `sase_beads_full_potential_consolidated/` set first — and its central claim has expired. That report opened with "0 open, 0 in progress." Today the store has **21 open, 8 in progress, 539 beads created in the last 11 days**. That flips the ranking: three items it deferred on "there's no standing backlog" grounds are now live, and three new defects appeared that only manifest once a backlog exists.

**The three things I'd act on, and none touch the Rust core:**

1. **Your test suite is writing into the production bead store — today.** `sase-97`, `sase-9a`–`9d` are pytest fixtures from `tests/test_bead/test_cli_golden.py` and `test_cli_changespec.py`, created at 12:19 and 13:05 this afternoon. One PLAN path points into `sase_17`'s pytest cache, so it's not workspace-local. They're **5 of the 11 beads `sase bead ready` returns (45%)** — and the shipped `bd/next` xprompt tells an agent to claim and work whatever `ready` returns. Upstream landed the identical guard one day ago (`50003b803`, "refuse test DBs on production servers").

2. **The `sase_beads` skill teaches 7 verbs; the CLI has 18** — and it teaches none of six capabilities that already ship. The most interesting: `%wait(bead=<id>)` is a real cross-agent barrier usable outside `sase bead work`, and `%id(<name>, bead=<id>)` binds a hand-launched agent to any bead with full claim lifecycle. That pair is what makes your 21 open beads individually workable instead of reachable only through epics. Neither is documented anywhere an agent will see. Also unused: child epics (12 of 320), `--size` xsmall/xlarge (0 uses each), `--changespec`/`--bug-id` (0 of 2,014).

3. **`bd/work_phase_bead` and `bd/next` say "Do NOT create new beads."** The prior report recommended baking a capture habit into those exact prompts — they currently prohibit it. Two sentences fix it (phase agents record `PROPOSED FOLLOW-UP:` in notes; land agent files them), and `bd/land_epic` already reads every child's notes.

Also measured: 273 `wip` plan files with only 30 bead-linked (a 243-item shadow backlog in 12 spellings of "not done"); design-link resolution improved 3.5% → 31% but broken count went *up* (220 → 229); and 60 plan files point at bead IDs that don't exist. Upstream shipped 298 commits in 11 days, almost all Dolt/lease/federation — the prior report's "do not follow" holds, though `--if-status`/`--if-assignee` compare-and-set is worth stealing now that you have a real claim loop.

I made that file this session, so I'll commit it.

Committed and pushed.

- **Commit:** `6302209` `docs(research): add beads next-moves report` on `main` in the research sidecar (`sase/repos/research`).
- **Staged:** only `202607/sase_beads_next_moves_20260725.md` (the one file I created this session).
- **Verified:** working tree clean; local `HEAD` and `origin/main` both at `6302209`, so the push landed.

One thing to flag: after the primary commit succeeded, the post-commit bookkeeping step failed with `project 'sase--research' was not found`. I ran `sase commit --resume` once and it failed identically — the project lookup uses the bare name `sase--research` rather than a registered project key, so retrying won't clear it. The commit and push are unaffected; only the agent-publication queueing was skipped. Worth a look separately if you rely on that publication step for sidecar commits.
