# Chat History - ace-run (research.1f.cld)

- **TIMESTAMP:** 2026-09-05 17:55:56 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1f.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260905_173207.md`

## Prompt

%id(cld, clan=research.1f) %m:@research_b  #gh:gh_sase-org__sase sase has a large amount of backward compatibility code,
which should not really be needed anymore. Every machine that uses sase can be accessed
from this machine via SSH. (see the `mac` and `apollo` entries in the ~/.ssh/config
file), so we should be able to migrate any config / data files that are using legacy
features.

Can you do some research to help me understand what work needs to be done to remove all
backward compatibility logic for legacy functionality from sase's codebase? End your
analysis with a recommended solution. Make sure your solution takes all of my machines
into account. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the codebase's backward compatibility surface.

I have enough evidence. Writing the report now.

Only the research sidecar has changes (the new report). Now the final declaration.

Report written to `sase/repos/research/202609/legacy_backcompat_removal.md` (556 lines).

## What I found

**The compatibility window this code exists to protect doesn't exist.** All three machines run byte-identical builds — `sase 0.17.1+98.g302875cbc`, core `0.32.23`, same plugins — from editable checkouts of the same commit, upgraded atomically by `sase update`, with config rendered from one chezmoi source. The only skew in the fleet is `sase-telegram` (0.4.9 wheel on mac/apollo vs +2 commits editable on athena).

**Size:** 693 of 3,995 modules carry a legacy marker, but the concentrated core is small — 60 pure facade modules totalling 1,936 LOC (the `ChangeSpec`→`Patch` shadow package tree), 5 live CLI aliases, 12 `LEGACY_*` format constants, and ~12,500 LOC of tests that exist only to hold them in place. The facades have **one** real internal caller between them.

**The biggest win needs no code change at all.** `sase agent names purge-local-state` — the documented remedy from `decisions:agents-sync-publish-only` — has never been run on the fleet. Dry-run today: mac 9,924 dismissed bundles / 9,894 artifacts / 6,501 chat files; apollo 10,076 / 10,076 / 6,562; athena 809 / 79 / 0. That's ~26,000 dead files per remote machine.

**Fleet state has silently diverged.** mac and apollo still carry retired skill dirs (`sase_artifact`, `sase_beads`, `sase_hg_commit`) across 6+ provider directories each; athena has none. athena alone carries `~/.sase/tasks/`, a 245 KB `agent_tags.json`, a legacy lumberjack lane, and `code-swap.lock`. Every machine is dirty differently — so "the migration already ran everywhere" is currently unverified.

**Root cause is governance, not code quality.** `sase_flags.md` makes a sunset flag mandatory for backward-compatible branches. There are 5 flags, 3 `sunset`, and all three gate *new* rollouts. Zero of the ~685 legacy branches has a flag, a removal bead, or a deadline — none will ever reach `FlagTriage`.

**One genuine blocker:** `sase-telegram` still writes `~/.sase/telegram/pending_actions.json` as its primary store (modified today on athena and apollo). The host merges it read-only. That plugin must be ported before the host-side merge can go.

## Recommendation

One epic, `Backcompat Zero`, six phases — opening with a **fleet state sweep before any code is deleted**, so deletion becomes provably safe rather than optimistically safe, and closing with a lint that fails any new unflagged compatibility branch. Tiers A/B/F delete outright (no window to protect); only Tier E — shared sidecar formats read by all three machines — gets sunset flags and a two-landing rule.

Highest-value first action: `purge-local-state --apply` on mac and apollo, after a backup. It's destructive (~6,500 chat transcripts per machine, no path back) so it wants your explicit go-ahead, not routine hygiene.
