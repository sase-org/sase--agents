# Chat History - ace-run (sase-10w.5.f0.f0--mon)

- **TIMESTAMP:** 2026-09-14 14:48:46 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-10w.5.f0.f0--mon

## Prompt

sase monitor start --command 'bash -lc set -euo pipefail\nCORE_DIR="$PWD/sase/repos/linked/sase-core"\nPIN_BEFORE="$(cat sase-core-revision.txt)"\nCORE_HEAD_BEFORE="$(git -C "$CORE_DIR" rev-parse HEAD)"\necho "sase_head=$(git rev-parse HEAD)"\necho "pin_before=$PIN_BEFORE"\necho "core_head_before=$CORE_HEAD_BEFORE"\ntest "$PIN_BEFORE" = "$CORE_HEAD_BEFORE"\nexport SASE_CORE_DIR="$CORE_DIR"\nexport GH_REPO=sase-org/sase\njust install\nPIN_AFTER="$(cat sase-core-revision.txt)"\nCORE_HEAD_AFTER="$(git -C "$CORE_DIR" rev-parse HEAD)"\necho "pin_after=$PIN_AFTER"\necho "core_head_after=$CORE_HEAD_AFTER"\ntest "$PIN_AFTER" = "$CORE_HEAD_AFTER"\n.venv/bin/python tools/check_sase_core_rs_bindings\n.venv/bin/python -m pytest tests/test_managed_tmp_reaper.py tests/test_check_sase_core_rs_bindings_tool.py\njust check\njust check-full' --reason 'Run local pin verification for approved sase-10w.5 closeout before CI and baseline steps'

## Response

ANSIBLE_NOCOWS=1
ATHENAS_DDNS_HOSTNAME=bbugyi.ddns.net
ATHENAS_SSH_PORT=34857
ATUIN_HISTORY_ID=
ATUIN_SESSION=01a0a117b09d743f9283000509868fde
ATUIN_SHLVL=3
ATUIN_TMUX_POPUP=false
BASH=/usr/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:extquote:force_fignore:globasciiranges:globskipdots:hostcomplete:interactive_comments:login_shell:patsub_replacement:progcomp:promptvars:sourcepath
BASH_ALIASES=()
BASH_ARGC=([0]="1")
BASH_ARGV=([0]="pipefail")
BASH_CMDS=()
BASH_EXECUTION_STRING=set
BASH_LINENO=()
BASH_LOADABLES_PATH=/usr/local/lib/bash:/usr/lib/bash:/opt/local/lib/bash:/usr/pkg/lib/bash:/opt/pkg/lib/bash:.
BASH_SOURCE=()
BASH_VERSINFO=([0]="5" [1]="2" [2]="37" [3]="1" [4]="release" [5]="x86_64-pc-linux-gnu")
BASH_VERSION='5.2.37(1)-release'
BB=bbugyi.ddns.net
BETTER_EXCEPTIONS=1
CARGO_BUILD_BUILD_DIR=/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws19-260914_140415/build
CARGO_INCREMENTAL=0
CARGO_PROFILE_DEV_DEBUG=line-tables-only
CARGO_PROFILE_TEST_DEBUG=line-tables-only
CARGO_TARGET_DIR=/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws19-260914_140415
CODEX_CI=1
CODEX_HOME=/home/bryan/.cache/sase/codex_home/1711751-cf08a23d1ce748d9bbeb86d45eab75aa
CODEX_MANAGED_BY_NPM=1
CODEX_MANAGED_PACKAGE_ROOT=/home/bryan/.config/nvm/versions/node/v22.14.0/lib/node_modules/@openai/codex
CODEX_PROJECT_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/
CODEX_SESSION_ID=01a0a117-ad1f-7891-be89-229bbce73100
CODEX_THREAD_ID=01a0a117-ad1f-7891-be89-229bbce73100
CODEX_VERSION=0.154.0
COLORTERM=
DATE=date
DB=/home/bryan/Sync
DBB=/home/bryan/Sync/bin
DBH=/home/bryan/Sync/home
DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus
DIRSTACK=()
DISPLAY=localhost:10.0
EDITOR=nvim
EUID=1000
FAV_CLIP_FILE=/home/bryan/Sync/var/notes/Journal/favs.txt
FPP_DISABLE_SPLIT=1
FZF_DEFAULT_COMMAND='rg --files --hidden --smart-case'
FZF_DEFAULT_OPTS='--reverse --height 40% --border'
GEMINI_API_KEY=AIzaSyDY9OUOTFXvy6MD_Hx4_CeI7Qg7rSEPRWQ
GEM_HOME=/home/bryan/.gems
GH_PAGER=cat
GIT_PAGER=cat
GO111MODULE=on
GPG_TTY=/dev/pts/5
GREP=grep
GROUPS=()
HISTSIZE=100000
HOME=/home/bryan
HOSTNAME=athena
HOSTTYPE=x86_64
IFS=$' \t\n'
JJ_CONFIG=/home/bryan/.config/jj/config.toml
LANG=en_US.UTF-8
LC_ALL=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=RQ
LIBRARY_PATH=
LOGNAME=bryan
LS=ls
LSCOLORS=Gxfxcxdxbxegedabagacad
LS_COLORS='rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.jxl=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:'
LUA_CPATH='./?.so;/usr/local/lib/lua/5.1/?.so;/usr/lib/x86_64-linux-gnu/lua/5.1/?.so;/usr/lib/lua/5.1/?.so;/usr/local/lib/lua/5.1/loadall.so;/home/bryan/.luarocks/lib/lua/5.1/?.so'
LUA_PATH='/usr/local/share/lua/5.1/?.lua;./?.lua;/usr/local/share/lua/5.1/?/init.lua;/usr/local/lib/lua/5.1/?.lua;/usr/local/lib/lua/5.1/?/init.lua;/usr/share/lua/5.1/?.lua;/usr/share/lua/5.1/?/init.lua;/home/bryan/.luarocks/share/lua/5.1/?.lua;/home/bryan/.luarocks/share/lua/5.1/?/init.lua'
M=✉
MACHTYPE=x86_64-pc-linux-gnu
MAILPATH='/var/mail/bryan? ✉ ✉ ✉ NEW MAIL IN /var/mail/bryan!!! ✉ ✉ ✉'
MASTER_BRANCH=master
MATLABPATH=/home/bryan/.matlab
MCFLY_KEY_SCHEME=vim
MCFLY_LIGHT=FALSE
MOTD_SHOWN=pam
MOV=/mnt/hercules/plex/Movies
MY_UUID=30634818
NIX_PROFILES='/nix/var/nix/profiles/default /home/bryan/.nix-profile'
NIX_SSL_CERT_FILE=/etc/ssl/certs/ca-certificates.crt
NO_COLOR=1
NVM_BIN=/home/bryan/.config/nvm/versions/node/v22.14.0/bin
NVM_CD_FLAGS=-q
NVM_DIR=/home/bryan/.config/nvm
NVM_INC=/home/bryan/.config/nvm/versions/node/v22.14.0/include/node
OLDPWD=/home/bryan
OPTERR=1
OPTIND=1
OSTYPE=linux-gnu
PAGER=less
PATH=/home/bryan/.cargo/bin:/home/bryan/.luarocks/bin:/home/bryan/projects/github/LuaLS/lua-language-server/bin:/home/bryan/.nix-profile/bin:/home/bryan/go/bin:/usr/local/go/bin:/home/bryan/.gems/bin:/home/bryan/.tmp/bin:/home/bryan/.flamegraph:/home/bryan/.dynamic-colors/bin:/home/bryan/bin:/home/bryan/.local/bin:/opt/rust-bin-1.98.1/bin:/home/bryan/.poetry/bin:/home/bryan/.cargo/bin:/usr/local/bin:/sbin:/usr/sbin:/usr/share/safe-rm/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/snap/bin
PIPESTATUS=([0]="0")
PPID=1767901
PS4='+ '
PWD=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
PYENV_SHELL=zsh
PYENV_VIRTUALENV_DISABLE_PROMPT=1
PYENV_VIRTUALENV_INIT=1
PYENV_VIRTUALENV_VERBOSE_ACTIVATE=1
PYTHONBREAKPOINT=pudb.set_trace
PYTHONPATH=/home/bryan/.local/bin:/usr/local/lib/python:/usr/local/bin
QT_QPA_PLATFORMTHEME=qt5ct
RECENTLY_EDITED_FILES_LOG=/home/bryan/Sync/var/recently_edited_files.log
RFSERVER_HOSTNAME=bbugyi.ddns.net
RFSERVER_PORT=23401
RFSERVER_TOKEN='P+UDE9+ZCD]vrK8}pdP='
RIPGREP_CONFIG_PATH=/home/bryan/.config/rgrc
RUST_SRC_PATH=/home/bryan/Sync/var/projects/rust/src
SASE_ACTIVE_PROJECT_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/
SASE_CORE_BACKEND=rust
SASE_FEATURE_FLAGS='{"ace_refresh_tokens":true,"admin_center_flags":true,"agent_sudo_requests":false,"agents_unified_query":true,"monitor_continuation_records":true,"provider_drain":true,"queue_capacity_budget":true,"ref_sync_gesture":true,"refresh_panel":true,"typed_launch_units":true}'
SASE_FINALIZER_PLAN_DIGEST=c21e7df7416530911e2f8a3a140f9bac08a842ff4e9f2cc76c2adffbc1d98145
SASE_FINAL_TURN_NONCE=CZDINg5zD1Q1lQvdGqezvhN61s1ANtXUW4sF66-OBfE
SASE_GH_PRE_ALLOCATED=1
SASE_GH_WORKSPACE_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/
SASE_GH_WORKSPACE_NUM=19
SASE_INTERNAL_AGENT_NAME_BYPASS=1
SASE_LAUNCH_SCRATCH_KEY=gh_sase-org__sase-ws19-260914_140415
SASE_LINKED_REPOS_JSON='[{"auto_clone": false, "env_name": "CHEZMOI", "kind": "linked", "name": "chezmoi", "primary_dir": "/home/bryan/.local/share/chezmoi", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/chezmoi", "workspace_num": 19}, {"auto_clone": true, "env_name": "SASE_CORE", "kind": "linked", "name": "sase-core", "primary_dir": "/home/bryan/projects/github/sase-org/sase-core", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_GITHUB", "kind": "linked", "name": "sase-github", "primary_dir": "/home/bryan/projects/github/sase-org/sase-github", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-github", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_TELEGRAM", "kind": "linked", "name": "sase-telegram", "primary_dir": "/home/bryan/projects/github/sase-org/sase-telegram", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-telegram", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_NVIM", "kind": "linked", "name": "sase-nvim", "primary_dir": "/home/bryan/projects/github/sase-org/sase-nvim", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-nvim", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_RESEARCH_ARTIFACTS", "kind": "linked", "name": "sase-research-artifacts", "primary_dir": "/home/bryan/projects/github/sase-org/sase-research-artifacts", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-research-artifacts", "workspace_num": 19}, {"auto_clone": true, "env_name": "PLANS", "kind": "sidecar", "name": "plans", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/plans", "remote_url": "git@github.com:sase-org/sase--plans.git", "slug": "sase--plans", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans", "workspace_num": 19}, {"auto_clone": false, "env_name": "BEADS", "kind": "sidecar", "name": "beads", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/beads", "remote_url": "git@github.com:sase-org/sase--beads.git", "slug": "sase--beads", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/beads", "workspace_num": 19}, {"auto_clone": false, "env_name": "RESEARCH", "kind": "sidecar", "name": "research", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/research", "remote_url": "git@github.com:sase-org/sase--research.git", "slug": "sase--research", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research", "workspace_num": 19}]'
SASE_LINKED_REPO_BEADS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/beads
SASE_LINKED_REPO_BEADS_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/beads
SASE_LINKED_REPO_PLANS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans
SASE_LINKED_REPO_PLANS_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/plans
SASE_LINKED_REPO_RESEARCH_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research
SASE_LINKED_REPO_RESEARCH_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/research
SASE_LINKED_REPO_SASE_CORE_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core
SASE_LINKED_REPO_SASE_CORE_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase-core
SASE_MONITOR_DIAGNOSTICS_DIR=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914140853/diagnostics
SASE_MONITOR_ID=x7hc3eyqendt
SASE_PLAN=/home/bryan/.sase/plans/202609/finish_10w5_and_start_10w6.md
SASE_PROC_ID=x7hc3eyqendt
SASE_PROC_LOG_PATH=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914140853/live_reply.md
SASE_PROC_SESSION_ID=
SASE_SDD_BEADS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/beads
SASE_SDD_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans
SASE_SDD_PLANS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans
SASE_SDD_RESEARCH_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research
SASE_SIBLING_REPOS_JSON='[{"auto_clone": false, "env_name": "CHEZMOI", "kind": "linked", "name": "chezmoi", "primary_dir": "/home/bryan/.local/share/chezmoi", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/chezmoi", "workspace_num": 19}, {"auto_clone": true, "env_name": "SASE_CORE", "kind": "linked", "name": "sase-core", "primary_dir": "/home/bryan/projects/github/sase-org/sase-core", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_GITHUB", "kind": "linked", "name": "sase-github", "primary_dir": "/home/bryan/projects/github/sase-org/sase-github", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-github", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_TELEGRAM", "kind": "linked", "name": "sase-telegram", "primary_dir": "/home/bryan/projects/github/sase-org/sase-telegram", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-telegram", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_NVIM", "kind": "linked", "name": "sase-nvim", "primary_dir": "/home/bryan/projects/github/sase-org/sase-nvim", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-nvim", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_RESEARCH_ARTIFACTS", "kind": "linked", "name": "sase-research-artifacts", "primary_dir": "/home/bryan/projects/github/sase-org/sase-research-artifacts", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-research-artifacts", "workspace_num": 19}, {"auto_clone": true, "env_name": "PLANS", "kind": "sidecar", "name": "plans", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/plans", "remote_url": "git@github.com:sase-org/sase--plans.git", "slug": "sase--plans", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans", "workspace_num": 19}, {"auto_clone": false, "env_name": "BEADS", "kind": "sidecar", "name": "beads", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/beads", "remote_url": "git@github.com:sase-org/sase--beads.git", "slug": "sase--beads", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/beads", "workspace_num": 19}, {"auto_clone": false, "env_name": "RESEARCH", "kind": "sidecar", "name": "research", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/research", "remote_url": "git@github.com:sase-org/sase--research.git", "slug": "sase--research", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research", "workspace_num": 19}]'
SASE_SIBLING_REPO_BEADS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/beads
SASE_SIBLING_REPO_BEADS_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/beads
SASE_SIBLING_REPO_PLANS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans
SASE_SIBLING_REPO_PLANS_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/plans
SASE_SIBLING_REPO_RESEARCH_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research
SASE_SIBLING_REPO_RESEARCH_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/research
SASE_SIBLING_REPO_SASE_CORE_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core
SASE_SIBLING_REPO_SASE_CORE_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase-core
SASE_TMPDIR=/home/bryan/.cache/sase/tmp
SAVEHIST=100000
SED=sed
SHELL=/bin/zsh
SHELLCHECK_OPTS='-e SC1090 -e SC1091 -e SC1117 -e SC2001 -e SC2016 -e SC2046 -e SC2059 -e SC2129 -e SC2155 -e SC2162'
SHELLOPTS=braceexpand:hashall:interactive-comments
SHLVL=3
SHV_SHELL_HISTORY_ROOT=/home/bryan/Sync/var/logs/shell-history
SSH_AGENT_PID=13573
SSH_AUTH_SOCK=/tmp/ssh-bd1YBG80VDga/agent.13572
SSH_CLIENT='100.108.201.99 58349 34857'
SSH_CONNECTION='100.108.201.99 58349 100.87.31.114 34857'
SSH_TTY=/dev/pts/0
STARSHIP_SESSION_KEY=9980293922887929
STARSHIP_SHELL=zsh
TEMP=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_140415
TERM=tmux-256color
TERM_PROGRAM=tmux
TERM_PROGRAM_VERSION=3.5a
TMP=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_140415
TMPDIR=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_140415
TMUX=/home/bryan/Sync/home/tmp/tmux/tmux-1000/default,14716,0
TMUX_PANE=%5
TMUX_PLUGIN_MANAGER_PATH=/home/bryan/.config/tmux/plugins/
TMUX_TMPDIR=/home/bryan/tmp/tmux
TV=/mnt/hercules/plex/TV
UID=1000
USER=bryan
VISUAL=nvim
WORKON_HOME=/home/bryan/.virtualenvs
XDG_CONFIG_HOME=/home/bryan/.config
XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
XDG_RUNTIME_DIR=/run/user/1000
XDG_SESSION_CLASS=user
XDG_SESSION_ID=23
XDG_SESSION_TYPE=tty
ZIM_CONFIG_DIR=/home/bryan/.local/share/chezmoi/dot_config
ZIM_ZSHRC_DIR=/home/bryan/.local/share/chezmoi
_=0
__ETC_PROFILE_NIX_SOURCED=1
export=
o=/home/bryan/org
rust_version=1.98.1
snap_bin_path=/snap/bin
snap_xdg_path=/var/lib/snapd/desktop
_is_in_path () 
{ 
    local path_="$1";
    shift;
    local P="$1";
    shift;
    if [[ ":${path_}:" == *":${P}:"* ]]; then
        return 0;
    else
        return 1;
    fi
}
dedup_path () 
{ 
    local path_="$1";
    shift;
    local new_path=;
    for P in $(echo "${path_}" | tr ":" "\n");
    do
        if ! _is_in_path "${new_path}" "${P}"; then
            if [[ -n "${new_path}" ]]; then
                new_path="${new_path}":"${P}";
            else
                new_path="${P}";
            fi;
        fi;
    done;
    echo "${new_path}"
}
gawklibpath_append () 
{ 
    [ -z "$AWKLIBPATH" ] && AWKLIBPATH=`gawk 'BEGIN {print ENVIRON["AWKLIBPATH"]}'`;
    export AWKLIBPATH="$AWKLIBPATH:$*"
}
gawklibpath_default () 
{ 
    unset AWKLIBPATH;
    export AWKLIBPATH=`gawk 'BEGIN {print ENVIRON["AWKLIBPATH"]}'`
}
gawklibpath_prepend () 
{ 
    [ -z "$AWKLIBPATH" ] && AWKLIBPATH=`gawk 'BEGIN {print ENVIRON["AWKLIBPATH"]}'`;
    export AWKLIBPATH="$*:$AWKLIBPATH"
}
gawkpath_append () 
{ 
    [ -z "$AWKPATH" ] && AWKPATH=`gawk 'BEGIN {print ENVIRON["AWKPATH"]}'`;
    export AWKPATH="$AWKPATH:$*"
}
gawkpath_default () 
{ 
    unset AWKPATH;
    export AWKPATH=`gawk 'BEGIN {print ENVIRON["AWKPATH"]}'`
}
gawkpath_prepend () 
{ 
    [ -z "$AWKPATH" ] && AWKPATH=`gawk 'BEGIN {print ENVIRON["AWKPATH"]}'`;
    export AWKPATH="$*:$AWKPATH"
}
insert_path () 
{ 
    local path_="$1";
    shift;
    local P="$1";
    shift;
    if _is_in_path "${path_}" "${P}"; then
        local new_path=;
        for p in $(echo "${path_}" | tr ":" "\n");
        do
            if [[ "${p}" == "${P}" ]]; then
                continue;
            fi;
            if [[ -n "${new_path}" ]]; then
                new_path="${new_path}":"${p}";
            else
                new_path="${p}";
            fi;
        done;
        path_="${new_path}";
    fi;
    echo "${P}":"${path_}"
}
source_if_exists () 
{ 
    [[ -f "$1" ]] && source "$1"
}
sase_head=dd672fd6cbd3e5bcf89ae51ea12e77ce62f1228d
pin_before=3566872b4916123fedf100b7c5684c701085655c
core_head_before=3566872b4916123fedf100b7c5684c701085655c
[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/982c5f16d72d609a2f083777b3bced8f9c7923a2a4bc8570df1c9bdb8793d9d0/sase_core_rs-0.34.28-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 3ms
Prepared 1 package in 0.28ms
Uninstalled 1 package in 0.83ms
Installed 1 package in 9ms
 - sase-core-rs==0.34.26 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core_py)
 + sase-core-rs==0.34.28 (from file:///home/bryan/.sase/cache/sase-core-wheels/982c5f16d72d609a2f083777b3bced8f9c7923a2a4bc8570df1c9bdb8793d9d0/sase_core_rs-0.34.28-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
   Compiling proc-macro2 v1.0.106
   Compiling quote v1.0.45
   Compiling unicode-ident v1.0.24
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling version_check v0.9.5
   Compiling zerocopy v0.8.48
   Compiling memchr v2.8.0
   Compiling once_cell v1.21.4
   Compiling serde_core v1.0.228
   Compiling pin-project-lite v0.2.17
   Compiling zmij v1.0.21
   Compiling shlex v1.3.0
   Compiling smallvec v1.15.1
   Compiling hashbrown v0.17.0
   Compiling typenum v1.20.0
   Compiling futures-core v0.3.32
   Compiling futures-sink v0.3.32
   Compiling equivalent v1.0.2
   Compiling serde v1.0.228
   Compiling find-msvc-tools v0.1.9
   Compiling serde_json v1.0.149
   Compiling pkg-config v0.3.33
   Compiling autocfg v1.5.0
   Compiling regex-syntax v0.8.10
   Compiling vcpkg v0.2.15
   Compiling itoa v1.0.18
   Compiling getrandom v0.4.2
   Compiling parking_lot_core v0.9.12
   Compiling crossbeam-utils v0.8.21
   Compiling slab v0.4.12
   Compiling rustix v1.1.4
   Compiling bitflags v2.11.1
   Compiling futures-task v0.3.32
   Compiling futures-io v0.3.32
   Compiling bitflags v1.3.2
   Compiling linux-raw-sys v0.12.1
   Compiling bytes v1.11.1
   Compiling httparse v1.10.1
   Compiling scopeguard v1.2.0
   Compiling thiserror v1.0.69
   Compiling lazy_static v1.5.0
   Compiling sync_wrapper v1.0.2
   Compiling log v0.4.29
   Compiling unsafe-libyaml v0.2.11
   Compiling fallible-streaming-iterator v0.1.9
   Compiling fastrand v2.4.1
   Compiling tower-service v0.3.3
   Compiling tower-layer v0.3.3
   Compiling fallible-iterator v0.3.0
   Compiling ryu v1.0.23
   Compiling cpufeatures v0.2.17
   Compiling hex v0.4.3
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-width v0.2.2
   Compiling thread_local v1.1.9
   Compiling tracing-core v0.1.36
   Compiling lock_api v0.4.14
   Compiling sharded-slab v0.1.7
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling cc v1.2.61
   Compiling aho-corasick v1.1.4
   Compiling futures-channel v0.3.32
   Compiling num-traits v0.2.19
   Compiling fluent-uri v0.1.4
   Compiling indexmap v2.14.0
   Compiling getrandom v0.2.17
   Compiling errno v0.3.14
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling fs2 v0.4.3
   Compiling tracing-log v0.2.0
   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
   Compiling ppv-lite86 v0.2.21
   Compiling regex-automata v0.4.14
   Compiling libsqlite3-sys v0.30.1
   Compiling rand_core v0.6.4
   Compiling signal-hook-registry v1.4.8
   Compiling tempfile v3.27.0
   Compiling chrono v0.4.44
   Compiling digest v0.10.7
   Compiling hashbrown v0.14.5
   Compiling rand_chacha v0.3.1
   Compiling sha2 v0.10.9
   Compiling hashlink v0.9.1
   Compiling dashmap v6.1.0
   Compiling regex v1.12.3
   Compiling matchers v0.2.0
   Compiling rand v0.8.6
   Compiling syn v2.0.117
   Compiling serde_derive v1.0.228
   Compiling futures-macro v0.3.32
   Compiling tracing-attributes v0.1.31
   Compiling tokio-macros v2.7.0
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling tokio v1.52.2
   Compiling futures-util v0.3.32
   Compiling tracing v0.1.44
   Compiling tracing-subscriber v0.3.23
   Compiling futures v0.3.32
   Compiling tower v0.5.3
   Compiling tokio-util v0.7.18
   Compiling lsp-types v0.97.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.34.28 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_core)
   Compiling sase_xprompt_lsp v0.34.28 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core/crates/sase_xprompt_lsp)
    Finished `dev-update` profile [optimized] target(s) in 2m 05s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 97 packages in 181ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
Prepared 1 package in 418ms
Uninstalled 1 package in 3ms
Installed 1 package in 3ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
pin_after=3566872b4916123fedf100b7c5684c701085655c
core_head_after=3566872b4916123fedf100b7c5684c701085655c
sase_core_rs 0.34.28 exposes all 602 bindings required by /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
collected 48 items

tests/test_managed_tmp_reaper.py ......................................  [ 79%]
tests/test_check_sase_core_rs_bindings_tool.py ..........                [100%]

============================= slowest 20 durations =============================
2.06s setup    tests/test_managed_tmp_reaper.py::test_horizons_are_chosen_per_subdirectory
0.63s setup    tests/test_check_sase_core_rs_bindings_tool.py::test_scan_resolves_every_call_site_statically
0.17s call     tests/test_managed_tmp_reaper.py::test_every_literal_managed_tmpdir_bucket_has_a_horizon
0.01s call     tests/test_managed_tmp_reaper.py::test_horizons_are_chosen_per_subdirectory

(16 durations < 0.005s hidden.  Use -vv to show these durations.)
============================== 48 passed in 4.15s ==============================
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
✓ committed plans
✗ test (scoped)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: contract-set-only, core-identity-changed); 3857 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: contract-set-only, core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 14/14 workers
14 workers [41680 items]

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
........................................................................ [  5%]
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
........................................................................ [  8%]
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
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
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
........................................................................ [ 24%]
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
..........................................ssss.......................... [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 30%]
........................................................................ [ 31%]
................................................s....................... [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 31%]
........................................................................ [ 32%]
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
........................................................................ [ 36%]
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
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 44%]
....................................................................E... [ 44%]
FE...................................................................... [ 44%]
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
........................................................................ [ 48%]
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
.......s................................................................ [ 51%]
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
........................................................................ [ 56%]
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
........................................................................ [ 60%]
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
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
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
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
........................................................................ [ 70%]
.........s.............................................................. [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 71%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
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
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 76%]
........................................................................ [ 77%]
...............s........................................................ [ 77%]
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
........................................................................ [ 79%]
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
........................................................................ [ 83%]
........................................................................ [ 83%]
.........................s.............................................. [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 84%]
........................................................................ [ 85%]
........................................................................ [ 85%]
........................................................................ [ 85%]
......................................s................................. [ 85%]
........................................................................ [ 85%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
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
........................................................................ [ 88%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 89%]
........................................................................ [ 90%]
........................................................................ [ 90%]
........................................................................ [ 90%]
.........................s.........................ss................... [ 90%]
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
..................................................................       [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7fd8a0de4f60>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


==================================== ERRORS ====================================
_ ERROR at teardown of test_ctrl_space_action_is_gated_only_while_prompt_is_mounted _
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

ace_group = <sase.ace.testing.ace_page_group.AcePageGroup object at 0x7f471aefae40>

    @pytest_asyncio.fixture(loop_scope="module")
    async def page(ace_group: AcePageGroup) -> AsyncIterator[AcePage]:
>       async with ace_group.checkout() as checkout:
                   ^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/widgets/test_vim_normal_key_containment.py:62: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
../../../../../../share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py:221: in __aexit__
    await anext(self.gen)
src/sase/ace/testing/ace_page_group.py:154: in checkout
    await self._reset_shared_page(shared_page)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = <sase.ace.testing.ace_page_group.AcePageGroup object at 0x7f471aefae40>
page = <sase.ace.testing.ace_page.AcePage object at 0x7f471aefbb60>

    async def _reset_shared_page(self, page: AcePage) -> None:
        baseline = self._baseline
        if baseline is None:
            raise RuntimeError("AcePageGroup baseline is not available")
    
        app = page.app
        await _drain_app_work(app)
        await _close_extra_screens(page)
        _remove_prompt_surfaces(app)
        app._notifications.clear()
        _reset_navigation_modes(app)
        _restore_baseline_state(app, baseline)
        await app.recompose()
        _restore_focus(app, baseline)
        app._refresh_current_tab()
        await page.pause()
    
        if self._reset_hook is not None:
            result = self._reset_hook(page)
            if result is not None:
                await result
            await page.pause()
    
        after = _IsolationSnapshot.capture(
            page,
            track_notifications=self._notifications,
        )
        leaks = after.diff(baseline)
        if leaks:
            lines = [
                f"{name}: expected {expected!r}, got {actual!r}"
                for name, (actual, expected) in sorted(leaks.items())
            ]
>           raise AssertionError(
                "AcePageGroup isolation leak(s):\n"
                + "\n".join(f"- {line}" for line in lines)
            )
E           AssertionError: AcePageGroup isolation leak(s):
E           - focus: expected ('CommitsTimeline', 'stitches-timeline'), got None

src/sase/ace/testing/ace_page_group.py:202: AssertionError
------------------------------ Captured log call -------------------------------
ERROR    sase.ace.tui.app:app.py:364 Unhandled exception in sase ace
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/timer.py", line 189, in _tick
    await invoke(self._callback)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    return await _invoke(callback, *params)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    result = callback(*params[:parameter_count])
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/screen.py", line 1248, in _on_timer_update
    self._compositor_refresh()
    ~~~~~~~~~~~~~~~~~~~~~~~~^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/screen.py", line 1214, in _compositor_refresh
    update = self._compositor.render_update(
        screen_stack=app._background_screens
    )
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1113, in render_update
    return self.render_full_update(simplify=simplify)
           ~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1149, in render_full_update
    chops = self._render_chops(crop, lambda y: True)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1222, in _render_chops
    for region, clip, strips in renders:
                                ^^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1068, in _get_renders
    widget.render_lines(
    ~~~~~~~~~~~~~~~~~~~^
        _Region(
        ^^^^^^^^
    ...<4 lines>...
        )
        ^
    ),
    ^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/widgets/_text_area.py", line 1200, in render_lines
    theme.apply_css(self)
    ~~~~~~~~~~~~~~~^^^^^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_text_area_theme.py", line 107, in apply_css
    gutter_style = get_style("text-area--gutter")
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/widget.py", line 1166, in get_component_rich_style
    component_styles = self.get_component_styles(*names)
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/dom.py", line 616, in get_component_styles
    raise KeyError(f"No {name!r} key in COMPONENT_CLASSES")
KeyError: "No 'text-area--gutter' key in COMPONENT_CLASSES"
__ ERROR at teardown of test_other_main_screen_vim_hosts_contain_normal_space __
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python
  + Exception Group Traceback (most recent call last):
  |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/conftest.py", line 200, in pytest_runtest_teardown
  |     yield
  |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pluggy/_callers.py", line 139, in _multicall
  |     teardown.throw(exception)
  |     ~~~~~~~~~~~~~~^^^^^^^^^^^
  |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/capture.py", line 905, in pytest_runtest_teardown
  |     return (yield)
  |             ^^^^^
  |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pluggy/_callers.py", line 121, in _multicall
  |     res = hook_impl.function(*args)
  |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/runner.py", line 194, in pytest_runtest_teardown
  |     item.session._setupstate.teardown_exact(nextitem)
  |     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^
  |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/runner.py", line 568, in teardown_exact
  |     raise BaseExceptionGroup("errors during test teardown", exceptions[::-1])
  | ExceptionGroup: errors during test teardown (2 sub-exceptions)
  +-+---------------- 1 ----------------
    | Traceback (most recent call last):
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/runner.py", line 555, in teardown_exact
    |     fin()
    |     ~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py", line 1053, in finish
    |     raise exceptions[0]
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py", line 1042, in finish
    |     fin()
    |     ~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py", line 330, in finalizer
    |     runner.run(async_finalizer(), context=context)
    |     ~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/runners.py", line 128, in run
    |     return self._loop.run_until_complete(task)
    |            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/base_events.py", line 720, in run_until_complete
    |     return future.result()
    |            ~~~~~~~~~~~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py", line 322, in async_finalizer
    |     await gen_obj.__anext__()
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/ace/tui/widgets/test_vim_normal_key_containment.py", line 56, in ace_group
    |     async with AcePageGroup() as group:
    |                ~~~~~~~~~~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/testing/ace_page_group.py", line 132, in __aexit__
    |     await page.__aexit__(exc_type, exc_val, exc_tb)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/testing/ace_page.py", line 305, in __aexit__
    |     await stack.__aexit__(exc_type, exc_val, exc_tb)
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 768, in __aexit__
    |     raise exc
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 751, in __aexit__
    |     cb_suppress = await cb(*exc_details)
    |                   ^^^^^^^^^^^^^^^^^^^^^^
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 221, in __aexit__
    |     await anext(self.gen)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/app.py", line 2145, in run_test
    |     raise self._exception
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/timer.py", line 189, in _tick
    |     await invoke(self._callback)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_callback.py", line 96, in invoke
    |     return await _invoke(callback, *params)
    |            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_callback.py", line 56, in _invoke
    |     result = callback(*params[:parameter_count])
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/screen.py", line 1248, in _on_timer_update
    |     self._compositor_refresh()
    |     ~~~~~~~~~~~~~~~~~~~~~~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/screen.py", line 1214, in _compositor_refresh
    |     update = self._compositor.render_update(
    |         screen_stack=app._background_screens
    |     )
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1113, in render_update
    |     return self.render_full_update(simplify=simplify)
    |            ~~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1149, in render_full_update
    |     chops = self._render_chops(crop, lambda y: True)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1222, in _render_chops
    |     for region, clip, strips in renders:
    |                                 ^^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_compositor.py", line 1068, in _get_renders
    |     widget.render_lines(
    |     ~~~~~~~~~~~~~~~~~~~^
    |         _Region(
    |         ^^^^^^^^
    |     ...<4 lines>...
    |         )
    |         ^
    |     ),
    |     ^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/widgets/_text_area.py", line 1200, in render_lines
    |     theme.apply_css(self)
    |     ~~~~~~~~~~~~~~~^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_text_area_theme.py", line 107, in apply_css
    |     gutter_style = get_style("text-area--gutter")
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/widget.py", line 1166, in get_component_rich_style
    |     component_styles = self.get_component_styles(*names)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/dom.py", line 616, in get_component_styles
    |     raise KeyError(f"No {name!r} key in COMPONENT_CLASSES")
    | KeyError: "No 'text-area--gutter' key in COMPONENT_CLASSES"
    +---------------- 2 ----------------
    | Traceback (most recent call last):
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/runner.py", line 555, in teardown_exact
    |     fin()
    |     ~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py", line 1053, in finish
    |     raise exceptions[0]
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py", line 1042, in finish
    |     fin()
    |     ~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py", line 330, in finalizer
    |     runner.run(async_finalizer(), context=context)
    |     ~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/runners.py", line 128, in run
    |     return self._loop.run_until_complete(task)
    |            ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~^^^^^^
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/asyncio/base_events.py", line 720, in run_until_complete
    |     return future.result()
    |            ~~~~~~~~~~~~~^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/pytest_asyncio/plugin.py", line 322, in async_finalizer
    |     await gen_obj.__anext__()
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/ace/tui/widgets/test_vim_normal_key_containment.py", line 62, in page
    |     async with ace_group.checkout() as checkout:
    |                ~~~~~~~~~~~~~~~~~~^^
    |   File "/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/contextlib.py", line 221, in __aexit__
    |     await anext(self.gen)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/testing/ace_page_group.py", line 154, in checkout
    |     await self._reset_shared_page(shared_page)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/testing/ace_page_group.py", line 181, in _reset_shared_page
    |     await app.recompose()
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/app.py", line 3499, in recompose
    |     await self.screen.mount_all(compose(self))
    |           ~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/widget.py", line 1516, in mount_all
    |     await_mount = self.mount(*widgets, before=before, after=after)
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/widget.py", line 1458, in mount
    |     mounted = self.app._register(
    |         parent, *widgets, before=insert_before, after=insert_after
    |     )
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/app.py", line 3594, in _register
    |     self._register_child(parent, widget, before, after)
    |     ~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/app.py", line 3540, in _register_child
    |     parent._nodes._append(child)
    |     ~~~~~~~~~~~~~~~~~~~~~^^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_node_list.py", line 129, in _append
    |     self._ensure_unique_id(widget_id)
    |     ~~~~~~~~~~~~~~~~~~~~~~^^^^^^^^^^^
    |   File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/textual/_node_list.py", line 158, in _ensure_unique_id
    |     raise DuplicateIds(
    |     ...<2 lines>...
    |     )
    | textual._node_list.DuplicateIds: Tried to insert a widget with ID 'ace-header', but a widget already exists with that ID (UsageHeader(id='ace-header')); ensure all child widgets have a unique ID.
    +------------------------------------
--------------------------- Captured stderr teardown ---------------------------
╭───────────────────── Traceback (most recent call last) ──────────────────────╮
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/pyt │
│ hon3.14/site-packages/textual/widgets/_text_area.py:1200 in render_lines     │
│                                                                              │
│   1197 │   def render_lines(self, crop: Region) -> list[Strip]:              │
│   1198 │   │   theme = self._theme                                           │
│   1199 │   │   if theme:                                                     │
│ ❱ 1200 │   │   │   theme.apply_css(self)                                     │
│   1201 │   │   return super().render_lines(crop)                             │
│   1202 │                                                                     │
│   1203 │   def render_line(self, y: int) -> Strip:                           │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │  crop = Region(x=0, y=0, width=116, height=1)                            │ │
│ │  self = PromptTextArea(                                                  │ │
│ │         │   id='prompt-input-g0-p0',                                     │ │
│ │         │   classes='active prompt-input -vim-normal -read-only solo'    │ │
│ │         )                                                                │ │
│ │ theme = TextAreaTheme(                                                   │ │
│ │         │   name='sase-jinja-prompt',                                    │ │
│ │         │   base_style=Style(                                            │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#dfdfdf',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=223,                                         │ │
│ │         │   │   │   │   green=223,                                       │ │
│ │         │   │   │   │   blue=223                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#100f0f',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=16, green=15, blue=15)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   gutter_style=Style(                                          │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#6f6d69',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=111,                                         │ │
│ │         │   │   │   │   green=109,                                       │ │
│ │         │   │   │   │   blue=105                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#100f0f',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=16, green=15, blue=15)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   cursor_style=Style(                                          │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#100f0f',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=16, green=15, blue=15)      │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#d0a215',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=208,                                         │ │
│ │         │   │   │   │   green=162,                                       │ │
│ │         │   │   │   │   blue=21                                          │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bold=True                                                │ │
│ │         │   ),                                                           │ │
│ │         │   cursor_line_style=Style(                                     │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#e1e0e0',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=225,                                         │ │
│ │         │   │   │   │   green=224,                                       │ │
│ │         │   │   │   │   blue=224                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#191818',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=25, green=24, blue=24)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   cursor_line_gutter_style=Style(                              │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#a3a099',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=163,                                         │ │
│ │         │   │   │   │   green=160,                                       │ │
│ │         │   │   │   │   blue=153                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#191818',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=25, green=24, blue=24)      │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bold=True                                                │ │
│ │         │   ),                                                           │ │
│ │         │   bracket_matching_style=Style(                                │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#e9e9e8',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=233,                                         │ │
│ │         │   │   │   │   green=233,                                       │ │
│ │         │   │   │   │   blue=232                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#575652',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=87, green=86, blue=82)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   selection_style=Style(                                       │ │
│ │         │   │   color=Color(                                             │ │
│ │         │   │   │   '#e4e4e3',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(                                │ │
│ │         │   │   │   │   red=228,                                         │ │
│ │         │   │   │   │   green=228,                                       │ │
│ │         │   │   │   │   blue=227                                         │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   bgcolor=Color(                                           │ │
│ │         │   │   │   '#31302e',                                           │ │
│ │         │   │   │   ColorType.TRUECOLOR,                                 │ │
│ │         │   │   │   triplet=ColorTriplet(red=49, green=48, blue=46)      │ │
│ │         │   │   )                                                        │ │
│ │         │   ),                                                           │ │
│ │         │   syntax_styles={                                              │ │
│ │         │   │   'string': Style(                                         │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#ce9178',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=206,                                     │ │
│ │         │   │   │   │   │   green=145,                                   │ │
│ │         │   │   │   │   │   blue=120                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'string.documentation': Style(                           │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#ce9178',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=206,                                     │ │
│ │         │   │   │   │   │   green=145,                                   │ │
│ │         │   │   │   │   │   blue=120                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'comment': Style(                                        │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#6a9955',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=106,                                     │ │
│ │         │   │   │   │   │   green=153,                                   │ │
│ │         │   │   │   │   │   blue=85                                      │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'heading.marker': Style(                                 │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#6e7681',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=110,                                     │ │
│ │         │   │   │   │   │   green=118,                                   │ │
│ │         │   │   │   │   │   blue=129                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword': Style(                                        │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#c586c0',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=197,                                     │ │
│ │         │   │   │   │   │   green=134,                                   │ │
│ │         │   │   │   │   │   blue=192                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'operator': Style(                                       │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#cccccc',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=204,                                     │ │
│ │         │   │   │   │   │   green=204,                                   │ │
│ │         │   │   │   │   │   blue=204                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'conditional': Style(                                    │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword.function': Style(                               │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword.return': Style(                                 │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   'keyword.operator': Style(                               │ │
│ │         │   │   │   color=Color(                                         │ │
│ │         │   │   │   │   '#569cd6',                                       │ │
│ │         │   │   │   │   ColorType.TRUECOLOR,                             │ │
│ │         │   │   │   │   triplet=ColorTriplet(                            │ │
│ │         │   │   │   │   │   red=86,                                      │ │
│ │         │   │   │   │   │   green=156,                                   │ │
│ │         │   │   │   │   │   blue=214                                     │ │
│ │         │   │   │   │   )                                                │ │
│ │         │   │   │   )                                                    │ │
│ │         │   │   ),                                                       │ │
│ │         │   │   ... +81                                                  │ │
│ │         │   },                                                           │ │
│ │         │   _theme_configured_attributes={                               │ │
│ │         │   │   'name',                                                  │ │
│ │         │   │   '_theme_configured_attributes',                          │ │
│ │         │   │   'syntax_styles'                                          │ │
│ │         │   }                                                            │ │
│ │         )                                                                │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/pyt │
│ hon3.14/site-packages/textual/_text_area_theme.py:107 in apply_css           │
│                                                                              │
│   104 │   │   assert self.base_style.bgcolor is not None                     │
│   105 │   │                                                                  │
│   106 │   │   if not configured("gutter_style"):                             │
│ ❱ 107 │   │   │   gutter_style = get_style("text-area--gutter")              │
│   108 │   │   │   if gutter_style:                                           │
│   109 │   │   │   │   self.gutter_style = gutter_style                       │
│   110 │   │   │   else:                                                      │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │  app_theme = Theme(                                                      │ │
│ │              │   name='flexoki',                                         │ │
│ │              │   primary='#205EA6',                                      │ │
│ │              │   secondary='#24837B',                                    │ │
│ │              │   warning='#AD8301',                                      │ │
│ │              │   error='#AF3029',                                        │ │
│ │              │   success='#66800B',                                      │ │
│ │              │   accent='#9B76C8',                                       │ │
│ │              │   foreground='#FFFCF0',                                   │ │
│ │              │   background='#100F0F',                                   │ │
│ │              │   surface='#1C1B1A',                                      │ │
│ │              │   panel='#282726',                                        │ │
│ │              │   boost=None,                                             │ │
│ │              │   dark=True,                                              │ │
│ │              │   luminosity_spread=0.15,                                 │ │
│ │              │   text_alpha=0.95,                                        │ │
│ │              │   variables={                                             │ │
│ │              │   │   'input-cursor-foreground': '#5E409D',               │ │
│ │              │   │   'input-cursor-background': '#FFFCF0',               │ │
│ │              │   │   'input-selection-background': '#6F6E69 35%',        │ │
│ │              │   │   'button-color-foreground': '#FFFCF0'                │ │
│ │              │   }                                                       │ │
│ │              )                                                           │ │
│ │ configured = <built-in method __contains__ of set object at              │ │
│ │              0x7f46eb47eea0>                                             │ │
│ │  get_style = <bound method Widget.get_component_rich_style of            │ │
│ │              PromptTextArea(id='prompt-input-g0-p0', classes='active     │ │
│ │              prompt-input -vim-normal -read-only solo')>                 │ │
│ │       self = TextAreaTheme(                                              │ │
│ │              │   name='sase-jinja-prompt',                               │ │
│ │              │   base_style=Style(                                       │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#dfdfdf',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=223,                                    │ │
│ │              │   │   │   │   green=223,                                  │ │
│ │              │   │   │   │   blue=223                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#100f0f',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=16,                                     │ │
│ │              │   │   │   │   green=15,                                   │ │
│ │              │   │   │   │   blue=15                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   gutter_style=Style(                                     │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#6f6d69',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=111,                                    │ │
│ │              │   │   │   │   green=109,                                  │ │
│ │              │   │   │   │   blue=105                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#100f0f',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=16,                                     │ │
│ │              │   │   │   │   green=15,                                   │ │
│ │              │   │   │   │   blue=15                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   cursor_style=Style(                                     │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#100f0f',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=16,                                     │ │
│ │              │   │   │   │   green=15,                                   │ │
│ │              │   │   │   │   blue=15                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#d0a215',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=208,                                    │ │
│ │              │   │   │   │   green=162,                                  │ │
│ │              │   │   │   │   blue=21                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bold=True                                           │ │
│ │              │   ),                                                      │ │
│ │              │   cursor_line_style=Style(                                │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#e1e0e0',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=225,                                    │ │
│ │              │   │   │   │   green=224,                                  │ │
│ │              │   │   │   │   blue=224                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#191818',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=25,                                     │ │
│ │              │   │   │   │   green=24,                                   │ │
│ │              │   │   │   │   blue=24                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   cursor_line_gutter_style=Style(                         │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#a3a099',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=163,                                    │ │
│ │              │   │   │   │   green=160,                                  │ │
│ │              │   │   │   │   blue=153                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#191818',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=25,                                     │ │
│ │              │   │   │   │   green=24,                                   │ │
│ │              │   │   │   │   blue=24                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bold=True                                           │ │
│ │              │   ),                                                      │ │
│ │              │   bracket_matching_style=Style(                           │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#e9e9e8',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=233,                                    │ │
│ │              │   │   │   │   green=233,                                  │ │
│ │              │   │   │   │   blue=232                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#575652',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=87,                                     │ │
│ │              │   │   │   │   green=86,                                   │ │
│ │              │   │   │   │   blue=82                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   selection_style=Style(                                  │ │
│ │              │   │   color=Color(                                        │ │
│ │              │   │   │   '#e4e4e3',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=228,                                    │ │
│ │              │   │   │   │   green=228,                                  │ │
│ │              │   │   │   │   blue=227                                    │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   bgcolor=Color(                                      │ │
│ │              │   │   │   '#31302e',                                      │ │
│ │              │   │   │   ColorType.TRUECOLOR,                            │ │
│ │              │   │   │   triplet=ColorTriplet(                           │ │
│ │              │   │   │   │   red=49,                                     │ │
│ │              │   │   │   │   green=48,                                   │ │
│ │              │   │   │   │   blue=46                                     │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   )                                                   │ │
│ │              │   ),                                                      │ │
│ │              │   syntax_styles={                                         │ │
│ │              │   │   'string': Style(                                    │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#ce9178',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=206,                                │ │
│ │              │   │   │   │   │   green=145,                              │ │
│ │              │   │   │   │   │   blue=120                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'string.documentation': Style(                      │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#ce9178',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=206,                                │ │
│ │              │   │   │   │   │   green=145,                              │ │
│ │              │   │   │   │   │   blue=120                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'comment': Style(                                   │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#6a9955',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=106,                                │ │
│ │              │   │   │   │   │   green=153,                              │ │
│ │              │   │   │   │   │   blue=85                                 │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'heading.marker': Style(                            │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#6e7681',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=110,                                │ │
│ │              │   │   │   │   │   green=118,                              │ │
│ │              │   │   │   │   │   blue=129                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword': Style(                                   │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#c586c0',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=197,                                │ │
│ │              │   │   │   │   │   green=134,                              │ │
│ │              │   │   │   │   │   blue=192                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'operator': Style(                                  │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#cccccc',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=204,                                │ │
│ │              │   │   │   │   │   green=204,                              │ │
│ │              │   │   │   │   │   blue=204                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'conditional': Style(                               │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword.function': Style(                          │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword.return': Style(                            │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   'keyword.operator': Style(                          │ │
│ │              │   │   │   color=Color(                                    │ │
│ │              │   │   │   │   '#569cd6',                                  │ │
│ │              │   │   │   │   ColorType.TRUECOLOR,                        │ │
│ │              │   │   │   │   triplet=ColorTriplet(                       │ │
│ │              │   │   │   │   │   red=86,                                 │ │
│ │              │   │   │   │   │   green=156,                              │ │
│ │              │   │   │   │   │   blue=214                                │ │
│ │              │   │   │   │   )                                           │ │
│ │              │   │   │   )                                               │ │
│ │              │   │   ),                                                  │ │
│ │              │   │   ... +81                                             │ │
│ │              │   },                                                      │ │
│ │              │   _theme_configured_attributes={                          │ │
│ │              │   │   'name',                                             │ │
│ │              │   │   '_theme_configured_attributes',                     │ │
│ │              │   │   'syntax_styles'                                     │ │
│ │              │   }                                                       │ │
│ │              )                                                           │ │
│ │  text_area = PromptTextArea(                                             │ │
│ │              │   id='prompt-input-g0-p0',                                │ │
│ │              │   classes='active prompt-input -vim-normal -read-only     │ │
│ │              solo'                                                       │ │
│ │              )                                                           │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/pyt │
│ hon3.14/site-packages/textual/widget.py:1166 in get_component_rich_style     │
│                                                                              │
│   1163 │   │                                                                 │
│   1164 │   │   if names not in self._rich_style_cache:                       │
│   1165 │   │   │   if default is None:                                       │
│ ❱ 1166 │   │   │   │   component_styles = self.get_component_styles(*names)  │
│   1167 │   │   │   else:                                                     │
│   1168 │   │   │   │   try:                                                  │
│   1169 │   │   │   │   │   component_styles = self.get_component_styles(*nam │
│                                                                              │
│ ╭──────────────────────────────── locals ─────────────────────────────────╮  │
│ │ default = None                                                          │  │
│ │   names = ('text-area--gutter',)                                        │  │
│ │ partial = False                                                         │  │
│ │    self = PromptTextArea(                                               │  │
│ │           │   id='prompt-input-g0-p0',                                  │  │
│ │           │   classes='active prompt-input -vim-normal -read-only solo' │  │
│ │           )                                                             │  │
│ ╰─────────────────────────────────────────────────────────────────────────╯  │
│                                                                              │
│ /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/pyt │
│ hon3.14/site-packages/textual/dom.py:616 in get_component_styles             │
│                                                                              │
│    613 │   │                                                                 │
│    614 │   │   for name in names:                                            │
│    615 │   │   │   if name not in self._component_styles:                    │
│ ❱  616 │   │   │   │   raise KeyError(f"No {name!r} key in COMPONENT_CLASSES │
│    617 │   │   │   component_styles = self._component_styles[name]           │
│    618 │   │   │   assert component_styles.node is not None                  │
│    619 │   │   │   styles._update_node(component_styles.node)                │
│                                                                              │
│ ╭───────────────────────────────── locals ─────────────────────────────────╮ │
│ │   name = 'text-area--gutter'                                             │ │
│ │  names = ('text-area--gutter',)                                          │ │
│ │   self = PromptTextArea(                                                 │ │
│ │          │   id='prompt-input-g0-p0',                                    │ │
│ │          │   classes='active prompt-input -vim-normal -read-only solo'   │ │
│ │          )                                                               │ │
│ │ styles = RenderStyles(                                                   │ │
│ │          │   PromptTextArea(                                             │ │
│ │          │   │   id='prompt-input-g0-p0',                                │ │
│ │          │   │   classes='active prompt-input -vim-normal -read-only     │ │
│ │          solo'                                                           │ │
│ │          │   )                                                           │ │
│ │          )                                                               │ │
│ ╰──────────────────────────────────────────────────────────────────────────╯ │
╰──────────────────────────────────────────────────────────────────────────────╯
KeyError: "No 'text-area--gutter' key in COMPONENT_CLASSES"
=================================== FAILURES ===================================
____________ test_other_main_screen_vim_hosts_contain_normal_space _____________
[gw4] linux -- Python 3.14.7 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/python

page = <sase.ace.testing.ace_page.AcePage object at 0x7f471aefbb60>

    async def test_other_main_screen_vim_hosts_contain_normal_space(page: AcePage) -> None:
        with _patch_config():
            await page.press(page.artifacts_digit("stitches"))
            await page.expect_state("artifacts_subtab", "stitches")
>           pane = page.query_one_widget("#artifacts-stitches-pane", CommitsPane)
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

tests/ace/tui/widgets/test_vim_normal_key_containment.py:251: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
src/sase/ace/testing/ace_page.py:381: in query_one_widget
    return self._app.query_one(selector, widget_type)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

self = AceApp(title='sase ace (v0.17.1)', classes={'-dark-mode'}, pseudo_classes={'focus', 'dark'})
selector = '#artifacts-stitches-pane'
expect_type = <class 'sase.ace.tui.widgets.artifacts.commits.CommitsPane'>

    def query_one(
        self,
        selector: str | type[QueryType],
        expect_type: type[QueryType] | None = None,
    ) -> QueryType | Widget:
        """Get a widget from this widget's children that matches a selector or widget type.
    
        Args:
            selector: A selector or widget type.
            expect_type: Require the object be of the supplied type, or None for any type.
    
        Raises:
            WrongType: If the wrong type was found.
            NoMatches: If no node matches the query.
    
        Returns:
            A widget matching the selector.
        """
        _rich_traceback_omit = True
    
        base_node = self._get_dom_base()
    
        if isinstance(selector, str):
            query_selector = selector
        else:
            query_selector = selector.__name__
    
        if is_id_selector(query_selector):
            cache_key = (base_node._nodes._updates, query_selector, expect_type)
            cached_result = base_node._query_one_cache.get(cache_key)
            if cached_result is not None:
                return cached_result
            if (
                node := walk_breadth_search_id(
                    base_node, query_selector[1:], with_root=False
                )
            ) is not None:
                if expect_type is not None and not isinstance(node, expect_type):
                    raise WrongType(
                        f"Node matching {query_selector!r} is the wrong type; expected type {expect_type.__name__!r}, found {node}"
                    )
                base_node._query_one_cache[cache_key] = node
                return node
>           raise NoMatches(f"No nodes match {query_selector!r} on {base_node!r}")
E           textual.css.query.NoMatches: No nodes match '#artifacts-stitches-pane' on Screen(id='_default')

.venv/lib/python3.14/site-packages/textual/dom.py:1503: NoMatches
=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: 14 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py::test_tab_completes_bead_plus_to_plus_one
tests/completion/test_zsh_smoke.py::test_dynamic_slot_fetches_fixture_candidates_and_caches
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask #zz-"ask #zzz-fixture-xprompt"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask %mo-"ask %model"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask @file:e-"ask @file:explicit:abc123"]
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=1872041) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=1872072) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=1872044) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
============================= slowest 20 durations =============================
66.40s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
63.98s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
46.80s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
39.78s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
35.82s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
26.17s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
23.92s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
18.93s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_update_dev_preview_and_restart
18.65s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_managed_confirm_closes_admin_center
18.64s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
16.78s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_core_only_success_restarts_once_and_receipts
16.78s call     tests/ace/tui/test_plugins_browser_pane_install.py::test_plugins_pane_install_marked_set_takes_batch_path
16.75s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_confirm_executes_and_restarts
16.59s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_loads_receipt_on_plan_worker
16.52s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_opens_preview_modal
16.39s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
15.96s call     tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_ctrl_space_action_is_gated_only_while_prompt_is_mounted
15.53s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
12.03s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
11.77s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
=========================== short test summary info ============================
FAILED tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_other_main_screen_vim_hosts_contain_normal_space
ERROR tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_ctrl_space_action_is_gated_only_while_prompt_is_mounted
ERROR tests/ace/tui/widgets/test_vim_normal_key_containment.py::test_other_main_screen_vim_hosts_contain_normal_space
= 1 failed, 41666 passed, 14 skipped, 81 warnings, 2 errors in 493.50s (0:08:13) =
error: recipe `test-scoped` failed on line 455 with exit code 1
error: recipe `check` failed on line 665 with exit code 1
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
✓ committed plans
✗ test cost
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-cost                │
└───────────────────────────────────────────────────────┘

---------- Running pytest cost attribution lane... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
configfile: pyproject.toml
testpaths: tests
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 13/13 workers
13 workers [41680 items]

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
........................................................................ [  5%]
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
........................................................................ [  8%]
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
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
........................................................................ [ 15%]
.............s.......................................................... [ 15%]
........................................................................ [ 15%]
........................................................................ [ 16%]
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
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 19%]
........................................................................ [ 20%]
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
........................................................................ [ 24%]
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
........................................................................ [ 30%]
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
........................................................................ [ 32%]
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
........................................................................ [ 36%]
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
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 42%]
......................................................................s. [ 42%]
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
........................................................................ [ 48%]
...............................................s.s......s....s.......... [ 48%]
........................................................................ [ 48%]
........................................................................ [ 48%]
....s...........................................................s....... [ 48%]
s....................................................................... [ 48%]
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
........................................................................ [ 56%]
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
........................................................................ [ 60%]
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
..........................................s............................. [ 64%]
........................................................................ [ 64%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
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
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 68%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
........................................................................ [ 69%]
.............................................s.......................... [ 69%]
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
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
........................................................................ [ 72%]
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
........................................................................ [ 76%]
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
........................................................................ [ 79%]
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
.................................................s...................... [ 81%]
........................................................................ [ 81%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 82%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
.s...................................................................... [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
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
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
........................................................................ [ 86%]
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
........................................................................ [ 88%]
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
................................................................         [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: 13 warnings
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=2217881) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_retry_branch_snapshots_failed_attempt changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/axe/test_run_agent_exec_attempts_integration.py::test_fallback_branch_snapshots_with_primary_model_marker changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/completion/test_zsh_smoke.py::test_tab_completes_bead_plus_to_plus_one
tests/completion/test_zsh_smoke.py::test_dynamic_slot_fetches_fixture_candidates_and_caches
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask #zz-"ask #zzz-fixture-xprompt"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask %mo-"ask %model"]
tests/completion/test_zsh_smoke.py::test_run_prompt_completes_embedded_markers_in_spaced_prompt[sase run "ask @file:e-"ask @file:explicit:abc123"]
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=2217891) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_does_not_double_prepend_on_repeated_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorContinuation::test_prepends_nudge_on_zero_wait_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorNoNudge::test_no_nudge_leaves_prompt_untouched changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorCodexDefaults::test_codex_transient_default_retries_with_preserved_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry.py::TestHandleWorkflowErrorPostPhaseTransition::test_retry_fires_for_coder_after_plan_approval changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_transient_429_not_a_usage_limit_match_still_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_to_different_non_disabled_provider changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_fallback_allowed_when_fallback_provider_carries_soft_disable changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_usage_limits.py::TestHandleWorkflowErrorUsageLimitPrecedence::test_known_codex_attempt_does_not_scan_quoted_claude_limit_prose changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_preserve_workspace_skips_prepare_on_fallback changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_exec_retry_workspace.py::TestHandleWorkflowErrorPreserveWorkspace::test_default_preserve_workspace_false_still_calls_prepare changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_failed_fork_admission.py::TestFailedForkParentAdmission::test_runner_admits_and_claims_real_workspace_for_failed_fork_parent changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info0-0-None] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20]
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_runner_slot_only_deferred_wait_gates_then_claims_workspace[wait_info1-None-20] changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_deferred_wait_gates_before_claim_and_prepares_claimed_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_incomplete_clan_fork_expands_after_wait_before_slot_and_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_combined_wait_runs_dependencies_then_gate_then_claim changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_flow.py::TestDeferredWorkspaceFlow::test_home_mode_deferred_wait_keeps_directory_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_repeat_stop_exits_before_workspace_claim_and_run_loop changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_deferred_workspace_without_extracted_wait_still_claims_real_workspace changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_claim_failure_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_bead_environment_mismatch_writes_error_and_skips_model_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_deferred_workspace_outcomes.py::TestDeferredWorkspaceOutcomes::test_launch_without_bead_never_invokes_claim_helper changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_when_config_is_none changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_non_retryable_error_raises_immediately changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_on_retryable_error changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_written_during_wait changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_retry_state_deleted_on_completion changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_fallback_model_tried_after_max_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_was_killed_during_wait_aborts_retry changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_done_json_includes_retry_metadata changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_no_retry_metadata_when_no_retries changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_retry_loop.py::TestRetryLoop::test_cross_provider_retry_uses_fallback_config changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_agent_is_admitted_before_workspace_preparation changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_admitted_root_is_counted_when_workspace_preparation_fails changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_no_wait_runner_records_run_started_at_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_persists_sdd_base_sha_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_populates_multi_agent_prompt_file_from_env changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_error_after_slot_admission_records_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_linked_repo_prep_failure_stops_before_execution changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_killed_while_waiting_does_not_record_run_started_at changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_runner_passes_recorded_run_started_at_to_runtime_formatter changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_system_exit_from_execution_writes_failure_marker_and_notifies changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_axe_run_agent_runner_started_at.py::TestRunStartedAtRecording::test_home_mode_running_marker_cleanup_updates_artifact_index changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_notification_modal_tab_order.py::test_on_mount_highlights_first_visible_row_when_initial_is_hidden
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/modals/notification_modal_snooze_status.py:136: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    self._snooze_status_timer = None
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_caller_named_args
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_explicit_named_args_override_caller
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_flatten_preserves_wrapper_model_override
tests/test_xprompt_processor_workflow_execute.py::test_execute_workflow_passes_inherited_vcs_tag_without_context_leak
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:474: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    flattened = _flatten_anonymous_workflow(workflow, project=project)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_returns_workflow_for_pure_multistep
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:114: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_xprompt_and_workflow
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#batch_split' is deprecated; use '#!batch_split' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_slow_path_with_args
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/xprompt/workflow_runner.py:297: UserWarning: Standalone workflow '#deploy' is deprecated; use '#!deploy' instead.
    standalone = _find_standalone_workflow_ref(prompt_text, prompts)

tests/test_xprompt_processor_workflow_flatten.py::test_flatten_anonymous_workflow_preserves_wrapper_model_directive
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/test_xprompt_processor_workflow_flatten.py:421: UserWarning: Standalone workflow '#split' is deprecated; use '#!split' instead.
    result = _flatten_anonymous_workflow(workflow)

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=2217950) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 26 poisoning change(s) across 26 test(s); 58991 warming mutation(s) filtered; 623 cooling mutation(s) filtered; 2450 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.pytest_cache/sase-global-leaks.json -
---------------- sase global leak detector blocking gate failed ----------------
============================= slowest 20 durations =============================
64.01s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
42.52s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
40.87s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
39.09s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
35.09s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
33.75s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
26.72s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
19.26s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
18.33s call     tests/ace/tui/test_plugins_browser_pane_marks.py::test_plugin_mark_survives_scope_switch_and_is_consumed_by_install
16.91s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_noop_closes_without_restart
16.67s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_confirm_executes_and_restarts
16.63s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_cancel_keeps_admin_center_open
15.70s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
14.77s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
13.21s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
12.58s call     tests/ace/tui/test_residual_freeze_soak.py::test_lowered_threshold_soak_keeps_fixed_paths_responsive
11.19s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
10.70s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
10.42s call     tests/test_markdown_print_width.py::test_no_function_parameter_defaults_to_the_width
9.22s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
========= 41667 passed, 14 skipped, 80 warnings in 1329.53s (0:22:09) ==========
error: recipe `test-cost` failed on line 422 with exit code 1
error: recipe `check-full` failed on line 686 with exit code 1

