#gh:gh_sase-org__sase Can you help me make it so CI failures reported via sase notifications by the
`ci_watch` chop (see #sshot for an example of one of these) result in at most one sase
notification per unique combination of repos with failing GitHub Actions workflows/jobs?

- In other words I only want to be notified when a repo that wasn't failing before,
  according to existing CI failure sase notifications, starts failing.
- The goal of this change is to reduce the number of notifications received by this chop
  since I currently get many in sequence when the projects I am tracking have failing
  GitHub Actions workflows/jobs.
- In order to make sure we are not losing any information here, we should add a new +1
  feature to sase notifications that is inspired by similar +1 functionality that is
  already supported by sase task beads.
- Instead of creating a new sase notification when this chop detects a combination of
  repo failures that already corresponds with an existing sase notification, we should
  +1 that notification with a useful (but concise) note.
- Make sure that +1 notes can be viewed and iterated over in the notification panel.
- #beau

#plan %m:@xlarge