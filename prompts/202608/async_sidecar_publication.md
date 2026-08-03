- **PLAN:**
  [202608/async_sidecar_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)
- **AGENTS:**
  - [bbugyi200.athena.sh--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sh.md#member-plan)

Can you help me start publishing the appropriate data/files to the `agents` and `beads` sidecar repo asyncronously
instead of blocking the `sase commit` command for this (see the sase-cl task bead for an example of the types of isssues
we are trying to prevent with this change)?

- Let's add a new lumberjack with a new chop that has the sole purpose of publishing to the `agents` and `beads` sidecar
  repos, since no sase agents should require that these be published to before they can launch and work on code changes
  (which requires the `just check` command to be in a healthy state in general, so make sure that we remove/fix any
  prompt-to-plan file link validation that the `sase validate` command might perform).
- All other logic that committed to and pushed to the `agents` and/or `beads` sidecar repos (e.g. the `sase commit`
  command) should be altered so it instead just marks which agents/agent families/beads need to be synced. The new chop
  should then take care of syncing these sidecar repos appropriately.
- Make sure this all works reliably.
- Close the sase-cl bead as a part of this change (make sure we have actually resolved the issue the bead reports).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before making
any file changes.
