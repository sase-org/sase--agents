#gh:gh_sase-org__sase %w:1e Can you help me make sure that xprompt swarms have the ability to
determine if a provider is soft disabled vs hard disabled? Also, the `#research_swarm`
xprompt swarm currently seems to not run the researcher for `<provider>` even if `<provider>`
is just soft disabled. This is not correct. This xprompt swarm should only be checking
if providers are hard disabled.

#plan