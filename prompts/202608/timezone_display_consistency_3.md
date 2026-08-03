- **PLAN:**
  [202608/timezone_display_consistency.md](https://github.com/sase-org/sase--plans/blob/main/202608/timezone_display_consistency.md)
- **AGENTS:**
  - [bbugyi200.athena.sase-em.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-em.land/README.md)

[#gh:gh_sase-org__sase](https://github.com/sase-org/sase-github/blob/7dd02fcec77649b34cba23ae33f30793311869dd/src/sase_github/xprompts/gh.yml)
%id(land, clan=sase-em, bead=sase-em) %model:@big_epic_lander %auto
%w:sase-em.1,sase-em.2,sase-em.3,sase-em.4,sase-em.5,sase-em.6 %w(bead=sase-em.1) %w(bead=sase-em.2) %w(bead=sase-em.3)
%w(bead=sase-em.4) %w(bead=sase-em.5) %w(bead=sase-em.6)
[#bd/land_epic:sase-em](https://github.com/sase-org/sase/blob/f4acb79189412ea61d2a59cd919aaf5aaca79b1c/src/sase/default_config.yml#L968)

<!-- sase:section:rendered -->

<details>
<summary><b>Agent Prompt</b> — rendered, 2.4 KB</summary>

```markdown
You are the land agent for epic bead sase-em: verify the epic is truly complete, integrate it with changes that landed
since it started, then close it out.

1. Verify. Run `sase bead show sase-em` (children, linked plan file), review the epic bead's own notes, then run
   `sase bead show` on every child and review every child note. Confirm each note was addressed, and read the actual
   source code and the epic's commits (bead IDs appear in commit messages) to confirm the work previous agents reported
   complete really is. While reviewing child beads, collect every `PROPOSED FOLLOW-UP:` note entry.

2. Integrate. Changes committed since this epic started could not integrate with this epic's feature while it was
   incomplete. Find them (e.g. `git log` since the first commit mentioning sase-em, excluding the epic's own commits; in
   a PR workflow also review commits on the base branch) and update anything that should now use what this epic added or
   that duplicates or conflicts with it. This integration is part of the epic's work.

3. Land. Unresolved issues caused by this epic remain epic work: plan and finish them before closing. For each genuinely
   distinct follow-up that is not caused by the epic, use `/sase_new_task` with details identifying the proposing bead;
   it will corroborate a duplicate, attach a causally related active-epic issue, or create a sized task as appropriate.
   Record every outcome, including why any proposal was declined, in your close note. Close the epic with
   `sase bead close sase-em --note "<what you verified in steps 1-2>"`. AFTER closing, run `just symvision` if available
   (epic-symbol whitelist entries for sase-em expire at close) and remove the stale entries and unused code it reports.
   Finally, set `status: done` in the frontmatter of the epic's plan file (the PLAN path shown by `sase bead show`). If
   the close is rejected, the named phases were never completed: finish or reopen them, or record the outcome
   deliberately with `--force --reason ... --resolution canceled|superseded`. Never force merely to make the command
   succeed.

If steps 1-2 uncover remaining work, use your /sase_plan skill to plan it and complete the skill's tier-aware
validate/revalidate/propose loop. Make step 3 the plan's final phase (close, run symvision, mark the plan file done) so
the agent that executes the plan finishes the landing. Otherwise do step 3 now.
```

</details>

<!-- /sase:section:rendered -->
