#gh:gh_sase-org__sase #fork:0gj.f0 Can you now help me make it so the research lead is given the file
paths of the research files created by the previous two agents instead of their chat
transcripts?

- I'm not sure if we currently inject a Jinja2 variable that allows us to access
  artifacts created by agents that the current agent waited for or not.
- If not, you should add that functionality. Make sure this does not affect performance
  at all (e.g. inject it lazily if necessary--think hard about whether any optimization
  is necessary here and only optimize if so).
- Regardless, that functionality should be unified with the `wait_chats` functionality
  by using the `wait.*` namespace (`wait.chats` and `wait.artifacts`, for example).

#plan %m:@xlarge