- **AGENTS:**
  - [bbugyi200.athena.1dl](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dl.md)
- **ARTIFACTS:**
  - [agents_stranded_count_scope.md](https://github.com/sase-org/sase--plans/blob/add19674ac41f2cdf7b04be0b2d728bc1c92c481/202611/agents_stranded_count_scope.md)

%model:@medium #gh:gh_sase-org__sase [@plan:202611/agents_stranded_count_scope.md][1]

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false Reviewer decisions for this plan (final · reviewer via ACE):

- backlog_hint = toast (planner default: toast). Implement the "backlog_hint = toast"
  branch; ignore "backlog_hint = strip", "backlog_hint = silent". Context: "Should the
  Agents tab still point at stranded beads that have no loaded agent row?".
- beads_filter = yes (planner default: yes). Implement the "beads_filter = yes" branch;
  ignore "beads_filter = no". Context: "Add a `status:stranded` filter to the Beads pane
  so the stranded backlog can be listed?". Implement only the branches selected above.
  %macros_enabled:true

[1]:
  https://github.com/sase-org/sase--plans/blob/add19674ac41f2cdf7b04be0b2d728bc1c92c481/202611/agents_stranded_count_scope.md
