#gh:gh_sase-org__sase We currently support the `glob` file path filter for the `file_hooks` sase
config field and we set `globs: ["20*/*/*.md", "!20*/*/*__*.md"]` in the sase.yml file
in my chezmoi repo. Can you help me improve this particular file hook configuration (the
one in my chezmoi repo) by adding support for a new `agent_name_globs` filter field?

- We should rename the `globs` filter field to `path_globs` to be clear/unambiguous.
- This new filter field will be used to only run the file hook command on files that
  were modified by / were NOT modified by (i.e. we need to support negative matches with
  a `!` prefix) by a sase agent with an agent name matching the particular set of globs
  (see how we do this for file paths with the current `globs` filter field for
  inspiration.)
- My goal with the change we will make to the current research file hook that I have
  configured is to start matching more research/ markdown files, but ignore any files
  created by the first two agents run in the `#research_swarm` xprompt swarm (since
  those research files are consolidated by the 3rd agent in that swarm).
- The `globs` filter field line defined in the sase.yml file in my chezmoi repo should
  thus be replaced with the following:
  ```
  path_globs: ["20*/**/*.md", "!20*/*/*__*.md"]
  agent_name_globs: ["!research.*.cld", "!research.*.cdx"]
  ```

#plan #m_opus