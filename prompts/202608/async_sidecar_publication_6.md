- **PLAN:**
  [202608/async_sidecar_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-ej.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.6/README.md)

[#gh:gh_sase-org__sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(6, clan=sase-ej, bead=sase-ej.6) %model:@small_phase_worker %auto %w:sase-ej.1,sase-ej.3,sase-ej.4,sase-ej.5
%w(bead=sase-ej.1) %w(bead=sase-ej.3) %w(bead=sase-ej.4) %w(bead=sase-ej.5)
[#bd/work_phase_bead:sase-ej.6](https://github.com/sase-org/sase/blob/465676c6916d4087d69e77863bd17e38ce557c59/src/sase/default_config.yml#L1022)

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 796 B</summary>

```markdown
Can you complete the work for bead sase-ej.6? The bead is already reserved for you and assigned to your agent name: it
was set to status=in_progress before you started reading this, either by the `sase bead work` launch checkpoint or by
the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its description and design file, do
the work, and close the bead with `sase bead close sase-ej.6 --note "<what you verified>"`. Closing an assigned phase
bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself:
record discovered follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ej.6 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages these into
task beads.
```

</details>

<!-- /sase:section:rendered -->
