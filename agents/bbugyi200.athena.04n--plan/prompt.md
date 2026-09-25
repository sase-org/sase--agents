#gh:gh_sase-org__sase I did not change the artifact link files that are modified in the
~/projects/github/sase-org/sase/sase/repos/research sase repo (a sidecar repo). I
suspect that these links are being added by a sase process or sase agents maybe. A sase
project's primary workspace directory should never be used for anything except for human
work. In other words, I should never see random modified files in
linked/external/sidecar repos in the primary workspace directory. Instead we should use
some other directory location for this that is specific to the sase agent that made
the links explicitly / that triggered the links. Can you help me confirm/deny my
suspicion, diagnose the true root cause, and fix the issue?

#plan %m:claude-fable-5