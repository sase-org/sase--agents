# Chat History - ace-run (research.q.cld)

- **TIMESTAMP:** 2026-07-29 18:02:15 EDT
- **MODEL:** claude/opus
- **AGENT:** research.q.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260729_174829.md`

## Prompt

%id(cld, clan=research.q) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I've been thinking a lot about codex sites and how SASE can take inspiration from that. Can you do some research with the goal of helping me understand the best way to implement SASE sites?

- We already have agents, beads, and plans sidecar repos. I want to use this to support the ability to create a SASE site that encapsulates all knowledge from these repos in one site, with multiple tabs of course and other niceties.
- I also want to write a /sase_sites xprompt skill that allows agents to fetch and create new sase sites.
- I'm thinking we should create a new sase web server to support this new functionality but use your best judgment.

End your analysis with a recommended solution including a high-level design/plan. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll research this. Let me start by understanding the current SASE codebase structure, the sidecar repos, and what "codex sites" refers to.

I have what I need. Let me write up the research.

Research written to `sase/repos/research/202607/sase_sites_design_research.md`. (No `just check` — new research markdown only.)

## Headline finding

**SASE already ships a site.** The four sidecars are ~21,400 cross-linked Markdown documents rendered deterministically into Git and browsed on GitHub. The knowledge graph and its edges already exist and are already maintained transactionally — plan header blocks (`PROMPT`/`PARENT`/`AGENTS`/`COMMITS`), bead lineage pages with Mermaid graphs, agent/family pages with neighbors, `SASE_BEAD`/`SASE_AGENT` commit trailers, and `hosted_links.py` resolving cross-repo URLs.

The gap is **presentation and query**, not data plumbing. That reframes sites as a new frontend over an existing, already-Rust-backed model.

## The scale number that decides the architecture

Measured on this machine, for the `sase` project alone: 3,303 plans + 2,800 prompt snapshots + 299 research notes + 2,311 bead pages + 12,585 agents-sidecar markdown files (33,693 files total) + 77 docs ≈ **21,400 documents / ~80 MiB of Markdown**.

This kills the two obvious implementations: mkdocs (per-page Python render + monolithic search index + `strict: true` over 21,400 docs) and naive one-HTML-file-per-doc static export (Cloudflare Workers allows 20,000 assets free / 100,000 paid).

## Recommendation: don't build a new web server

- **Index-first.** New `sase_core::site` module: node/edge schema over the existing artifact-ref grammar, SQLite via the `rusqlite` already in the workspace (a derived cache like `beads.db`), incremental by blob SHA. Reuses `sase_core::{plan,bead,query,artifact_ref,agent_scan}`.
- **One model, two render targets** — deliberately mirroring `mkdocs serve`/`build`: deterministic static export as the *primary* artifact, plus a `/sites` router on the **existing** axum `sase_gateway`. That daemon already has `mobile_http_enabled` as a feature flag, a non-loopback bind refusal, pairing/bearer auth, an audit log, SSE, and a committed contract snapshot. A FastAPI server would violate the recorded Rust core boundary and duplicate all four.
- **Two site kinds:** `project` (generated, tabs mirroring ACE, corpus tabs *derived from the store record* since document roles are generic) and `custom` (agent-authored).
- **Authored sites are declarative projections, not web apps** — the key divergence from Codex Sites. A ~30-line `SiteSpec` YAML plus prose, data sourced through the ACE query language, rendered from a fixed widget vocabulary (`table`, `board`, `graph`, `metric_row`, `gallery`, …). Deterministic, PR-reviewable, golden-testable, no arbitrary JS. Covers every artifact type Codex users build.
- **Steal from Codex:** save/deploy separation with commit-tied versions; graduated visibility, private by default.

## Sharpest risk

A naive unified public site would publish **2,984 chat transcripts and 5,389 agent prompts** irreversibly into Git. The design excludes agent prompts/chats/variables by default and makes `sase site build` *refuse* public/sidecar visibility when the agents sidecar is configured `visibility: private`.

Also flagged: avoid "codex" as a SASE noun — it's already a supported agent-provider name.

The plan is six phases (spike → index+static → agents/search/graph → serve → authored sites + `/sase_sites` skill → publishing), plus a cheap interim win (generated cross-sidecar root index) available in one small change. `/sase_sites` is modeled on `/sase_repo`'s hard contract — use the printed path, never edit generated output, **never deploy** (propose via `/sase_gate`).

Four open questions are listed at the end, including whether the `sase` project's own site should be public.

Sources: [ChatGPT/Codex Sites docs](https://learn.chatgpt.com/docs/sites), [Kingy AI guide](https://kingy.ai/news/openai-sites-a-detailed-guide-to-codexs-new-hosted-website-and-app-builder/), [Taskade](https://www.taskade.com/blog/codex-sites-explained), [Stacktree](https://stacktr.ee/blog/sites-in-codex-explained), [Cloudflare asset limits changelog](https://developers.cloudflare.com/changelog/2025-09-02-increased-static-asset-limits/), [Workers Static Assets](https://developers.cloudflare.com/workers/static-assets/), [DeepWiki docs](https://docs.devin.ai/work-with-devin/deepwiki), [Codersera DeepWiki guide](https://codersera.com/blog/deepwiki-complete-guide-2026/).

I made that research file, so I'll commit it.

Committed and pushed. Working tree is clean and in sync with `origin/main`.

- `832bda6 docs(research): design SASE sites over the sidecar corpus` — adds `202607/sase_sites_design_research.md` to the research sidecar.
- Agent-hood publication was queued (the agents sync lock was busy) and will retry automatically; the primary commit and push both succeeded.

One thing worth flagging: the rebase pulled in an upstream commit immediately beneath mine, `2ccd5ff docs(research): design SASE Sites architecture`. Someone (or another agent) wrote a separate SASE Sites design note concurrently.

That commit is `202607/sase_sites_architecture.md` (657 lines) — a parallel research note on the same question, landed independently. My note is `202607/sase_sites_design_research.md` (660 lines). Both are now in `main`; neither overwrote the other. You may want to reconcile them into one canonical design, since they were written without knowledge of each other and could recommend different architectures.
