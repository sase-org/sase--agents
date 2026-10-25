# Chat History - ace-run (sase-1nn.8.4.3.5.4.land--code)

- **TIMESTAMP:** 2026-10-25 13:26:27 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1nn.8.4.3.5.4.land--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202610/gh_sase_org__sase-ace_run-sase_1nn_8_4_3_5_4_land__plan-261025_033846.md`
- **2. --code** — `~/.sase/chats/202610/gh_sase_org__sase-ace_run-sase_1nn_8_4_3_5_4_land__code-261025_033846.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@plan:202610/release_watch_final_repairs.md

The above plan has been reviewed and approved. Implement it now.


## Response

Done. Implemented the approved `release_watch_final_repairs` tale and landed the full 0.18.1 chain.

**Top finding:** all five audit regressions plus the related gaps are fixed and proved — the corrected watcher passes 101/101 offline stub asserts while the same suite fails 21 on the originals.

Corrected copies in `/tmp/sase-final-repairs-corrected/` (`watch.sh`, `wrapper.sh`, `tests/run_tests.sh` + stubs, `results.log`), retained as explicit artifacts on `sase-1nn.8.4.3.5.4`:
- [watch](file:explicit:c9c67d045dc4ab3914700c7f), [wrapper](file:explicit:1e0ab9ab99957072dc97bc3c), [harness](file:explicit:94a8441efe4a276c445ed91d), [results](file:explicit:0e4a6b022c54bb52b5c89b40), [bundle](file:explicit:4ba0356b7df4109c81997f99)

Key fixes: pending/canceled/malformed checks now block dispatch; fetch and PyPI-transport failures return unknown with no actions; ambiguous cut/publish/ratchet budgets reserve before attempt and reconcile read-only; preflight persists nothing; exact wheel-suffix and version validation; per-tick scratch reset with unknown-not-lag; final-attempt-only voting; stale run IDs never claimed; every git/gh/curl/sase call bounded via timeout; monitor/agent artifact separation with explicit lander registration.

Closed `sase-1nn.8.4.3.5.4`, `sase-1nn.8.4.3.5`, `sase-1nn.8.4.3`, `sase-1nn.8.4`, `sase-1nn.8`, `sase-1nn` normally (canceled watches left as historical truth, `just symvision` clean each time) and marked all seven linked plans done. No tracked `sase` source files changed.
