#gh:gh_sase-org__sase We currently allow agent tribe panel configuration to specify the panel's
default expansion state (and use this to make the `@chop` agent tribe collapsed by
default), but we preference the previous expansion state and use that when known. Can
you help me make it so we stop doing this and, for example, always start the `@chop`
agent tribe panel in a collapsed state? Keep in mind that this should only affect agent
tribe panels when they first come into existence so if new agents are added to an
existing tribe, that should never have any impact on the expansion state.

#plan #m_opus