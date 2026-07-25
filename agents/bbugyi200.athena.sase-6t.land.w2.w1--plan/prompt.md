#gh:gh_sase-org__sase
%w:sase-6t.land.w2 We recently added the `<ctrl+d>`, `<ctrl+u>`, `<ctrl+f>`, and `<ctrl+b>` keymaps to allow the user to jump a certain number of entries up and down the left pane entries on sub-tabs of the "Artifacts" tab. `<ctrl+d/u>` jump down/up 10 entries, whereas `<ctrl+f/b>` jump down/up 5 entries. The problem is that the `<ctrl+d/u>` keymaps need to be used to scroll the right pane down/up instead. Can you help me fix this?

- Let's make the `<ctrl+f/b>` keymaps jump down/up 10 entries instead of 5 and remap the `<ctrl+d/u>` keymaps to scroll the right pane down/up.
- Also, let's start adding the contents of the plan file to the bottom of the right pane that is shown on the "Plans" sub-tab.

#plan