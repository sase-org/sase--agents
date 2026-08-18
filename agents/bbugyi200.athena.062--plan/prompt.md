#gh:gh_sase-org__sase Can you help me make sure that the VCS xprompt workflow MRU store we use for
the `<ctrl+space>` keymap is working as intended? Whenever a sase agent is launched
using a particular project/patch as an argument to a particular VCS xprompt workflow
(e.g. `#gh`), that xprompt (and that argument) should be considered the most recently
used and should thus be pre-filled in the prompt input widget the next time the user
uses the `<ctrl+space>` keymap.

#if_not_plan