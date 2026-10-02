- **PLAN:**
  [202610/memory_batch_read_pager_files.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_batch_read_pager_files.md)
- **AGENTS:**
  - [bbugyi200.athena.0vh--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vh.md)

I don't think that we currently handle opening memory files in the sase pager properly
when done so via the `v` keymap on the "Agents" tab by selecting a bulk memory read. For
example, when I go to view a bulk memory read of the `sase_sizes.md glossary:Pomodoro`
memories, each of those memory files should be opened separately in the pager (the pager
should already support accepting multiple targets) instead of the output that is shown
to the sase agent when they run the `sase memory read` command (which displays each
memory file's contents inline, with separators). Can you help me fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
