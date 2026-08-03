- **PLAN:**
  [202608/revert_bead_reprefix_epic.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_bead_reprefix_epic.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-ez.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ez.1/README.md)

[#gh:gh_sase-org__sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(sase-ez.1, bead=sase-ez.1) %clan(sase-ez, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium_phase_worker %auto
[#bd/work_phase_bead:sase-ez.1](https://github.com/sase-org/sase/blob/850cb910ee9f944e6c5871187581758cdba9c9d3/src/sase/default_config.yml#L1021)

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 796 B</summary>

```markdown
Can you complete the work for bead sase-ez.1? The bead is already reserved for you and assigned to your agent name: it
was set to status=in_progress before you started reading this, either by the `sase bead work` launch checkpoint or by
the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its description and design file, do
the work, and close the bead with `sase bead close sase-ez.1 --note "<what you verified>"`. Closing an assigned phase
bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself:
record discovered follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ez.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages these into
task beads.
```

</details>

<!-- /sase:section:rendered -->
