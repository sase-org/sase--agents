- **PLAN:**
  [202608/commit_completion_excludes_sidecars.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_completion_excludes_sidecars.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-ek.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ek.2/README.md)

[#gh:gh_sase-org__sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(2, clan=sase-ek, bead=sase-ek.2) %model:@small_phase_worker %auto %w:sase-ek.1 %w(bead=sase-ek.1)
[#bd/work_phase_bead:sase-ek.2](https://github.com/sase-org/sase/blob/70410a05b1a6250bbe6adb86c41a65cbef827e9b/src/sase/default_config.yml#L1002)

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 796 B</summary>

```markdown
Can you complete the work for bead sase-ek.2? The bead is already reserved for you and assigned to your agent name: it
was set to status=in_progress before you started reading this, either by the `sase bead work` launch checkpoint or by
the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its description and design file, do
the work, and close the bead with `sase bead close sase-ek.2 --note "<what you verified>"`. Closing an assigned phase
bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself:
record discovered follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ek.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages these into
task beads.
```

</details>

<!-- /sase:section:rendered -->
