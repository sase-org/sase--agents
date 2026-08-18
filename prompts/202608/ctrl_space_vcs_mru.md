- **PLAN:**
  [202608/ctrl_space_vcs_mru.md](https://github.com/sase-org/sase--plans/blob/main/202608/ctrl_space_vcs_mru.md)
- **AGENTS:**
  - [bbugyi200.athena.062--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.md)

Can you help me make sure that the VCS xprompt workflow MRU store we use for the
`<ctrl+space>` keymap is working as intended? Whenever a sase agent is launched using a
particular project/patch as an argument to a particular VCS xprompt workflow (e.g.
`#gh`), that xprompt (and that argument) should be considered the most recently used and
should thus be pre-filled in the prompt input widget the next time the user uses the
`<ctrl+space>` keymap.

If not, use your /sase_plan skill to plan the appropriate changes.
