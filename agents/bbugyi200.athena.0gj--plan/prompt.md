#gh:gh_sase-org__sase Can you help me start explicitly requesting that the two initial researchers
(not the lead researcher) in the `#research_swarm` xprompt swarm use the `__a` / `__b`
filename suffices (e.g. `202609/foo__a.md` instead of `202609/foo.md`)?

- We should try to accomplish this in a generic way by having the `#research` xprompt
  accept an optional input argument that, when provided, specifies the suffix identifier
  (e.g. `a` or `b`).
- The motivation behind this change is to eliminate the case where both of these agents
  choose the same file name, which will result in a merge conflict for the last agent to
  commit.

#plan %m:@xlarge