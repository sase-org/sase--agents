#gh:gh_sase-org__sase #fork:vq Can you now help me update the sase config schema so we nest all file
hook filter fields under a new `filters` property? For example, you should convert the
file hook configuration in the sase.yml file (defined in my chezmoi repo) from this old
version (shown below) to this new version (also shown below). #plan

### OLD Version

```
file_hooks:
  - name: research-highlights
    description: Render new research reports into Highlights PDFs for the Obsidian reading queue.
    command: bob highlights create
    sidecars: [research]
    path_globs: ["20*/**/*.md", "!20*/*/*__*.md"]
    agent_name_globs: ["!research.*.cld", "!research.*.cdx"]
    ops: [ADD]
    timeout: 120s
```

### NEW Version

```
file_hooks:
  - name: research-highlights
    description: Render new research reports into Highlights PDFs for the Obsidian reading queue.
    command: bob highlights create
    filters:
      sidecars: [research]
      path_globs: ["20*/**/*.md", "!20*/*/*__*.md"]
      agent_name_globs: ["!research.*.cld", "!research.*.cdx"]
      ops: [ADD]
    timeout: 120s
```