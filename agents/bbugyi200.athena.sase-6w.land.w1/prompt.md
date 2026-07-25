#gh:gh_sase-org__sase %wait:sase-6w.land Can you now take inspiration from the agent family and agent clan summaries on the agent metadata panel to create a similar summary that should be shown in the agent metadata panel when an Agent tribe is selected?

- Make sure that tribe panels support all of the advanced functionality that is supported by family panels and clan panels (e.g. numbered keymaps to jump to members, section folding, etc...).
- Currently it is only possible to select an agent tribe panel when that panel is collapsed.
- I want to make it possible to select these panels when they are expanded as well.
- We can accomplish this by allowing the keymap to select the current tribe panel when there is nothing else to collapse (i.e. when it would normally/currently do nothing).
- Make sure that the j/k/l keymaps behave as you would expect when an expanded Agent Tribe Panel is selected. In other words, we should navigate to the next/previous agent tribe panels and select that panel, for the j/k keymaps, or select the previously selected (or top, if we don't know the previously selected) agent/agent family/agent clan in the currently selected agent tribe panel.
- Make sure that we make a selected agent tribe panel that is expanded visually distinct since otherwise it would be difficult to tell that it is the tribe that is selected and not an agent within that tribe.
- #beau 

#plan #m_fable