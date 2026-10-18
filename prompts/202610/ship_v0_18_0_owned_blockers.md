- **PLAN:**
  [202610/ship_v0_18_0_owned_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)
- **AGENTS:**
  - [bbugyi200.athena.11b--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md)

Can you help me get this project's full check green on master so `ci_watch` merges the
release-please PR and and v0.18.0 of sase is released to PyPI? Confirm the release
before landing. If a phase is dedicated to waiting for the release, make sure the agent
responsible for that phase definitely closes its bead at some point (so the epic lander,
which has a better shot of fixing any unexpected issues that crop up, definitely runs).
Epic landers should continue to create nested epics as necessary until they are able to
fix all release blockers and observe the release of v0.18.0 to PyPI (evidence of this
release should be used to create an artifact by the final epic lander).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
