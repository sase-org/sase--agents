#gh:gh_sase-org__sase When an xprompt workflow has hidden steps, we can view them by selecting their
agent shell / agent family and using the `l` keymap twice (once to expand the agent
shell / agent family and once to show hidden steps). The user is supposed to then be
able to use the `H` keymap to reverse these operations (the first use should hide hidden
steps and the 2nd use should collapse the agent shell / agent family). In #sshot, for
example, if the user were to press `H`, I would expect the `02i` agent family to remain
open but for its hidden steps to disappear. But this doesn't work. The entire `02i`
agent family is just immediately collapsed. Can you help me fix this?

#plan