#gh:gh_sase-org__sase No enabled sase project should use the "feature" task type except for the
"sase" sase project (indicated by the fact that only this repo defines this task type in
its project-local sase/sase.yml file), so I don't understand why the bob-cli project
seems to support the "feature" task type anyway (see the command output below and the
task type sections in the bob-cli project repo's agent instruction files for context).
Can you help me diagnose the root cause of this issue and fix it?

#plan