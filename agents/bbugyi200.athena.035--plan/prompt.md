#gh:gh_sase-org__sase Sase has a major conceptual bug concerning its concept of a "primary project
workspace". Can you help me confirm/deny the claims below and then fix these issues /
make these improvements?

- We currently seem to do a lot of work in the primary project workspace that should be
  done in an emphemeral workspace instead. The primary workspace is for the user's use
  ONLY. We should migrate ALL other mutations (read-only access is fine--especially
  because we can expect some sidecar repos to stay up-to-date--see the related bullet
  below) to emphemeral workspaces.
- There are multiple instances in our codebase where a git conflict, which can occur
  during normal operations in some instances, blocks some piece of work (for example,
  bead conflicts seem to be able to block epic launches after epic approvals). If we use
  emphemeral workspaces, it should be safe to just run the
  `git reset --hard origin/main` command and retry whatever operation just caused a
  conflict.
- The primary workspace's sidecar repos should be able to be configured to sync
  periodically somehow (we should be smart about this and try to sync these repos when
  there are known changes to them--or during a scheduled sync just to make sure we don't
  catch anything). I think we are already doing this for some sidecar repos, but not all
  of the ones we should be:
  - plans
  - beads
  - research
  - Any other sidecar repo the user decides to configure to auto-sync in the future...

#plan