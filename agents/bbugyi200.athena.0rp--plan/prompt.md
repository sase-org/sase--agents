#gh:gh_sase-org__sase Can you help me stop running `just toobig` as a part of the `just check` command
(we should still run this command in CI and fail if it fails)? The rationale: agents can
rarely act on this command's failures directly (the `toobig_split` job handles this).

#plan %q(10)