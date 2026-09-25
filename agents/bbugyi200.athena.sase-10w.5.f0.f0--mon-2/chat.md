# Chat History - ace-run (sase-10w.5.f0.f0--mon-2)

- **TIMESTAMP:** 2026-09-14 16:27:52 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-10w.5.f0.f0--mon-2

## Prompt

sase monitor start --command 'bash -lc set -euo pipefail\nCORE_DIR="$(sase repo open sase-core -r "Use audited linked core checkout for 10w.5 full verification after fast-forward")"\nPIN_BEFORE="$(cat sase-core-revision.txt)"\nCORE_HEAD_BEFORE="$(git -C "$CORE_DIR" rev-parse HEAD)"\necho "sase_head=$(git rev-parse HEAD)"\necho "sase_origin_master=$(git rev-parse origin/master)"\necho "pin_before=$PIN_BEFORE"\necho "core_head_before=$CORE_HEAD_BEFORE"\ngit status --short\ntest "$PIN_BEFORE" = "$CORE_HEAD_BEFORE"\nexport SASE_CORE_DIR="$CORE_DIR"\nexport GH_REPO=sase-org/sase\njust install\nPIN_AFTER="$(cat sase-core-revision.txt)"\nCORE_HEAD_AFTER="$(git -C "$CORE_DIR" rev-parse HEAD)"\necho "pin_after=$PIN_AFTER"\necho "core_head_after=$CORE_HEAD_AFTER"\ntest "$PIN_AFTER" = "$CORE_HEAD_AFTER"\n.venv/bin/python tools/check_sase_core_rs_bindings\n.venv/bin/python -m pytest tests/test_global_state_leak_detector.py tests/test_sase_global_state_isolation.py tests/sdd/test_git_identity_fixture.py tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation -q\nGH_REPO=sase-org/sase just check-full' --reason 'Run required just check-full for 10w.5 leak-detector repair after current-master fast-forward and machines-pane wait hardening'

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
CARGO_BUILD_BUILD_DIR=/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws19-260914_153457/build
CARGO_INCREMENTAL=0
CARGO_PROFILE_DEV_DEBUG=line-tables-only
CARGO_PROFILE_TEST_DEBUG=line-tables-only
CARGO_TARGET_DIR=/home/bryan/.cache/sase/tmp/cargo-targets/gh_sase-org__sase-ws19-260914_153457
CODEX_CI=1
CODEX_HOME=/home/bryan/.cache/sase/codex_home/3618552-10d868f5b73647788c5355b7d8e6c0ac
CODEX_MANAGED_BY_NPM=1
CODEX_MANAGED_PACKAGE_ROOT=/home/bryan/.config/nvm/versions/node/v22.14.0/lib/node_modules/@openai/codex
CODEX_PROJECT_DIR=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/
CODEX_SESSION_ID=01a0a16b-a793-7c63-819a-651681bc01e2
CODEX_THREAD_ID=01a0a16b-a793-7c63-819a-651681bc01e2
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
LESS=QR
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
PPID=3809292
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
SASE_FINAL_TURN_NONCE=3rXreRIbaj8mVzTp7GHjaQjUGrcax-VIYWLg-_wAhBE
SASE_INTERNAL_AGENT_NAME_BYPASS=1
SASE_LAUNCH_SCRATCH_KEY=gh_sase-org__sase-ws19-260914_153457
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
SASE_MONITOR_DELIVERY_ARTIFACTS_DIR=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914150831
SASE_MONITOR_DELIVERY_IDENTITY=sase-10w.5.f0.f0--3
SASE_MONITOR_DELIVERY_KEY='{"branch": "failed", "monitor_id": "9bcnhj6xhcvy", "result_id": "result:9bcnhj6xhcvy:c605b15cea021dc2"}'
SASE_MONITOR_DIAGNOSTICS_DIR=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914154713/diagnostics
SASE_MONITOR_ID=pvf8mtys23j2
SASE_PROC_ID=pvf8mtys23j2
SASE_PROC_LOG_PATH=/home/bryan/.sase/projects/gh_sase-org__sase/artifacts/ace-run/202609/14/20260914154713/live_reply.md
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
STARSHIP_SESSION_KEY=3231642722038323
STARSHIP_SHELL=zsh
TEMP=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_153457
TERM=tmux-256color
TERM_PROGRAM=tmux
TERM_PROGRAM_VERSION=3.5a
TMP=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_153457
TMPDIR=/home/bryan/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws19-260914_153457
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
sase_head=bfd22d8df3f168ac232ec428ca83944d5d650b5a
sase_origin_master=bfd22d8df3f168ac232ec428ca83944d5d650b5a
pin_before=3566872b4916123fedf100b7c5684c701085655c
core_head_before=3566872b4916123fedf100b7c5684c701085655c
 [31mM[m tests/_global_state_leaks/fingerprints.py
 [31mM[m tests/ace/tui/test_machines_pane.py
 [31mM[m tests/test_global_state_leak_detector.py
[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/linked/sase-core for local dev.
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[rust-install] Installing cached sase_core_rs wheel from /home/bryan/.sase/cache/sase-core-wheels/982c5f16d72d609a2f083777b3bced8f9c7923a2a4bc8570df1c9bdb8793d9d0/sase_core_rs-0.34.28-cp312-abi3-manylinux_2_39_x86_64.whl.
Resolved 1 package in 1ms
Prepared 1 package in 0.18ms
Uninstalled 1 package in 1ms
Installed 1 package in 7ms
 ~ sase-core-rs==0.34.28 (from file:///home/bryan/.sase/cache/sase-core-wheels/982c5f16d72d609a2f083777b3bced8f9c7923a2a4bc8570df1c9bdb8793d9d0/sase_core_rs-0.34.28-cp312-abi3-manylinux_2_39_x86_64.whl)
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
    Finished `dev-update` profile [optimized] target(s) in 0.17s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 97 packages in 15ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
Prepared 1 package in 602ms
Uninstalled 1 package in 2ms
Installed 1 package in 3ms
 ~ sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19)
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
pin_after=3566872b4916123fedf100b7c5684c701085655c
core_head_after=3566872b4916123fedf100b7c5684c701085655c
sase_core_rs 0.34.28 exposes all 603 bindings required by /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase
.........................                                                [100%]
============================= slowest 20 durations =============================
4.03s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
1.27s call     tests/test_global_state_leak_detector.py::test_report_only_mode_keeps_pytest_green_on_poison
1.12s call     tests/test_global_state_leak_detector.py::test_fail_on_poison_mode_fails_pytest_on_poison
0.10s call     tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation
0.06s setup    tests/test_global_state_leak_detector.py::test_live_config_refresh_thread_is_poisoning_not_warming
0.05s call     tests/test_global_state_leak_detector.py::test_process_snapshot_ignores_suite_git_identity_environment
0.05s call     tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads
0.02s call     tests/sdd/test_git_identity_fixture.py::test_test_created_repo_can_commit_without_local_identity

(12 durations < 0.005s hidden.  Use -vv to show these durations.)
25 passed in 7.92s
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
created: 9/9 workers
9 workers [41722 items]

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
.................s...................................................... [ 12%]
........................................................................ [ 12%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
........................................................................ [ 13%]
.........................................................s.............. [ 14%]
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
..................................s..................................... [ 19%]
.....................s....s............................................. [ 20%]
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
..........................................s............................. [ 24%]
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
........................................................................ [ 28%]
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
...................................................................s.... [ 41%]
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
..................................................................s..... [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 47%]
........................................................................ [ 47%]
..................................s..................................... [ 47%]
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
........................................................................ [ 52%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 53%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
........................................................................ [ 54%]
...........................................s...s..s....s................ [ 54%]
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
........................................................................ [ 76%]
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
........................................................................ [ 83%]
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
........................................................................ [ 96%]
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
..................................                                       [100%]/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f13b2edb950>: None

Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/hypothesis/internal/conjecture/junkdrawer.py", line 468, in gc_callback
    now = _perf_counter()
KeyboardInterrupt


  warnings.warn(pytest.PytestUnraisableExceptionWarning(msg))
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.venv/lib/python3.14/site-packages/_pytest/unraisableexception.py:67: PytestUnraisableExceptionWarning: Exception ignored while calling GC callback <function gc_cumulative_time.<locals>.gc_callback at 0x7f599421bd70>: None

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
.venv/lib/python3.14/site-packages/_pytest/config/__init__.py:852
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

tests/sdd/test_artifact_link_event_acceptance_process_death.py::test_real_killed_publisher_process_leaves_no_corrupt_object_and_recovers
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/sdd/test_artifact_link_event_acceptance_process_death.py:57: DeprecationWarning: This process (pid=3875474) is multi-threaded, use of fork() may lead to deadlocks in the child.
    child = os.fork()

tests/ace/tui/test_dismissed_index_startup_sync.py::test_start_post_mount_background_loads_schedules_dismissed_sync_once
  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/src/sase/ace/tui/actions/update_toast.py:87: RuntimeWarning: coroutine 'Timer._run_timer' was never awaited
    log.debug("Failed to start periodic update checks", exc_info=True)
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

tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
  <frozen os>:898: DeprecationWarning: This process (pid=3875437) is multi-threaded, use of fork() may lead to deadlocks in the child.

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
  /home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib/python3.14/pty.py:66: DeprecationWarning: This process (pid=3875437) is multi-threaded, use of forkpty() may lead to deadlocks in the child.
    pid, fd = os.forkpty()

-- Docs: https://docs.pytest.org/en/stable/how-to/capture-warnings.html
- sase global leak detector: 0 poisoning change(s) across 0 test(s); 58888 warming mutation(s) filtered; 533 cooling mutation(s) filtered; 2479 invalidation(s) filtered; report=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/.pytest_cache/sase-global-leaks.json -
============================= slowest 20 durations =============================
64.81s call     tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap
50.26s call     tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection
48.99s call     tests/test_check_feature_flags_tool_run.py::test_main_static_on_repo_exits_zero
48.49s call     tests/test_check_feature_flags_tool_run.py::test_static_main_ignores_exploding_bd_command
41.40s call     tests/sdd/test_git_identity_fixture.py::test_sdd_git_identity_survives_empty_home_subprocess
36.32s call     tests/history/test_continuation_replay_hydration.py::test_hundred_handoff_from_final_monitor_result_grows_linearly
26.43s call     tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action
20.51s call     tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed
16.93s call     tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_opens_preview_modal
16.74s call     tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py::test_updates_pane_mixed_managed_failure_notifies_once_without_restart
14.51s call     tests/test_commit_workflow_bead_lifecycle_e2e.py::test_stitch_create_requires_keep_then_closes_only_assigned_phase
13.40s call     tests/test_procs_service.py::test_settlement_recovers_every_injected_crash_checkpoint_repeatedly
11.62s call     tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation
11.42s call     tests/feature_flags/test_host_config_safety.py::test_config_seed_tests_do_not_snapshot_config_dir_at_module_scope
11.18s call     tests/ace/tui/test_deleted_proc_queue_imports.py::test_tests_do_not_import_deleted_proc_queue_module
10.85s call     tests/ace/tui/test_artifacts_scaffold.py::test_number_keys_jump_artifacts_without_entering_from_other_tabs
10.58s call     tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_flag_on_relaunches_stranded_agent
10.50s call     tests/ace/tui/test_agents_filter_bar_session.py::test_circumflex_history_replaces_the_live_edit_while_the_bar_is_open
9.35s call     tests/monitor/test_monitor_start_ack.py::test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker
9.31s call     tests/test_procs_supervisor.py::test_starter_exit_does_not_kill_a_released_proc
========= 41709 passed, 14 skipped, 76 warnings in 2210.16s (0:36:50) ==========
recording: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260914T202651Z-3874423.json
baseline:  /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/baselines/test_cost_baseline.json
timings:   /home/bryan/.sase/test-selection/gh_sase-org__sase/timings covers 3850/3853 files total=6030.206s cost-delta=-322.388s (-5.3%)
Test Cost Report
  record: 533c582fc63c2717
  recorded_at: 2026-09-14T20:26:51.551374+00:00
  host: athena
  mode: cost
  worker_count: 9

Summary
  per-test wall: 5707.817s
  per-test CPU: 3307.857s
  per-test idle: 2399.961s
  collection: 252.258s
  worker wall: 21475.190s
  worker CPU: 16941.730s
  peak worker RSS KiB: 1,921,124 KiB
  median worker RSS KiB: 755,304 KiB
  post-collection worker RSS KiB: 756,120 KiB
  worker RSS curve: start=182,796 KiB, post_collection=756,120 KiB, median=755,304 KiB, peak=1,921,124 KiB, samples=443
  files: 3853
  nodes: 41722

Diff
  per-test wall: current 5707.817s; baseline 3719.000s; delta +1988.817 (+53.5%)
  per-test CPU: current 3307.857s; baseline n/a; delta n/a
  per-test idle: current 2399.961s; baseline n/a; delta n/a
  collection: current 252.258s; baseline 27.600s; delta +224.658 (+814.0%)
  worker wall: current 21475.190s; baseline n/a; delta n/a
  worker CPU: current 16941.730s; baseline n/a; delta n/a
  peak worker RSS KiB: current 1,921,124 KiB; baseline 1,126,400 KiB; delta +794724.000 (+70.6%)
  median worker RSS KiB: current 755,304 KiB; baseline n/a; delta n/a
  post-collection worker RSS KiB: current 756,120 KiB; baseline n/a; delta n/a

Causes
  AcePage.__aenter__: 1127.581s (756x)  delta +737.581 (+189.1%)
  Textual App.run_test enter: 894.547s (3945x)  delta +472.547 (+112.0%)
  subprocess.run: 535.631s (49337x)  delta +275.631 (+106.0%)
  ACE settle_pilot: 516.994s (8864x)  delta n/a
  Pilot.pause(delay): 458.820s (18111x)  delta n/a
  Textual App.run_test exit: 84.400s (3945x)  delta n/a
  sase.config.core.load_merged_config: 73.868s (29038x)  delta +73.868
  AcePage.__aexit__: 67.878s (754x)  delta n/a
  sase.main.parser.create_parser: 51.049s (1949x)  delta -8.951 (-14.9%)
  Pilot.pause(None): 47.671s (836x)  delta n/a
  YAML load: 25.884s (58938x)  delta -39.116 (-60.2%)
  subprocess.Popen: 0.928s (1080x)  delta n/a
  ACE pause_until_cpu_idle: 0.001s (2x)  delta n/a
  gettext.find: 0.001s (8x)  delta +0.001

Top 10 Files
  by wall:
      97.774s  tests/test_check_feature_flags_tool_run.py
      82.526s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      75.514s  tests/fakey/test_monitor_capacity_e2e.py
      56.499s  tests/test_ace_testing.py
      52.598s  tests/ace/tui/test_agents_filter_bar_session.py
      52.514s  tests/ace/tui/test_plugins_browser_pane_loading.py
      50.283s  tests/test_contract_manifest.py
      42.451s  tests/ace/tui/test_axe_entry_editor_modal.py
      41.433s  tests/sdd/test_git_identity_fixture.py
      40.402s  tests/ace/tui/test_agents_zoom_panel_files.py
  by CPU:
      97.542s  tests/test_check_feature_flags_tool_run.py
      76.323s  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      55.416s  tests/test_ace_testing.py
      50.715s  tests/ace/tui/test_plugins_browser_pane_loading.py
      41.146s  tests/ace/tui/test_agents_filter_bar_session.py
      39.068s  tests/ace/tui/test_axe_entry_editor_modal.py
      37.476s  tests/ace/tui/test_xprompt_browser_load_keymap.py
      36.708s  tests/ace/tui/test_usage_header.py
      34.705s  tests/ace/tui/test_artifacts_scaffold.py
      33.261s  tests/ace/tui/test_plugins_browser_pane_install.py
  by idle:
      69.050s  tests/fakey/test_monitor_capacity_e2e.py
      50.253s  tests/test_contract_manifest.py
      41.415s  tests/sdd/test_git_identity_fixture.py
      30.395s  tests/monitor/test_monitor_start_ack.py
      28.052s  tests/history/test_continuation_replay_hydration.py
      27.848s  tests/ace/tui/test_agents_zoom_panel_files.py
      27.615s  tests/pager/test_rendered_link_contract.py
      26.452s  tests/test_procs_service.py
      23.679s  tests/monitor/test_monitor_supervise_timeout.py
      22.393s  tests/test_plan_approval_responses.py
  by AcePage.__aenter__:
      47.257s    37x  tests/test_ace_testing.py
      32.165s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      28.347s    15x  tests/ace/tui/test_artifacts_current_project_scope.py
      28.265s    21x  tests/ace/tui/test_usage_header.py
      26.314s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
      24.361s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
      23.234s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      22.090s    13x  tests/ace/tui/test_config_center_resume.py
      20.418s    12x  tests/ace/tui/test_plugins_browser_pane_all_current.py
      19.487s    12x  tests/ace/tui/test_projects_pane.py
  by Textual App.run_test enter:
      31.871s    40x  tests/test_ace_testing.py
      21.341s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
      18.749s    15x  tests/ace/tui/test_artifacts_current_project_scope.py
      17.369s    21x  tests/ace/tui/test_usage_header.py
      16.404s    13x  tests/ace/tui/test_plugins_browser_pane_install.py
      14.651s    17x  tests/ace/tui/test_axe_entry_editor_modal.py
      14.447s    12x  tests/ace/tui/test_agents_filter_bar_session.py
      13.761s    14x  tests/ace/tui/test_config_center_resume.py
      13.237s    13x  tests/ace/tui/test_statistics_view_number_select.py
      12.499s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
  by subprocess.run:
      50.252s     1x  tests/test_contract_manifest.py
      41.399s     6x  tests/sdd/test_git_identity_fixture.py
      17.659s     8x  tests/monitor/test_monitor_supervise_timeout.py
      14.206s    25x  tests/test_commit_workflow_bead_lifecycle_e2e.py
      12.752s    18x  tests/test_plan_approval_responses.py
       9.902s    14x  tests/test_plan_gates_execution.py
       8.010s    11x  tests/test_bead/test_snooze_gate_actions.py
       7.207s    32x  tests/test_suite_gate_scoped_integration.py
       7.158s    10x  tests/test_plan_gates_action_api.py
       6.764s     9x  tests/ace/tui/test_notification_plan_gate.py
  by ACE settle_pilot:
      29.163s   143x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      22.775s    28x  tests/ace/tui/test_plugins_browser_pane_sase_update.py
      22.103s    20x  tests/ace/tui/test_plugins_browser_pane_sase_update_mixed.py
      14.769s    90x  tests/ace/tui/test_plugins_browser_pane_loading.py
      13.395s    42x  tests/ace/tui/test_xprompt_browser_load_keymap.py
      12.890s   315x  tests/ace/tui/test_agents_filter_bar_session.py
      10.123s    54x  tests/ace/tui/test_axe_entry_editor_modal.py
      10.092s    47x  tests/ace/tui/test_plugins_browser_pane_install.py
       9.179s    41x  tests/ace/tui/test_statistics_view_number_select.py
       8.952s    36x  tests/ace/tui/test_config_pane_widget_commit.py
  by Pilot.pause(delay):
      27.672s   286x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
      20.064s   198x  tests/pager/test_rendered_link_contract.py
      13.285s   180x  tests/ace/tui/test_plugins_browser_pane_loading.py
      12.882s    84x  tests/ace/tui/test_xprompt_browser_load_keymap.py
       8.984s   630x  tests/ace/tui/test_agents_filter_bar_session.py
       8.623s   108x  tests/ace/tui/test_axe_entry_editor_modal.py
       8.340s    82x  tests/ace/tui/test_statistics_view_number_select.py
       7.876s    72x  tests/ace/tui/test_config_pane_widget_commit.py
       7.713s    56x  tests/ace/tui/test_plugins_browser_pane_uninstall.py
       7.134s    64x  tests/ace/tui/test_config_pane_widget.py
  by Textual App.run_test exit:
       2.392s     8x  tests/ace/tui/test_config_pane_widget_jump.py
       2.223s     4x  tests/ace/tui/test_feature_flags_pane_journeys.py
       2.148s     7x  tests/ace/tui/test_artifacts_relation_collapse_interactions.py
       1.991s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       1.782s    20x  tests/ace/tui/modals/test_memory_panel.py
       1.775s    40x  tests/test_ace_testing.py
       1.767s    21x  tests/ace/tui/test_usage_header.py
       1.665s    12x  tests/ace/tui/test_projects_pane.py
       1.650s    13x  tests/test_prompt_normal_mode_quote_bracket_objects.py
       1.614s    14x  tests/ace/tui/test_config_center_resume.py
  by sase.config.core.load_merged_config:
       1.905s    36x  tests/main/test_doctor_command.py
       0.230s   453x  tests/test_bead/test_cli_show_style.py
       0.097s   394x  tests/test_managed_tmp_reaper.py
       0.082s    98x  tests/ace/tui/test_agents_filter_bar_session.py
       0.080s    76x  tests/completion/test_build.py
       0.078s   156x  tests/test_bead/test_cli_show.py
       0.073s    60x  tests/main/test_parser_monitor.py
       0.070s   116x  tests/test_bead/test_cli_note.py
       0.068s   931x  tests/main/test_init_memory_markdown_templates.py
       0.066s    17x  tests/test_commit_workflow_checkpointing.py
  by AcePage.__aexit__:
       4.001s    20x  tests/ace/tui/test_plugins_browser_pane_loading.py
       2.550s    10x  tests/ace/tui/test_plugins_browser_pane_agent_clis.py
       2.404s     8x  tests/ace/tui/test_config_pane_widget_jump.py
       2.325s     4x  tests/ace/tui/test_feature_flags_pane_journeys.py
       2.152s     7x  tests/ace/tui/test_artifacts_relation_collapse_interactions.py
       1.826s    35x  tests/test_ace_testing.py
       1.817s    21x  tests/ace/tui/test_usage_header.py
       1.711s    12x  tests/ace/tui/test_projects_pane.py
       1.618s    15x  tests/ace/tui/test_plugin_action_confirm_modal.py
       1.617s    13x  tests/ace/tui/test_config_center_resume.py
  by sase.main.parser.create_parser:
       2.255s     9x  tests/main/test_doctor_command.py
       1.974s    14x  tests/test_mobile_gateway.py
       1.929s    50x  tests/completion/test_update_refresh_soak.py
       1.821s    14x  tests/test_bead/test_task_beads.py
       1.761s    11x  tests/main/test_skills_handler.py
       1.757s    22x  tests/test_bead/test_cli_at_path_values.py
       1.611s    11x  tests/test_bead/test_cli_close_phases.py
       1.579s    12x  tests/main/test_memory_cli_show.py
       1.528s     9x  tests/main/test_agents_dispatch_handler.py
       1.450s     9x  tests/test_bead/test_cli_update_bulk.py
  by Pilot.pause(None):
       4.488s    67x  tests/test_models_panel_selector_builder.py
       3.377s    44x  tests/test_models_panel_override_flows.py
       2.634s    25x  tests/test_models_panel_edit_custom.py
       2.632s    39x  tests/test_notification_modal_scroll.py
       2.459s    39x  tests/test_models_panel_jump.py
       2.063s    29x  tests/test_models_panel_edit.py
       1.902s    44x  tests/test_approve_options_modal_state.py
       1.810s    32x  tests/test_model_picker_modal.py
       1.746s    36x  tests/test_command_palette_modal.py
       1.595s    49x  tests/pager/test_app_history.py
  by YAML load:
       3.736s  5328x  tests/ace/tui/widgets/test_vim_normal_key_containment.py
       1.242s  5171x  tests/main/test_init_skills_sources.py
       0.900s   959x  tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py
       0.775s  3426x  tests/main/test_init_memory_task_types_note.py
       0.769s   980x  tests/test_bead_xprompt_tags.py
       0.680s   480x  tests/test_pooled_alias_single_consumption.py
       0.546s  1632x  tests/test_bead/test_work_queue_capacity.py
       0.531s  2382x  tests/main/test_init_memory_plan.py
       0.456s  2112x  tests/main/test_init_memory_commit.py
       0.432s  1940x  tests/main/test_init_memory_bead_note.py
  by subprocess.Popen:
       0.155s     2x  tests/test_agent_name_wipe.py
       0.049s    67x  tests/test_xprompt_model_alias_shortcut_parity.py
       0.030s    34x  tests/test_procs_service.py
       0.028s    49x  tests/sdd_store/test_sidecar_bead_adoption.py
       0.025s    31x  tests/test_xprompt_directive_completion_parity.py
       0.022s    38x  tests/sdd_store/test_materialize.py
       0.019s    28x  tests/test_bead/test_workspace_sidecar_bead_eviction.py
       0.018s    26x  tests/llm_provider/test_grok_usage_probe.py
       0.014s    21x  tests/llm_provider/test_codex_usage_probe.py
       0.011s     3x  tests/test_axe_chop_runner_script.py
  by ACE pause_until_cpu_idle:
       0.001s     1x  tests/test_ace_wait.py
       0.000s     1x  tests/test_a.py
  by gettext.find:
       0.000s     1x  tests/ace/tui/artifact_file_viewer/test_entrypoint.py
       0.000s     1x  tests/test_patch_set_origin_cli.py
       0.000s     1x  tests/fakey/test_gate_capacity_custom_e2e.py
       0.000s     1x  tests/test_core_health.py
       0.000s     1x  tests/test_axe_status_cli.py
       0.000s     1x  tests/agent_clis/test_cli_install.py
       0.000s     1x  tests/test_select_tests_tool.py
       0.000s     1x  tests/prompt_command/test_parser.py
test cost budget regression: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260914T202651Z-3874423.json
budgets: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/tests/perf/baselines/test_cost_budgets.json
- [hard] total_file_cpu_seconds: actual 3307.857 exceeds budget 2600.000 + 25% tolerance (3250.000)
- [hard] causes.ace_page_enter.cpu: actual 1127.463 exceeds budget 840.000 + 25% tolerance (1050.000)
- [hard] causes.textual_app_run_test_enter.cpu: actual 895.853 exceeds budget 690.000 + 25% tolerance (862.500)
test cost budget advisories: /home/bryan/.sase/test-selection/gh_sase-org__sase/timings/cost/20260914T202651Z-3874423.json
wall-clock overages usually mean the host was busy, not that the suite got more expensive; the cpu/count figures alongside each entry are contention-stable, so compare them to tell the two apart.
- [advisory] total_file_wall_seconds: actual 5707.817 exceeds budget 4700.000 + 15% tolerance (5405.000) (cpu=3307.857s)
- [advisory] causes.ace_page_enter: actual 1127.581 exceeds budget 540.000 + 15% tolerance (621.000) (cpu=1127.463s, count=756)
- [advisory] causes.ace_settle_pilot: actual 516.994 exceeds budget 340.000 + 15% tolerance (391.000) (cpu=481.950s, count=8864)
- [advisory] causes.pilot_pause_delay: actual 458.820 exceeds budget 230.000 + 15% tolerance (264.500) (cpu=423.915s, count=18111)
- [advisory] causes.textual_app_run_test_enter: actual 894.547 exceeds budget 470.000 + 15% tolerance (540.500) (cpu=895.853s, count=3945)
- [advisory] causes.yaml_load: actual 25.884 exceeds budget 20.000 + 15% tolerance (23.000) (cpu=25.832s, count=58938)
error: recipe `test-cost` failed on line 424 with exit code 1
error: recipe `check-full` failed on line 686 with exit code 1

