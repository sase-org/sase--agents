# Chat History - ace-run (research.0t.cld)

- **TIMESTAMP:** 2026-08-21 09:43:38 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.0t.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260821_092709.md`

## Prompt

%id(cld, clan=research.0t) %wait(priority=20) %m:@research_b  #gh:gh_sase-org__sase I want to investigate and close out all of the remaining open sase feature flags, which represent deprecations and/or new features (some of which have been enabled already and others which are off by default). I already have some agents working on the `artifact_links` and `pluggable_finalizers` feature flags, so those are being handled. Can you do some research with the goal of helping me understand what needs to be done to get rid of the rest of the feature flags? End your analysis with a list of next steps associated with each open feature flag (except for the two that are already being worked). Keep your report concise and practical. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by reading the flag memory, glossary, and research-artifact skills so the report matches how SASE tracks flags and where the write-up belongs.

The research-artifact skill path didn’t resolve; I’ll locate it and load the flag memory plus glossary next.

Flag lifecycle is loaded. Next I’ll inventory open flags and inspect the research sidecar so the report lands in the right place.

Nine flags are registered; I’ll skip the two already in progress and open the research sidecar plus each remaining flag’s dossier.

The flag-show sweep is still running. I’ll pull existing flag research, beads, and the registry in parallel while it finishes.

Flag show is in. Next I’ll pull each flag bead, the real config (not the env snapshot), and the gated call sites.

The env snapshot is lying about “overrides.” I’ll read the registry, overlay, and call sites next so we know which flags are actually opted in.

Beads are loaded. I’ll inspect call sites, both-state tests, related epics, and whether any soak evidence already exists.

This is a research swarm. I’ll check the xprompt output convention so my report lands as the B draft the consolidator expects.

The swarm expects `research.0t.cld.md`. I’ll collect soak evidence and the remaining blockers, then write that file.

I have enough to write the close-out report. Next I’ll save it as the swarm’s B draft and register it as an artifact.

Nine flags are open. Two are already being retired (`artifact_links`, `pluggable_finalizers`). The other seven can be closed without waiting for `FlagTriage` (~85 days / v0.18.0): flag beads stay `open`, and `sase bead work <id>` can launch a removal worker today.

Durable config has **no** `feature_flags:` overrides. This ACE process currently forces on only `artifact_links`, `pluggable_finalizers`, and `completion_refresh_on_update`; that soak dies on restart unless it is written to user config.

Full write-up: `research:202608/research.0t.cld.md` (`file:explicit:d8bb2fb38575555a49421331`).

**Recommended order**

| Flag | Bead | What to do |
| --- | --- | --- |
| `plugin_catalog_scoped_latest` | `sase-qq` | **Remove now.** Scoped path is implemented, tested, and CI-pinned. Off is the leftover full-catalog PyPI storm. |
| `prettier_enabled` | `sase-qf` | **Remove now**, after rewriting visual/fakey tests that still set `SASE_DISABLE_PRETTIER`. Nobody uses that escape hatch outside tests. |
| `commit_finalizer_shared_clone_exempt` | `sase-qi` | **Remove now** unless a real discard has already been mislabeled as a shared-clone race. |
| `completion_refresh_on_update` | `sase-qg` | **Remove now.** On is non-fatal, already on in this ACE, and skips chezmoi-owned stamps. |
| `ref_sync_gesture` | `sase-qu` | **Remove now** if `@kind::` has not eaten a real colon; otherwise Extend to 0.18.0. The bead asked for two minor releases of soak. |
| `epic_resume_gate` | `sase-qh` | **Enable, then soak.** The chop currently no-ops every five minutes with `reason=flag_disabled`. Do not delete the flag until one real stall has gated cleanly. |
| `coder_inherits_planner_chat` | `sase-qe` | **Product decision.** Off (plan-file-only) is today's documented default; On restores old `#fork`. Keep it as a config field, or Remove with `winner=disabled`. Do not make `#fork` unconditional without soaking. |

Leave `artifact_links` (`099--plan`) and `pluggable_finalizers` (epic `sase-rr`) alone. Each Remove change should delete the Off branch, drop the registry entry, sync the schema, update tests/docs, and close the flag bead in the same commit — same pattern as the Admin Center ConfigHub and Launch retirements.
