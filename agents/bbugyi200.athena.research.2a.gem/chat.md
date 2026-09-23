# Chat History - ace-run (research.2a.gem)

- **TIMESTAMP:** 2026-09-23 07:24:08 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.2a.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260923_071242.md`

## Prompt

%id(gem, clan=research.2a)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.2a.cld`, `research.2a.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about migrating my apollo
Digital Ocean droplet to a more powerful machine where sase agents can work faster. I
did some research a few weeks ago related to this when I originally upgraded that
machine. I had originally intended for this upgrade to be temporary but now I am
thinking that I will find having a second devlopment machine useful long-term. I think
in order to upgrade the apollo machine I need to upgrade the disk, which means I need to
reprovision/re-create the machine, right? I want to make sure that I have scripted as
much of this as possible so I can spin up a third machine with an identical setup in as
few steps as possible.

Can you do some research with the goal of helping me decide the best way to do this? End
your analysis with a recommended solution (i.e. steps to upgrade the machine and a plan
to automate the machine's setup). 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Apollo Droplet Upgrade and Fleet Automation Research (`research.2a.gem`)

The research report has been completed, written to disk, and registered as a durable SASE artifact snapshot.

- **Report Path:** [`apollo_droplet_upgrade_and_setup_automation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/repos/research/202609/apollo_droplet_upgrade_and_setup_automation__gem.md)
- **Artifact Label:** `research:202609/apollo_droplet_upgrade_and_setup_automation__gem.md`
- **Artifact Ref:** `file:explicit:052c1a9569f97dcc047fcff3`

---

## Key Findings & Direct Answers

### 1. Does upgrading `apollo` require upgrading the disk?
**No.** DigitalOcean provides **CPU/RAM-Only (Flexible) Resize**.
- You can upgrade `apollo` from its current 16 vCPU / 32 GiB RAM configuration to 32 vCPUs / 64 GiB RAM (`c-32`) or 48 vCPUs / 96 GiB RAM (`c-48`) while keeping the existing 200 GiB SSD root disk completely unchanged.
- **Reversibility:** CPU/RAM-only resizes are **100% reversible**. You can scale up during heavy workloads and scale back down anytime without data loss.

### 2. Does upgrading the disk mean reprovisioning / re-creating the machine?
**No.** DigitalOcean supports **in-place disk enlargement** ("Disk, CPU, and RAM" permanent resize).
- To expand the root disk, you simply power off the droplet, resize it in the DO Control Panel or via `doctl`, and power it back on. DigitalOcean's hypervisor, kernel, and `cloud-init`/`growpart` automatically resize the partition and `ext4` filesystem (`/dev/vda1`).
- Zero files, packages, user configs, SSH keys, or network identities are lost. The IP address and Tailscale node identity remain identical.
- **The Catch (Irreversibility):** Unlike CPU/RAM-only resizes, **disk upgrades in DigitalOcean are permanent and irreversible**. You cannot downsize a root disk once expanded. If you enlarge `apollo`'s disk to 400 GiB (`c-32`) or 600 GiB (`c-48`), the droplet is permanently locked into a billing floor of at least $1.00/hr (~$720/mo) or $1.50/hr (~$1,080/mo).

### 3. Is root disk expansion even necessary?
**No, and detachable block storage is a better alternative.**
- **Live Disk Probe:** `apollo` currently has **74 GiB free** (63% utilization).
- **Ephemeral SASE Bloat:** **63 GiB** of used space on `apollo` is ephemeral: **43 GiB** in stale numbered workspace clones (`~/.local/state/sase/workspaces/`) and **20 GiB** in temporary caches (`~/.cache/sase/tmp/`). Pruning stale workspaces immediately frees up substantial headroom.
- **Detachable Block Storage:** If you need extra disk space long-term, attaching a **DigitalOcean Block Storage Volume** (NVMe SSD, $0.10/GiB-month; e.g. 200 GiB for $20/month) mounted at `~/.local/state/sase/workspaces` is far superior to root disk expansion. Volumes expand online dynamically without reboots, can be detached or moved between droplets, and avoid locking the compute tier.

---

## Recommended Solution

### Phase 1: In-Place Upgrade of Apollo (5 Minutes, Reversible)

Do **not** destroy, recreate, or reprovision `apollo`. You can double its agent throughput immediately:

1. **Quiesce services and reclaim ephemeral disk space:**
   ```bash
   ssh apollo
   sase axe stop
   sase service stop
   rm -rf ~/.local/state/sase/workspaces/* ~/.cache/sase/tmp/*
   sudo poweroff
   ```
2. **Execute CPU/RAM-Only Flexible Resize to `c-32`:**
   ```bash
   # From your local machine with doctl (or via DO web console):
   doctl compute droplet-action resize 568763576 --size c-32 --resize-disk=false --wait
   doctl compute droplet-action power-on 568763576 --wait
   ```
3. **Verify and restart services:**
   ```bash
   ssh apollo
   nproc        # 32 vCPUs (doubles test worker concurrency from 14 to 28)
   free -m      # 64 GiB RAM
   sase service start
   sase axe start
   ```

---

### Phase 2: Fleet Setup Automation for a Third Machine

A two-stage automation workflow enables spinning up an identical third machine (e.g. `artemis`) in a single command.

#### 1. Cloud-Init Template (`cloud-init-sase.yaml`)
Automates root-level OS bootstrapping, package installation, user `bryan` creation, systemd linger, and Tailscale join:
```yaml
#cloud-config
hostname: artemis
manage_etc_hosts: true

users:
  - name: bryan
    gecos: "Bryan Bugyi"
    sudo: ALL=(ALL) NOPASSWD:ALL
    shell: /bin/zsh
    ssh_authorized_keys:
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDI1y8msQy8gFD2ijZQRQ81SPBpNwd420Akn0hVH35mNkX/TNGg/UeCYCgma+K0xYC0efbqhvSMYMqwoGnP23PrzinfQuWsivpYf7JHr2a9TB+Df9RJH9VyuTL57RqYvON8U86yfQMfqt3T4Nf61DXtTw5z0g+f3gLDmiqjgVnkwGF/BGeEKN+et1umOX90cprI/jZCAx8dqh31yh3AHTX6gtf82beoMqt2iOLdiTTuQxMyuYh15jqqxNun/N2B7vZJeTSzR6VJ/zpffWlUMiWNNnQQoLIDPHYfUldo6u9iNtrLE3nVubeUi8s7TjU9JGIt315RN1H5MULq2RazYnXVoQz94IwFaIXNc4gj1ge+3IbZ4cSVnruQ93US+2B8gF5IwBaL2y3jhMLsY51VvQ3uwhoq4hwQPG9VeMLsC6F4mI7hfc9zfLoQQ2NgfKg2Ude+oMHQxZv518UnUwZ+mxxS/ijcBk/GfD8xJ3Ax9+DlR8CuHHVYhiKqMZ630CLxszc= bbugyi@bbugyi-mac.roam.internal

packages:
  - build-essential
  - pkg-config
  - libssl-dev
  - git
  - curl
  - wget
  - unzip
  - tmux
  - zsh
  - jq
  - ripgrep
  - fd-find
  - cmake
  - ninja-build
  - gettext
  - fontconfig
  - fonts-firacode

runcmd:
  - loginctl enable-linger bryan
  - curl -fsSL https://tailscale.com/install.sh | sh
  - tailscale up --authkey=<reusable-tskey> --ssh --hostname=artemis
```

#### 2. User-Level Bootstrap Script (`bootstrap-sase-host.sh`)
Automates toolchains (`uv`, `rustup`, `just`, `chezmoi`, `node`), clones SASE repositories, compiles `sase-core-rs`, installs SASE via `uv tool install --editable`, and initializes SASE services.

#### 3. Chezmoi Gaps to Address Before Adding a 3rd Host
In [`bbugyi200/dotfiles`](https://github.com/bbugyi200/dotfiles):
- **`.chezmoiignore`**: Currently ignores `.config/sase/sase_<hostname>.yml` and `.ssh/tailnet.conf` unless the hostname is `athena`, `apollo`, or `Kellys-MacBook-Pro`. Add the 3rd hostname to the ignore whitelist.
- **`private_tailnet.conf`**: Add a host entry for the new machine's tailnet domain (e.g. `artemis.tail297af1.ts.net`).
- **`sase_<hostname>.yml`**: Create `home/dot_config/sase/sase_artemis.yml` defining the machine ID and enabled services (`gateway: enabled: true`).

See the full report in [`apollo_droplet_upgrade_and_setup_automation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/repos/research/202609/apollo_droplet_upgrade_and_setup_automation__gem.md) for full script contents, configuration schemas, and workload benchmarks.
