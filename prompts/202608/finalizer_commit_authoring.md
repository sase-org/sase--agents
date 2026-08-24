- **PLAN:**
  [202608/finalizer_commit_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)
- **AGENTS:**
  - [bbugyi200.athena.0ca--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md)

The `research.10.cdx` sase agent failing because it didn't commit its research file
using the finalizer. Overall we've been having issues with this finalizer since it
rolled out. Can you dig into why this agent failed and review previous failed agents
that failed for similar reasons related to this finalizer? A solution for these
problems? This is a new feature so it's very possible that this is designed wrong. Don't
be afraid to make larger changes. Just call them out explicitly.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
