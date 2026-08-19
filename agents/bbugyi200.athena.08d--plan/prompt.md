#gh:gh_sase-org__sase At some point, we added the requirement that all agent family member nodes have
a name, like xprompt workflow Bash/Python steps do (see the `08b` agent family member
names like `main`, `sase`, and `research-swarm priority check` shown in #sshot). This is
only correct for xprompt workflow Bash/Python steps (which could use the clarity). Sase
shells should NEVER show these names (or have these names at all--check to make sure
there isn't some reason we actually need these, but I don't think we do). Can you help
me start showing these names only for xprompt workflow Bash/Python steps?

#plan %m:grok-4.6