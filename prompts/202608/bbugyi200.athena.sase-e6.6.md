- **AGENTS:**
  - [bbugyi200.athena.sase-e6.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.6/README.md)

%id(6, clan=sase-e6, bead=sase-e6.6)
[#gh:gh_sase-org__sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%model:@small_phase_worker %auto %w:sase-e6.4,sase-e6.5 %w(bead=sase-e6.4) %w(bead=sase-e6.5)
[#bd/work_phase_bead:sase-e6.6](https://github.com/sase-org/sase/blob/c8211ae5cf3e08f0c3d4402ee5b6bdfe6617a0e0/src/sase/default_config.yml#L1002)

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 796 B</summary>

```markdown
Can you complete the work for bead sase-e6.6? The bead is already reserved for you and assigned to your agent name: it
was set to status=in_progress before you started reading this, either by the `sase bead work` launch checkpoint or by
the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its description and design file, do
the work, and close the bead with `sase bead close sase-e6.6 --note "<what you verified>"`. Closing an assigned phase
bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself:
record discovered follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-e6.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages these into
task beads.
```

</details>

<!-- /sase:section:rendered -->
