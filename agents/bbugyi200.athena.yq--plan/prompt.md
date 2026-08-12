#gh:gh_sase-org__sase The `sase stitch create` command currently requires sase agents to specify
every file they want included in the commit that gets created using repeated `-f|--file`
options. Can you help me change this so every file (including new, untracked files) is
included by default?

- Sase agents should be the only ones modifying files in any of the repos they work on,
  so this is the more reasonable default I think.
- We should remove the `-f|--file` option in favor of a new `-x|--exclude` option that
  allows a sase agent to specify that one or more files should not be included in the
  commit.
- Make sure to update the instructions in the /sase_git_commit xprompt skill
  accordingly.

#plan #m_opus