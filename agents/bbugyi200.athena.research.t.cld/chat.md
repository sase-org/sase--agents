# Chat History - ace-run (research.t.cld)

- **TIMESTAMP:** 2026-07-30 06:56:02 EDT
- **MODEL:** claude/opus
- **AGENT:** research.t.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260730_064747.md`

## Prompt

%id(cld, clan=research.t) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I'm looking for new ways to improve sase artifacts. Can you do some research to help me decide the best path forward? End your analysis with a ranked list of recommended improvements. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by understanding what "sase artifacts" are in this codebase before researching improvements.

Substantial subsystem. Let me dig into the docs, source, and recent history.

There's prior research on artifact refs. Let me read that plus the core docs and source.

Prior research from yesterday exists. I need to know what it recommended, what's since shipped, and what's genuinely new. Let me check.

Much of that research has since shipped. Let me establish the current state precisely.

Most prior recommendations shipped. Now let me find what genuinely remains and what's new. Checking the current grammar, index schema, and the specific gaps the old research flagged.

Key infrastructure has landed (sha256/size/mime, fragments, full CLI). Let me check which prior gaps remain open and measure the corpus today.

Notable: corpus is 94.5% auto-captured images, growing ~27 MB/day, and the index only spans 24 days. Let me check retention, search, and consumption paths.

Confirmed: no retention/GC, and `-q` searches only labels/paths, not contents. Let me check orphans, lineage, and the non-TUI consumers.

Strong signal: 92% of the corpus is visual-regression test snapshots that already live in git. Let me confirm the capture path and a few remaining questions.

The capture heuristic is regex over prompt text — any media path an agent *mentions* gets permanently copied. Let me quantify how much of that is already in git.

I have enough evidence. Let me verify the final numbers I'll cite.

Decisive finding. Let me confirm the research directory's repo status before writing.

Separate sidecar repo, gitignored from the main tree — no `just check` needed. Writing the research now.

Written to `sase/repos/research/202607/artifact_lifecycle_and_capture_economics.md`.

## What I found

I started by checking prior art and found `artifact_refs_and_inspector.md` from **yesterday** — so my first job was figuring out what had since shipped rather than re-deriving it. **Seven of its nine recommendations landed** in the last ~10 days: the kind-tagged ref grammar with fragment anchors, the read CLI, the three missing record fields (now at 100% coverage), the Files sub-tab, the reader modal, the copy-as palette with OSC 52, and `@`-completion.

So the identity problem that report diagnosed is genuinely solved. The binding constraint has moved, and the measurements say where:

**The store is 662 MB over 25 days, and 73% of it is repeat copies of 403 version-controlled PNG test goldens.**

The root cause is in `artifact_file_defaults.py:48` — default capture is a **regex sweep over agent prompt files** that keeps any media path an agent *mentions*. It cannot tell "I made this" from "someone showed me this," and defaults to keeping. Consequences:

- Agent-declared artifacts: **216 records / 5.6 MB** (0.8% of bytes), 5.6% dead source paths
- Heuristic-captured: **4,071 records / 656.5 MB**, 29.8% dead source paths
- Snapshot captures: 3,950 records across only **403 distinct labels** — one golden was captured 32 times, and **zero** were explicitly declared

And there is **no lifecycle at all** — no prune, no retention config, no delete verb. `doctor` can backfill and verify but cannot reclaim a byte. At 26.5 MB/day that's ~9.7 GB/year.

One thing worth flagging: I checked whether content-addressed storage would fix this, and **it wouldn't** — only 107 redundant copies / ~36 MB. The repeat captures aren't byte-identical because each caught a different revision of the golden. But git already stores that history, which is the actual point.

## Ranked recommendations

1. **Make capture mean authorship, not mention** — one predicate at one call site; cuts ~73% of intake while preserving every declared artifact. Reference git-tracked files as `commit:<repo>@<sha>` instead of copying them.
2. **`sase artifact prune` + retention policy** — staged report → dry-run → opt-in config, with hard protection for explicit/referenced/consumed artifacts.
3. **Serve artifact content through the mobile gateway** — the resolver now exists in core; this consumer is newly unblocked but unwired.
4. **Record consumption at `@`-ref expansion** — turns the store into a graph and makes pruning defensible.
5. **`--grep` content search** — only 213 text records / 0.3 MB, so no index needed.
6. **Persist artifact refs on beads/ChangeSpecs** — reruns the proven `sase-9z` playbook.
7. **Finish the raw-`cat` residue** from the prior tranche.

Items 1 and 2 are complements — one stops the inflow, the other drains the pool — and together they address that 73%.

No `just check` run: the research sidecar is a separate git repo, gitignored from the main tree, and research markdown is a documented exception.

I created that file this session, so I'll commit it.

Committed. Both finalizer entries pointed at the same directory — the research sidecar and the linked `research` repo resolve to the same checkout — so a single commit covered both.

**`fb00d0d docs(research): analyze artifact lifecycle and capture economics`** — 1 file, 316 insertions, in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research`.

Verified after: working tree clean, `main` level with `origin/main` (pushed, not just committed). The main workspace at `sase_19` is clean on `master` — no changes there, consistent with the research file being the only thing I wrote this session.

The commit body records the measured findings rather than the plan: 662 MB / 25 days with 73% of bytes being repeat copies of 403 git-tracked PNG goldens, the mention-not-authorship capture heuristic at `artifact_file_defaults.py:48`, the 216-record / 5.6 MB declared vs. 4,071-record / 656.5 MB heuristic split, the absent lifecycle at ~26.5 MB/day, and the negative result that content-addressed storage would not help. Tagged `docs` since it's a research report only.

No `just check` — research markdown in the sidecar is a documented exception, and the main tree was untouched.
