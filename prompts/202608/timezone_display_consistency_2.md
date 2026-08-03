- **PLAN:**
  [202608/timezone_display_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-em.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-em.6/README.md)

[#gh:gh_sase-org__sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(6, clan=sase-em, bead=sase-em.6) %model:@small_phase_worker %auto
%w:sase-em.1,sase-em.2,sase-em.3,sase-em.4,sase-em.5 %w(bead=sase-em.1) %w(bead=sase-em.2) %w(bead=sase-em.3)
%w(bead=sase-em.4) %w(bead=sase-em.5)
[#bd/work_phase_bead:sase-em.6](https://github.com/sase-org/sase/blob/6424082f968b220212dd3656413d076fd1ce9fb0/src/sase/default_config.yml#L1021)

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 796 B</summary>

```markdown
Can you complete the work for bead sase-em.6? The bead is already reserved for you and assigned to your agent name: it
was set to status=in_progress before you started reading this, either by the `sase bead work` launch checkpoint or by
the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its description and design file, do
the work, and close the bead with `sase bead close sase-em.6 --note "<what you verified>"`. Closing an assigned phase
bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself:
record discovered follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-em.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages these into
task beads.
```

</details>

<!-- /sase:section:rendered -->
