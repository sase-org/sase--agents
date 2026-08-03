- **PLAN:** [202608/bead_show_speed.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_speed.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-en.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-en.4/README.md)

[#gh:gh_sase-org__sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(4, clan=sase-en, bead=sase-en.4) %model:@small_phase_worker %auto %w:sase-en.1,sase-en.2,sase-en.3
%w(bead=sase-en.1) %w(bead=sase-en.2) %w(bead=sase-en.3)
[#bd/work_phase_bead:sase-en.4](https://github.com/sase-org/sase/blob/18d438bc066a15569c2f2faa393ffa4e1aa94f11/src/sase/default_config.yml#L1021)

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 796 B</summary>

```markdown
Can you complete the work for bead sase-en.4? The bead is already reserved for you and assigned to your agent name: it
was set to status=in_progress before you started reading this, either by the `sase bead work` launch checkpoint or by
the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its description and design file, do
the work, and close the bead with `sase bead close sase-en.4 --note "<what you verified>"`. Closing an assigned phase
bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself:
record discovered follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-en.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages these into
task beads.
```

</details>

<!-- /sase:section:rendered -->
