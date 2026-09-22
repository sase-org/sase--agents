# Chat History - ace-run (research.24.cld)

- **TIMESTAMP:** 2026-09-21 17:42:37 EDT
- **MODEL:** claude/opus
- **AGENT:** research.24.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260921_162653.md`

## Prompt

%id(cld, clan=research.24)
%m:claude/opus@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher cld in a 3-researcher swarm.
The other researchers, `research.24.mus`, `research.24.gem`, are independently investigating the same request and will write their own self-named reports ending in `__mus.md` and `__gem.md`. Your report will end in `__cld.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to make the sase-core repo
much easier to maintain by sase agents. Can you do some research with the goal of
helping me decide the best way to implement this? End your analysis with a recommended
solution.

- Review the sase_core_maintainability_audit.md file in the research sidecar repo for
  context and inspiration before peforming your own research.
- I want you to perform your own research that builds upon this previous research file
  and takes into account the recent effort to reduce Rust file sizes in sase-core (see
  the sase-14s and sase-15b epic beads for context).
- Think hard about what it means for Rust code to be easy to understand / maintain by
  sase agents. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cld` suffix, i.e. `<stem>__cld.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Reading the prior audit now, then I'll look at the sase-14s/sase-15b epics and measure the current sase-core tree.

Read both epic plans; now measuring the current sase-core tree (file sizes, hubs, docs, lints) post-split.

Mapping the build environment agents actually use (per-run target dirs, sccache, incremental off). Next: timing a sase_core edit cycle and checking how the sase repo drives sase-core work.

Parsing per-crate timings from the `--timings` reports, then rerunning the incremental series cleanly (the first pass was skewed by `-p` feature-unification rebuilds).

Next: measuring function-level complexity with clippy's `too_many_lines`/`cognitive_complexity` (file size was the previous epics' only proxy).

Working out a concrete crate-extraction order: measuring per-module churn over recent history so the split targets where agents actually edit.

Cutting just two "keystone" edges (`agent_launch → editor`, `plan → bead`) would drop mean post-split rebuild scope from 33% to 19% of the crate. Checking what those edges actually carry.

I have enough evidence. Writing the report now.

Report written and key claims spot-verified. Registering it as an artifact.

Artifact registered. Freeing the ~20 GB of build scratch my timing experiments created (disk is at 90%).

I wrote the report and registered it as an artifact (`file:explicit:6c33124109a462c6c94710f0`, label `research:202609/sase_core_agent_maintainability__cld.md`). The host will commit it to the research repo.

**Report:** `sase/repos/research/202609/sase_core_agent_maintainability__cld.md`

**Main finding:** sase-14s and sase-15b solved file size. Code quality is fine too: only 136 functions are over 100 lines and there are no macro DSLs. What now costs agents most is something else:

1. **Slow edit-and-check cycle, mostly caused by the build setup.** I timed builds on athena with the same settings agents get.
   - Editing one `sase_core` file and re-checking takes **57–79 s**. `just check` takes **205–296 s**, which is close enough to the 300 s tool timeout that 6 of the 10 sase-14s phases had to poll or hand off.
   - About 85% of that is the single 296k-line `sase_core` crate being re-checked from scratch.
   - Incremental builds are switched off because sccache refuses them. Bypassing sccache for the workspace's own crates only measured **~23 s**.
   - Narrowing a build with `-p` rebuilds `sase_core` from scratch even with no edits (**+53–95 s**). That scope resolves 10 dependencies with different features, and `check.sh` passes `-p` through thinking it is cheaper.
2. **Shared files and duplicate names, not file size, drive merge conflicts and wasted lookups.**
   - `sase_core/src/lib.rs` re-exports 2,674 names and was touched by **40%** of feature and fix commits in the last two months.
   - The binding split created a new shared file, `prelude.rs`, with 645 aliases.
   - One exposed function can go by five names across the Python, binding and core layers.
3. **The things most likely to break are not checked by the compiler or any test.** These include:
   - the binding registration lists
   - a hand-written binding manifest missing 191 entries
   - schema versions copied by hand across both repos
   - a stated minimum Rust version (1.78) that isn't true, which has broken agents twice
4. **sase-core's instructions never reach agents.** Claude reads `AGENTS.md` only when there is no `CLAUDE.md` in the working directory or above it, and SASE workspaces have one. I didn't check the loading rules for the other providers. There is also no module map and no written recipe for adding a binding.

**Recommendation:** stop running size-only split epics once sase-15b lands, and do four things in order:
- **P0 (hours):**
  - Allow incremental builds for the workspace crates and give every build scope the same dependency features.
  - Add `CLAUDE.md` and `GEMINI.md` files to sase-core that point at `AGENTS.md`, and have `sase repo open` print "read AGENTS.md first".
  - Rewrite `AGENTS.md` as a real guide and correct the stated minimum Rust version.
- **P1 (one epic):** add automatic checks so the gains can't slip back:
  - a file-size limit that can only shrink
  - a test that every binding is registered
  - one schema-version table that Python reads instead of copying
  - required module docs
  - a check that the module dependency graph has no cycles
- **P2:** remove `lib.rs`'s 2,674 re-exports and `prelude.rs`'s 645 aliases, and name binding folders after their core modules. Cut the few "keystone" dependencies: each is one small helper living in the wrong module (`canonical_directive_name`, `validate_model_value`, …). By my model, moving about five of them reduces what an average commit would rebuild after a crate split from **33% to 14%** of today's crate.
- **P3:** only then split `sase_core` into about 6–10 crates. Two rules: the heavy crate must not depend on the extracted crates, and every new crate must be added to `changelog_include` in `release-plz.toml`.

I considered merging sase-core into the sase repo and recommend against it for now: most of the cross-repo friction (pins bumped by hand, the extension not rebuilding) can be automated instead.

**Not verified:**
- **The crate-split savings** come from a static model, not a real split; the first extracted crate should be timed before planning the rest.
- **Build timings** were taken on a busy host (load 17–74), so read them as ranges.
- **One test failure:** bare `cargo test` failed in the `sase_core_py` library tests, while `./scripts/check.sh test --workspace` passed. I think a library path setup in `check.sh` explains it, but I didn't confirm that.

**Open issue:** sase master currently calls a Rust binding that its pinned sase-core revision doesn't contain. The commit (`8e0f38a53`) is labelled "interim; verification pending build" and belongs to the in-flight sase-15p work, so I didn't file a bead.

My timing experiments left ~20 GB of build files, which I deleted because the disk is 90% full. The sase-core checkout is clean.
