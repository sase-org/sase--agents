# Chat History - ace-run (research.4q.cld)

- **TIMESTAMP:** 2026-10-17 16:20:15 EDT
- **MODEL:** claude/opus
- **AGENT:** research.4q.cld
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261017_154710.md`

## Prompt

%id(cld, clan=research.4q)
%m:claude/opus@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 4-researcher swarm.
The other researchers, `research.4q.cdx`, `research.4q.grk`, `research.4q.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__grk.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you reassess the solution proposed by the
merge_queue_fenced_master_and_exact_sha_releases.md file in the research sidecar repo,
make any changes to its requirements (in the new report your create) that you think are
warranted (but clearly call these out), and then recommend whether or not this work
should be a single epic or multiple epics with justification and indepent epic
verification steps if you think that multiple are warranted? 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Reading the target report now; next I'll check its claims against the sase repo.

Verifying the report's claims against live CI, the release PR, and the current workflows.

Still checking the live CI state; the recent gate failures look like a mix of repeat flakes.

Checking whether the persistent gate failure is a time-dependent test (environment drift) rather than a flake.

Spawning two parallel helpers: one maps the sase landing/finalizer/waiter code paths, the other checks release-please's merge-commit behavior.

Confirming whether `sase==0.17.1`, the only current release, still resolves from PyPI.

Confirmed: `pip install sase` currently resolves to **sase 0.1.0**, because every `sase-core-rs` 0.32.x that sase 0.17.1 needs was deleted from PyPI. Checking the retention epic that did that.

Evidence is in hand. Two quick fact checks before writing: whether `visual-test` now passes in Full CI, and the gate's recent pass rate.

Spot-checking a few of the helper's file:line references before citing them.

Report written. Checking the research repo for formatting conventions, then registering the artifact.

Formatted and registered (`file:explicit:5d741e662ee8faca15140930`). Now submitting the final declaration.

I've written the reassessment and registered it as an artifact. My view: the report's core design is right, but five corrections change what gets built, and the work should be four epics plus two smaller items outside them.

**Report:** `sase/repos/research/202610/merge_queue_reassessment_requirements_and_epic_split__cld.md`
**Artifact:** `file:explicit:5d741e662ee8faca15140930`, label `research:202610/merge_queue_reassessment_requirements_and_epic_split__cld.md`. It will be committed to the research repo when this turn ends.

**What holds up:** a native merge queue that GitHub enforces, with zero approvals; releases that publish exactly the commit that was tested; and making the gate trustworthy before enforcing it. I agree with the report's reasons for rejecting the host-side landing lane, required PRs without a queue, and human approvals.

**What I changed, with evidence the report didn't have:**
1. **`pip install sase` is broken today.** It installs sase 0.1.0. sase 0.17.1 needs `sase-core-rs` 0.32.x, which PyPI retention deleted around Sep 20; I confirmed this with `uv pip compile`. So the first requirement is now "the latest release installs", ahead of "master is green". I also added a daily install check and a rule that retention never deletes core versions a published sase still needs.
2. **I reversed the report's merge-method choice: use rebase with one commit per PR, not merge commits.** I had release-please's source read and a simulation run. With merge commits, each change appears 2–3 times in the changelog, and some changes can be silently missed. The repo's merge-commit message is already set to PR title plus description, so the duplicates are guaranteed. Merge commits would also hide agent attribution from SASE tools that read only first parents, and double commit counts.
3. **A queue stops bad landings, not drift.** Master Gate has failed 20 times in a row since the report was written. That one day showed four kinds of failure:
   - a flaky test;
   - a test that broke because its fixture used real dates;
   - a real regression from a landing;
   - a landing that calls a core function no published `sase-core-rs` has.

   The queue stops only the regression. A red base would fail every queued PR and set off a storm of repair agents. So I added:
   - a check that the base is red before blaming the PR;
   - a breaker that pauses the queue after repeated identical failures;
   - a way for the base fix to jump the queue;
   - a nightly run of the gate with the clock shifted forward.
4. **Releases need a step that cuts a `sase-core` release when needed.** The report says the core version must be published but only checks for it. HEAD currently calls a core function that no published release has.
5. **Queue landing should be a per-project setting, not a feature flag.** A permanent outage fallback has to be config under SASE's flag rules. And rather than moving bead closing to after the merge (agents close beads in three prompt templates), I kept closing as it is and made the waits on a bead require the merge.

Smaller corrections:
- The required check the report designs would fail on every PR, so nothing could ever be queued.
- GitHub rulesets can't require a check only for the release PR.
- Revert, TUI-save and human commit paths also push to master.
- `ci_watch` lives in the external `bugyi-chops` repo.
- "Ship 0.18.0" duplicates the active `sase-1lh` work, so I moved it out of this program.

**Epic recommendation: four epics.**
- **Two items outside the epics:** a few minutes of human GitHub settings today, and restoring installability now under the existing `sase-1lh` work.
- **A, B and C run in parallel:**
  - **A – honest, installable releases:** build and test the exact release commit, the core-release step, the retention rule and the install check.
  - **B – trustworthy gate:** one rerun of failed tests, an expiring quarantine, the shifted-clock canary.
  - **C – queue-aware landing:** a SASE feature, tested end to end on a scratch repo.
- **D – cut master over:** starts only after B's 7-day flake target is met and C passes on the scratch repo.

The report gives each epic verification steps that don't depend on the others: a TestPyPI dry run for A, planted flaky and date-dependent tests for B, scripted scratch-repo scenarios for C, and checks on the real repo for D.

One epic would hold releases hostage to the biggest, riskiest piece. It would also stay open across a week-long soak and two GitHub settings changes that a person has to approve, and keep a temporary flag alive for weeks. Splitting further would leave pieces that can't be verified on their own.

Not done: I changed no rulesets, workflows, memory files or beads, and filed no follow-up beads, since the install outage is already tracked in `sase-10d` and `sase-1m4`. The GitHub merge-queue behaviours I couldn't confirm from docs are listed as checks for the scratch repo.

Sources:
- [GitHub Docs: Managing a merge queue](https://docs.github.com/en/enterprise-server@3.20/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue)
- [GitHub GraphQL reference: pulls (`enqueuePullRequest`)](https://docs.github.com/en/enterprise-server@3.17/graphql/reference/pulls)
- [opendefensecloud/dev-kit#22](https://github.com/opendefensecloud/dev-kit/pull/22) (same release-please duplication under merge commits)
