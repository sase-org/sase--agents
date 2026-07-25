#gh:gh_sase-org__sase Can you help me split the `@phase_worker` model alias up into a new `phase_worker` model alias bucket?

- Let's continue to define the `@phase_worker` model alias as is, but define it in the new `phase_worker` bucket.
- Let's also start defining the new `@small_phase_worker`, `@medium_phase_worker`, and `@large_phase_worker` model aliases.
- All of these should default to using the `@phase_worker` model alias as their value.
- We should use these new model aliases for the phase agents that we launch (which alias we use should depend on the size of the phase).

#plan