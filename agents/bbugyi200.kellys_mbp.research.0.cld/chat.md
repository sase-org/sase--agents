# Chat History - ace-run (research.0.cld)

- **TIMESTAMP:** 2026-09-02 14:32:00 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0.cld
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260902_140733.md`

## Prompt

%id(cld, clan=research.0) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase Sase agents that I ran on my `athena` machine are not being
synced to this machine correctly or something is (likely) wrong at the architectural
level. These sase agent (see the `~/tmp/screenshots/20260902_124640.png` screenshot for
context), for example, look wrong. When completed agents are synced from another
machine, they should be in a dismissed state by default (i.e. should not be visible on
the "Agents" tab), should be **fully** revivable (make sure we persist all of the
necessary artifacts for this--the fact that we are showing `*--code` agent shells which
clearly belong to agent families, as root nodes is concerning), and should have agent
names that are properly scoped for the currently configured machine/user (stripping
`bbugyi200.` from the agent hoods is appropriate for this machine, for example, but not
if a different username were configured).

Can you do some research with the goal of helping me fix this issue and sase's
architecture, if needed, to support these requirements? End your analysis with a
recommended solution. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by looking at the screenshot for context and getting oriented in the repo.

I have a complete causal chain. Writing the research report now.

Research written to `sase/repos/research/202609/cross_machine_agent_history_import.md`.

## What's actually happening

The three symptoms are one bug with three faces. `athena` publishes its history **twice** — a complete modern **v2** payload (1,963 hood packages, 9,183 run pages, 1,046 family containers) and a **stale legacy v1** manifest frozen since 2026-07-23. This machine imported **only v1** — all 338 of it — and **zero** v2.

The v1 shim is lossy by construction: no dismissal, no dismissed bundle, no saved family group, no prompt in the wire at all, no `parent_timestamp`, and — the giveaway in the artifact — it writes `name: "athena.7n--code"` next to `agent_family: "7n"`. Those are two different namespaces, so the `--code` member can never attach to its family and renders as a root row.

**The keystone finding:** the v1 import is self-perpetuating. It wrote 651 `origin: import_v1` entries into the name registry (97% of this machine's registry), and `ensure_import_namespace_available` tolerates v1-over-v1 but **not v2-over-v1**. I confirmed it by running the planner read-only:

```
00 -> ImportedNameCollisionError: 'athena.00' collides: owner namespace 'athena' is already occupied
```

All 364 `athena.*` entries offend. The 1,948 hoods behind your `⇅ 1948` badge can never land. The machine is wedged on the broken path with no supported exit — there's no command to forget a v1 import.

Two more things worth knowing: 287 bare local names (`06`, `0j`, …) are now permanently reserved on this machine by athena's *unlocalized* family names, and dismissing those rows re-globalized them as `bbugyi200.kellys_mbp.athena.06--code` — athena's runs now assert they ran here.

## On the naming requirement

`localize_agent_name` already does exactly what you asked — `bbugyi200.` is stripped precisely because the configured username matches, and a different username keeps it. What's broken is what happens *after*: the prefix is plain text in the same dotted namespace as hoods, so `agent_local_hood("athena.7n--code")` returns `athena`. Every athena run collapses into one fabricated hood (71 today, 9,484 once v2 lands). And `foreign_agent_owner_root` returns `None` — SASE holds 1,963 athena hood packages and still doesn't know `athena` is a machine, because sibling machines are discovered only from config overlay files that happen to exist locally.

## Recommendation

Five workstreams, sequenced. The lead item is three lines: `collect_owner_namespace_entries` uses `setdefault`, which can't upgrade the untyped `auto_prefix` root that the registry rescan creates — that alone defeats any correct guard. Then a **v1→v2 adoption rule** so wedged machines heal on the next `sase agent sync` instead of needing a purge; **retire v1 as an import source** (I verified all 238 v1 hoods are covered, so `sase agent retire-v1 --apply` on athena passes its gate); a **typed `OwnerRoot` in sase-core** so parsing takes the known-root set and returns owner and hood separately; and publishing `raw_xprompt.md` at *launch* rather than opportunistically at publication — 35% of published run pages have no prompt because the artifact was cleaned first.

Two out-of-scope defects I hit and documented but did not file as beads (say the word and I will): 15 hoods quarantine on a `chat.md` digest mismatch, all on `--mon` members — a publisher-side race on athena. And `sase memory read` is fully broken on this machine: `/Users/bbugyi/memory` and `/Users/bbugyi/sase/memory` both exist, so home discovery raises `LayoutCollisionError` before any project read can run.
