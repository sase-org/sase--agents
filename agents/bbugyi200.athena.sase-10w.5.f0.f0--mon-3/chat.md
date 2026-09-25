# Chat History - ace-run (sase-10w.5.f0.f0--mon-3)

- **TIMESTAMP:** 2026-09-14 18:38:31 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-10w.5.f0.f0--mon-3

## Prompt

sase monitor start --command 'bash -lc set -euo pipefail\nCORE_DIR="$(sase repo open sase-core -r "Use audited linked core checkout for 10w.5 full verification after budget recalibration")"\nPIN_BEFORE="$(cat sase-core-revision.txt)"\nCORE_HEAD_BEFORE="$(git -C "$CORE_DIR" rev-parse HEAD)"\necho "sase_head=$(git rev-parse HEAD)"\necho "sase_origin_master=$(git rev-parse origin/master)"\necho "pin_before=$PIN_BEFORE"\necho "core_head_before=$CORE_HEAD_BEFORE"\ngit status --short\ntest "$PIN_BEFORE" = "$CORE_HEAD_BEFORE"\nexport SASE_CORE_DIR="$CORE_DIR"\nexport GH_REPO=sase-org/sase\njust install\nPIN_AFTER="$(cat sase-core-revision.txt)"\nCORE_HEAD_AFTER="$(git -C "$CORE_DIR" rev-parse HEAD)"\necho "pin_after=$PIN_AFTER"\necho "core_head_after=$CORE_HEAD_AFTER"\ntest "$PIN_AFTER" = "$CORE_HEAD_AFTER"\n.venv/bin/python tools/check_sase_core_rs_bindings\nGH_REPO=sase-org/sase just check-full' --reason 'Run required just check-full after consuming current master and repairing 10w.5 local cost/machines-pane failures'

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
CARGO_BUILD_BUILD_DIR=/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws19-260914_162826/build
CARGO_INCREMENTAL=0
CARGO_PROFILE_DEV_DEBUG=line-tables-only
CARGO_PROFILE_TEST_DEBUG=line-tables-only
CARGO_TARGET_DIR=/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws19-260914_162826
CODEX_CI=1
CODEX_HOME=/home/bryan/.cache/sase/codex_home/450505-2bbbd8571e8b40408fe2d89708ff91b7
CODEX_MANAGED_BY_NPM=1
CODEX_MANAGED_PACKAGE_ROOT=/home/bryan/.config/nvm/versions/node/v22.14.0/lib/node_modules/@openai/codex
CODEX_PROJECT_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/
CODEX_SESSION_ID=01a0a19c-9e6e-77d3-ad6c-90a3d2df91a3
CODEX_THREAD_ID=01a0a19c-9e6e-77d3-ad6c-90a3d2df91a3
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
PPID=843386
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
SASE_FINAL_TURN_NONCE=29fF1oKz8YZGwGkXB4mkY3ARcD_D1TEThwIXcGiW_Ec
SASE_INTERNAL_AGENT_NAME_BYPASS=1
SASE_LAUNCH_SCRATCH_KEY=gh_sase-org__sase-ws19-260914_162826
SASE_LINKED_REPOS_JSON='[{"auto_clone": false, "env_name": "CHEZMOI", "kind": "linked", "name": "chezmoi", "primary_dir": "/home/bryan/.local/share/chezmoi", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/chezmoi", "workspace_num": 19}, {"auto_clone": true, "env_name": "SASE_CORE", "kind": "linked", "name": "sase-core", "primary_dir": "/home/bryan/projects/github/sase-org/sase-core", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_GITHUB", "kind": "linked", "name": "sase-github", "primary_dir": "/home/bryan/projects/github/sase-org/sase-github", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-github", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_TELEGRAM", "kind": "linked", "name": "sase-telegram", "primary_dir": "/home/bryan/projects/github/sase-org/sase-telegram", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-telegram", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_NVIM", "kind": "linked", "name": "sase-nvim", "primary_dir": "/home/bryan/projects/github/sase-org/sase-nvim", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-nvim", "workspace_num": 19}, {"auto_clone": false, "env_name": "SASE_RESEARCH_ARTIFACTS", "kind": "linked", "name": "sase-research-artifacts", "primary_dir": "/home/bryan/projects/github/sase-org/sase-research-artifacts", "remote_url": null, "slug": null, "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-research-artifacts", "workspace_num": 19}, {"auto_clone": true, "env_name": "PLANS", "kind": "sidecar", "name": "plans", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/plans", "remote_url": "git@github.com:sase-org/sase--plans.git", "slug": "sase--plans", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans", "workspace_num": 19}, {"auto_clone": false, "env_name": "BEADS", "kind": "sidecar", "name": "beads", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/beads", "remote_url": "git@github.com:sase-org/sase--beads.git", "slug": "sase--beads", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/beads", "workspace_num": 19}, {"auto_clone": false, "env_name": "RESEARCH", "kind": "sidecar", "name": "research", "primary_dir": "/home/bryan/projects/github/sase-org/sase/sase/repos/research", "remote_url": "git@github.com:sase-org/sase--research.git", "slug": "sase--research", "workspace_dir": "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research", "workspace_num": 19}]'
SASE_LINKED_REPO_BEADS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/beads
SASE_LINKED_REPO_BEADS_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/beads
SASE_LINKED_REPO_PLANS_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/plans
SASE_LINKED_REPO_PLANS_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/plans
SASE_LINKED_REPO_RESEARCH_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research
SASE_LINKED_REPO_RESEARCH_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase/sase/repos/research
SASE_LINKED_REPO_SASE_CORE_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core
SASE_LINKED_REPO_SASE_CORE_PRIMARY_DIR=/home/bryan/projects/github/sase-org/sase-core
SASE_MONITOR_CONTINUATION=1
SASE_MONITOR_DELIVERY_ARTIFACTS_DIR=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914154713
SASE_MONITOR_DELIVERY_IDENTITY=sase-10w.5.f0.f0--4
SASE_MONITOR_DELIVERY_KEY='{"branch": "failed", "monitor_id": "pvf8mtys23j2", "result_id": "result:pvf8mtys23j2:de8a906b681d098f"}'
SASE_MONITOR_DIAGNOSTICS_DIR=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914164309/diagnostics
SASE_MONITOR_ID=e6fn28vjwk86
SASE_PROC_ID=e6fn28vjwk86
SASE_PROC_LOG_PATH=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914164309/live_reply.md
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
STARSHIP_SESSION_KEY=2801023134319052
STARSHIP_SHELL=zsh
TEMP=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_162826
TERM=tmux-256color
TERM_PROGRAM=tmux
TERM_PROGRAM_VERSION=3.5a
TMP=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_162826
TMPDIR=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_162826
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
sase_head=00acd607fa0a303cd767fd001d2ff12d2f7e4ea2
sase_origin_master=00acd607fa0a303cd767fd001d2ff12d2f7e4ea2
pin_before=3566872b4916123fedf100b7c5684c701085655c
core_head_before=3566872b4916123fedf100b7c5684c701085655c
 [31mM[m tests/ace/tui/test_machines_pane.py
 [31mM[m tests/perf/baselines/test_cost_budgets.json
[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/982c5f16d72d609a2f083777b3bced8f9c7923a2a4bc8570df1c9bdb8793d9d0/sase_core_rs-0.34.28-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 0.16ms
Uninstalled 1 package in 1ms
Installed 1 package in 12ms
 ~ sase-core-rs==0.34.28 (from file:///home/bryan/.sase/cache/sase-core-wheels/982c5f16d72d609a2f083777b3bced8f9c7923a2a4bc8570df1c9bdb8793d9d0/sase_core_rs-0.34.28-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
    Finished `dev-update` profile [optimized] target(s) in 0.48s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 97 packages in 117ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
Prepared 1 package in 461ms
Uninstalled 1 package in 9ms
Installed 1 package in 6ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
pin_after=3566872b4916123fedf100b7c5684c701085655c
core_head_after=3566872b4916123fedf100b7c5684c701085655c
sase_core_rs 0.34.28 exposes all 603 bindings required by /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase
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
created: 4/4 workers
4 workers [41745 items]

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
........................................................................ [ 18%]
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
..................................s..................................... [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
........................................................................ [ 29%]
....................s................................................... [ 30%]
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
........................................................................ [ 33%]
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
........................................................................ [ 48%]
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
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
........................................................................ [ 57%]
......s................................................................. [ 58%]
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
......................................................................s. [ 65%]
s..s.s.................................................................. [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 65%]
........................................................................ [ 66%]
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
........................................................................ [ 76%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
........................................................................ [ 77%]
...................s.................................................... [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 78%]
........................................................................ [ 79%]
......s................................................................. [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 79%]
........................................................................ [ 80%]
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
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 83%]
........................................................................ [ 84%]
..............................................................s......... [ 84%]
..........................................s.....s....................... [ 84%]
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
.....s.................................................................. [ 88%]
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
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
........................................................................ [ 99%]
.........................................................                [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7fbe7bbc0930>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))


═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=============================== warnings summary ===============================
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852: PytestAssertRewriteWarning: Module already imported so cannot be rewritten; tests._axe_lumberjack_fixtures
    self.import_plugin(import_spec)

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

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=956779) is multi-threaded, use of fork() may lead to deadlocks in the child.

tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_successful_post_preparation_summary_survives_later_metadata_write changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/fixtures.py:924: RuntimeWarning: tests/test_run_agent_runner_clan_summary_refresh.py::test_unsuccessful_post_preparation_summary_keeps_earlier_success changed the process working directory from '/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19' to '<deleted>'; restored it.
    next(it)

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
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=956789) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

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

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=956779) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
  Enable tracemalloc to get traceback where the object was allocated.
  See https://docs.pytest.org/en/stable/how-to/capture-warnings.html#resource-warnings for more info.

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 0 poisoning change(s) across 0 test(s); 58676 warming mutation(s) filtered; 440 cooling mutation(s) filtered; 2559 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.pytest_cache/sase-global-leaks.json -
============================= slowest 20 durations =============================
63.27s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
38.73s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
36.30s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
31.70s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
26.42s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
26.10s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
20.42s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
18.81s call     tests/ace/tui/test_plugins_browser_pane_uninstall.py::test_plugins_pane_uninstall_no_change_refreshes_without_restart
18.80s call     tests/ace/tui/test_plugins_browser_pane_update.py::test_plugins_pane_update_confirm_executes_and_writes_receipt
18.69s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_manual_update_reuses_load_fetches
18.67s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_true_noop_does_not_restart
18.67s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_update_dev_confirm_closes_admin_center
16.63s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_update_dev_preview_and_restart
16.61s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_core_only_success_restarts_once_and_receipts
16.58s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_cancel_keeps_admin_center_open
16.56s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_loads_receipt_on_plan_worker
16.56s call     tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py::test_updates_pane_sase_dev_update_shows_all_commit_groups
16.47s call     tests/ace/tui/test_plugins_browser_pane_loading.py::test_updates_pane_manual_update_drops_expired_load_freshness
13.83s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
12.92s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
========= 41732 passed, 14 skipped, 71 warnings in 6685.29s (1:51:25) ==========
recording: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260914T223819Z-955628.json
baseline:  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/baselines/test_cost_baseline.json
timings:   /home/bryan/.sase/test-selection/gh_sase-org__sase/timings covers 1348/3854 files total=3548.736s cost-delta=+1644.139s (+46.3%)
Test Cost Report
  record: 004cc7d584f31985
  recorded_at: 2026-09-14T22:38:19.823016+00:00
  host: athena
  mode: cost
  worker_count: 4

Summary
  per-test wall: 5192.875s
  per-test CPU: 3163.864s
  per-test idle: 2029.011s
  collection: 138.544s
  worker wall: 33355.390s
  worker CPU: 24649.070s
  peak worker RSS KiB: 1,985,148 KiB
  median worker RSS KiB: 754,858 KiB
  post-collection worker RSS KiB: 755,048 KiB
  worker RSS curve: start=182,992 KiB, post_collection=755,048 KiB, median=754,858 KiB, peak=1,985,148 KiB, samples=431
  files: 3854
  nodes: 41745

Diff
  per-test wall: current 5192.875s; baseline 3719.000s; delta +1473.875 (+39.6%)
  per-test CPU: current 3163.864s; baseline n/a; delta n/a
  per-test idle: current 2029.011s; baseline n/a; delta n/a
  collection: current 138.544s; baseline 27.600s; delta +110.944 (+402.0%)
  worker wall: current 33355.390s; baseline n/a; delta n/a
  worker CPU: current 24649.070s; baseline n/a; delta n/a
  peak worker RSS KiB: current 1,985,148 KiB; baseline 1,126,400 KiB; delta +858748.000 (+76.2%)
  median worker RSS KiB: current 754,858 KiB; baseline n/a; delta n/a
  post-collection worker RSS KiB: current 755,048 KiB; baseline n/a; delta n/a

Causes
  AcePage.__aenter__: 996.376s (756x)  delta +606.376 (+155.5%)
  Textual App.run_test enter: 795.863s (3946x)  delta +373.863 (+88.6%)
  ACE settle_pilot: 614.323s (8633x)  delta n/a
  subprocess.run: 440.344s (49206x)  delta +180.344 (+69.4%)
  Pilot.pause(delay): 432.287s (17649x)  delta n/a
  Textual App.run_test exit: 72.911s (3946x)  delta n/a
  sase.config.core.load_merged_config: 65.657s (29005x)  delta +65.657
  AcePage.__aexit__: 59.641s (754x)  delta n/a
  Pilot.pause(None): 48.523s (836x)  delta n/a
  sase.main.parser.create_parser: 44.435s (1949x)  delta -15.565 (-25.9%)
  YAML load: 23.791s (58879x)  delta -41.209 (-63.4%)
  subprocess.Popen: 0.815s (1068x)  delta n/a
  ACE pause_until_cpu_idle: 0.001s (2x)  delta n/a
  gettext.find: 0.000s (4x)  delta +0.000

Top 10 Files
  by wall:
      76.058s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      75.343s  tests/test_check_feature_flags_tool_run.py
      72.317s  tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py
      70.986s  tests/fakey/test_monitor_capacity_e2e.py
      61.114s  tests/ace/tui/test_plugins_browser_pane_loading.py
      54.261s  tests/test_ace_testing.py
      45.744s  tests/ace/tui/test_plugins_browser_pane_sase_update.py
      45.415s  tests/ace/tui/test_agents_filter_bar_session.py
      43.219s  tests/ace/tui/test_axe_entry_editor_modal.py
      41.131s  tests/ace/tui/test_artifacts_scaffold.py
  by CPU:
      75.123s  tests/test_check_feature_flags_tool_run.py
      69.842s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      54.284s  tests/test_ace_testing.py
      43.443s  tests/ace/tui/test_plugins_browser_pane_loading.py
      41.035s  tests/ace/tui/test_axe_entry_editor_modal.py
      36.818s  tests/ace/tui/test_artifacts_scaffold.py
      33.852s  tests/ace/tui/test_agents_filter_bar_session.py
      32.605s  tests/ace/tui/test_xprompt_browser_load_keymap.py
      32.286s  tests/ace/tui/test_usage_header.py
      29.723s  tests/ace/tui/test_plugins_browser_pane_install.py
  by idle:
      64.684s  tests/fakey/test_monitor_capacity_e2e.py
      59.052s  tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py
      31.699s  tests/test_contract_manifest.py
      29.660s  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py
      29.620s  tests/ace/tui/test_plugins_browser_pane_sase_update.py
      28.032s  tests/ace/tui/test_agents_zoom_panel_files.py
      27.921s  tests/monitor/test_monitor_start_ack.py
      27.404s  tests/pager/test_rendered_link_contract.py
      23.834s  tests/test_procs_service.py
      22.163s  tests/dispatch/test_machine_bootstrap_real_gateway.py
  by AcePage.__aenter__:
      44.033s    37x  tests/test_ace_testing.py
      27.308s    21x  tests/ace/tui/test_usage_header.py
      27.018s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      24.491s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      22.999s    15x  tests/ace/tui/test_artifacts_current_project_scope.py
      19.762s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
      18.679s    12x  tests/ace/tui/test_artifacts_scaffold.py
      17.727s    13x  tests/ace/tui/test_statistics_view_number_select.py
      17.658s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
      17.618s    15x  tests/test_keymaps_e2e.py
  by Textual App.run_test enter:
      27.844s    40x  tests/test_ace_testing.py
      16.732s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      15.350s    15x  tests/ace/tui/test_artifacts_current_project_scope.py
      14.301s    21x  tests/ace/tui/test_usage_header.py
      14.096s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      13.711s    13x  tests/ace/tui/test_statistics_view_number_select.py
      13.029s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
      12.909s    13x  tests/ace/tui/test_xprompt_browser_load_keymap.py
      12.507s    12x  tests/ace/tui/test_projects_pane.py
      11.691s    15x  tests/test_keymaps_e2e.py
  by ACE settle_pilot:
      62.593s    21x  tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py
      33.923s    30x  tests/ace/tui/test_plugins_browser_pane_sase_update.py
      32.981s    23x  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py
      29.616s    85x  tests/ace/tui/test_plugins_browser_pane_loading.py
      24.204s   143x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      19.734s    36x  tests/ace/tui/test_plugins_browser_pane_update.py
      19.283s    32x  tests/ace/tui/test_plugins_browser_pane_uninstall.py
      11.921s    21x  tests/ace/tui/test_projects_pane_current_project_seed.py
      10.145s   253x  tests/ace/tui/test_statistics_pane_filters.py
       9.789s    56x  tests/ace/tui/test_axe_entry_editor_modal.py
  by subprocess.run:
      31.700s     1x  tests/test_contract_manifest.py
      13.971s     8x  tests/monitor/test_monitor_supervise_timeout.py
      13.671s    25x  tests/test_commit_workflow_bead_lifecycle_e2e.py
      11.599s    18x  tests/test_plan_approval_responses.py
       9.094s    14x  tests/test_plan_gates_execution.py
       7.186s    11x  tests/test_bead/test_snooze_gate_actions.py
       6.813s    10x  tests/test_plan_gates_action_api.py
       5.875s     9x  tests/ace/tui/test_notification_plan_gate.py
       5.826s    32x  tests/test_suite_gate_scoped_integration.py
       5.740s    41x  tests/test_fork_workflow.py
  by Pilot.pause(delay):
      22.462s   286x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      20.050s   198x  tests/pager/test_rendered_link_contract.py
      13.656s   170x  tests/ace/tui/test_plugins_browser_pane_loading.py
      11.670s    42x  tests/ace/tui/test_projects_pane_current_project_seed.py
       8.619s   506x  tests/ace/tui/test_statistics_pane_filters.py
       8.494s    70x  tests/ace/tui/test_plugins_browser_pane_detail.py
       8.480s    64x  tests/ace/tui/test_config_pane_widget.py
       8.301s   112x  tests/ace/tui/test_axe_entry_editor_modal.py
       8.278s   666x  tests/ace/tui/test_agents_filter_bar_session.py
       7.945s    98x  tests/ace/tui/test_plugins_browser_pane_install.py
  by Textual App.run_test exit:
       2.853s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       2.563s    13x  tests/ace/tui/test_xprompt_browser_load_keymap.py
       2.523s    12x  tests/ace/tui/test_projects_pane.py
       2.364s     8x  tests/ace/tui/test_statistics_pane_filters.py
       2.352s     8x  tests/ace/tui/test_projects_pane_current_project_seed.py
       2.131s     3x  tests/ace/tui/test_artifacts_files_grouping.py
       1.614s     9x  tests/ace/tui/test_config_pane_widget.py
       1.510s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
       1.461s    11x  tests/ace/tui/test_plugins_browser_pane_detail.py
       1.450s     1x  tests/ace/tui/test_startup_stopwatch_live_update.py
  by sase.config.core.load_merged_config:
       1.508s    40x  tests/main/test_repo_log.py
       0.209s   453x  tests/test_bead/test_cli_show_style.py
       0.092s   394x  tests/test_managed_tmp_reaper.py
       0.078s   156x  tests/test_bead/test_cli_show.py
       0.064s    76x  tests/completion/test_build.py
       0.062s   931x  tests/main/test_init_memory_markdown_templates.py
       0.061s    23x  tests/test_plan_search_cli.py
       0.056s    17x  tests/test_commit_workflow_checkpointing.py
       0.055s    17x  tests/test_commit_workflow_dispatch.py
       0.055s   112x  tests/main/test_completion_handler.py
  by AcePage.__aexit__:
       4.095s     3x  tests/ace/tui/test_artifacts_files_grouping.py
       3.097s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       2.585s    13x  tests/ace/tui/test_xprompt_browser_load_keymap.py
       2.563s    12x  tests/ace/tui/test_projects_pane.py
       2.438s     8x  tests/ace/tui/test_projects_pane_current_project_seed.py
       2.367s     8x  tests/ace/tui/test_statistics_pane_filters.py
       1.760s     9x  tests/ace/tui/test_config_pane_widget.py
       1.558s    11x  tests/ace/tui/test_plugins_browser_pane_detail.py
       1.547s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
       1.516s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
  by Pilot.pause(None):
       3.983s    39x  tests/test_notification_modal_scroll.py
       3.006s    44x  tests/test_models_panel_override_flows.py
       2.949s    67x  tests/test_models_panel_selector_builder.py
       2.301s    39x  tests/test_models_panel_jump.py
       2.077s    29x  tests/test_models_panel_edit.py
       1.984s     8x  tests/test_models_panel_provider_modal_drain.py
       1.809s    44x  tests/test_approve_options_modal_state.py
       1.742s    32x  tests/test_model_picker_modal.py
       1.654s    36x  tests/test_command_palette_modal.py
       1.651s    25x  tests/test_models_panel_edit_custom.py
  by sase.main.parser.create_parser:
       2.371s    21x  tests/main/test_parser_monitor.py
       2.213s   146x  tests/test_bead/test_cli_show_style.py
       1.817s    10x  tests/main/test_repo_log.py
       1.773s    11x  tests/test_bead/test_cli_show_epic_expansion.py
       1.560s     2x  tests/main/test_agent_prompts_handler.py
       1.528s    50x  tests/completion/test_update_refresh_soak.py
       1.453s     2x  tests/test_editor_helper_finalizer_catalog.py
       1.307s     3x  tests/test_bead/test_cli_rm.py
       1.089s    29x  tests/test_bead/test_cli_note.py
       1.084s    31x  tests/test_bead/test_cli_show_json.py
  by YAML load:
       3.701s  5328x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
       1.144s  5171x  tests/main/test_init_skills_sources.py
       0.826s   959x  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py
       0.738s   980x  tests/test_bead_xprompt_tags.py
       0.639s  3426x  tests/main/test_init_memory_task_types_note.py
       0.624s   480x  tests/test_pooled_alias_single_consumption.py
       0.453s  2382x  tests/main/test_init_memory_plan.py
       0.440s  1632x  tests/test_bead/test_work_queue_capacity.py
       0.409s  2112x  tests/main/test_init_memory_commit.py
       0.387s     6x  tests/test_models_panel_keymaps.py
  by subprocess.Popen:
       0.105s     2x  tests/test_agent_name_wipe.py
       0.039s    67x  tests/test_xprompt_model_alias_shortcut_parity.py
       0.026s    49x  tests/sdd_store/test_sidecar_bead_adoption.py
       0.025s    34x  tests/test_procs_service.py
       0.021s    26x  tests/llm_provider/test_grok_usage_probe.py
       0.020s    38x  tests/sdd_store/test_materialize.py
       0.019s    31x  tests/test_xprompt_directive_completion_parity.py
       0.018s    21x  tests/llm_provider/test_codex_usage_probe.py
       0.016s    28x  tests/test_bead/test_workspace_sidecar_bead_eviction.py
       0.011s    18x  tests/sdd_store/test_sidecar_init_creation.py
  by ACE pause_until_cpu_idle:
       0.001s     1x  tests/test_ace_wait.py
       0.000s     1x  tests/test_a.py
  by gettext.find:
       0.000s     1x  tests/ace/tui/artifact_file_viewer/test_entrypoint.py
       0.000s     1x  tests/test_mobile_gateway.py
       0.000s     1x  tests/test_agent_restart_cli.py
       0.000s     1x  tests/agent_clis/test_cli.py
test cost budget regression: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260914T223819Z-955628.json
budgets: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/baselines/test_cost_budgets.json
- [hard] peak_worker_rss_kib: actual 1985148.000 exceeds budget 1700000.000 + 15% tolerance (1955000.000)
test cost budget advisories: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260914T223819Z-955628.json
wall-clock overages usually mean the host was busy, not that the suite got more expensive; the cpu/count figures alongside each entry are contention-stable, so compare them to tell the two apart.
- [advisory] causes.ace_page_enter: actual 996.376 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=1000.297s, count=756)
- [advisory] causes.ace_settle_pilot: actual 614.323 exceeds budget 340.000 + 15% tolerance (391.000) (cpu=445.417s, count=8633)
- [advisory] causes.pilot_pause_delay: actual 432.287 exceeds budget 230.000 + 15% tolerance (264.500) (cpu=397.590s, count=17649)
- [advisory] causes.textual_app_run_test_enter: actual 795.863 exceeds budget 470.000 + 15% tolerance (540.500) (cpu=799.218s, count=3946)
- [advisory] causes.yaml_load: actual 23.791 exceeds budget 20.000 + 15% tolerance (23.000) (cpu=23.750s, count=58879)
error: recipe `test-cost` failed on line 424 with exit code 1
error: recipe `check-full` failed on line 686 with exit code 1

