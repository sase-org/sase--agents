#gh:gh_sase-org__sase Can you help me stop some chop agents from running that I no longer find
useful?

- Each of these chops is defined in my bbugyi200/bugyi-chops GitHub repo and configured
  in my chezmoi repo.
- Completely remove the `code_quality` lumberjack and remove the corresponding `audit_*`
  chops. Remove the `bugyi_chop_recent_*` scripts from the bugyi-chops repo, since they
  are no longer used.
- The `bugyi_chop_ci_watch` chop should be changed so, instead of launching a `ci_fix.*`
  sase agent, it proposes the launch of a new agent using a sase gate instead (so the
  user can approve/reject that agent's launch at their own convenience). Make sure that
  duplicate gates are never sent.

#plan #m_opus