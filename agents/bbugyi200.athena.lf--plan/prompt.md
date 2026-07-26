#gh:gh_sase-org__sase Can you help me start instructing agents via the explanation text that is output by the `sase plan validate` command's `--explain` option to start prepending `<slug_id>: ` to epic plan file phase descriptions instead of referencing the full section title?

- Make sure that other sase agents are aware of this convention by updating the `/sase_beads` xprompt skill accordingly.
- Take ~/tmp/screenshots/20260726_074825.png as an example. After these changes, `'One critical section for bead mutation, commit, and integration' section: `  should be `serialize: ` instead.

#plan #m_opus