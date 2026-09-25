# Chat History - ace-run (sase-zt.6.5.2--mon-0)

- **TIMESTAMP:** 2026-09-13 15:53:17 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-zt.6.5.2--mon-0

## Prompt

sase monitor start --command 'sh -c set -eu\njust validate\n.venv/bin/python tools/probe_core_floor --advisory --sase-core-dir sase/repos/linked/sase-core\njust validate-committed-plans\njust test-scoped\n.venv/bin/python tools/print_scoped_summary\necho "MAIN_HEAD=$(git rev-parse HEAD)"\necho "CORE_PIN=$(tr -d "[:space:]" < sase-core-revision.txt)"' --reason 'Finish remaining just check after unrelated sase-zx flag lint'

## Response

ANSIBLE_NOCOWS='1'
ATHENAS_DDNS_HOSTNAME='bbugyi.ddns.net'
ATHENAS_SSH_PORT='34857'
ATUIN_HISTORY_ID='01a09bfaabc973df8b8d3aeca918e664'
ATUIN_SESSION='01a096b90d017082b6ab8c199e7ca003'
ATUIN_SHLVL='2'
ATUIN_TMUX_POPUP='false'
AWS_PAGER=''
BB='bbugyi.ddns.net'
BETTER_EXCEPTIONS='1'
CARGO_BUILD_BUILD_DIR='/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws11-260913_152452/build'
CARGO_INCREMENTAL='0'
CARGO_PROFILE_DEV_DEBUG='line-tables-only'
CARGO_PROFILE_TEST_DEBUG='line-tables-only'
CARGO_TARGET_DIR='/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws11-260913_152452'
CARGO_TERM_PROGRESS_WHEN='always'
CARGO_TERM_PROGRESS_WIDTH='80'
CI='true'
CLICOLOR='1'
CLICOLOR_FORCE='1'
COLORTERM='truecolor'
DATE='date'
DB='/home/bryan/Sync'
DBB='/home/bryan/Sync/bin'
DBH='/home/bryan/Sync/home'
DBUS_SESSION_BUS_ADDRESS='unix:path=/run/user/1000/bus'
DISABLE_INSTALLATION_CHECKS='1'
DISPLAY='localhost:10.0'
EDITOR='nvim'
FAV_CLIP_FILE='/home/bryan/Sync/var/notes/Journal/favs.txt'
FORCE_COLOR='1'
FPP_DISABLE_SPLIT='1'
FZF_DEFAULT_COMMAND='rg --files --hidden --smart-case'
FZF_DEFAULT_OPTS='--reverse --height 40% --border'
GEMINI_API_KEY='AIzaSyDY9OUOTFXvy6MD_Hx4_CeI7Qg7rSEPRWQ'
GEM_HOME='/home/bryan/.gems'
GH_PAGER='cat'
GIT_EDITOR='true'
GIT_PAGER='cat'
GIT_SEQUENCE_EDITOR='true'
GIT_TERMINAL_PROMPT='0'
GO111MODULE='on'
GPG_TTY=''
GRADLE_OPTS='-Dorg.gradle.console=rich'
GREP='grep'
GROK_AGENT='1'
GROK_SESSION_ID='a3441f15-f3cd-4d2c-9038-6991f15101e5'
HISTSIZE='100000'
HOME='/home/bryan'
IFS=' 	
'
JJ_CONFIG='/home/bryan/.config/jj/config.toml'
LANG='en_US.UTF-8'
LC_ALL='en_US.UTF-8'
LC_CTYPE='en_US.UTF-8'
LESS='RQ'
LIBRARY_PATH=''
LOGNAME='bryan'
LS='ls'
LSCOLORS='Gxfxcxdxbxegedabagacad'
LS_COLORS='rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.jxl=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:'
LUA_CPATH='./?.so;/usr/local/lib/lua/5.1/?.so;/usr/lib/x86_64-linux-gnu/lua/5.1/?.so;/usr/lib/lua/5.1/?.so;/usr/local/lib/lua/5.1/loadall.so;/home/bryan/.luarocks/lib/lua/5.1/?.so'
LUA_PATH='/usr/local/share/lua/5.1/?.lua;./?.lua;/usr/local/share/lua/5.1/?/init.lua;/usr/local/lib/lua/5.1/?.lua;/usr/local/lib/lua/5.1/?/init.lua;/usr/share/lua/5.1/?.lua;/usr/share/lua/5.1/?/init.lua;/home/bryan/.luarocks/share/lua/5.1/?.lua;/home/bryan/.luarocks/share/lua/5.1/?/init.lua'
MAILPATH='/var/mail/bryan? ✉ ✉ ✉ NEW MAIL IN /var/mail/bryan!!! ✉ ✉ ✉'
MANPAGER='cat'
MASTER_BRANCH='master'
MATLABPATH='/home/bryan/.matlab'
MAVEN_OPTS='-Dstyle.color=always'
MCFLY_KEY_SCHEME='vim'
MCFLY_LIGHT='FALSE'
MOTD_SHOWN='pam'
MOV='/mnt/hercules/plex/Movies'
MY_UUID='30634818'
NIX_PROFILES='/nix/var/nix/profiles/default /home/bryan/.nix-profile'
NIX_SSL_CERT_FILE='/etc/ssl/certs/ca-certificates.crt'
NO_COLOR='1'
NPM_CONFIG_PROGRESS='true'
NVM_BIN='/home/bryan/.config/nvm/versions/node/v22.14.0/bin'
NVM_CD_FLAGS='-q'
NVM_DIR='/home/bryan/.config/nvm'
NVM_INC='/home/bryan/.config/nvm/versions/node/v22.14.0/include/node'
OLDPWD='/home/bryan/projects/github/sase-org/sase/sase/repos/research'
OPTIND='1'
PAGER='cat'
PATH='/home/bryan/.config/nvm/versions/node/v22.14.0/bin:/home/bryan/.pyenv/plugins/pyenv-virtualenv/shims:/home/bryan/.pyenv/shims:/home/bryan/.pyenv/bin:/home/bryan/.cargo/bin:/home/bryan/.luarocks/bin:/home/bryan/projects/github/LuaLS/lua-language-server/bin:/home/bryan/.nix-profile/bin:/home/bryan/go/bin:/usr/local/go/bin:/home/bryan/.gems/bin:/home/bryan/.tmp/bin:/home/bryan/.flamegraph:/home/bryan/.dynamic-colors/bin:/home/bryan/bin:/home/bryan/.local/bin:/opt/rust-bin-1.98.1/bin:/home/bryan/.poetry/bin:/usr/local/bin:/sbin:/usr/sbin:/usr/share/safe-rm/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/snap/bin:/home/bryan/.fzf/bin'
PIP_PROGRESS_BAR='on'
PPID='2430887'
PS1='$ '
PS2='> '
PS4='+ '
PWD='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'
PYENV_SHELL='zsh'
PYENV_VIRTUALENV_DISABLE_PROMPT='1'
PYENV_VIRTUALENV_INIT='1'
PYENV_VIRTUALENV_VERBOSE_ACTIVATE='1'
PYTHONBREAKPOINT='pudb.set_trace'
PYTHONPATH='/home/bryan/.local/bin:/usr/local/lib/python:/usr/local/bin'
QT_QPA_PLATFORMTHEME='qt5ct'
RECENTLY_EDITED_FILES_LOG='/home/bryan/Sync/var/recently_edited_files.log'
RFSERVER_HOSTNAME='bbugyi.ddns.net'
RFSERVER_PORT='23401'
RFSERVER_TOKEN='P+UDE9+ZCD]vrK8}pdP='
RIPGREP_CONFIG_PATH='/home/bryan/.config/rgrc'
RUST_SRC_PATH='/home/bryan/Sync/var/projects/rust/src'
SASE_ACTIVE_PROJECT_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11'
SASE_BEAD_ID='sase-zt.6.5.2'
SASE_CORE_BACKEND='rust'
SASE_FEATURE_FLAGS='{"ace_refresh_tokens":true,"admin_center_flags":true,"agents_unified_query":true,"monitor_continuation_records":true,"provider_drain":true,"queue_capacity_budget":true,"ref_sync_gesture":true,"refresh_panel":true,"typed_launch_units":true}'
SASE_FINALIZER_PLAN_DIGEST='c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145'
SASE_FINAL_TURN_NONCE='reW-AmJJN_dPp7LvtFRdpaJ8c_mwZjh4df5RIOJaFyU'
SASE_INTERNAL_AGENT_NAME_BYPASS='1'
SASE_LINKED_REPOS_JSON='[{"auto_clone": false, "env_name": "CHEZMOI", "kind": "linked", "name": "chezmoi", "primary_dir": "/home/bryan/.local/share/chezmoi", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/chezmoi", "workspace_num": 11}, {"auto_clone": true, "env_name": "SASE_CORE", "kind": "linked", "name": "sase-core", "primary_dir": "/home/bryan/projects/github/sase-org/sase-core", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_GITHUB", "kind": "linked", "name": "sase-github", "primary_dir": "/home/bryan/projects/github/sase-org/sase-github", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-github", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_TELEGRAM", "kind": "linked", "name": "sase-telegram", "primary_dir": "/home/bryan/projects/github/sase-org/sase-telegram", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-telegram", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_NVIM", "kind": "linked", "name": "sase-nvim", "primary_dir": "/home/bryan/projects/github/sase-org/sase-nvim", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-nvim", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_RESEARCH_ARTIFACTS", "kind": "linked", "name": "sase-research-artifacts", "primary_dir": "/home/bryan/projects/github/sase-org/sase-research-artifacts", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-research-artifacts", "workspace_num": 11}, {"auto_clone": true, "env_name": "PLANS", "kind": "sidecar", "name": "plans", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/plans", "remote_url": "git@github.com:sase-org/sase--plans.git", "slug": "sase--plans", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/plans", "workspace_num": 11}, {"auto_clone": false, "env_name": "BEADS", "kind": "sidecar", "name": "beads", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/beads", "remote_url": "git@github.com:sase-org/sase--beads.git", "slug": "sase--beads", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/beads", "workspace_num": 11}, {"auto_clone": false, "env_name": "RESEARCH", "kind": "sidecar", "name": "research", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/research", "remote_url": "git@github.com:sase-org/sase--research.git", "slug": "sase--research", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research", "workspace_num": 11}]'
SASE_LINKED_REPO_BEADS_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/beads'
SASE_LINKED_REPO_BEADS_PRIMARY_DIR='/home/bryan/projects/github/sase-org/sase/sase/repos/beads'
SASE_LINKED_REPO_PLANS_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/plans'
SASE_LINKED_REPO_PLANS_PRIMARY_DIR='/home/bryan/projects/github/sase-org/sase/sase/repos/plans'
SASE_LINKED_REPO_SASE_CORE_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core'
SASE_LINKED_REPO_SASE_CORE_PRIMARY_DIR='/home/bryan/projects/github/sase-org/sase-core'
SASE_MONITOR_CONTINUATION='1'
SASE_MONITOR_DELIVERY_ARTIFACTS_DIR='/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/13/20260913151109'
SASE_MONITOR_DELIVERY_IDENTITY='sase-zt.6.5.2--1'
SASE_MONITOR_DELIVERY_KEY='{"branch": "failed", "monitor_id": "ejmqnypn6p19", "result_id": "result:ejmqnypn6p19:390858a3edea0d78"}'
SASE_MONITOR_DIAGNOSTICS_DIR='/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/13/20260913153629/diagnostics'
SASE_MONITOR_ID='0hetrdtc92b7'
SASE_PROC_ID='0hetrdtc92b7'
SASE_PROC_LOG_PATH='/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/13/20260913153629/live_reply.md'
SASE_PROC_SESSION_ID=''
SASE_SDD_BEADS_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/beads'
SASE_SDD_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/plans'
SASE_SDD_PLANS_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/plans'
SASE_SDD_RESEARCH_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research'
SASE_SIBLING_REPOS_JSON='[{"auto_clone": false, "env_name": "CHEZMOI", "kind": "linked", "name": "chezmoi", "primary_dir": "/home/bryan/.local/share/chezmoi", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/chezmoi", "workspace_num": 11}, {"auto_clone": true, "env_name": "SASE_CORE", "kind": "linked", "name": "sase-core", "primary_dir": "/home/bryan/projects/github/sase-org/sase-core", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_GITHUB", "kind": "linked", "name": "sase-github", "primary_dir": "/home/bryan/projects/github/sase-org/sase-github", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-github", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_TELEGRAM", "kind": "linked", "name": "sase-telegram", "primary_dir": "/home/bryan/projects/github/sase-org/sase-telegram", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-telegram", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_NVIM", "kind": "linked", "name": "sase-nvim", "primary_dir": "/home/bryan/projects/github/sase-org/sase-nvim", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-nvim", "workspace_num": 11}, {"auto_clone": false, "env_name": "SASE_RESEARCH_ARTIFACTS", "kind": "linked", "name": "sase-research-artifacts", "primary_dir": "/home/bryan/projects/github/sase-org/sase-research-artifacts", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-research-artifacts", "workspace_num": 11}, {"auto_clone": true, "env_name": "PLANS", "kind": "sidecar", "name": "plans", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/plans", "remote_url": "git@github.com:sase-org/sase--plans.git", "slug": "sase--plans", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/plans", "workspace_num": 11}, {"auto_clone": false, "env_name": "BEADS", "kind": "sidecar", "name": "beads", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/beads", "remote_url": "git@github.com:sase-org/sase--beads.git", "slug": "sase--beads", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/beads", "workspace_num": 11}, {"auto_clone": false, "env_name": "RESEARCH", "kind": "sidecar", "name": "research", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/research", "remote_url": "git@github.com:sase-org/sase--research.git", "slug": "sase--research", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/research", "workspace_num": 11}]'
SASE_SIBLING_REPO_BEADS_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/beads'
SASE_SIBLING_REPO_BEADS_PRIMARY_DIR='/home/bryan/projects/github/sase-org/sase/sase/repos/beads'
SASE_SIBLING_REPO_PLANS_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/plans'
SASE_SIBLING_REPO_PLANS_PRIMARY_DIR='/home/bryan/projects/github/sase-org/sase/sase/repos/plans'
SASE_SIBLING_REPO_SASE_CORE_DIR='/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/sase/repos/linked/sase-core'
SASE_SIBLING_REPO_SASE_CORE_PRIMARY_DIR='/home/bryan/projects/github/sase-org/sase-core'
SASE_TMPDIR='/home/bryan/.cache/sase/tmp'
SAVEHIST='100000'
SED='sed'
SHELL='/bin/zsh'
SHELLCHECK_OPTS='-e SC1090 -e SC1091 -e SC1117 -e SC2001 -e SC2016 -e SC2046 -e SC2059 -e SC2129 -e SC2155 -e SC2162'
SHLVL='4'
SHV_SHELL_HISTORY_ROOT='/home/bryan/Sync/var/logs/shell-history'
SSH_AGENT_PID='13573'
SSH_AUTH_SOCK='/tmp/ssh-bd1YBG80VDga/agent.13572'
SSH_CLIENT='100.108.201.99 58349 34857'
SSH_CONNECTION='100.108.201.99 50340 100.87.31.114 34857'
SSH_TTY='/dev/pts/0'
STARSHIP_SESSION_KEY='5794606811348305'
STARSHIP_SHELL='zsh'
SYSTEMD_PAGER='cat'
TEMP='/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws11-260913_152452'
TERM='xterm-256color'
TERM_PROGRAM='tmux'
TERM_PROGRAM_VERSION='3.5a'
TMP='/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws11-260913_152452'
TMPDIR='/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws11-260913_152452'
TMUX='/home/bryan/Sync/home/tmp/tmux/tmux-1000/default,14716,0'
TMUX_PANE='%15'
TMUX_PLUGIN_MANAGER_PATH='/home/bryan/.config/tmux/plugins/'
TMUX_TMPDIR='/home/bryan/tmp/tmux'
TV='/mnt/hercules/plex/TV'
USER='bryan'
VISUAL='nvim'
WORKON_HOME='/home/bryan/.virtualenvs'
XDG_CONFIG_HOME='/home/bryan/.config'
XDG_DATA_DIRS='/usr/local/share:/usr/share:/var/lib/snapd/desktop'
XDG_RUNTIME_DIR='/run/user/1000'
XDG_SESSION_CLASS='user'
XDG_SESSION_ID='23'
XDG_SESSION_TYPE='tty'
ZIM_CONFIG_DIR='/home/bryan/.local/share/chezmoi/dot_config'
ZIM_ZSHRC_DIR='/home/bryan/.local/share/chezmoi'
_='/home/bryan/.local/bin/sase'
export=''
o='/home/bryan/org'
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
.venv/bin/python tools/validate_sase_core_rs_version --pyproject pyproject.toml --published-minimum
.venv/bin/python tools/check_feature_flags --static
.venv/bin/sase validate
SASE validation
  ok     doctor plugins.required
  ok     init memory --check
  ok     init repo --check
  ok     init skills --check
  ok     doctor config.file_hooks
  ok     plan links validate
  ok     agent prompts validate

Warnings:
  init skills: 35 provider skill files out of sync with rendered sources; redeploy is deferred until land. Rerun `sase init skills` after landing.
[core-floor-probe] blocked_unpublished: sase-core-rs==0.34.23 is missing 4 capability(s), and at least one has no containing sase-core release tag yet.
[core-floor-probe] artifact_ref_link_location_wire_schema_version: first appears in sase-core 17947a0 (feat(artifact-ref): add the one link-location grammar); no release tag contains it yet.
[core-floor-probe] artifact_ref_split_link_location: first appears in sase-core 17947a0 (feat(artifact-ref): add the one link-location grammar); no release tag contains it yet.
[core-floor-probe] continuation_decide_resume_adoption: first appears in sase-core 23f19f0 (feat(continuation): plan ancestry retention and resume-adoption decisions); no release tag contains it yet.
[core-floor-probe] continuation_plan_retention: first appears in sase-core 23f19f0 (feat(continuation): plan ancestry retention and resume-adoption decisions); no release tag contains it yet.
{"cache_hit": false, "capabilities": [{"commit": "17947a0", "name": "artifact_ref_link_location_wire_schema_version", "release": null, "subject": "feat(artifact-ref): add the one link-location grammar"}, {"commit": "17947a0", "name": "artifact_ref_split_link_location", "release": null, "subject": "feat(artifact-ref): add the one link-location grammar"}, {"commit": "23f19f0", "name": "continuation_decide_resume_adoption", "release": null, "subject": "feat(continuation): plan ancestry retention and resume-adoption decisions"}, {"commit": "23f19f0", "name": "continuation_plan_retention", "release": null, "subject": "feat(continuation): plan ancestry retention and resume-adoption decisions"}], "declared_floor": "0.34.23", "exit_code": 4, "message": "sase-core-rs==0.34.23 is missing 4 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
.venv/bin/python -m sase.scripts.validate_committed_plans
Committed plan validation passed: 4638 files (1193 strict, 3445 legacy), 0 errors, 0 warnings.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 3818 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.1.0, hypothesis-6.167.1, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 13/13 workers
13 workers [41406 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
.................................F...................................... [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 14%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 18%]
........................................................................ [ 19%]
..........................................s............................. [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 21%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 22%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
......................................ssss.............................. [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 37%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 38%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 44%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 45%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 49%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 50%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
........................................................................ [ 55%]
....................s................................................... [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 59%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 60%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................F............................... [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 67%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
..................................s..................................... [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
..............................ss........................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
..............................................F......................... [ 72%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 74%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 75%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
........................................................................ [ 79%]
.......................s................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 80%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
.........................................F.............................. [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
s....................................................................... [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
...................................................s.................... [ 86%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 87%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
........................................................................ [ 88%]
.......................................................s................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 91%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 92%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 93%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 94%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 95%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 96%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 97%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 98%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
......                                                                   [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: CI run was detected because environment variable "CI" was defined. 
inline-snapshot runs with --inline-snapshot=disable by default in CI. This means
that tests with snapshots will continue to run, but snapshot(x) will only return
x and inline-snapshot will not be able to fix snapshots or generate reports. You
can change this by using --inline-snapshot=report for example.


=================================== FAILURES ===================================
__________ test_async_bounded_agents_search_load_rejects_stale_query ___________
[gw0] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

    async def test_async_bounded_agents_search_load_rejects_stale_query() -> None:
        app = _SearchLoadApp()
        app._agent_search_query = "project:sase"
    
        def fake_load_agents(*_args: object, **_kwargs: object) -> _AgentDiskLoadResult:
            app._agent_search_query = "model:opus"
            return _AgentDiskLoadResult(
                all_agents=[],
                dismissed_from_loader=[],
                load_state=AgentLoadState(
                    tier="tier1",
                    complete_visible_inbox=True,
                    complete_history=False,
                    artifact_source="artifact_index",
                    used_artifact_index=True,
                    bounded_prefix=True,
                    requested_limit=120,
                    returned_count=0,
                    has_more=True,
                ),
            )
    
        with (
            patch(
                "sase.ace.tui.actions.agents._loading_disk."
                "_compute_external_dismissal_merge",
                return_value=None,
            ),
            patch("sase.ace.patch.find_all_patches_cached", return_value=[]),
            patch(
                "sase.ace.tui.actions.agents._loading.load_agents_from_disk_with_state",
                side_effect=fake_load_agents,
            ),
            patch("sase.ace.tui.repro.capture.record_agents_tab_loader_result"),
        ):
>           await app._load_agents_async(source="filter")

tests/ace/tui/actions/test_agent_search_history_split.py:155: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/tui/actions/agents/_loading_disk.py:403: in _load_agents_async
    _reschedule_stale_agent_query_load(
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

app = <tests.ace.tui.actions.test_agent_search_history_split._SearchLoadApp object at 0x7f8fbff15a90>
source = 'filter', full_history = False, full_history_reason = None
index_freshness = 'cached', complete_prefix = False

    def _reschedule_stale_agent_query_load(
        app: Any,
        *,
        source: str,
        full_history: bool,
        full_history_reason: str | None,
        index_freshness: Literal["revalidate", "cached"],
        complete_prefix: bool = False,
    ) -> None:
        """Schedule a replacement read for the current query after discarding stale data."""
        schedule_refresh = getattr(app, "_schedule_agents_async_refresh", None)
        if not callable(schedule_refresh):
            return
>       schedule_refresh(
            source=source,
            full_history=full_history,
            full_history_reason=(
                full_history_reason or "stale_query_retry" if full_history else None
            ),
            revalidate_index=index_freshness == "revalidate",
            complete_prefix=complete_prefix,
        )
E       TypeError: _SearchLoadApp._schedule_agents_async_refresh() got an unexpected keyword argument 'full_history'

src/sase/ace/tui/actions/agents/_loading_disk.py:146: TypeError
_______ test_supervisor_freezes_stage_manifest_and_retained_log_metadata _______
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-2/popen-gw5/test_supervisor_freezes_stage_0')
monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7fc7ab0fa270>

    def test_supervisor_freezes_stage_manifest_and_retained_log_metadata(
        tmp_path: Path,
        monkeypatch,
    ) -> None:
        monkeypatch.setenv("SASE_MONITOR_LOG_MAX_BYTES", "64")
        payload = "import sys; print('stage boom'); print('x' * 120); sys.exit(4)"
        command = (
            f"{shlex.quote(str(_run_silent_path()))} 'test (scoped)' "
            f"{shlex.quote(sys.executable)} -c {shlex.quote(payload)}"
        )
        artifacts_dir, _project_file = _make_member(tmp_path, command=command)
    
        exit_status = run_supervisor(artifacts_dir)
    
        assert exit_status == 1
        meta = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
        assert meta["monitor_state"] == "failed"
        manifest_path = Path(meta["monitor_diagnostic_manifest_path"])
        retained_path = Path(meta["monitor_retained_log_metadata_path"])
        assert manifest_path.exists()
        assert retained_path.exists()
    
        manifest = json.loads(manifest_path.read_text(encoding="utf-8"))
        assert manifest["complete"] is False
        assert manifest["stages"][0]["status"] == "failed"
        assert manifest["stages"][0]["diagnostic_refs"]
    
        diagnostics = read_diagnostics_text(artifacts_dir)
        assert "stage boom" in diagnostics.text
        assert diagnostics.metadata["available"] is True
    
        metadata = retained_log_metadata(artifacts_dir)
        assert metadata["total_observed_bytes"] > 0
        assert metadata["retained_ranges"]
        assert metadata["segments"]
    
>       result_path = Path(meta["continuation_monitor_result_path"])
                           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
E       KeyError: 'continuation_monitor_result_path'

tests/monitor/test_monitor_diagnostics.py:120: KeyError
_ test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard __
[gw6] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

    def test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard() -> (
        None
    ):
        """Suffix shadows not handled by canonical dedup are still suppressed."""
        app = FakeLoadingApp()
        raw_suffix = "20260202120000"
        cached_running = make_agent(
            agent_type=AgentType.RUNNING,
            cl_name="active",
            status="RUNNING",
            raw_suffix=raw_suffix,
            workflow="run",
        )
        incoming_running = make_agent(
            agent_type=AgentType.RUNNING,
            cl_name="unknown",
            status="RUNNING",
            raw_suffix=raw_suffix,
            workflow="run",
        )
    
        app._agent_load_state = SOURCE_SCAN_STATE
        app._agents_seen_complete_history = True
        app._agents_with_children = [cached_running]
        app._agents = list(app._agents_with_children)
    
        app._apply_loaded_agents(
            [incoming_running],
            [],
            on_agents_tab=False,
            selected_identity=None,
            load_state=INCOMPLETE_INDEX_STATE,
        )
    
>       assert app._agents == [cached_running]
E       AssertionError: assert [Agent(agent_...message=None)] == [Agent(agent_...message=None)]
E         
E         At index 0 diff: Agent(agent_type=<AgentType.RUNNING: 'run'>, cl_name='unknown', project_file='/tmp/projects/myproj/myproj.sase', status='RUNNING', start_time=datetime.datetime(2024, 1, 1, 12, 0), status_bucket=None, run_start_time=None, wait_start_time=None, stop_time=None, workspace_num=None, workflow='run', hook_command=None, stitch_id=None, mentor_profile=None, mentor_name=None, reviewer=None, pid=None, raw_suffix='20260202120000', response_path=None, diff_path=None, diff_has_real_edits=None, live_file_change_hint=None, linked_file_change_hint=None, extra_files=[], plan_path=None, archived_plan_path=None, sdd_plan_path=None, plan_committed=None, epic_plan_ref=None, epic_bead_id=None, phase_bead_id=None, bug=None, cl_num=None, parent_workflow=None, parent_timestamp=None, step_name=None, step_type=None, step_source=None, step_output=None, record_shape='full', index_record_dir=None, prompt_step_file_name=None, step_index=None, total_steps=None, parent_step_index=None, parent_total_steps=None, is_hidden_step=False, parent_appears_as_agent=False, appears_as_agent=False, is_anonymous=False, error_message=None, error_traceback=None, activity=None, monitor_id=None, monitor_state=None, monitor_command=None, monitor_label=None, monitor_start_status=None, monitor_stop_status=None, monitor_exit_code=None, monitor_cwd=None, monitor_reason=None, monitor_next_action=None, monitor_next_output=None, monitor_next_model=None, monitor_completion_ref=None, monitor_profile=None, monitor_policy_digest=None, monitor_timeout_seconds=None, monitor_idle_timeout_seconds=None, monitor_output_truncated=False, monitor_diagnostic_manifest_ref=None, monitor_retained_log_ref=None, continuation_monitor_result_id=None, continuation_monitor_result_ref=None, continuation_checkpoint_ref=None, continuation_node_ref=None, continuation_manifest_ref=None, monitor_budget_decision_path=None, monitor_followup_outcome=None, monitor_followup_error=None, monitor_followup_agent=None, monitor_followup_degraded_reason=None, monitor_followup_prompt_path=None, monitor_host_completion_status=None, monitor_host_completion_message=None, monitor_host_completion_reason=None, gate_id=None, gate_kind=None, gate_state=None, gate_start_status=None, gate_stop_status=None, gate_accent=None, gate_label=None, gate_reason=None, gate_timeout_seconds=None, gate_elapsed_seconds=None, gate_output_path=None, gate_output_truncated=False, gate_bundle_path=None, gate_notification_id=None, gate_decision_path=None, gate_creator_agent=None, gate_request_fingerprint=None, gate_workspace_policy=None, gate_next_action=None, gate_next_fork=None, gate_next_output=None, gate_next_model=None, gate_followup_agent=None, gate_followup_outcome=None, gate_followup_error=None, gate_followup_degraded_reason=None, gate_followup_prompt_path=None, proc_id=None, proc_status=None, proc_phase=None, proc_label=None, proc_origin=None, proc_language=None, proc_code_digest=None, proc_safe_preview=None, proc_log_path=None, proc_log_tail='', proc_output_truncated=False, proc_waits=[], proc_condition_result=None, proc_supervisor_id=None, proc_settlement_state=None, proc_request_fingerprint=None, output_path=None, model=None, llm_provider=None, reasoning_effort=None, model_alias=None, vcs_provider=None, workspace_dir=None, linked_repos=(), agent_name=None, presented_agent_name=None, presented_identity_name=None, waiting_for=[], waiting_for_beads=[], wait_duration=None, wait_until=None, queue_capacity=None, queue_capacity_explicit=False, wait_runners=None, wait_runners_explicit=False, wait_priority=None, wait_priority_explicit=False, queue_weight=None, queue_weight_explicit=False, queue_weight_invalid=False, queue_weight_error=None, slot_requested_at=None, runner_slots_in_use=None, runner_occupied_capacity=None, runner_effective_limit=None, runner_admission_limit=None, runner_slot_queue_position=None, runner_slot_queue_size=None, runner_capacity_blockers=(), runner_slot_yielded=False, artifacts_dir=None, embedded_workflow_name=None, is_pre_prompt_step=False, hidden=False, source_username=None, source_machine=None, source_run_id=None, archive_visibility='visible', archive_payload_sha256=None, archive_capabilities=None, historically_viewable=True, durably_revivable=True, restartable=True, missing_requirements=[], reverted=False, retry_count=0, max_retries=0, retry_next_at_epoch=None, retry_wait_seconds=0, using_fallback=False, fallback_model=None, retry_status=None, _from_patch=False, approve=False, auto_approve_plan_action=None, plan_action=None, role_suffix=None, agent_family=None, agent_family_role=None, imported_source_owner=None, agent_clan=None, agent_clan_generation=None, clan_tribe=None, clan_summary=None, is_clan_container=False, is_imported_family_container=False, tree_parent_key=None, tree_depth=0, clan_tribes=(), agent_family_parallel=False, plan_chain_root=False, tribe=None, output_variables={}, followup_agents=[], runtime_children=[], retry_of_timestamp=None, retry_attempt=0, retry_chain_root_timestamp=None, retried_as_timestamp=None, retry_terminal=False, retry_error_category=None, retry_chain_siblings=[], plan_times=[], code_time=None, epic_time=None, feedback_times=[], feedback_plan_paths={}, questions_times=[], question_request_path=None, question_response_path=None, question_session_id=None, retry_times=[], attempt_history=[], project_display_name=None, fleet_origin_alias=None, fleet_origin_installation_id=None, fleet_logical_key=None, fleet_exact_key=None, fleet_revision=None, fleet_freshness=None, fleet_connection_health=None, fleet_observed_at_unix=None, fleet_host_running_count=None, fleet_host_total_count=None, fleet_host_waiting_count=None, fleet_host_failed_count=None, fleet_host_done_count=None, fleet_host_unknown_count=None, fleet_followed=False, fleet_bounded_intent=None, fleet_diagnostic=None, fleet_dispatch_status=None, fleet_dispatch_message=None) != Agent(agent_type=<AgentType.RUNNING: 'run'>, cl_name='active', project_file='/tmp/projects/myproj/myproj.sase', status='RUNNING', start_time=datetime.datetime(2024, 1, 1, 12, 0), status_bucket=None, run_start_time=None, wait_start_time=None, stop_time=None, workspace_num=None, workflow='run', hook_command=None, stitch_id=None, mentor_profile=None, mentor_name=None, reviewer=None, pid=None, raw_suffix='20260202120000', response_path=None, diff_path=None, diff_has_real_edits=None, live_file_change_hint=None, linked_file_change_hint=None, extra_files=[], plan_path=None, archived_plan_path=None, sdd_plan_path=None, plan_committed=None, epic_plan_ref=None, epic_bead_id=None, phase_bead_id=None, bug=None, cl_num=None, parent_workflow=None, parent_timestamp=None, step_name=None, step_type=None, step_source=None, step_output=None, record_shape='full', index_record_dir=None, prompt_step_file_name=None, step_index=None, total_steps=None, parent_step_index=None, parent_total_steps=None, is_hidden_step=False, parent_appears_as_agent=False, appears_as_agent=False, is_anonymous=False, error_message=None, error_traceback=None, activity=None, monitor_id=None, monitor_state=None, monitor_command=None, monitor_label=None, monitor_start_status=None, monitor_stop_status=None, monitor_exit_code=None, monitor_cwd=None, monitor_reason=None, monitor_next_action=None, monitor_next_output=None, monitor_next_model=None, monitor_completion_ref=None, monitor_profile=None, monitor_policy_digest=None, monitor_timeout_seconds=None, monitor_idle_timeout_seconds=None, monitor_output_truncated=False, monitor_diagnostic_manifest_ref=None, monitor_retained_log_ref=None, continuation_monitor_result_id=None, continuation_monitor_result_ref=None, continuation_checkpoint_ref=None, continuation_node_ref=None, continuation_manifest_ref=None, monitor_budget_decision_path=None, monitor_followup_outcome=None, monitor_followup_error=None, monitor_followup_agent=None, monitor_followup_degraded_reason=None, monitor_followup_prompt_path=None, monitor_host_completion_status=None, monitor_host_completion_message=None, monitor_host_completion_reason=None, gate_id=None, gate_kind=None, gate_state=None, gate_start_status=None, gate_stop_status=None, gate_accent=None, gate_label=None, gate_reason=None, gate_timeout_seconds=None, gate_elapsed_seconds=None, gate_output_path=None, gate_output_truncated=False, gate_bundle_path=None, gate_notification_id=None, gate_decision_path=None, gate_creator_agent=None, gate_request_fingerprint=None, gate_workspace_policy=None, gate_next_action=None, gate_next_fork=None, gate_next_output=None, gate_next_model=None, gate_followup_agent=None, gate_followup_outcome=None, gate_followup_error=None, gate_followup_degraded_reason=None, gate_followup_prompt_path=None, proc_id=None, proc_status=None, proc_phase=None, proc_label=None, proc_origin=None, proc_language=None, proc_code_digest=None, proc_safe_preview=None, proc_log_path=None, proc_log_tail='', proc_output_truncated=False, proc_waits=[], proc_condition_result=None, proc_supervisor_id=None, proc_settlement_state=None, proc_request_fingerprint=None, output_path=None, model=None, llm_provider=None, reasoning_effort=None, model_alias=None, vcs_provider=None, workspace_dir=None, linked_repos=(), agent_name=None, presented_agent_name=None, presented_identity_name=None, waiting_for=[], waiting_for_beads=[], wait_duration=None, wait_until=None, queue_capacity=None, queue_capacity_explicit=False, wait_runners=None, wait_runners_explicit=False, wait_priority=None, wait_priority_explicit=False, queue_weight=None, queue_weight_explicit=False, queue_weight_invalid=False, queue_weight_error=None, slot_requested_at=None, runner_slots_in_use=None, runner_occupied_capacity=None, runner_effective_limit=None, runner_admission_limit=None, runner_slot_queue_position=None, runner_slot_queue_size=None, runner_capacity_blockers=(), runner_slot_yielded=False, artifacts_dir=None, embedded_workflow_name=None, is_pre_prompt_step=False, hidden=False, source_username=None, source_machine=None, source_run_id=None, archive_visibility='visible', archive_payload_sha256=None, archive_capabilities=None, historically_viewable=True, durably_revivable=True, restartable=True, missing_requirements=[], reverted=False, retry_count=0, max_retries=0, retry_next_at_epoch=None, retry_wait_seconds=0, using_fallback=False, fallback_model=None, retry_status=None, _from_patch=False, approve=False, auto_approve_plan_action=None, plan_action=None, role_suffix=None, agent_family=None, agent_family_role=None, imported_source_owner=None, agent_clan=None, agent_clan_generation=None, clan_tribe=None, clan_summary=None, is_clan_container=False, is_imported_family_container=False, tree_parent_key=None, tree_depth=0, clan_tribes=(), agent_family_parallel=False, plan_chain_root=False, tribe=None, output_variables={}, followup_agents=[], runtime_children=[], retry_of_timestamp=None, retry_attempt=0, retry_chain_root_timestamp=None, retried_as_timestamp=None, retry_terminal=False, retry_error_category=None, retry_chain_siblings=[], plan_times=[], code_time=None, epic_time=None, feedback_times=[], feedback_plan_paths={}, questions_times=[], question_request_path=None, question_response_path=None, question_session_id=None, retry_times=[], attempt_history=[], project_display_name=None, fleet_origin_alias=None, fleet_origin_installation_id=None, fleet_logical_key=None, fleet_exact_key=None, fleet_revision=None, fleet_freshness=None, fleet_connection_health=None, fleet_observed_at_unix=None, fleet_host_running_count=None, fleet_host_total_count=None, fleet_host_waiting_count=None, fleet_host_failed_count=None, fleet_host_done_count=None, fleet_host_unknown_count=None, fleet_followed=False, fleet_bounded_intent=None, fleet_diagnostic=None, fleet_dispatch_status=None, fleet_dispatch_message=None)
E         
E         Full diff:
E           [
E               Agent(
E                   agent_type=<AgentType.RUNNING: 'run'>,
E         -         cl_name='active',
E         +         cl_name='unknown',
E                   project_file='/tmp/projects/myproj/myproj.sase',
E                   status='RUNNING',
E                   start_time=datetime.datetime(2024, 1, 1, 12, 0),
E                   status_bucket=None,
E                   run_start_time=None,
E                   wait_start_time=None,
E                   stop_time=None,
E                   workspace_num=None,
E                   workflow='run',
E                   hook_command=None,
E                   stitch_id=None,
E                   mentor_profile=None,
E                   mentor_name=None,
E                   reviewer=None,
E                   pid=None,
E                   raw_suffix='20260202120000',
E                   response_path=None,
E                   diff_path=None,
E                   diff_has_real_edits=None,
E                   live_file_change_hint=None,
E                   linked_file_change_hint=None,
E                   extra_files=[],
E                   plan_path=None,
E                   archived_plan_path=None,
E                   sdd_plan_path=None,
E                   plan_committed=None,
E                   epic_plan_ref=None,
E                   epic_bead_id=None,
E                   phase_bead_id=None,
E                   bug=None,
E                   cl_num=None,
E                   parent_workflow=None,
E                   parent_timestamp=None,
E                   step_name=None,
E                   step_type=None,
E                   step_source=None,
E                   step_output=None,
E                   record_shape='full',
E                   index_record_dir=None,
E                   prompt_step_file_name=None,
E                   step_index=None,
E                   total_steps=None,
E                   parent_step_index=None,
E                   parent_total_steps=None,
E                   is_hidden_step=False,
E                   parent_appears_as_agent=False,
E                   appears_as_agent=False,
E                   is_anonymous=False,
E                   error_message=None,
E                   error_traceback=None,
E                   activity=None,
E                   monitor_id=None,
E                   monitor_state=None,
E                   monitor_command=None,
E                   monitor_label=None,
E                   monitor_start_status=None,
E                   monitor_stop_status=None,
E                   monitor_exit_code=None,
E                   monitor_cwd=None,
E                   monitor_reason=None,
E                   monitor_next_action=None,
E                   monitor_next_output=None,
E                   monitor_next_model=None,
E                   monitor_completion_ref=None,
E                   monitor_profile=None,
E                   monitor_policy_digest=None,
E                   monitor_timeout_seconds=None,
E                   monitor_idle_timeout_seconds=None,
E                   monitor_output_truncated=False,
E                   monitor_diagnostic_manifest_ref=None,
E                   monitor_retained_log_ref=None,
E                   continuation_monitor_result_id=None,
E                   continuation_monitor_result_ref=None,
E                   continuation_checkpoint_ref=None,
E                   continuation_node_ref=None,
E                   continuation_manifest_ref=None,
E                   monitor_budget_decision_path=None,
E                   monitor_followup_outcome=None,
E                   monitor_followup_error=None,
E                   monitor_followup_agent=None,
E                   monitor_followup_degraded_reason=None,
E                   monitor_followup_prompt_path=None,
E                   monitor_host_completion_status=None,
E                   monitor_host_completion_message=None,
E                   monitor_host_completion_reason=None,
E                   gate_id=None,
E                   gate_kind=None,
E                   gate_state=None,
E                   gate_start_status=None,
E                   gate_stop_status=None,
E                   gate_accent=None,
E                   gate_label=None,
E                   gate_reason=None,
E                   gate_timeout_seconds=None,
E                   gate_elapsed_seconds=None,
E                   gate_output_path=None,
E                   gate_output_truncated=False,
E                   gate_bundle_path=None,
E                   gate_notification_id=None,
E                   gate_decision_path=None,
E                   gate_creator_agent=None,
E                   gate_request_fingerprint=None,
E                   gate_workspace_policy=None,
E                   gate_next_action=None,
E                   gate_next_fork=None,
E                   gate_next_output=None,
E                   gate_next_model=None,
E                   gate_followup_agent=None,
E                   gate_followup_outcome=None,
E                   gate_followup_error=None,
E                   gate_followup_degraded_reason=None,
E                   gate_followup_prompt_path=None,
E                   proc_id=None,
E                   proc_status=None,
E                   proc_phase=None,
E                   proc_label=None,
E                   proc_origin=None,
E                   proc_language=None,
E                   proc_code_digest=None,
E                   proc_safe_preview=None,
E                   proc_log_path=None,
E                   proc_log_tail='',
E                   proc_output_truncated=False,
E                   proc_waits=[],
E                   proc_condition_result=None,
E                   proc_supervisor_id=None,
E                   proc_settlement_state=None,
E                   proc_request_fingerprint=None,
E                   output_path=None,
E                   model=None,
E                   llm_provider=None,
E                   reasoning_effort=None,
E                   model_alias=None,
E                   vcs_provider=None,
E                   workspace_dir=None,
E                   linked_repos=(),
E                   agent_name=None,
E                   presented_agent_name=None,
E                   presented_identity_name=None,
E                   waiting_for=[],
E                   waiting_for_beads=[],
E                   wait_duration=None,
E                   wait_until=None,
E                   queue_capacity=None,
E                   queue_capacity_explicit=False,
E                   wait_runners=None,
E                   wait_runners_explicit=False,
E                   wait_priority=None,
E                   wait_priority_explicit=False,
E                   queue_weight=None,
E                   queue_weight_explicit=False,
E                   queue_weight_invalid=False,
E                   queue_weight_error=None,
E                   slot_requested_at=None,
E                   runner_slots_in_use=None,
E                   runner_occupied_capacity=None,
E                   runner_effective_limit=None,
E                   runner_admission_limit=None,
E                   runner_slot_queue_position=None,
E                   runner_slot_queue_size=None,
E                   runner_capacity_blockers=(),
E                   runner_slot_yielded=False,
E                   artifacts_dir=None,
E                   embedded_workflow_name=None,
E                   is_pre_prompt_step=False,
E                   hidden=False,
E                   source_username=None,
E                   source_machine=None,
E                   source_run_id=None,
E                   archive_visibility='visible',
E                   archive_payload_sha256=None,
E                   archive_capabilities=None,
E                   historically_viewable=True,
E                   durably_revivable=True,
E                   restartable=True,
E                   missing_requirements=[],
E                   reverted=False,
E                   retry_count=0,
E                   max_retries=0,
E                   retry_next_at_epoch=None,
E                   retry_wait_seconds=0,
E                   using_fallback=False,
E                   fallback_model=None,
E                   retry_status=None,
E                   _from_patch=False,
E                   approve=False,
E                   auto_approve_plan_action=None,
E                   plan_action=None,
E                   role_suffix=None,
E                   agent_family=None,
E                   agent_family_role=None,
E                   imported_source_owner=None,
E                   agent_clan=None,
E                   agent_clan_generation=None,
E                   clan_tribe=None,
E                   clan_summary=None,
E                   is_clan_container=False,
E                   is_imported_family_container=False,
E                   tree_parent_key=None,
E                   tree_depth=0,
E                   clan_tribes=(),
E                   agent_family_parallel=False,
E                   plan_chain_root=False,
E                   tribe=None,
E                   output_variables={},
E                   followup_agents=[],
E                   runtime_children=[],
E                   retry_of_timestamp=None,
E                   retry_attempt=0,
E                   retry_chain_root_timestamp=None,
E                   retried_as_timestamp=None,
E                   retry_terminal=False,
E                   retry_error_category=None,
E                   retry_chain_siblings=[],
E                   plan_times=[],
E                   code_time=None,
E                   epic_time=None,
E                   feedback_times=[],
E                   feedback_plan_paths={},
E                   questions_times=[],
E                   question_request_path=None,
E                   question_response_path=None,
E                   question_session_id=None,
E                   retry_times=[],
E                   attempt_history=[],
E                   project_display_name=None,
E                   fleet_origin_alias=None,
E                   fleet_origin_installation_id=None,
E                   fleet_logical_key=None,
E                   fleet_exact_key=None,
E                   fleet_revision=None,
E                   fleet_freshness=None,
E                   fleet_connection_health=None,
E                   fleet_observed_at_unix=None,
E                   fleet_host_running_count=None,
E                   fleet_host_total_count=None,
E                   fleet_host_waiting_count=None,
E                   fleet_host_failed_count=None,
E                   fleet_host_done_count=None,
E                   fleet_host_unknown_count=None,
E                   fleet_followed=False,
E                   fleet_bounded_intent=None,
E                   fleet_diagnostic=None,
E                   fleet_dispatch_status=None,
E                   fleet_dispatch_message=None,
E               ),
E           ]

tests/test_agent_loader_incomplete_history_dedup.py:104: AssertionError
_________ test_settle_monitor_artifacts_leaves_stopped_at_unpersisted __________
[gw5] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/bin/python

tmp_path = PosixPath('/var/tmp/sase-75285096/pytest-of-bryan/pytest-2/popen-gw5/test_settle_monitor_artifacts_0')

    def test_settle_monitor_artifacts_leaves_stopped_at_unpersisted(
        tmp_path: Path,
    ) -> None:
        artifacts_dir = _make_proc_monitor(tmp_path)
        state = _settlement_state(artifacts_dir)
    
        settle_monitor_artifacts(state)
    
        on_disk = json.loads((Path(artifacts_dir) / "agent_meta.json").read_text())
        assert "stopped_at" not in on_disk
>       assert on_disk["continuation_monitor_result_ref"].startswith(
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
            "local:continuation/records/monitor_result/"
        )
E       KeyError: 'continuation_monitor_result_ref'

tests/monitor/test_monitor_proc_settlement.py:74: KeyError
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: 13 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:885: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py::test_tab_completes_bead_plus_to_plus_one
tests/completion/test_zsh_smoke.py::test_dynamic_slot_fetches_fixture_candidates_and_caches
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask #zz-"ask #zzz-fixture-xprompt"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask %mo-"ask %model"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask @file:e-"ask @file:explicit:abc123"]
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=2445531) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2445563) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:1014: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=2445563) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
144.66s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
111.48s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
59.03s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
39.73s call     tests/ace/tui/test_config_pane_widget_jump.py::test_config_jump_paints_hints_over_visible_rows_in_order
38.25s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
38.24s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
35.24s call     tests/ace/tui/test_config_pane_widget_navigation.py::test_config_pane_h_l_collapse_expand_and_descend
26.57s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
25.63s call     tests/ace/tui/test_xprompt_browser_filter.py::test_xprompts_open_browse_first_with_hidden_filter
24.99s call     tests/test_agent_load_tiering_harness.py::test_load_tiering_query_battery_has_no_missing_rows_within_tier1_window
23.81s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
21.75s call     tests/monitor/test_monitor_start.py::test_start_monitor_persists_next_action_intent_after_ack
19.63s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
19.03s call     tests/ace/tui/test_xprompt_browser_jump.py::test_apostrophe_in_jump_mode_returns_to_previous_item
18.94s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_owner_through_real_monitor_and_next_handoff
18.16s call     tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_manual_update_drops_expired_load_freshness
17.05s call     tests/gate_conformance/test_gate_shell_conformance.py::test_shell_gate_settles_identically_across_every_surface
16.98s call     tests/monitor/test_monitor_owner_cleanup.py::test_owner_cleanup_stops_monitor_child_and_suppresses_followup
16.81s call     tests/ace/tui/test_plugins_browser_pane_update.py::test_plugins_pane_editable_update_uses_dev_preview_and_restart
16.76s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_managed_confirm_closes_admin_center
=========================== short test summary info ============================
FAILED tests/ace/tui/actions/test_agent_search_history_split.py::test_async_bounded_agents_search_load_rejects_stale_query - TypeError: _SearchLoadApp._schedule_agents_async_refresh() got an unexpected keyword argument 'full_history'
FAILED tests/monitor/test_monitor_diagnostics.py::test_supervisor_freezes_stage_manifest_and_retained_log_metadata - KeyError: 'continuation_monitor_result_path'
FAILED tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard - AssertionError: assert [Agent(agent_...message=None)] == [Agent(agent_...message=None)]
  
  At index 0 diff: Agent(agent_type=<AgentType.RUNNING: 'run'>, cl_name='unknown', project_file='/tmp/projects/myproj/myproj.sase', status='RUNNING', start_time=datetime.datetime(2024, 1, 1, 12, 0), status_bucket=None, run_start_time=None, wait_start_time=None, stop_time=None, workspace_num=None, workflow='run', hook_command=None, stitch_id=None, mentor_profile=None, mentor_name=None, reviewer=None, pid=None, raw_suffix='20260202120000', response_path=None, diff_path=None, diff_has_real_edits=None, live_file_change_hint=None, linked_file_change_hint=None, extra_files=[], plan_path=None, archived_plan_path=None, sdd_plan_path=None, plan_committed=None, epic_plan_ref=None, epic_bead_id=None, phase_bead_id=None, bug=None, cl_num=None, parent_workflow=None, parent_timestamp=None, step_name=None, step_type=None, step_source=None, step_output=None, record_shape='full', index_record_dir=None, prompt_step_file_name=None, step_index=None, total_steps=None, parent_step_index=None, parent_total_steps=None, is_hidden_step=False, parent_appears_as_agent=False, appears_as_agent=False, is_anonymous=False, error_message=None, error_traceback=None, activity=None, monitor_id=None, monitor_state=None, monitor_command=None, monitor_label=None, monitor_start_status=None, monitor_stop_status=None, monitor_exit_code=None, monitor_cwd=None, monitor_reason=None, monitor_next_action=None, monitor_next_output=None, monitor_next_model=None, monitor_completion_ref=None, monitor_profile=None, monitor_policy_digest=None, monitor_timeout_seconds=None, monitor_idle_timeout_seconds=None, monitor_output_truncated=False, monitor_diagnostic_manifest_ref=None, monitor_retained_log_ref=None, continuation_monitor_result_id=None, continuation_monitor_result_ref=None, continuation_checkpoint_ref=None, continuation_node_ref=None, continuation_manifest_ref=None, monitor_budget_decision_path=None, monitor_followup_outcome=None, monitor_followup_error=None, monitor_followup_agent=None, monitor_followup_degraded_reason=None, monitor_followup_prompt_path=None, monitor_host_completion_status=None, monitor_host_completion_message=None, monitor_host_completion_reason=None, gate_id=None, gate_kind=None, gate_state=None, gate_start_status=None, gate_stop_status=None, gate_accent=None, gate_label=None, gate_reason=None, gate_timeout_seconds=None, gate_elapsed_seconds=None, gate_output_path=None, gate_output_truncated=False, gate_bundle_path=None, gate_notification_id=None, gate_decision_path=None, gate_creator_agent=None, gate_request_fingerprint=None, gate_workspace_policy=None, gate_next_action=None, gate_next_fork=None, gate_next_output=None, gate_next_model=None, gate_followup_agent=None, gate_followup_outcome=None, gate_followup_error=None, gate_followup_degraded_reason=None, gate_followup_prompt_path=None, proc_id=None, proc_status=None, proc_phase=None, proc_label=None, proc_origin=None, proc_language=None, proc_code_digest=None, proc_safe_preview=None, proc_log_path=None, proc_log_tail='', proc_output_truncated=False, proc_waits=[], proc_condition_result=None, proc_supervisor_id=None, proc_settlement_state=None, proc_request_fingerprint=None, output_path=None, model=None, llm_provider=None, reasoning_effort=None, model_alias=None, vcs_provider=None, workspace_dir=None, linked_repos=(), agent_name=None, presented_agent_name=None, presented_identity_name=None, waiting_for=[], waiting_for_beads=[], wait_duration=None, wait_until=None, queue_capacity=None, queue_capacity_explicit=False, wait_runners=None, wait_runners_explicit=False, wait_priority=None, wait_priority_explicit=False, queue_weight=None, queue_weight_explicit=False, queue_weight_invalid=False, queue_weight_error=None, slot_requested_at=None, runner_slots_in_use=None, runner_occupied_capacity=None, runner_effective_limit=None, runner_admission_limit=None, runner_slot_queue_position=None, runner_slot_queue_size=None, runner_capacity_blockers=(), runner_slot_yielded=False, artifacts_dir=None, embedded_workflow_name=None, is_pre_prompt_step=False, hidden=False, source_username=None, source_machine=None, source_run_id=None, archive_visibility='visible', archive_payload_sha256=None, archive_capabilities=None, historically_viewable=True, durably_revivable=True, restartable=True, missing_requirements=[], reverted=False, retry_count=0, max_retries=0, retry_next_at_epoch=None, retry_wait_seconds=0, using_fallback=False, fallback_model=None, retry_status=None, _from_patch=False, approve=False, auto_approve_plan_action=None, plan_action=None, role_suffix=None, agent_family=None, agent_family_role=None, imported_source_owner=None, agent_clan=None, agent_clan_generation=None, clan_tribe=None, clan_summary=None, is_clan_container=False, is_imported_family_container=False, tree_parent_key=None, tree_depth=0, clan_tribes=(), agent_family_parallel=False, plan_chain_root=False, tribe=None, output_variables={}, followup_agents=[], runtime_children=[], retry_of_timestamp=None, retry_attempt=0, retry_chain_root_timestamp=None, retried_as_timestamp=None, retry_terminal=False, retry_error_category=None, retry_chain_siblings=[], plan_times=[], code_time=None, epic_time=None, feedback_times=[], feedback_plan_paths={}, questions_times=[], question_request_path=None, question_response_path=None, question_session_id=None, retry_times=[], attempt_history=[], project_display_name=None, fleet_origin_alias=None, fleet_origin_installation_id=None, fleet_logical_key=None, fleet_exact_key=None, fleet_revision=None, fleet_freshness=None, fleet_connection_health=None, fleet_observed_at_unix=None, fleet_host_running_count=None, fleet_host_total_count=None, fleet_host_waiting_count=None, fleet_host_failed_count=None, fleet_host_done_count=None, fleet_host_unknown_count=None, fleet_followed=False, fleet_bounded_intent=None, fleet_diagnostic=None, fleet_dispatch_status=None, fleet_dispatch_message=None) != Agent(agent_type=<AgentType.RUNNING: 'run'>, cl_name='active', project_file='/tmp/projects/myproj/myproj.sase', status='RUNNING', start_time=datetime.datetime(2024, 1, 1, 12, 0), status_bucket=None, run_start_time=None, wait_start_time=None, stop_time=None, workspace_num=None, workflow='run', hook_command=None, stitch_id=None, mentor_profile=None, mentor_name=None, reviewer=None, pid=None, raw_suffix='20260202120000', response_path=None, diff_path=None, diff_has_real_edits=None, live_file_change_hint=None, linked_file_change_hint=None, extra_files=[], plan_path=None, archived_plan_path=None, sdd_plan_path=None, plan_committed=None, epic_plan_ref=None, epic_bead_id=None, phase_bead_id=None, bug=None, cl_num=None, parent_workflow=None, parent_timestamp=None, step_name=None, step_type=None, step_source=None, step_output=None, record_shape='full', index_record_dir=None, prompt_step_file_name=None, step_index=None, total_steps=None, parent_step_index=None, parent_total_steps=None, is_hidden_step=False, parent_appears_as_agent=False, appears_as_agent=False, is_anonymous=False, error_message=None, error_traceback=None, activity=None, monitor_id=None, monitor_state=None, monitor_command=None, monitor_label=None, monitor_start_status=None, monitor_stop_status=None, monitor_exit_code=None, monitor_cwd=None, monitor_reason=None, monitor_next_action=None, monitor_next_output=None, monitor_next_model=None, monitor_completion_ref=None, monitor_profile=None, monitor_policy_digest=None, monitor_timeout_seconds=None, monitor_idle_timeout_seconds=None, monitor_output_truncated=False, monitor_diagnostic_manifest_ref=None, monitor_retained_log_ref=None, continuation_monitor_result_id=None, continuation_monitor_result_ref=None, continuation_checkpoint_ref=None, continuation_node_ref=None, continuation_manifest_ref=None, monitor_budget_decision_path=None, monitor_followup_outcome=None, monitor_followup_error=None, monitor_followup_agent=None, monitor_followup_degraded_reason=None, monitor_followup_prompt_path=None, monitor_host_completion_status=None, monitor_host_completion_message=None, monitor_host_completion_reason=None, gate_id=None, gate_kind=None, gate_state=None, gate_start_status=None, gate_stop_status=None, gate_accent=None, gate_label=None, gate_reason=None, gate_timeout_seconds=None, gate_elapsed_seconds=None, gate_output_path=None, gate_output_truncated=False, gate_bundle_path=None, gate_notification_id=None, gate_decision_path=None, gate_creator_agent=None, gate_request_fingerprint=None, gate_workspace_policy=None, gate_next_action=None, gate_next_fork=None, gate_next_output=None, gate_next_model=None, gate_followup_agent=None, gate_followup_outcome=None, gate_followup_error=None, gate_followup_degraded_reason=None, gate_followup_prompt_path=None, proc_id=None, proc_status=None, proc_phase=None, proc_label=None, proc_origin=None, proc_language=None, proc_code_digest=None, proc_safe_preview=None, proc_log_path=None, proc_log_tail='', proc_output_truncated=False, proc_waits=[], proc_condition_result=None, proc_supervisor_id=None, proc_settlement_state=None, proc_request_fingerprint=None, output_path=None, model=None, llm_provider=None, reasoning_effort=None, model_alias=None, vcs_provider=None, workspace_dir=None, linked_repos=(), agent_name=None, presented_agent_name=None, presented_identity_name=None, waiting_for=[], waiting_for_beads=[], wait_duration=None, wait_until=None, queue_capacity=None, queue_capacity_explicit=False, wait_runners=None, wait_runners_explicit=False, wait_priority=None, wait_priority_explicit=False, queue_weight=None, queue_weight_explicit=False, queue_weight_invalid=False, queue_weight_error=None, slot_requested_at=None, runner_slots_in_use=None, runner_occupied_capacity=None, runner_effective_limit=None, runner_admission_limit=None, runner_slot_queue_position=None, runner_slot_queue_size=None, runner_capacity_blockers=(), runner_slot_yielded=False, artifacts_dir=None, embedded_workflow_name=None, is_pre_prompt_step=False, hidden=False, source_username=None, source_machine=None, source_run_id=None, archive_visibility='visible', archive_payload_sha256=None, archive_capabilities=None, historically_viewable=True, durably_revivable=True, restartable=True, missing_requirements=[], reverted=False, retry_count=0, max_retries=0, retry_next_at_epoch=None, retry_wait_seconds=0, using_fallback=False, fallback_model=None, retry_status=None, _from_patch=False, approve=False, auto_approve_plan_action=None, plan_action=None, role_suffix=None, agent_family=None, agent_family_role=None, imported_source_owner=None, agent_clan=None, agent_clan_generation=None, clan_tribe=None, clan_summary=None, is_clan_container=False, is_imported_family_container=False, tree_parent_key=None, tree_depth=0, clan_tribes=(), agent_family_parallel=False, plan_chain_root=False, tribe=None, output_variables={}, followup_agents=[], runtime_children=[], retry_of_timestamp=None, retry_attempt=0, retry_chain_root_timestamp=None, retried_as_timestamp=None, retry_terminal=False, retry_error_category=None, retry_chain_siblings=[], plan_times=[], code_time=None, epic_time=None, feedback_times=[], feedback_plan_paths={}, questions_times=[], question_request_path=None, question_response_path=None, question_session_id=None, retry_times=[], attempt_history=[], project_display_name=None, fleet_origin_alias=None, fleet_origin_installation_id=None, fleet_logical_key=None, fleet_exact_key=None, fleet_revision=None, fleet_freshness=None, fleet_connection_health=None, fleet_observed_at_unix=None, fleet_host_running_count=None, fleet_host_total_count=None, fleet_host_waiting_count=None, fleet_host_failed_count=None, fleet_host_done_count=None, fleet_host_unknown_count=None, fleet_followed=False, fleet_bounded_intent=None, fleet_diagnostic=None, fleet_dispatch_status=None, fleet_dispatch_message=None)
  
  Full diff:
    [
        Agent(
            agent_type=<AgentType.RUNNING: 'run'>,
  -         cl_name='active',
  +         cl_name='unknown',
            project_file='/tmp/projects/myproj/myproj.sase',
            status='RUNNING',
            start_time=datetime.datetime(2024, 1, 1, 12, 0),
            status_bucket=None,
            run_start_time=None,
            wait_start_time=None,
            stop_time=None,
            workspace_num=None,
            workflow='run',
            hook_command=None,
            stitch_id=None,
            mentor_profile=None,
            mentor_name=None,
            reviewer=None,
            pid=None,
            raw_suffix='20260202120000',
            response_path=None,
            diff_path=None,
            diff_has_real_edits=None,
            live_file_change_hint=None,
            linked_file_change_hint=None,
            extra_files=[],
            plan_path=None,
            archived_plan_path=None,
            sdd_plan_path=None,
            plan_committed=None,
            epic_plan_ref=None,
            epic_bead_id=None,
            phase_bead_id=None,
            bug=None,
            cl_num=None,
            parent_workflow=None,
            parent_timestamp=None,
            step_name=None,
            step_type=None,
            step_source=None,
            step_output=None,
            record_shape='full',
            index_record_dir=None,
            prompt_step_file_name=None,
            step_index=None,
            total_steps=None,
            parent_step_index=None,
            parent_total_steps=None,
            is_hidden_step=False,
            parent_appears_as_agent=False,
            appears_as_agent=False,
            is_anonymous=False,
            error_message=None,
            error_traceback=None,
            activity=None,
            monitor_id=None,
            monitor_state=None,
            monitor_command=None,
            monitor_label=None,
            monitor_start_status=None,
            monitor_stop_status=None,
            monitor_exit_code=None,
            monitor_cwd=None,
            monitor_reason=None,
            monitor_next_action=None,
            monitor_next_output=None,
            monitor_next_model=None,
            monitor_completion_ref=None,
            monitor_profile=None,
            monitor_policy_digest=None,
            monitor_timeout_seconds=None,
            monitor_idle_timeout_seconds=None,
            monitor_output_truncated=False,
            monitor_diagnostic_manifest_ref=None,
            monitor_retained_log_ref=None,
            continuation_monitor_result_id=None,
            continuation_monitor_result_ref=None,
            continuation_checkpoint_ref=None,
            continuation_node_ref=None,
            continuation_manifest_ref=None,
            monitor_budget_decision_path=None,
            monitor_followup_outcome=None,
            monitor_followup_error=None,
            monitor_followup_agent=None,
            monitor_followup_degraded_reason=None,
            monitor_followup_prompt_path=None,
            monitor_host_completion_status=None,
            monitor_host_completion_message=None,
            monitor_host_completion_reason=None,
            gate_id=None,
            gate_kind=None,
            gate_state=None,
            gate_start_status=None,
            gate_stop_status=None,
            gate_accent=None,
            gate_label=None,
            gate_reason=None,
            gate_timeout_seconds=None,
            gate_elapsed_seconds=None,
            gate_output_path=None,
            gate_output_truncated=False,
            gate_bundle_path=None,
            gate_notification_id=None,
            gate_decision_path=None,
            gate_creator_agent=None,
            gate_request_fingerprint=None,
            gate_workspace_policy=None,
            gate_next_action=None,
            gate_next_fork=None,
            gate_next_output=None,
            gate_next_model=None,
            gate_followup_agent=None,
            gate_followup_outcome=None,
            gate_followup_error=None,
            gate_followup_degraded_reason=None,
            gate_followup_prompt_path=None,
            proc_id=None,
            proc_status=None,
            proc_phase=None,
            proc_label=None,
            proc_origin=None,
            proc_language=None,
            proc_code_digest=None,
            proc_safe_preview=None,
            proc_log_path=None,
            proc_log_tail='',
            proc_output_truncated=False,
            proc_waits=[],
            proc_condition_result=None,
            proc_supervisor_id=None,
            proc_settlement_state=None,
            proc_request_fingerprint=None,
            output_path=None,
            model=None,
            llm_provider=None,
            reasoning_effort=None,
            model_alias=None,
            vcs_provider=None,
            workspace_dir=None,
            linked_repos=(),
            agent_name=None,
            presented_agent_name=None,
            presented_identity_name=None,
            waiting_for=[],
            waiting_for_beads=[],
            wait_duration=None,
            wait_until=None,
            queue_capacity=None,
            queue_capacity_explicit=False,
            wait_runners=None,
            wait_runners_explicit=False,
            wait_priority=None,
            wait_priority_explicit=False,
            queue_weight=None,
            queue_weight_explicit=False,
            queue_weight_invalid=False,
            queue_weight_error=None,
            slot_requested_at=None,
            runner_slots_in_use=None,
            runner_occupied_capacity=None,
            runner_effective_limit=None,
            runner_admission_limit=None,
            runner_slot_queue_position=None,
            runner_slot_queue_size=None,
            runner_capacity_blockers=(),
            runner_slot_yielded=False,
            artifacts_dir=None,
            embedded_workflow_name=None,
            is_pre_prompt_step=False,
            hidden=False,
            source_username=None,
            source_machine=None,
            source_run_id=None,
            archive_visibility='visible',
            archive_payload_sha256=None,
            archive_capabilities=None,
            historically_viewable=True,
            durably_revivable=True,
            restartable=True,
            missing_requirements=[],
            reverted=False,
            retry_count=0,
            max_retries=0,
            retry_next_at_epoch=None,
            retry_wait_seconds=0,
            using_fallback=False,
            fallback_model=None,
            retry_status=None,
            _from_patch=False,
            approve=False,
            auto_approve_plan_action=None,
            plan_action=None,
            role_suffix=None,
            agent_family=None,
            agent_family_role=None,
            imported_source_owner=None,
            agent_clan=None,
            agent_clan_generation=None,
            clan_tribe=None,
            clan_summary=None,
            is_clan_container=False,
            is_imported_family_container=False,
            tree_parent_key=None,
            tree_depth=0,
            clan_tribes=(),
            agent_family_parallel=False,
            plan_chain_root=False,
            tribe=None,
            output_variables={},
            followup_agents=[],
            runtime_children=[],
            retry_of_timestamp=None,
            retry_attempt=0,
            retry_chain_root_timestamp=None,
            retried_as_timestamp=None,
            retry_terminal=False,
            retry_error_category=None,
            retry_chain_siblings=[],
            plan_times=[],
            code_time=None,
            epic_time=None,
            feedback_times=[],
            feedback_plan_paths={},
            questions_times=[],
            question_request_path=None,
            question_response_path=None,
            question_session_id=None,
            retry_times=[],
            attempt_history=[],
            project_display_name=None,
            fleet_origin_alias=None,
            fleet_origin_installation_id=None,
            fleet_logical_key=None,
            fleet_exact_key=None,
            fleet_revision=None,
            fleet_freshness=None,
            fleet_connection_health=None,
            fleet_observed_at_unix=None,
            fleet_host_running_count=None,
            fleet_host_total_count=None,
            fleet_host_waiting_count=None,
            fleet_host_failed_count=None,
            fleet_host_done_count=None,
            fleet_host_unknown_count=None,
            fleet_followed=False,
            fleet_bounded_intent=None,
            fleet_diagnostic=None,
            fleet_dispatch_status=None,
            fleet_dispatch_message=None,
        ),
    ]
FAILED tests/monitor/test_monitor_proc_settlement.py::test_settle_monitor_artifacts_leaves_stopped_at_unpersisted - KeyError: 'continuation_monitor_result_ref'
===== 4 failed, 41389 passed, 14 skipped, 80 warnings in 931.01s (0:15:31) =====
error: recipe `test-scoped` failed on line 455 with exit code 1
scoped: escalated to the full suite (rules: core-identity-changed); contexts baseline not consulted
MAIN_HEAD=faad5c3dc3f00539ab9ef8441aabf7b9de2153a0
CORE_PIN=7f43a996e9393449e838881f907d40fc76d0fdc6

