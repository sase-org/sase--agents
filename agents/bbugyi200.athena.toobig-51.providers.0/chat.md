# Chat History - ace-run (toobig-51.providers.0)

- **TIMESTAMP:** 2026-09-09 00:44:14 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-51.providers.0

## Prompt

%wait:toobig-51.file_completion_workers.0
%id(providers.0, clan=toobig-51)
%model:@medium
%auto
%wait(runners=3)
%wait(priority=20)
#gh:gh_sase-org__sase
Can you help me split the `src/sase/dispatch/providers.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by inspecting `providers.py` and how it's imported so we can split it into files of 500 lines or fewer without breaking callers.

The file is 921 lines, so I’ll map its classes and imports next and check how similar dispatch modules were already split.

I’ll inspect tests and callers next so the public import surface stays stable after the split.

I’ll split along the existing seams: hook specs, inventory collection, and discovery/connection plans, and keep `providers.py` as a thin public facade so imports and the entry point stay stable.

`provider_discovery.py` is 501 lines, so I’ll trim a couple of blank lines to bring it under the 500-line cap.

I’ll keep the public entry point on `sase.dispatch.providers` so the split stays an internal refactor.

Symvision flagged private cross-module imports, so I’ll read that reference note and make those helpers public.

Split `src/sase/dispatch/providers.py` (921 lines) into four modules, each under 500 lines. Existing `from sase.dispatch.providers import …` paths and the `sase_dispatch` builtin entry point still work.

| File | Lines | Role |
|---|---|---|
| `provider_hooks.py` | 70 | Hook specs, `hookimpl`/`hookspec`, `iter_mapping_specs` |
| `provider_inventory.py` | 401 | Builtin providers and spec collection |
| `provider_discovery.py` | 494 | Discovery and connection-plan resolution |
| `providers.py` | 32 | Public facade that re-exports the old API |

The isolated worker entry now imports hook/runtime pieces directly instead of pulling in the whole discovery stack. Tests that used the old private aliases now import `DispatchProviderExecutionError` and `run_dispatch_provider_operation` from `provider_runtime`.

`just check` passed (lint gates plus 160 scoped test files).
