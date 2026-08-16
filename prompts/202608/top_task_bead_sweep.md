- **PLAN:**
  [202608/top_task_bead_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/top_task_bead_sweep.md)
- **AGENTS:**
  - [bbugyi200.athena.04c--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04c.md)

Can you help me complete some work that was recommended by previous agents by following
the steps listed below?:

1. Review all of my current open (not in-progress) sase task beads for the "sase" sase
   project.
2. Close any task beads that are no longer relevant with a good reason.
3. Select the 5 task beads that would have the most impact if worked to completion.
4. Use your /sase_plan skill to fix the issues / make the improvements that correspond
   with these 5 task beads. Make sure the plan file you propose tells the agent(s) to:
   - If you think any of these 5 beads need approval from the user before working (be
     lenient here and don't ask for approval for objective improvements), do not ask
     directly. Instead, leave a `TASK NEEDS APPROVAL` note on the bead.
   - Mark the bead(s) you intend to work as in-progress by changing their status with
     the `sase bead update` command.
   - Leave a brief note on the task bead(s) explaining the work that was done to fix the
     reported issue / make the requested improvement or, if the agent was unable to
     complete the work, justifying why they were unable to do so.
   - Close each of the 5 task beads that it was able to finish.
   - If there are more task beads associated with the "sase" project, the agent should
     then start a pseudo monitor using the `sleep 1` command with a next action that
     instructs the next agent to follow this exact prompt (with these exact same steps).
   - If there are no more task beads to work, the agent should move on to the next
     numbered step in this prompt.
5. Review all `TASK NEEDS APPROVAL` notes left by prior agent shells and consolidate
   them into a single report for the user with suggested next actions.
6. Terminate.
