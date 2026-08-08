#gh:gh_sase-org__sase #fork:vc Can you now help me update the sase.yml file in my chezmoi repo? Let's use the filter fields below in-place of the current `globs:` line in that file. #plan #m_opus
```
path_globs: ["20*/**/*.md", "!20*/*/*__*.md"]
agent_name_globs: ["!research.*.cld", "!research.*.cdx"]
```