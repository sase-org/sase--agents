#gh:gh_sase-org__sase Currently, if you press `<ctrl+k>` in the prompt input widget when a VCS
xprompt workflow exists in the prompt, we prepend the xprompt workflow to the prompt
history query. Can you help me stop this behavior (it is not useful)? Instead, let's
start prepending the `project:<project_name>` filter to the query (you may need to add
support to for the new `project:<project_name>` prompt history query filter). #beau

#plan %m:gpt-6-astra