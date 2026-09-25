# Chat History - ace-run (06k--mon)

- **TIMESTAMP:** 2026-09-07 18:36:52 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** 06k--mon

## Prompt

sase monitor start --command 'export SASE_CORE_DIR="$PWD/sase/repos/external/gh/sase-org/sase-core"; just install && .venv/bin/python tools/check_sase_core_rs_bindings && .venv/bin/python -m pytest -q tests/test_check_sase_core_rs_bindings_tool.py tests/test_pending_actions.py tests/core/test_source_language_facade.py tests/artifact_refs/test_document_source_resolution.py tests/test_xprompt_directive_contract.py tests/test_xprompt_directive_completion_parity.py tests/test_proc_env_isolation.py' --reason 'Build the exact updated CI core pin and verify the missing-binding, directive, and nested-test failures from GitHub Actions'

## Response

Using CPython 3.14.7
Creating virtual environment at: .venv
Activate with: source .venv/bin/activate
[install] Installing local sase_core_rs from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/external/gh/sase-org/sase-core for local dev.
Traceback (most recent call last):
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/tools/refresh_linked_checkout", line 30, in <module>
    raise SystemExit(main())
                     ~~~~^^
  File "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/tools/refresh_linked_checkout", line 21, in main
    from sase._linked_repo_workspaces import refresh_clean_linked_checkout
ModuleNotFoundError: No module named 'sase'
# Harden cargo crate downloads against transient crates.io flakiness.
# CI has hit `curl ... [16] Error in the HTTP2 framing layer` while
# maturin's `cargo metadata` fetches deps; disabling HTTP/2 multiplexing
# and raising the retry count makes the download resilient. Both are
# overridable from the environment.
[sase-core-wheel-cache] miss: no exact cached wheel
Resolved 1 package in 32ms
Installed 1 package in 12ms
 + maturin==1.15.0
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
    Blocking waiting for file lock on build directory
   Compiling pyo3-build-config v0.22.6
   Compiling sase_core v0.32.40 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/external/gh/sase-org/sase-core/crates/sase_core)
   Compiling pyo3-macros-backend v0.22.6
   Compiling pyo3-ffi v0.22.6
   Compiling pyo3 v0.22.6
   Compiling pyo3-macros v0.22.6
   Compiling sase_gateway v0.32.40 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/external/gh/sase-org/sase-core/crates/sase_gateway)
   Compiling sase_core_py v0.32.40 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/external/gh/sase-org/sase-core/crates/sase_core_py)
    Finished `release` profile [optimized] target(s) in 10m 56s
📦 Built wheel for abi3 Python ≥ 3.12 to /tmp/.tmpd4AP8O/sase_core_rs-0.32.40-cp312-abi3-linux_x86_64.whl
✏️ Setting installed package as editable
🛠 Installed sase-core-rs-0.32.40
🍹 Building a mixed python/rust project
🐍 Found CPython 3.14 at /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/.venv/bin/python
🔗 Found pyo3 bindings with abi3-py3.12 support
📡 Using build options features from pyproject.toml
    Finished `release` profile [optimized] target(s) in 0.21s
📦 Built wheel for abi3 Python ≥ 3.12 to /home/bryan/.sase/cache/sase-core-wheels/.build-nix10g75/sase_core_rs-0.32.40-cp312-abi3-manylinux_2_39_x86_64.whl
/home/bryan/.sase/cache/sase-core-wheels/f0b2afe58d89b624ca475252d0f8c190cbe04683bc6f94a52e98b51db14d0b29/sase_core_rs-0.32.40-cp312-abi3-manylinux_2_39_x86_64.whl
# Keep the LSP server in lockstep with the extension: both are built
# from the same sase-core checkout, and the ACE/LSP parity tests
# compare their directive contracts.
   Compiling proc-macro2 v1.0.106
   Compiling unicode-ident v1.0.24
   Compiling quote v1.0.45
   Compiling libc v0.2.186
   Compiling cfg-if v1.0.4
   Compiling version_check v0.9.5
   Compiling zerocopy v0.8.48
   Compiling memchr v2.8.0
   Compiling once_cell v1.21.4
   Compiling serde_core v1.0.228
   Compiling pin-project-lite v0.2.17
   Compiling serde v1.0.228
   Compiling futures-sink v0.3.32
   Compiling smallvec v1.15.1
   Compiling typenum v1.20.0
   Compiling hashbrown v0.17.0
   Compiling zmij v1.0.21
   Compiling equivalent v1.0.2
   Compiling shlex v1.3.0
   Compiling futures-core v0.3.32
   Compiling find-msvc-tools v0.1.9
   Compiling pkg-config v0.3.33
   Compiling itoa v1.0.18
   Compiling regex-syntax v0.8.10
   Compiling vcpkg v0.2.15
   Compiling serde_json v1.0.149
   Compiling autocfg v1.5.0
   Compiling futures-io v0.3.32
   Compiling parking_lot_core v0.9.12
   Compiling getrandom v0.4.2
   Compiling rustix v1.1.4
   Compiling futures-task v0.3.32
   Compiling crossbeam-utils v0.8.21
   Compiling slab v0.4.12
   Compiling bitflags v2.11.1
   Compiling bitflags v1.3.2
   Compiling thiserror v1.0.69
   Compiling bytes v1.11.1
   Compiling linux-raw-sys v0.12.1
   Compiling httparse v1.10.1
   Compiling scopeguard v1.2.0
   Compiling ryu v1.0.23
   Compiling cpufeatures v0.2.17
   Compiling lazy_static v1.5.0
   Compiling tower-layer v0.3.3
   Compiling fastrand v2.4.1
   Compiling fallible-iterator v0.3.0
   Compiling tower-service v0.3.3
   Compiling log v0.4.29
   Compiling unsafe-libyaml v0.2.11
   Compiling fallible-streaming-iterator v0.1.9
   Compiling sync_wrapper v1.0.2
   Compiling nu-ansi-term v0.50.3
   Compiling unicode-width v0.2.2
   Compiling hex v0.4.3
   Compiling thread_local v1.1.9
   Compiling tracing-core v0.1.36
   Compiling lock_api v0.4.14
   Compiling ahash v0.8.12
   Compiling generic-array v0.14.7
   Compiling futures-channel v0.3.32
   Compiling sharded-slab v0.1.7
   Compiling cc v1.2.61
   Compiling fluent-uri v0.1.4
   Compiling num-traits v0.2.19
   Compiling aho-corasick v1.1.4
   Compiling tracing-log v0.2.0
   Compiling indexmap v2.14.0
   Compiling syn v2.0.117
   Compiling crypto-common v0.1.7
   Compiling block-buffer v0.10.4
   Compiling libsqlite3-sys v0.30.1
   Compiling digest v0.10.7
   Compiling errno v0.3.14
   Compiling getrandom v0.2.17
   Compiling socket2 v0.6.3
   Compiling mio v1.2.0
   Compiling fs2 v0.4.3
   Compiling signal-hook-registry v1.4.8
   Compiling chrono v0.4.44
   Compiling rand_core v0.6.4
   Compiling sha2 v0.10.9
   Compiling regex-automata v0.4.14
   Compiling tempfile v3.27.0
   Compiling ppv-lite86 v0.2.21
   Compiling serde_derive v1.0.228
   Compiling futures-macro v0.3.32
   Compiling tracing-attributes v0.1.31
   Compiling tokio-macros v2.7.0
   Compiling thiserror-impl v1.0.69
   Compiling serde_repr v0.1.20
   Compiling hashbrown v0.14.5
   Compiling rand_chacha v0.3.1
   Compiling tokio v1.52.2
   Compiling rand v0.8.6
   Compiling futures-util v0.3.32
   Compiling hashlink v0.9.1
   Compiling dashmap v6.1.0
   Compiling tracing v0.1.44
   Compiling regex v1.12.3
   Compiling matchers v0.2.0
   Compiling tracing-subscriber v0.3.23
   Compiling lsp-types v0.97.0
   Compiling serde_yaml v0.9.34+deprecated
   Compiling futures v0.3.32
   Compiling tower v0.5.3
   Compiling tokio-util v0.7.18
   Compiling tower-lsp-server v0.21.1
   Compiling rusqlite v0.32.1
   Compiling sase_core v0.32.40 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/external/gh/sase-org/sase-core/crates/sase_core)
   Compiling sase_xprompt_lsp v0.32.40 (/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/sase/repos/external/gh/sase-org/sase-core/crates/sase_xprompt_lsp)
    Finished `dev-update` profile [optimized] target(s) in 1m 57s
[rust-lsp-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/.venv/bin/sase-xprompt-lsp
uv pip install --python .venv/bin/python --no-sources $(just _core-overrides-arg) -e ".[dev]"
Resolved 97 packages in 266ms
   Building sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38
      Built sase @ file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38
Prepared 1 package in 1.58s
Installed 96 packages in 666ms
 + ast-serialize==0.10.0
 + asttokens==3.0.2
 + attrs==26.1.0
 + bracex==3.0.1
 + build==1.6.0
 + cachetools==7.1.8
 + certifi==2026.7.22
 + cffi==2.1.1
 + charset-normalizer==3.5.1
 + colorama==0.4.6
 + coverage==7.16.0
 + cryptography==50.0.1
 + distlib==0.4.3
 + docutils==0.23
 + execnet==2.1.2
 + executing==2.2.1
 + filelock==3.32.5
 + hypothesis==6.167.1
 + id==1.6.1
 + idna==3.19
 + iniconfig==2.3.0
 + inline-snapshot==0.35.4
 + jaraco-classes==3.4.0
 + jaraco-context==6.1.2
 + jaraco-functools==4.6.0
 + jeepney==0.9.0
 + jinja2==3.1.6
 + jsonschema==4.26.0
 + jsonschema-specifications==2025.9.1
 + keyring==25.7.0
 + librt==0.15.0
 + linkify-it-py==2.2.0
 + markdown-it-py==4.2.0
 + markupsafe==3.0.3
 + mdit-py-plugins==0.6.1
 + mdurl==0.1.2
 + more-itertools==11.1.0
 + mypy==2.3.1
 + mypy-extensions==1.1.0
 + nh3==0.3.7
 + packaging==26.3
 + pathspec==1.1.1
 + pillow==12.3.0
 + platformdirs==4.11.7
 + pluggy==1.6.0
 + pycparser==3.0
 + pygments==2.19.2
 + pyinstrument==5.1.3
 + pyproject-api==1.11.0
 + pyproject-hooks==1.2.0
 + pytest==9.1.1
 + pytest-asyncio==1.4.0
 + pytest-cov==7.1.0
 + pytest-mock==3.15.1
 + pytest-xdist==3.8.0
 + python-discovery==1.6.0
 + pyyaml==6.0.3
 + readme-renderer==46.0
 + referencing==0.37.0
 + requests==2.34.2
 + requests-toolbelt==1.0.0
 + rfc3986==2.0.0
 + rich==15.0.0
 + rpds-py==2026.6.3
 + ruamel-yaml==0.19.1
 + ruff==0.16.6
 + sase==0.17.1 (from file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38)
 + schedule==1.2.2
 + secretstorage==3.5.0
 + sortedcontainers==2.4.0
 + symvision==0.1.0
 + textual==8.2.8
 + tomli-w==1.2.0
 + toobig==0.1.0
 + tox==4.61.2
 + tree-sitter==0.26.0
 + tree-sitter-bash==0.25.1
 + tree-sitter-css==0.25.0
 + tree-sitter-go==0.25.0
 + tree-sitter-html==0.23.2
 + tree-sitter-java==0.23.5
 + tree-sitter-javascript==0.25.0
 + tree-sitter-json==0.24.8
 + tree-sitter-markdown==0.5.1
 + tree-sitter-python==0.25.0
 + tree-sitter-regex==0.25.0
 + tree-sitter-rust==0.24.2
 + tree-sitter-sql==0.3.11
 + tree-sitter-toml==0.7.0
 + tree-sitter-xml==0.7.0
 + tree-sitter-yaml==0.7.2
 + twine==7.0.0
 + typing-extensions==4.16.0
 + urllib3==2.7.0
 + virtualenv==21.7.8
 + wcmatch==11.0.1
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
sase_core_rs 0.32.40 exposes all 465 bindings required by /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_38/src/sase
........................................................................ [ 64%]
..........FF.FF.............F...........                                 [100%]
=================================== FAILURES ===================================
___________ test_runtime_directive_vocabulary_matches_core_contract ____________

    def test_runtime_directive_vocabulary_matches_core_contract() -> None:
        contract = _contract_by_name()
        runtime_names = set(_KNOWN_DIRECTIVES) | set(_SPECIAL_RUNTIME_DIRECTIVES)
    
        assert set(contract) == runtime_names
        assert _contract_aliases(contract) == {
            alias: name
            for alias, name in _DIRECTIVE_ALIASES.items()
            if name in runtime_names
        }
        assert {
            name for name, row in contract.items() if bool(row["allows_multiple"])
        } == set(_MULTI_VALUE_DIRECTIVES) | {"alt", "xprompts_enabled"}
        assert _contract_keywords(contract) == {
            "alt": (),
            "auto": (),
            "clan": ("summary", "summary_script", "tribe"),
            "dispatch": (),
            "effort": (),
            "final": (),
            "hide": (),
            "id": ("bead", "clan", "family", "tribe"),
            "model": (),
            "repeat": (),
            "wait": ("agent", "bead", "priority", "proc", "runners", "time", "unit"),
            "if": (),
            "proc": (
                "bash",
                "python",
                "timeout",
                "idle_timeout",
                "cwd",
                "workspace",
                "label",
            ),
            "xprompts_enabled": (),
        }
        assert contract["model"]["dynamic_keyword_role"] == "model_alias_key"
        assert (
            _suggested_values(contract["auto"]) == AUTO_COMPATIBILITY_ARGUMENT_SUGGESTIONS
        )
        assert _suggested_values(contract["effort"]) == tuple(EFFORT_LEVELS_ORDERED)
        assert _suggested_values(contract["repeat"]) == ("2", "3")
        assert _suggested_values(contract["xprompts_enabled"]) == ("false", "true")
        assert _contract_syntax_forms(contract) == {
            "alt": ("brace_shorthand", "colon", "parenthesized"),
            "auto": ("colon", "bare", "plus"),
            "clan": ("colon", "parenthesized"),
            "dispatch": ("colon", "parenthesized"),
            "effort": ("colon",),
            "final": ("colon", "parenthesized"),
            "hide": ("bare", "plus"),
            "id": ("colon", "parenthesized", "bare"),
            "model": ("colon", "parenthesized"),
            "repeat": ("colon",),
            "wait": ("colon", "parenthesized", "bare"),
            "if": ("double_colon",),
            "proc": ("parenthesized", "double_colon"),
            "xprompts_enabled": ("colon",),
        }
        assert contract["if"]["feature_flag"] == "typed_launch_units"
        assert contract["proc"]["feature_flag"] == "typed_launch_units"
>       assert contract["dispatch"].get("feature_flag") is None
E       AssertionError: assert 'remote_dispatch' is None
E        +  where 'remote_dispatch' = <built-in method get of dict object at 0x7f25f6374380>('feature_flag')
E        +    where <built-in method get of dict object at 0x7f25f6374380> = {'name': 'dispatch', 'alias': None, 'description': 'Send this launch to an enrolled remote machine', 'argument_hint': ':machine or (machine)', ...}.get

tests/test_xprompt_directive_contract.py:82: AssertionError
__________________ test_ace_and_lsp_directive_name_rows_match __________________

tmp_path = PosixPath('/tmp/pytest-of-bryan/pytest-0/test_ace_and_lsp_directive_nam0')

    def test_ace_and_lsp_directive_name_rows_match(tmp_path: Path) -> None:
        ace_candidates, shared = build_directive_completion_candidates("%")
        assert shared == ""
        ace_rows = _ace_surface_rows(ace_candidates)
        expected_labels: list[str] = []
        for row in sase_core_rs.directive_contract():
            if row.get("feature_flag"):
                continue
            expected_labels.append(f"%{row['name']}")
            expected_labels.extend(
                recipe["label"]
                for recipe in row.get("recipes", [])
                if isinstance(recipe, dict)
            )
    
        with LspSession(tmp_path) as lsp:
            lsp_rows = lsp.complete("%")
    
        assert {row.label for row in ace_rows} == set(expected_labels)
        assert _surface_rows(lsp_rows) == _surface_rows(ace_rows)
        assert "%if" not in expected_labels
        assert "%proc" not in expected_labels
>       assert "%dispatch" in expected_labels
E       AssertionError: assert '%dispatch' in ['%model', '%model:...', '%model(..., alias=...)', '%effort', '%effort:...', '%final', ...]

tests/test_xprompt_directive_completion_parity.py:62: AssertionError
_________________ test_ace_and_lsp_include_dispatch_directive __________________

tmp_path = PosixPath('/tmp/pytest-of-bryan/pytest-0/test_ace_and_lsp_include_dispa0')

    def test_ace_and_lsp_include_dispatch_directive(
        tmp_path: Path,
    ) -> None:
        ace_candidates, shared = build_directive_completion_candidates("%")
        assert shared == ""
        ace_labels = {row.label for row in _ace_surface_rows(ace_candidates)}
        with LspSession(tmp_path) as lsp:
            lsp_labels = {row.label for row in lsp.complete("%")}
    
>       assert "%dispatch" in ace_labels
E       AssertionError: assert '%dispatch' in {'%alt', '%alt:...', '%auto', '%auto:...', '%clan', '%clan(..., tribe=...)', ...}

tests/test_xprompt_directive_completion_parity.py:89: AssertionError
________________ test_ace_and_lsp_include_dispatch_machine_rows ________________

tmp_path = PosixPath('/tmp/pytest-of-bryan/pytest-0/test_ace_and_lsp_include_dispa1')

    def test_ace_and_lsp_include_dispatch_machine_rows(
        tmp_path: Path,
    ) -> None:
        ace_rows = _ace_clause_rows("%dispatch:")
        with LspSession(tmp_path) as lsp:
            lsp_rows = lsp.complete("%dispatch:")
    
>       assert _surface_rows(lsp_rows) == _surface_rows(ace_rows)
E       AssertionError: assert [] == [SurfaceRow(l...unavailable')]
E         
E         Right contains one more item: SurfaceRow(label='no matching remote machines', insertion='', documentation='no matching remote machines', detail='unavailable')
E         Use -v to get more diff

tests/test_xprompt_directive_completion_parity.py:100: AssertionError
__________ test_ace_and_lsp_directive_argument_rows_match[%dispatch:] __________

tmp_path = PosixPath('/tmp/pytest-of-bryan/pytest-0/test_ace_and_lsp_directive_arg0')
text = '%dispatch:'

    @pytest.mark.parametrize(
        "text",
        [
            "%effort:",
            "%auto:",
            "%repeat:",
            "%xprompts_enabled:",
            "%id(worker, be",
            "%id(worker, cl",
            "%id(worker, fa",
            "%id(worker, tr",
            "%clan(research, su",
            "%clan(research, tr",
            "%wait(",
            "%wait:",
            "%wait(bead=",
            "%dispatch:",
            "%model:",
            "%model(me",
            "%model(opus, medium=",
        ],
    )
    def test_ace_and_lsp_directive_argument_rows_match(
        tmp_path: Path,
        text: str,
    ) -> None:
        with (
            patch(MODEL_CATALOG_PATCH, return_value=_model_entries()),
            patch(MODEL_ALIAS_NAMES_PATCH, return_value=("medium",)),
            patch(MODEL_ALIAS_DESCRIPTION_PATCH, side_effect=_model_alias_description),
        ):
            ace_rows = _ace_clause_rows(text)
            with LspSession(tmp_path) as lsp:
                lsp_rows = lsp.complete(text)
    
>       assert _surface_rows(lsp_rows) == _surface_rows(ace_rows)
E       AssertionError: assert [] == [SurfaceRow(l...unavailable')]
E         
E         Right contains one more item: SurfaceRow(label='no matching remote machines', insertion='', documentation='no matching remote machines', detail='unavailable')
E         Use -v to get more diff

tests/test_xprompt_directive_completion_parity.py:139: AssertionError
============================= slowest 20 durations =============================
22.87s call     tests/test_proc_env_isolation.py::test_sase_ml_file_families_ignore_inherited_live_proc_env
7.04s setup    tests/test_check_sase_core_rs_bindings_tool.py::test_scan_resolves_every_call_site_statically
0.12s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match
0.11s call     tests/test_pending_actions.py::test_register_and_resolve_shared_pending_action_store
0.10s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(bead=]
0.07s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%model:]
0.07s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait(]
0.07s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%model(opus, medium=]
0.07s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_wait_prose_replacement_ranges_match
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%effort:]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_typed_launch_directives_when_enabled
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%id(worker, fa]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%wait:]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%xprompts_enabled:]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%id(worker, be]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%id(worker, cl]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%clan(research, su]
0.06s call     tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%model(me]
=========================== short test summary info ============================
FAILED tests/test_xprompt_directive_contract.py::test_runtime_directive_vocabulary_matches_core_contract
FAILED tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_name_rows_match
FAILED tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_directive
FAILED tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_include_dispatch_machine_rows
FAILED tests/test_xprompt_directive_completion_parity.py::test_ace_and_lsp_directive_argument_rows_match[%dispatch:]
5 failed, 107 passed in 37.59s

