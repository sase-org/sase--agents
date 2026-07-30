%clan(research.v, tribe=research, summary=[[[bold]RESEARCH PROMPT:[/bold] I want to allow users to customize sase finalizers
#gh:gh_sase-org__sase via a new `%final` directive. Can you do some research to help me decide the
best way to implement this?

- First of all, we should generalize our current finalizer so users can define
  their own.
- Users should be able to disable the default finalier (and any additional
  default finalizers we add later).
- We should support multiple finalizers (we already have one builtin finalizer
  that requires the agent to commit changes).
- We should make each finalizer configurable (a prompt used for the finalizer
  followed by a custom script that is run and some extra configuration, like
  retry attempts, trigger conditions, other finalizers that this one depends on,
  etc...) and provide plugin support (i.e. allow sase plugins to define their
  own finalizers in sase plugin repos).
- We should expect all agents to set sase variables for the finalizer to read
  (see the sase-be epic bead for some related work that sets us up for this).

End your analysis with a recommended solution.]]) %id:research.v.cdx
%wait(priority=20) %model:@research_a I want to allow users to customize sase finalizers
via a new `%final` directive. Can you do some research to help me decide the
best way to implement this?

- First of all, we should generalize our current finalizer so users can define
  their own.
- Users should be able to disable the default finalier (and any additional
  default finalizers we add later).
- We should support multiple finalizers (we already have one builtin finalizer
  that requires the agent to commit changes).
- We should make each finalizer configurable (a prompt used for the finalizer
  followed by a custom script that is run and some extra configuration, like
  retry attempts, trigger conditions, other finalizers that this one depends on,
  etc...) and provide plugin support (i.e. allow sase plugins to define their
  own finalizers in sase plugin repos).
- We should expect all agents to set sase variables for the finalizer to read
  (see the sase-be epic bead for some related work that sets us up for this).

End your analysis with a recommended solution. #research