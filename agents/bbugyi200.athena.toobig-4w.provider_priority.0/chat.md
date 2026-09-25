# Chat History - ace-run (toobig-4w.provider_priority.0)

- **TIMESTAMP:** 2026-09-07 08:41:53 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-4w.provider_priority.0

## Prompt

%wait:toobig-4w.wipe.0
%id(provider_priority.0, clan=toobig-4w)
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/llm_provider/provider_priority.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by reading the provider-priority module and how it's used, then split it so every file stays at or under 500 lines.

I'll map the module's size, internal structure, and callers next so the split follows existing provider-module patterns.

The module is 777 lines, so I’ll read the rest of it and a nearby split (temporary override / provider disable) to match that layout.

I’ll check the contract validator and nearby split patterns so the public import path stays stable.

I’ll keep `provider_priority.py` as the public import surface and split types and routing into sibling modules, matching the other facade splits in this package.

I’ll check Symvision rules next so the new sibling modules don’t trip unused-symbol or private-import lint.

Symvision forbids importing `_`-prefixed helpers across files, so I’ll keep those helpers local and inline the one-liners.

Split `src/sase/llm_provider/provider_priority.py` (777 lines) into three modules, all under 500 lines. Existing imports still go through `provider_priority.py`.

| File | Role | Lines |
| --- | --- | --- |
| `provider_priority.py` | Public facade: get/set/clear/decode plus re-exports | 192 |
| `provider_priority_types.py` | Wire records, decode/write envelopes, priority route key | 236 |
| `provider_priority_routing.py` | Routing-context capture and availability classification | 420 |
| `provider_priority_peek.py` | Unchanged lock-free display peek | 144 |

Callers can keep importing from `sase.llm_provider.provider_priority`. The docs module table now lists the new siblings.

`just check` passed (lint including mypy/symvision/toobig, plus the scoped test run).
