#gh:gh_sase-org__sase The number of agent panels we show on the agents tab depends on how
many different tribes are in use by the different agents on the Agents tab. All
agents that do not have a tribe get added to a section that is called "untagged"
currently (or we may have renamed it in a recent migration where we replaced all
instances of "tag" with "tribe"). Regardless of what it's called now though, I
want to start instead adding agents to the new `@default` (reserved) tribe by
default if one is not able to be determined any other way. Can you help me make this change? #plan %w:sase-7o.4