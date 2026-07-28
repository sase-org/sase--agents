#gh:gh_sase-org__sase Can you help me improve the agent counts shown at the top of the "Agents" tab of the `sase ace` TUI?

- Let's start showing the `<N>/<M>`, where `<N>` is the number of agents running and `<M>` is the number of configured maxiumum allowed running agents to use the same `<N>` used by the `running` count on that same line.
- Let's start showing the `<Q>` queued, where `<Q>` is the number of agents that are currently queued to run inside the same square brackets, but only when there are a non-zero number of sase agents that are currently queued (which should only happen when `<N>` is equal to `<M>`).
- For example, in #sshot, `[5/10 · 0 queued]  [5 running · 4 waiting · 31 done]` should be replaced with `[5/10 running · 4 waiting · 31 done]`.

#plan