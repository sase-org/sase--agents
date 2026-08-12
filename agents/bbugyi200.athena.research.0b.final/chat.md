# Chat History - ace-run (research.0b.final)

- **TIMESTAMP:** 2026-08-12 13:23:45 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0b.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_123932.md`

## Prompt

%id(final, clan=research.0b) %wait(priority=20) %m:@research_lead
%wait:research.0b.cdx %wait:research.0b.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I recently made some improvements to the "Artifacts" tab (see
the sase-js epic bead for context) and would like to continue improving these sub-tabs
by adding new functionality. Before doing that however, I think it's a good idea to try
to unify these sub-tabs as much as possible by providing a similar interface for each
for users and a practical contract for artifact ref type designers to follow to make
sure new sidecar repo tabs follow the same standard. Can you do some research with the
goal of helping me decide the best way to implement this? End your analysis with a
recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0b.cdx` -> `__a`, `research.0b.cld` -> `__b`), then read both reports.
   Never assign `__a`/`__b` from filesystem order.
2. Research the request yourself, prioritizing gaps, weak evidence, and disagreements
   between the two reports.
3. Pick a descriptive stem `<name>` that collides with nothing in the month directory
   (do NOT end the name with `_consolidated` or `_<YYYYmmdd>` or anything similar unless
   it relates to the research topic), create `<month-dir>/<name>/`, and move the two
   reports to `<name>__a.md` and `<name>__b.md` inside it. Preserve both files and never
   overwrite: on any collision, pick a different stem first.
4. Write the consolidated report to `<name>/<name>.md`: merge the strongest findings
   from both reports and your own research, resolve conflicts, cut duplication, and add
   missing critical context without unnecessary length.

Final layout:

```text
<month-dir>/<name>/
├── <name>__a.md
├── <name>__b.md
└── <name>.md
```

## Response

I'll start by reading both researcher transcripts to identify their report files.

Both reports are read. Now let me verify their concrete claims and dig into the areas where they disagree.

All claims verified, plus several new findings. Now setting up the output directory.

Now writing the consolidated report.

Consolidated report written to `sase/repos/research/202608/artifacts_pane_contract/artifacts_pane_contract.md`, with both source reports preserved beside it (`__a` = `research.0b.cdx`, `__b` = `research.0b.cld`, assigned from the transcripts). The sase workspace tree is clean — `sase/repos/` is gitignored, so no `just check` was needed.

## Where the two researchers agreed

Both independently reached the same diagnosis: **`sase-js` shipped a dynamic tab *registry* but not a dynamic *pane*.** `provider_spec` is carried all the way into `ArtifactsDocumentsPane.__init__` and read by nothing — I confirmed this is the entire set of hits in the ACE tree. Both also agree Patches should stay contract-exempt, and both reject letting plugins ship Textual code.

## Conflicts I resolved

**Rust vs. Python for the contract** was the sharp one — `__a` put typed coercion and a normalized browse wire in `sase-core`; `__b` argued presentation belongs in Python per `rust_core_backend_boundary`. Reading `crates/sase_core/src/artifact_ref/` shows they're each right about a different half: `ref.pane` is Textual presentation → Python, but `ArtifactEntryWire.properties` is `BTreeMap<String, String>`, so the spec validates that `updated_time` is a `datetime` and then the wire flattens it to a string. That's the one genuine core change, and it's new work — the entry wire is currently constructed only in a Rust unit test.

**Digits**: `__a` said drop them, `__b` said derive from a declared `order`. Order-derived digits still shift when a new provider's order lands between two existing ones, so I recommend persisted per-kind allocation and flag it as an open decision.

## What my pass added

- **A new defect**: `_provider_label` pluralizes with a naive `+ "s"`, so the tab reads **"Researchs"**. `__b` reported it as "Research" — that was inferred, not executed.
- **A trap in both recommendations**: the spec digest comes from Rust, which drops keys it doesn't model. A Python-only `ref.pane` block **won't change `provider_spec_digest`**, so the digest-keyed caches both reports recommend wouldn't invalidate on a pane-block edit. Needs a separate `presentation_digest` designed in.
- **A correction that makes Phase 0 cheaper**: `__b` said provider loss has "no doctor finding". `sase doctor -C config.repos` already fires — verified live in this workspace. ACE is discarding an existing diagnostic. The genuinely uncovered path is `sase_core_rs` being unimportable, which I reproduced: the bare `except` swallows the ImportError and the degraded four-tab result then gets *cached* under a stable `("unavailable",)` token.
- **The cheapest high-value change, verified end to end**: frontmatter is already parsed into a `dict[str, str]` on each row and rendered through `ordered_plan_property_items`, a pure sort against a plan-specific constant. Parameterizing that one function by `detail.fields` makes the detail band spec-driven with no spec change, no Rust change, no new plumbing. I broke it out as Phase 0.5.
- Smaller: the `ref:*` → `artifacts_plans` shim is in **five** places, not three; inline `ref: pane:` would be rejected today by the `_KNOWN_REF_CONFIG_KEYS` allowlist while a `use:` spec wouldn't be; and `sase-k6` already proposes a different "schema 2" in the same subsystem, so the bead text needs to say "provider spec schema 2" explicitly.

The recommendation merges `__b`'s capability contract and verb keymap (the cheap, user-visible front half) with `__a`'s adapter model as the destination rather than the gate — and confirms `__a`'s point that the browse entry should extend the existing `ArtifactEntryWire` rather than compete with it. Six open decisions are listed at the end for you.

All three files are in place and these are my changes from the prior pass. Committing them now.

The two old paths no longer exist on disk (the renames are already staged). Re-running without them.

Committed. Both repos are clean and in sync with upstream.

**Commit** `eefdae1` — `docs(research): consolidate the artifacts pane contract reports` (research sidecar, `main`, pushed).

Final layout in `202608/artifacts_pane_contract/`:

| File | Source |
|---|---|
| `artifacts_pane_contract__a.md` | `research.0b.cdx` (renamed from `artifacts_subtab_contract.md`) |
| `artifacts_pane_contract__b.md` | `research.0b.cld` (renamed from `unified_artifacts_subtab_contract.md`) |
| `artifacts_pane_contract.md` | consolidated, 699 lines |

Both renames were already staged from the prior pass, so the two old paths no longer existed on disk — the first commit attempt failed on those `-f` pathspecs and the re-run without them staged the renames correctly. Git recorded both as pure renames (0 content change), so neither source report was modified.

The sase workspace itself needed no `just check` — nothing outside the gitignored `sase/repos/` tree was touched.

One thing to flag, from the commit output: the project has **2 quarantined agent-hood publication requests**, so the link written to this commit may not resolve until the outbox clears. That's pre-existing and outward-facing, so I did not clear it — `sase agent sync --retry-quarantined` is the remediation if you want it retried.
