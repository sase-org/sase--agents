# Chat History - ace-run (research.5.cld)

- **TIMESTAMP:** 2026-09-03 17:29:58 EDT
- **MODEL:** claude/opus
- **AGENT:** research.5.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260903_171140.md`

## Prompt

%id(cld, clan=research.5) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I've been thinking about ways we could allow sase to dispatch
to other known machines so the user can open up one TUI on one machine and manage all of
their agents across all machines.

- In practice, I plan to use this to manage all (e.g. launch, view, kill, etc...) sase
  agents that are running on any of my Tailscale devices from the `sase ace` TUI on my
  MacBook.
- We can therefore rely on the machines having their names or IP addresses configured
  somewhere and will likely need a lightweight, fast way of communicating between the
  different devices (ZeroMQ would be my choice, but do your own research to determine
  which external framework, if any, we should use).
- Some lag is to be expected across network devices. But, once fully synced, I should be
  able to view and manage (e.g. from the "Agents" tab in the TUI) sase agents running on
  different machines in all of the same ways I can view and manage sase agents that are
  running on the local machine (i.e. the same machine as the TUI).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Make sure that the solution you
recommend is reliable and robust. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding the existing SASE architecture — how agents are tracked, how the ACE TUI reads them, and where the Rust core boundary sits — then research transport options.

Good — I have the format. Now let me dig into how SASE tracks and manages agents today.

This is a major finding — there's already a `sase_gateway` daemon. Let me examine it closely.

Now let me research the transport landscape.

I have a comprehensive evidence base. Let me verify a few final citation details.

Now I'll write the research report.

Research written to `sase/repos/research/202609/cross_machine_agent_dispatch.md`.

## What I found

**SASE has already built most of this twice, and neither copy is connected to the TUI.**

1. `sase-core/crates/sase_gateway` is an 11,229-line axum daemon that already serves `GET /api/v1/agents`, `POST /api/v1/agents/launch`, `.../kill`, `.../retry`, and SSE — behind device pairing and bearer tokens. Its own bind-policy error already says *"only for explicit LAN or **tailnet** exposure."*
2. The ACE Agents tab already has a **provider seam designed for exactly this**: `AgentsProviderSnapshot.used_daemon`/`fallback_reason`, `AgentEventApplyResult.resync_required`, `AgentsViewport`. The factory returns only the direct provider and `agents_daemon_reads_enabled()` is a hard `False`.
3. Machine identity is solved — `~/.sase/machine_name` is already `kellys_mbp` / `apollo`, and `machine_hood.rs` qualifies names as `<machine>.<name>`.

## The decisive measurement

I measured against your live tailnet:

| | |
|---|---|
| `tailscale ping apollo` | **32 ms**, direct P2P (no DERP) |
| `sase mobile agent-bridge list-agents` on apollo | **~3.8 s** |
| `ssh apollo sase agent list --json` | 6.77 s cold, **5.51 s** warm with ControlMaster |

**The network isn't the bottleneck — the process model is.** The gateway forks a fresh Python interpreter per request (`host_bridge.rs:186`), costing ~120× the round trip. ControlMaster only saved 1.2 s of 6.8 s, because the remaining 4.8 s is remote interpreter startup. Any framework choice is downstream of fixing that.

## Recommendation: not ZeroMQ

Promote the gateway into a per-machine `sase node` daemon, **serve agent reads resident from the Rust `agent_scan` SQLite index** instead of forking Python, add a real change feed, and light up the existing provider seam.

ZeroMQ loses on five counts, but chiefly: it solves framing when your problem is a 3.8 s fork; it adds a C dependency to a deliberately 13-dependency Python project (which has no HTTP client at all — `mobile_gateway.py` uses stdlib `urllib`); libzmq's last stable release is **4.3.5, Oct 2023** with an unresolved July 2026 thread asking if it's still maintained; and Tailscale already gives you the encryption, identity, ACLs, and MagicDNS naming that CURVE would reinvent.

Two things I'd flag as the real risk, both in the report:

- **The SSE stream is not a change feed today.** `AgentsChanged` fires *only* as an echo of the gateway's own mutations — an agent launched by a local TUI or a chop emits nothing. A MacBook watching apollo this way would miss nearly every real change. §6.6 proposes an index generation cursor.
- **`athena` is offline right now** (3 days). The report insists on a two-plane design — live daemon plus the existing git sidecar — so an agent never vanishes because its machine did.

Three open questions I couldn't resolve for you are listed in §10, the sharpest being whether remote `tmux` attach should refuse cleanly or shell out to `ssh -t`.

Sources: [libzmq releases](https://github.com/zeromq/libzmq/releases) · [zeromq-dev status thread](http://www.mail-archive.com/zeromq-dev@lists.zeromq.org/msg31708.html) · [NATS leaf nodes](https://docs.nats.io/running-a-nats-service/configuration/leafnodes) · [Tailscale Serve](https://tailscale.com/docs/features/tailscale-serve) · [Tailscale identity](https://tailscale.com/docs/concepts/tailscale-identity)
