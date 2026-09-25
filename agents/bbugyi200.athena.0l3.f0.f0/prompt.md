#gh:gh_sase-org__sase #fork:0l3.f0 Here is the command output. Was it relevant?
```
❯ sase completion install
Detected shell: zsh (parent process 'zsh')
STEP       STATUS  DETAIL
detect     ok      parent process 'zsh'
target     ok      /home/bryan/.oh-my-zsh/custom/completions (framework completions directory)
ownership  fail    target is managed by chezmoi; pass --force to convert to a local install

# Recommended compsys styles for sase (grouped, described, menu-selected):
zstyle ':completion:*' menu select
zstyle ':completion:*' group-name ''
zstyle ':completion:*:descriptions' format '%F{yellow}-- %d --%f'
zstyle ':completion:*' verbose yes
zstyle ':completion:*' list-grouped true
zstyle ':completion:*' use-cache on
```