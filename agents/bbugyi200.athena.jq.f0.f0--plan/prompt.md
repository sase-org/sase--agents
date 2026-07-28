#gh:gh_sase-org__sase #fork:jq.f0 Can you now help me actually just make it grey (the same color as `running` or `waiting` on the same line) unless the current number of running agent exceeds a certain threshold (see bullets below)?

- Let's start making the color yellow (the current color) if we reach or exceed 50% of the allowed running agents.
- Let's start making the color orange if we reach or exceed 75% of the allowed running agents.
- Let's start making the color red when we hit the maximum number of allowed running agents.
- Round up to the nearest integer when calculating the percentages above.

#plan