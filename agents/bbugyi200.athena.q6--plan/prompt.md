#gh:gh_sase-org__sase sase agents keep failing the finalizer check because the
commit_message.md file gets left around (created by agents to use with the
`sase commit` command). See the failed sase agent named `q2` for an example of
this. Can you help me fix this by instructing agents (in the /sase_git_commit
xprompt skill) to write this commit message file (if the agent decides to create
one) to the .sase/commit_message.md file instead (this should fix this issue
since the .sase/ directory is ignored by git)? #plan #m_opus