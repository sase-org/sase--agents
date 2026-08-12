# Chat History - ace-run (research.0c.final)

- **TIMESTAMP:** 2026-08-12 18:29:21 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0c.final
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260812_180049.md`

## Prompt

%id(final, clan=research.0c) %wait(priority=20) %m:@research_lead
%wait:research.0c.cdx %wait:research.0c.cld
#gh:gh_sase-org__sase 
You are the lead researcher: two independent researchers have reported on the request
below, and you will add your own research and merge all three perspectives into one
consolidated report.

Research request:

I want to add an llm provider to sase that supports grok. I think that there is a grok-cli tool available, right? Can you do some research to help me decide the best way to implement this? End your analysis with a recommended solution.

The researchers' chat transcripts:

{{ wait_chats }}

Month directory (create it if missing):

$(sase repo path research --ensure)/$(date +%Y%m)

Steps:

1. Read both transcripts to learn which report file each researcher wrote
   (`research.0c.cdx` -> `__a`, `research.0c.cld` -> `__b`), then read both reports.
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

Both transcripts identified. Now let me locate the reports and start my own research in parallel.

Both reports read. There's a substantive disagreement on the core technical choice. Let me verify the key claims myself.

The probe install survives. Let me verify the disputed claims directly against the actual binary.

Version and offline catalog confirmed. Now the disputed flags:

Now let me probe the flags where the two reports disagree:

This gives me the real wire output. Let me capture the full terminal frame to test B's `errors[]` claim:

Decisive: the four usage keys and the `errors[]` gap are both confirmed live. Now let me check them against SASE's actual Claude parser:

Gap confirmed exactly. Let me verify the remaining reuse claims:

`--prompt-file /dev/stdin` verified end-to-end (reaches auth; control fails at file read). Now the version regex:

Notable: no `grok-4.6` anywhere in the binary, but `grok-build` appears often. Let me check whether it's a model alias or just the product name:

Significant find — the binary warns about its own compatibility surface. Let me characterize it:

Rust core claim confirmed. Now let me check the grok-build source for the usage-fidelity issue:

Let me confirm whether the native format exposes what the compat projection hides:

I have everything I need. Let me set up the directory structure:

Now the consolidated report:

Done. Final layout is at `sase/repos/research/202608/grok_build_provider/`.

## Answer to your question

Yes, there's a `grok-cli` — but the name is ambiguous and the one you're probably thinking of is the wrong target. `superagent-ai/grok-cli` (renamed `grok-dev`) hasn't shipped since 2026-05-15. **xAI's own Grok Build** (`@xai-official/grok`, `1.0.0` on 2026-08-07, `1.0.3` published today) is the real integration target.

**Recommendation:** native in-tree `grok` provider driving Grok Build headless with `--output-format streaming-messages-json`, reusing SASE's existing Claude parsers, registered explicit-only (no autodetect priority — `grok-dev` claims the same binary name *and* `~/.grok/`). Work collapses to one provider module + a ~5-line shared fix. No Rust core changes.

## What I added as lead

The two researchers agreed on the target but **disagreed on the core technical choice**: `__a` (cdx) wanted the native ACP format plus two new bespoke parsers; `__b` (cld) wanted the Claude-compatible format with zero new parsers. The probe install from `__b`'s session was still on disk, so I re-ran the binary myself and settled it — `__b` is right, and I confirmed the load-bearing claims live: the four usage keys match `initial_usage_totals()` exactly, and the `errors[]` gap is real (failure frames carry `errors[]` and omit `result`/`error`/`message`, so SASE would capture an empty detail).

**A finding neither report had.** Reading the vendor's Rust source, `streaming-messages-json` is a *projection* of Grok's usage ledger, and it drops the `usage_is_incomplete` marker — reading it only to emit a `tracing::warn!`. Token counts silently `.unwrap_or(0)`. The trigger is `ledger_incomplete || cancellation_may_hide_usage`, and both halves hit SASE specifically: Grok ships built-in subagents, and cancellation *is* SASE's interrupt path. So every interrupted Grok run is a candidate for silently zeroed usage, undetectable from the stream. It doesn't overturn the recommendation — the failure mode is under-reported telemetry, not wrong text — but it turns "reuse the parser and you're done" into "reuse it, and treat Grok usage as best-effort." I added a Stage 0 measurement step for it and kept the native format as a documented escape hatch.

Other conflicts resolved by direct test: `--prompt-file /dev/stdin` works end-to-end, not just "parses" (control case fails distinctly at file read), so `__b`'s stdin transport wins over `__a`'s temp file. `__a`'s `--no-ask-user` is real and parses — but is hidden from `--help`, as are `--no-auto-update` and `--yolo`. On models, both were partly right: `__a`'s `grok-4.6` doesn't appear anywhere in the binary, but its `grok-build` alias instinct has more support than `__b` credited — xAI's own embedded doc examples use `"model":"grok-build"`, while `grok models` offline reports only `grok-4.5`. That one genuinely needs an authenticated account, which is the only real blocker.

No changes to the sase repo itself, so `just check` doesn't apply. The two source reports are preserved intact; the moves are uncommitted in the research sidecar if you want them committed.

Mapping verified by content hash — cdx → `__a`, cld → `__b`, both byte-identical to the originals. Committing now.

Recent history uses `docs(research):` for consolidations. Writing the commit message:

Committed. Working tree clean and in sync with `origin/main`.

## What I did this pass

**Verified the `__a`/`__b` mapping before committing** rather than trusting it. Grepping both transcripts for the report paths they wrote confirmed `research.0c.cdx` → `202608/grok_llm_provider_research.md` and `research.0c.cld` → `202608/grok_llm_provider.md`; SHA-256 comparison against `git show HEAD:` for each proved the moved files are byte-identical to their sources. Git recorded both as pure renames (`0` changed lines), so neither source report was altered.

**Commit** `f31177f docs(research): consolidate the Grok provider reports` — 3 files, 627 insertions (the consolidated report), two renames.

```text
202608/grok_build_provider/
├── grok_build_provider__a.md   (cdx, 19k)
├── grok_build_provider__b.md   (cld, 33k)
└── grok_build_provider.md      (consolidated, 36k)
```

One caveat from the commit output: the primary commit and push succeeded, but prompt-archive / agent-hood publication was deferred because the agents sync lock was busy. It is queued and retries automatically — nothing for you to do, but that side-artifact isn't published yet.

No files changed in the sase repo itself, so `just check` doesn't apply here.

## The deliverable, in short

Yes, a `grok-cli` exists — but the name is ambiguous and the obvious candidate is the wrong one. `superagent-ai/grok-cli` (now `grok-dev`) has been dead since 2026-05-15. xAI's own **Grok Build** (`@xai-official/grok`) is the live target.

**Recommendation:** a native in-tree `grok` provider driving Grok Build headless with `--output-format streaming-messages-json`, reusing SASE's existing parsers for that wire format, registered explicit-only (no autodetect priority — `grok-dev` claims both the same binary name and `~/.grok/`). One provider module plus a ~5-line shared fix; no Rust core changes.

The lead-pass contribution that changed the shape of the recommendation: I re-ran the binary to settle the researchers' disagreement (`__b`'s zero-new-parser approach wins over `__a`'s two bespoke parsers), and reading the vendor's Rust source turned up something neither report had — the compat projection drops the `usage_is_incomplete` marker and zeroes unknown token counts, and its trigger condition (subagents, cancellation) is exactly SASE's interrupt path. That makes Grok usage telemetry best-effort rather than exact, which is why the report carries a Stage 0 measurement step and keeps the native format documented as an escape hatch.
