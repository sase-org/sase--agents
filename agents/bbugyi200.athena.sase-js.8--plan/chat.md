# Chat History - ace-run (sase-js.8--code)

- **TIMESTAMP:** 2026-08-11 17:05:53 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-js.8--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_js_8__plan-260811_132715.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_js_8__code-260811_132715.md`

## Prompt

%model:@medium_worker
#gh:gh_sase-org__sase
@sase/repos/plans/202608/research_plugin.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by opening the target repository through the required `/sase_repo` skill, since this plan's work happens in `sase-org/sase-research`, not this workspace.

Found the Rust source. Let's read the `provider_spec.rs` file in full, plus `kinds.rs` and `mod.rs` for context.

Now let me read all the key files in parallel.

The `tests/test_ci_install_contract.py` file's actual content is about CI-workflow coordination assertions (not wheel/entry-point install checks as the name might suggest) — I'll flag this clearly in the report. Let me now pull the remaining files: workflows, docs, xprompts, default_config.yml, errors.py, and the Justfile that the contract test references.

Now let's look at the pyproject.toml entry-points section fully, plus sase_xprompts / sase_config examples, and the plugin doc referenced.

I'm waiting on three background research agents (SASE's artifact-provider registry contract, and packaging/CI references from `sase-telegram` and `sase-github`) before writing any plugin code, since the provider-spec field names must match exactly. I'll continue once they report back.

Now let's check the doctor test file for artifact provider diagnostics and the `_repo_init_config.py` file, plus `tests/artifact_refs/test_context.py` and remaining registry-related tests.

Still running. I'll wait for their completion notifications rather than poll.

Waiting on the three background research agents before proceeding with the implementation.

# Report: `sase-github` entry-point / plugin / CI structure (for scaffolding `sase-research`)

Repo read directly from: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github`

---

## 1. `pyproject.toml` (full) and entry-point / package-data pattern

Full contents of `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/pyproject.toml`:

```toml
[build-system]
requires = ["hatchling>=1.27"]
build-backend = "hatchling.build"

[project]
name = "sase-github"
version = "0.2.4"
description = "GitHub VCS plugin for sase"
requires-python = ">=3.12"
license = "MIT"
license-files = ["LICENSE"]
dependencies = ["sase>=0.11.0"]

[project.optional-dependencies]
dev = [
    "ruff",
    "mypy",
    "pytest",
    "pytest-cov",
    "pytest-mock",
]

[project.entry-points."sase_vcs"]
github = "sase_github.plugin:GitHubPlugin"

[project.entry-points."sase_workspace"]
github = "sase_github.workspace_plugin:GitHubWorkspacePlugin"

[project.entry-points."sase_config"]
sase_github = "sase_github"

[project.entry-points."sase_xprompts"]
sase_github = "sase_github"

[tool.hatch.build.targets.wheel]
packages = ["src/sase_github"]

[tool.ruff]
target-version = "py312"
line-length = 88
src = ["src", "tests"]

[tool.ruff.lint]
select = ["E", "W", "F", "B", "C4", "UP"]
ignore = ["E501", "W291", "F401", "F821", "B007"]

[tool.mypy]
files = ["src"]
mypy_path = ["src"]
python_version = "3.12"
check_untyped_defs = true
disallow_incomplete_defs = true
disallow_untyped_defs = true
ignore_missing_imports = false

[[tool.mypy.overrides]]
module = ["sase.*"]
ignore_missing_imports = true

[tool.pytest.ini_options]
testpaths = ["tests"]
pythonpath = ["src", "tests"]
addopts = [
    "--import-mode=importlib",
    "--strict-markers",
    "--strict-config",
    "-v",
]
```

**The general entry-point pattern — two distinct shapes:**

- **Plugin-class entry points** (`sase_vcs`, `sase_workspace`) point at a *specific class inside a module*, using the `module:Attribute` colon syntax:
  - `github = "sase_github.plugin:GitHubPlugin"`
  - `github = "sase_github.workspace_plugin:GitHubWorkspacePlugin"`
  - The entry-point **name** (`github`) is the plugin's identifier within that hook family (i.e. what `vcs_classify_repo`/`ws_detect_workflow_type` return), not the package name.
- **Discovery/data entry points** (`sase_config`, `sase_xprompts`) point at the **bare package**, no colon, no callable:
  - `sase_github = "sase_github"`
  - `sase_github = "sase_github"`
  - Here the entry-point name is conventionally the package's own name (`sase_github`), and the value is just the importable package. sase core presumably does `importlib.resources` or introspects the package's `__path__` to find `default_config.yml` and `xprompts/*.yml` inside it — there is no dotted-attribute target because these aren't hookimpl objects, they're locatable data.

**Layout backing `sase_xprompts` / `sase_config`:**
- `src/sase_github/xprompts/` contains four flat `.yml` files: `gh.yml`, `new_pr_desc.yml`, `prdd.yml`, `pr_diff.yml` (no `.md` files — despite the user's premise, xprompts here are YAML workflow specs, not Markdown).
- `src/sase_github/default_config.yml` sits directly beside `config.py`, `errors.py`, `plugin.py`, `workspace_plugin.py`, `__init__.py` inside `src/sase_github/`. Its **full current content** is just:
  ```yaml
  xprompts: {}
  ```
  (docs/configuration.md describes it as contributing `xprompts.pr_diff`, but the file on disk today is an empty `xprompts: {}` stub — worth noting as a possible doc/code drift, not something to copy verbatim.)

**Package-data inclusion mechanism:** There is **no** `[tool.hatch.build.targets.wheel].force-include`, no `package-data` glob, and no `MANIFEST.in`/`include` directive anywhere in the repo. The only wheel-target config is:
```toml
[tool.hatch.build.targets.wheel]
packages = ["src/sase_github"]
```
This relies on **Hatchling's default src-layout packages behavior**: when `packages = ["src/sase_github"]` is set, Hatchling includes the *entire directory tree* under that package path in the wheel (all `.py`, `.yml` files, etc.) automatically — no separate data-file whitelisting is needed. So `xprompts/*.yml` and `default_config.yml`, sitting inside `src/sase_github/`, ship for free as part of the package directory copy. For `sase-research` you'd mirror this exactly: put data files under `src/sase_research/...` and declare only `packages = ["src/sase_research"]`.

---

## 2. `src/sase_github/__init__.py` and `plugin.py` — hookimpl registration pattern

`src/sase_github/__init__.py` (full):
```python
"""sase-github: GitHub VCS plugin for sase."""

from sase_github.errors import (
    GitHubAuthenticationError,
    GitHubIssueError,
    GitHubRateLimitError,
)
from sase_github.plugin import GitHubPlugin
from sase_github.workspace_plugin import GitHubWorkspacePlugin

__all__ = [
    "GitHubAuthenticationError",
    "GitHubIssueError",
    "GitHubPlugin",
    "GitHubRateLimitError",
    "GitHubWorkspacePlugin",
]
```
Note: `__init__.py` re-exports the plugin classes but is **not** itself where entry points point — the entry points in `pyproject.toml` point directly at `sase_github.plugin:GitHubPlugin` / `sase_github.workspace_plugin:GitHubWorkspacePlugin`. The `sase_config`/`sase_xprompts` entry points point at the package (`sase_github`) as a whole, which is why `__init__.py` matters for those (it's the resolvable module object), but doesn't need to expose anything special for them.

`src/sase_github/plugin.py` — hookimpl pattern (from `class GitHubPlugin(GitCommon):`):

Import of the hookimpl decorator:
```python
from sase.vcs_provider._hookspec import hookimpl
```

Decorator usage — every hook method is a plain instance method decorated with the bare `@hookimpl` (no arguments), method name == hookspec name:
```python
class GitHubPlugin(GitCommon):
    """Pluggy plugin for GitHub-hosted git repositories."""

    @hookimpl
    def vcs_classify_repo(self, git_dir: str) -> str | None:
        ...

    @hookimpl
    def vcs_can_rename_branch(self, cwd: str) -> bool:
        ...

    @hookimpl
    def vcs_list_issues(self, cwd: str, state: IssueListState, limit: int) -> list[IssueWire]:
        ...

    @hookimpl
    def vcs_get_issue(self, number: int, cwd: str) -> IssueWire:
        ...

    @hookimpl
    def vcs_create_issue(self, title: str, body: str, labels: Sequence[str], cwd: str) -> IssueWire:
        ...

    @hookimpl
    def vcs_update_issue(self, number: int, cwd: str, title: str | None, body: str | None,
                          state: IssueState | None, labels: Sequence[str] | None) -> IssueWire:
        ...

    @hookimpl
    def vcs_get_issue_url(self, number: int, cwd: str) -> str:
        ...

    @hookimpl
    def vcs_list_pull_requests(self, cwd: str, state: PullRequestListState, limit: int) -> list[PullRequestWire]:
        ...

    @hookimpl
    def vcs_abandon_change(self, cl: str, revision: str, cwd: str) -> tuple[bool, str | None]:
        ...

    @hookimpl
    def vcs_get_change_url(self, cwd: str) -> tuple[bool, str | None]:
        ...

    @hookimpl
    def vcs_get_change_body(self, change_ref: str, cwd: str) -> tuple[bool, str | None]:
        ...

    @hookimpl
    def vcs_get_pr_number(self, cwd: str) -> tuple[bool, str | None]:
        ...

    @hookimpl
    def vcs_get_cl_number(self, cwd: str) -> tuple[bool, str | None]:
        ...

    @hookimpl
    def vcs_mail(self, revision: str, cwd: str) -> tuple[bool, str | None]:
        ...

    @hookimpl
    def vcs_create_pull_request(self, payload: dict, cwd: str) -> tuple[bool, str | None]:
        ...
```
This class also extends `sase.vcs_provider.plugins._git_common.GitCommon` and reuses its `_run`/`_to_result` helpers, plus inherits `vcs_create_commit`/`vcs_create_proposal` hooks (not overridden here).

`src/sase_github/workspace_plugin.py` follows the identical pattern for the `sase_workspace` hookspec family, importing:
```python
from sase.workspace_provider import (
    ExternalRepoCloneResult, ResolvedRef, SddSidecarPreflight,
    VcsNamespaceEntry, VcsRefNamespaces, VcsRepoCandidates,
    VcsRepoEntry, WorkflowMetadata, hookimpl,
)
```
(note: `hookimpl` is imported from `sase.workspace_provider` here, not `sase.vcs_provider._hookspec` — each hookspec family exposes its own `hookimpl` marker object). `GitHubWorkspacePlugin` (plain class, no base class) implements ~15 `@hookimpl` methods: `ws_get_workflow_metadata`, `ws_detect_workflow_type`, `ws_get_change_label`, `ws_resolve_ref`, `ws_clone_external_repo`, `ws_peek_ref`, `ws_list_repo_candidates`, `ws_list_ref_namespaces`, `ws_extract_change_identifier`, `ws_generate_submitted_check_script`, `ws_supports_reviewer_comments`, `ws_get_workspace_directory`, `ws_materialize_sdd_store`, `ws_preflight_sdd_sidecar`, `ws_create_sdd_remote`, `ws_prepare_mail`, `ws_format_commit_description`, `ws_submit`.

**Takeaway for `sase_artifact_ref_providers` / `sase_file_hook_providers`:** you'll want, per hookspec family, to `from sase.<family_module> import hookimpl` (check whether the hookspec module re-exports its own `hookimpl`, e.g. via `_hookspec` submodule or top-level), define a plain class (not necessarily subclassing anything unless there's a shared-behavior base like `GitCommon`), and decorate each method with bare `@hookimpl` where the method name matches the hookspec name exactly.

---

## 3. `.github/workflows/*.yml` — full inventory and job matrices

Three workflows: `ci.yml`, `pr-title.yml`, `publish.yml`.

### `ci.yml` — name: `CI`
Triggers: `push`/`pull_request` on `branches: [master]`. `permissions: contents: read`.

Top-level `env`:
```yaml
env:
  SASE_PYTHON_REF: master
  SASE_PYTHON_PATH: .ci/sase
  SASE_RUST_CORE_REF: master
  SASE_RUST_CORE_PATH: .ci/sase-core
```

**Job `lint`** (single Ubuntu run, no matrix): checks out own repo, then checks out `sase-org/sase` at `${{ env.SASE_PYTHON_REF }}` into `.ci/sase`, then checks out `sase-org/sase-core` at `${{ env.SASE_RUST_CORE_REF }}` into `.ci/sase-core`, sets up `astral-sh/setup-uv@v4`, `extractions/setup-just@v2`, `dtolnay/rust-toolchain@stable`, installs Python 3.12 + venv, runs `just install`, then `just lint`.

**Job `test`** — matrix `python-version: ["3.12", "3.13"]`. Same sibling-repo checkout steps repeated (SASE python source + SASE Rust core source), plus `dtolnay/rust-toolchain@stable`, per-matrix `uv venv --python ${{ matrix.python-version }} .venv`, `just install`, `just test`.

This is exactly the "coordinate CI against SASE and sase-core source revisions" lane you're after. Precise excerpt (the coordinated-source-checkout steps, identical in both jobs):
```yaml
      - name: Check out SASE
        uses: actions/checkout@v4
        with:
          repository: sase-org/sase
          ref: ${{ env.SASE_PYTHON_REF }}
          path: ${{ env.SASE_PYTHON_PATH }}
      - name: Check out SASE Rust core
        uses: actions/checkout@v4
        with:
          repository: sase-org/sase-core
          ref: ${{ env.SASE_RUST_CORE_REF }}
          path: ${{ env.SASE_RUST_CORE_PATH }}
```
The `just install` recipe (see `Justfile` in §5 below) is what actually wires `SASE_PYTHON_PATH`/`SASE_RUST_CORE_PATH` into an editable `-e` overrides install plus a `maturin develop --release` build of the Rust core against those checkouts.

### `pr-title.yml` — name: `PR Title`
Triggers on `pull_request` (`opened, edited, reopened, ready_for_review, synchronize`) for `branches: [master]`. Single job `conventional-title`, no matrix — validates `github.event.pull_request.title` against a Conventional Commits regex (`feat|fix|perf|docs|ci|test|chore|refactor|build|deps`), used for squash-merge release-please metadata.

### `publish.yml` — name: `Publish`
Triggers: `push` to `master`, and `workflow_dispatch` with boolean input `publish_existing`.

Same coordinated-source `env` block as `ci.yml`. Four jobs, chained via `needs`:
1. **`release`** — `googleapis/release-please-action@v5`, only on `push`, produces `release_created` output.
2. **`build`** — `needs: release`; gated on `release_created == 'true'` OR manual dispatch with `publish_existing == true`; builds wheel/sdist with `uv build`, uploads as `dist` artifact.
3. **`install-smoke`** — `needs: build`; downloads `dist/`, checks out `sase-org/sase` and `sase-org/sase-core` sibling sources (identical pattern to `ci.yml`), sets up uv/just/rust-toolchain, installs the built wheel into a **fresh venv** with a source-override pip constraints file, then runs `just install-source-sase`, then an inline Python "smoke check" script that calls `importlib.metadata.entry_points()` and asserts each expected entry point resolves to its exact target string. This inline script **is** the "clean wheel install, enumerate entry points" contract check — quoted precisely:
```yaml
  install-smoke:
    needs: build
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - uses: actions/checkout@v4
      - uses: actions/download-artifact@v4
        with:
          name: dist
          path: dist/
      - name: Check out SASE
        uses: actions/checkout@v4
        with:
          repository: sase-org/sase
          ref: ${{ env.SASE_PYTHON_REF }}
          path: ${{ env.SASE_PYTHON_PATH }}
      - name: Check out SASE Rust core
        uses: actions/checkout@v4
        with:
          repository: sase-org/sase-core
          ref: ${{ env.SASE_RUST_CORE_REF }}
          path: ${{ env.SASE_RUST_CORE_PATH }}
      - uses: astral-sh/setup-uv@v4
      - uses: extractions/setup-just@v2
      - uses: dtolnay/rust-toolchain@stable
      - name: Set up Python
        run: uv python install 3.12
      - name: Install built sase-github wheel into a fresh venv
        run: |
          uv venv --python 3.12 /tmp/smoke-venv
          printf -- '-e %s\n' "$(realpath "${SASE_PYTHON_PATH}")" > /tmp/sase-overrides.txt
          uv pip install --python /tmp/smoke-venv/bin/python --overrides /tmp/sase-overrides.txt dist/*.whl
          just install-source-sase /tmp/smoke-venv/bin/python
      - name: Smoke check
        run: |
          /tmp/smoke-venv/bin/python - <<'PY'
          from importlib.metadata import entry_points

          import sase_github

          expected = {
              "sase_vcs": {"github": "sase_github.plugin:GitHubPlugin"},
              "sase_workspace": {
                  "github": "sase_github.workspace_plugin:GitHubWorkspacePlugin"
              },
              "sase_config": {"sase_github": "sase_github"},
              "sase_xprompts": {"sase_github": "sase_github"},
          }

          discovered = entry_points()
          for group, entries in expected.items():
              group_entries = {
                  entry_point.name: entry_point.value
                  for entry_point in discovered.select(group=group)
              }
              for name, value in entries.items():
                  actual = group_entries.get(name)
                  if actual != value:
                      raise SystemExit(
                          f"{group} entry point {name!r}: expected {value!r}, got {actual!r}"
                      )

          assert sase_github
          PY
```
4. **`publish`** — `needs: [release, build, install-smoke]`; gated the same way; downloads `dist/`, runs `pypa/gh-action-pypi-publish@release/v1` under `environment: pypi` with `id-token: write`.

**Important correction to your premise:** the actual "clean wheel install + enumerate entry points" contract lives in this `install-smoke` job of `publish.yml`, not in the pytest test named `tests/test_ci_install_contract.py` — see §5 below.

---

## 4. Docs structure (headers only)

`docs/architecture.md`:
- `# Architecture`
- `## Plugin System`
  - `### Entry Points` (table of entry points)
  - `### GitHubPlugin (plugin.py)` (hook table)
  - `### GitHubWorkspacePlugin (workspace_plugin.py)` (hook table)
- `## Reference Resolution`
  - `### Mode 1: Repo Path (user/project)`
  - `### Mode 2: Project Shorthand (myproject)`
  - `### Mode 3: Patch Name`
- `## Ref Namespace Completion`
- `## Submission Flow`
- `## Config Helper`

`docs/configuration.md`:
- `# Configuration`
- `## GitHub Enterprise setup` (numbered checklist)
- `## github_hosts`
- `## github_orgs`
- `## Default Config`
- `## Requirements`
- `## SDD sidecar repository`
- `## Workspace Layout`
- `## Project Files`

`docs/xprompts.md`:
- `# XPrompts`
- `## #gh — GitHub Workflow` → `### Input`, `### Steps`, `### Usage Examples`
- `## #new_pr_desc — PR Description Generator` → `### Input`, `### Steps`, `### Usage Example`
- `## #prdd — PR Description Detail` → `### Steps`

---

## 5. `tests/test_ci_install_contract.py` (full contents, and a key clarification)

**Clarification first:** despite the filename, this file does **not** test wheel-installability or entry-point discoverability at all — no `pytest` test in it touches `importlib.metadata` or installs a wheel (confirmed via `grep -rn "entry_points\|importlib.metadata" tests/ src/` → zero hits). Instead it's a **static-assertion test that greps the raw text of `.github/workflows/ci.yml`, `.github/workflows/publish.yml`, and `Justfile`** to assert the coordinated-source CI wiring (sibling `sase`/`sase-core` checkouts, python-version matrix, `just install` invocation counts, etc.) is present and hasn't regressed. The actual "clean wheel install, enumerate entry points" logic lives instead in the `install-smoke` job's inline Python heredoc inside `publish.yml` (quoted in full in §3 above) — that's the piece you should structurally mirror if you want a genuine wheel/entry-point contract test; the pytest file here is really a "CI-file-content contract" test.

Full contents of `tests/test_ci_install_contract.py`:
```python
from pathlib import Path


ROOT = Path(__file__).resolve().parents[1]


def _read(relative_path: str) -> str:
    return (ROOT / relative_path).read_text()


def test_ci_builds_coordinated_sase_sources() -> None:
    workflow = _read(".github/workflows/ci.yml")

    assert "SASE_PYTHON_PATH: .ci/sase" in workflow
    assert "SASE_RUST_CORE_PATH: .ci/sase-core" in workflow
    assert workflow.count("repository: sase-org/sase\n") == 2
    assert workflow.count("repository: sase-org/sase-core\n") == 2
    assert workflow.count("uses: dtolnay/rust-toolchain@stable") == 2
    assert 'python-version: ["3.12", "3.13"]' in workflow
    assert "uv venv --python 3.12 .venv" in workflow
    assert "uv venv --python ${{ matrix.python-version }} .venv" in workflow
    assert workflow.count("run: just install") == 2


def test_task_runner_requires_both_source_overrides() -> None:
    justfile = _read("Justfile")

    assert "SASE_PYTHON_PATH and SASE_RUST_CORE_PATH must be set together" in justfile
    assert "crates/sase_core_py" in justfile
    assert justfile.count("set -eu") == 2
    assert '"$venv_path/bin/maturin" develop --release' in justfile
    assert "PYO3_USE_ABI3_FORWARD_COMPATIBILITY=1" in justfile
    assert (
        'uv pip install --python "$python_path" --no-deps -e "$sase_python_path"'
        in justfile
    )
    assert 'just install-source-sase "$venv_path/bin/python"' in justfile
    assert 'uv pip install --python {{ venv_bin }}/python -e ".[dev]"' in justfile
    assert "SASE_CORE_PATH" not in justfile


def test_release_smoke_builds_coordinated_sase_sources() -> None:
    workflow = _read(".github/workflows/publish.yml")
    smoke_job = workflow.split("  install-smoke:\n", maxsplit=1)[1].split(
        "  publish:\n", maxsplit=1
    )[0]

    assert "repository: sase-org/sase\n" in smoke_job
    assert "repository: sase-org/sase-core\n" in smoke_job
    assert "uses: dtolnay/rust-toolchain@stable" in smoke_job
    assert "just install-source-sase /tmp/smoke-venv/bin/python" in smoke_job
    assert (
        "uv pip install --python /tmp/smoke-venv/bin/python --overrides "
        "/tmp/sase-overrides.txt dist/*.whl" in smoke_job
    )
    assert smoke_job.index("dist/*.whl") < smoke_job.index("just install-source-sase")
```
Note: it reads files off `ROOT = Path(__file__).resolve().parents[1]` (repo root, one level above `tests/`) with plain `.read_text()` — no fixtures, no network, no venv creation; it's pure string/substring assertions on CI-config files, keeping the pytest suite fast and hermetic while still failing loudly if someone edits the workflow YAML/Justfile in a way that breaks the coordinated-source lane. If you want a real wheel-install/entry-point pytest contract test for `sase-research`, you'd need to write a new one (not present here) — likely spawning a subprocess venv, building, installing, and asserting `importlib.metadata.entry_points()` — modeled on the `install-smoke` shell/Python block rather than on this file.

`Justfile` recipes referenced by the test (full recipe bodies, for context) — `install-source-sase`, `install`, `lint`, `fmt`, `test`, `check`, `clean`, `build` — are quoted in full above under the tool output; the two load-bearing ones are `install-source-sase python:` (does `uv pip install -e "$sase_python_path"`, `uv pip install maturin`, then `maturin develop --release` inside `crates/sase_core_py` with `PYO3_USE_ABI3_FORWARD_COMPATIBILITY=1`, then a `--no-deps` reinstall) and `install:` (branches on whether `SASE_PYTHON_PATH`/`SASE_RUST_CORE_PATH` are both set, both unset, or only one set — erroring in the last case with `"SASE_PYTHON_PATH and SASE_RUST_CORE_PATH must be set together"`).

---

## 6. Python floor / ruff / mypy / pytest config (consolidated, cross-referenced with §1)

- **Python floor:** `requires-python = ">=3.12"` in `[project]`; `target-version = "py312"` in `[tool.ruff]`; `python_version = "3.12"` in `[tool.mypy]`. CI test matrix additionally exercises **3.13** (`python-version: ["3.12", "3.13"]` in `ci.yml`), but the floor/declared minimum is 3.12.
- **ruff:** `line-length = 88`; `src = ["src", "tests"]`; lint `select = ["E", "W", "F", "B", "C4", "UP"]`; lint `ignore = ["E501", "W291", "F401", "F821", "B007"]` (line-too-long, trailing whitespace, unused-import, undefined-name, and loop-variable-not-used-in-body are all suppressed — somewhat permissive ignores worth reconsidering for a fresh package rather than copying blindly).
- **mypy:** `files = ["src"]`, `mypy_path = ["src"]` (tests are excluded from mypy's file set), `check_untyped_defs = true`, `disallow_incomplete_defs = true`, `disallow_untyped_defs = true`, `ignore_missing_imports = false` globally but with a per-module override:
  ```toml
  [[tool.mypy.overrides]]
  module = ["sase.*"]
  ignore_missing_imports = true
  ```
  (needed because `sase` core, while a runtime dependency, doesn't ship inline type stubs the mypy run can otherwise resolve in this environment).
- **pytest:** `testpaths = ["tests"]`; `pythonpath = ["src", "tests"]` (so tests import `sase_github` directly from `src/` without an install, and can import test-local helpers); `addopts = ["--import-mode=importlib", "--strict-markers", "--strict-config", "-v"]` — i.e. strict markers (undefined `@pytest.mark.foo` fails), strict ini config parsing, verbose output, and the `importlib` import mode (avoids `sys.path` mutation / duplicate-module issues across test files).

---

### Files referenced (absolute paths)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/pyproject.toml`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/src/sase_github/__init__.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/src/sase_github/plugin.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/src/sase_github/workspace_plugin.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/src/sase_github/config.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/src/sase_github/errors.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/src/sase_github/default_config.yml`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/src/sase_github/xprompts/{gh,new_pr_desc,prdd,pr_diff}.yml`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/.github/workflows/{ci,pr-title,publish}.yml`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/docs/{architecture,configuration,xprompts}.md`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/tests/test_ci_install_contract.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-github/Justfile`

Got the sase-github findings — CI coordinated-source pattern, entry-point registration style, and the wheel-install-smoke job structure are clear. Waiting on the other two agents (sase-core registry contract, sase-telegram structure).

Still waiting on the remaining two background research agents before continuing.

# Report: `sase-telegram` packaging / release / dev-workflow structure (reference for `sase-research`)

All paths below are under `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/sase-telegram/`.

---

## 1. `pyproject.toml` (full contents, 73 lines)

Path: `pyproject.toml`

```toml
[build-system]
requires = ["hatchling>=1.27"]
build-backend = "hatchling.build"

[project]
name = "sase-telegram"
version = "0.4.7"
description = "Telegram integration chop for sase"
readme = "README.md"
requires-python = ">=3.12"
license = "MIT"
license-files = ["LICENSE"]
dependencies = [
    "PyYAML>=6.0",
    "sase>=0.1.0",
    "python-telegram-bot>=21.0",
]

[project.urls]
Repository = "https://github.com/sase-org/sase-telegram"
Issues = "https://github.com/sase-org/sase-telegram/issues"

[project.optional-dependencies]
dev = [
    "ruff",
    "mypy",
    "pytest",
    "pytest-cov",
    "pytest-mock",
]

[project.scripts]
sase_chop_tg_outbound = "sase_telegram.scripts:outbound_main"
sase_chop_tg_inbound = "sase_telegram.scripts:inbound_main"

[tool.hatch.build.targets.wheel]
packages = ["src/sase_telegram"]

[tool.ruff]
target-version = "py312"
line-length = 88
src = ["src", "tests"]

[tool.ruff.lint]
select = ["E", "W", "F", "B", "C4", "UP"]
ignore = ["E501", "W291", "F401", "F821", "B007"]

[tool.mypy]
files = ["src"]
mypy_path = ["src"]
python_version = "3.12"
check_untyped_defs = true
disallow_incomplete_defs = true
disallow_untyped_defs = true
ignore_missing_imports = false

[[tool.mypy.overrides]]
module = ["sase.*"]
ignore_missing_imports = true

[[tool.mypy.overrides]]
module = ["telegram.*"]
ignore_missing_imports = true

[tool.pytest.ini_options]
testpaths = ["tests"]
pythonpath = ["src", "tests"]
addopts = [
    "--import-mode=importlib",
    "--strict-markers",
    "--strict-config",
    "-v",
]
```

Notes / observations:
- **Build backend**: hatchling (`>=1.27`), standard `hatchling.build`.
- **Version**: `version = "0.4.7"` is a **static, literal string** in `[project]` — it is *not* `dynamic = ["version"]`. Release-please rewrites this literal `version` field directly (and `CHANGELOG.md`, and `.release-please-manifest.json`) as part of its release PR. There is no `[tool.hatch.version]` source-of-truth file.
- **Dependencies**: `PyYAML>=6.0`, `sase>=0.1.0`, `python-telegram-bot>=21.0`. Only one optional-dependency group, `dev` (no separate `test` group) — it bundles `ruff`, `mypy`, `pytest`, `pytest-cov`, `pytest-mock` together.
- **Entry points**: uses `[project.scripts]` (console-script entry points), not a `[project.entry-points."..."]` plugin table. Two scripts: `sase_chop_tg_outbound` and `sase_chop_tg_inbound`, both pointing at `sase_telegram.scripts:<name>_main`.
- **`[tool.hatch.build.targets.wheel]`**: only `packages = ["src/sase_telegram"]` — **no explicit package-data/force-include/artifacts config**. I grepped the whole file for `pdf_style|package-data|force-include|artifacts|include\b` and got zero matches. Yet `src/sase_telegram/pdf_style.css` (a non-`.py` resource file) exists in the package tree and is used by `pdf_convert.py`. This works because hatchling's default wheel builder, when given `packages = [...]`, includes **every file under that package directory that is tracked by VCS** (respecting `.gitignore`) — no special directive is needed for a `.md`/`.yml`/`.css` file sitting inside `src/sase_telegram/`. If you want a resource file (e.g. a `.yml` template) included in `sase-research`'s wheel, simply placing it inside `src/sase_research/` and keeping it committed to git is sufficient; you don't need `include`/`artifacts` keys unless the file lives outside the package dir or is gitignored.
- **Ruff**: `target-version = "py312"`, `line-length = 88`, `src = ["src", "tests"]`. Lint select set is narrow: `["E", "W", "F", "B", "C4", "UP"]`, with several codes explicitly ignored: `["E501", "W291", "F401", "F821", "B007"]` (line-too-long, trailing whitespace, unused-import, undefined-name, unused-loop-variable — a fairly permissive ignore list).
- **Mypy**: `files = ["src"]`, `mypy_path = ["src"]`, `python_version = "3.12"`. It sets `check_untyped_defs`, `disallow_incomplete_defs`, `disallow_untyped_defs` all `true`, and `ignore_missing_imports = false` at the top level — this is a strict-ish but not full `strict = true` config (no `disallow_untyped_calls`, no `warn_return_any`, etc.). Two override blocks silence missing stubs for `sase.*` and `telegram.*`.
- **Pytest**: `testpaths = ["tests"]`, `pythonpath = ["src", "tests"]`, `addopts` includes `--import-mode=importlib`, `--strict-markers`, `--strict-config`, `-v`. There is **no `[tool.coverage.*]** section and no `--cov` flag in `addopts`** despite `pytest-cov` being a dev dependency — coverage is present as a tool but not wired into default test runs or CI. No custom `markers` are registered either (so `--strict-markers` mainly guards against typos since none are declared).

---

## 2. `Justfile` (full contents)

Path: `Justfile`

```just
# sase-telegram task runner

repo_dir := justfile_directory()
venv_dir := ".venv"
venv_path := clean(repo_dir / venv_dir)
venv_bin := venv_dir / "bin"
venv_python := venv_bin / "python"
venv_maturin := clean(repo_dir / venv_bin / "maturin")

# Override with SASE_TELEGRAM_SASE_SOURCE_DIR=/path/to/sase when the local
# checkout is not in one of the standard development locations below.
local_sase_source_override := env_var_or_default("SASE_TELEGRAM_SASE_SOURCE_DIR", "")
ci_sase_source := clean(repo_dir / ".sase-deps" / "sase")
sibling_sase_source := clean(repo_dir / ".." / "sase")
linked_workspace_sase_source := clean(repo_dir / ".." / ".." / ".." / "..")
local_sase_source := if local_sase_source_override != "" { clean(local_sase_source_override) } else if path_exists(linked_workspace_sase_source / "src" / "sase") == "true" { linked_workspace_sase_source } else if path_exists(sibling_sase_source / "src" / "sase") == "true" { sibling_sase_source } else { ci_sase_source }

# Override with SASE_TELEGRAM_SASE_CORE_SOURCE_DIR=/path/to/sase-core when the
# matching Rust core checkout is not next to this repo or in CI dependencies.
local_sase_core_source_override := env_var_or_default("SASE_TELEGRAM_SASE_CORE_SOURCE_DIR", "")
ci_sase_core_source := clean(repo_dir / ".sase-deps" / "sase-core")
sibling_sase_core_source := clean(repo_dir / ".." / "sase-core")
local_sase_core_source := if local_sase_core_source_override != "" { clean(local_sase_core_source_override) } else if path_exists(sibling_sase_core_source / "crates" / "sase_core_py" / "pyproject.toml") == "true" { sibling_sase_core_source } else if path_exists(ci_sase_core_source / "crates" / "sase_core_py" / "pyproject.toml") == "true" { ci_sase_core_source } else { "" }
local_sase_core_py_source := local_sase_core_source / "crates" / "sase_core_py"

default:
    @just --list

_local-sase-source:
    @printf '%s\n' {{ quote(local_sase_source) }}

_local-sase-core-source:
    @printf '%s\n' {{ quote(local_sase_core_source) }}

_validate-local-sase:
    @sase_src={{ quote(local_sase_source) }}; \
    if [ ! -f "$sase_src/pyproject.toml" ] || [ ! -d "$sase_src/src/sase" ]; then \
        printf '%s\n' "Local SASE source checkout not found at: $sase_src" >&2; \
        printf '%s\n' "Set SASE_TELEGRAM_SASE_SOURCE_DIR=/path/to/sase, create ../sase next to this repo, run inside a SASE linked workspace, or check out .sase-deps/sase in CI." >&2; \
        exit 1; \
    fi

_validate-local-sase-core:
    @core_src={{ quote(local_sase_core_source) }}; \
    if [ -z "$core_src" ] || [ ! -f "$core_src/crates/sase_core_py/pyproject.toml" ]; then \
        printf '%s\n' "Local SASE core checkout not found at: $core_src" >&2; \
        printf '%s\n' "Set SASE_TELEGRAM_SASE_CORE_SOURCE_DIR=/path/to/sase-core, create ../sase-core next to this repo, or check out .sase-deps/sase-core in CI." >&2; \
        exit 1; \
    fi

_ensure-venv:
    @[ -x {{ quote(venv_python) }} ] || uv venv {{ quote(venv_dir) }}

_install-local-sase-core: _validate-local-sase-core _ensure-venv
    @[ -x {{ quote(venv_maturin) }} ] || uv pip install --python {{ quote(venv_python) }} maturin
    cd {{ quote(local_sase_core_py_source) }} && VIRTUAL_ENV={{ quote(venv_path) }} PYO3_USE_ABI3_FORWARD_COMPATIBILITY=1 {{ quote(venv_maturin) }} develop --release

_setup: _validate-local-sase _validate-local-sase-core
    @if [ ! -x {{ quote(venv_python) }} ]; then \
        uv venv {{ quote(venv_dir) }}; \
        uv pip install --python {{ quote(venv_python) }} -e ".[dev]"; \
    fi
    just _install-local-sase-core
    uv pip install --python {{ quote(venv_python) }} --no-deps -e {{ quote(local_sase_source) }}

install: _validate-local-sase _validate-local-sase-core _ensure-venv
    uv pip install --python {{ quote(venv_python) }} -e ".[dev]"
    just _install-local-sase-core
    uv pip install --python {{ quote(venv_python) }} --no-deps -e {{ quote(local_sase_source) }}

lint: _setup
    {{ venv_bin }}/ruff check src/ tests/
    {{ venv_bin }}/mypy

fmt: _setup
    {{ venv_bin }}/ruff format src/ tests/
    {{ venv_bin }}/ruff check --fix src/ tests/

test *args: _setup
    {{ venv_bin }}/pytest {{ args }}

check: lint test

clean:
    rm -rf build/ dist/ *.egg-info src/*.egg-info .mypy_cache/ .ruff_cache/ .pytest_cache/

build: _setup
    {{ venv_bin }}/python -m build
```

Recipe-by-recipe summary:
- **`default`** — `just --list` (lists recipes).
- **`_local-sase-source` / `_local-sase-core-source`** — debug helpers that print the resolved sibling-source paths.
- **`_validate-local-sase` / `_validate-local-sase-core`** — fail with a helpful message if the sibling `sase` (Python) or `sase-core` (Rust, via `crates/sase_core_py`) checkout can't be found in any of: an env-var override, a SASE linked-workspace layout, a `../sase` (or `../sase-core`) sibling directory, or `.sase-deps/<repo>` (the CI checkout location).
- **`_ensure-venv`** — creates `.venv` via `uv venv` if it doesn't already have a python.
- **`_install-local-sase-core`** — installs `maturin` into the venv if missing, then runs `maturin develop --release` inside the sibling `sase-core` repo's `crates/sase_core_py` (with `VIRTUAL_ENV` pointed at the local venv and `PYO3_USE_ABI3_FORWARD_COMPATIBILITY=1`) to build/install the Rust core Python bindings into the local venv.
- **`_setup`** — one-time bootstrap: creates the venv and does `uv pip install -e ".[dev]"` if the venv python doesn't exist yet, then always runs `_install-local-sase-core` and installs the sibling `sase` source in editable, `--no-deps` mode.
- **`install`** — public recipe: always does `uv pip install -e ".[dev]"`, then `_install-local-sase-core`, then editable `--no-deps` install of the sibling `sase` source.
- **`lint`** (depends on `_setup`) — `ruff check src/ tests/` then `mypy` (using pyproject config).
- **`fmt`** (depends on `_setup`) — `ruff format src/ tests/` then `ruff check --fix src/ tests/`.
- **`test *args`** (depends on `_setup`) — `pytest {{args}}` (accepts pass-through args).
- **`check`** — just `lint` then `test` (no separate coverage step).
- **`clean`** — removes `build/`, `dist/`, `*.egg-info`, `src/*.egg-info`, `.mypy_cache/`, `.ruff_cache/`, `.pytest_cache/`.
- **`build`** (depends on `_setup`) — `python -m build`.

**Note**: there is **no `test-cov` recipe** in this Justfile — despite `pytest-cov` being a listed dev dependency, coverage isn't wired into any Justfile recipe or into pytest `addopts`.

Also worth noting for `sase-research`: this Justfile encodes a **coordinated multi-repo dev workflow** — it expects a sibling `sase` (pure Python) checkout *and* a sibling `sase-core` (Rust, built via `maturin develop --release`) checkout, resolvable via env var override → SASE linked-workspace layout → `../sase`(`-core`) sibling dir → `.sase-deps/<repo>` (CI). If `sase-research` doesn't need the Rust `sase-core` bindings, the `sase-core`/`maturin` machinery can likely be dropped, keeping only the `sase` source-checkout resolution/validation/install pattern.

---

## 3. `.gitignore`, `LICENSE`, `CHANGELOG.md`, `AGENTS.md`/`CLAUDE.md`

**`.gitignore`** (full contents):
```
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# C extensions
*.so

# Distribution / packaging
build/
dist/
*.egg-info/
*.egg
wheels/

# Virtual environments
.venv/
venv/
ENV/

# Test / coverage
.tox/
.nox/
htmlcov/
.coverage
.coverage.*
coverage.xml
*.cover
*.py,cover
.pytest_cache/

# Mypy
.mypy_cache/

# Ruff
.ruff_cache/

# IDE
.vscode/
.idea/
*.swp
*.swo
*~

# OS
.DS_Store
Thumbs.db

# exploration markdown files
explore/

# Private Claude Instructions
CLAUDE.local.md

# Copied context files (from @ file references)
.sase/

# Hypothesis
.hypothesis/
```

**`LICENSE`**: MIT License. Copyright line: `Copyright (c) 2026 Bryan Bugyi`. Standard MIT boilerplate text follows (permission grant + "AS IS" warranty disclaimer). The `pyproject.toml` references it via `license = "MIT"` and `license-files = ["LICENSE"]` (SPDX-style license expression + explicit license-files list, which is the modern PEP 639-ish hatchling-supported form — note the CHANGELOG even has a historical fix entry: *"add MIT LICENSE file and bundle it in wheels"*, confirming this was deliberately fixed to ensure the license ships in the wheel).

**`CHANGELOG.md`**: Standard **release-please-managed** changelog (Keep-a-Changelog-adjacent but specifically release-please's format, not manually maintained). Header is `# Changelog`, and each release section looks like:
```
## [0.4.7](https://github.com/sase-org/sase-telegram/compare/v0.4.6...v0.4.7) (2026-08-08)

### Features
* add declared-input step flow for gate options ([afa933b](...))
...
### Bug Fixes
* **bead:** fail closed on project discovery errors ([89e73d0](...))
```
Entries are grouped under `### Features`, `### Bug Fixes`, `### ⚠ BREAKING CHANGES`, `### Documentation`, etc., derived automatically from Conventional Commit messages, each linking to the compare URL and commit SHA. This is exactly release-please's auto-generated changelog format (do not hand-edit sections — release-please appends new release blocks on top).

**`AGENTS.md`** (full contents):
```markdown
# sase-telegram - Agent Instructions

## Overview
Telegram integration chop for sase. Provides outbound notification delivery
and inbound action handling via Telegram bot API.

## Build & Run
```bash
just install    # Install in editable mode with dev deps
just lint       # ruff + mypy
just fmt        # Auto-format
just test       # pytest
just check      # lint + test
```

## Architecture
- `src/sase_telegram/credentials.py` — Bot token (via `pass`), chat ID and username (env vars)
- `src/sase_telegram/telegram_client.py` — Sync wrapper with retry/backoff and message splitting
- `src/sase_telegram/formatting.py` — Notification → MarkdownV2 formatting and inline keyboards
- `src/sase_telegram/callback_data.py` — Encode/decode inline keyboard callback data
- `src/sase_telegram/inbound.py` — Pure logic for callback/text/photo processing (no API calls)
- `src/sase_telegram/outbound.py` — High-water mark tracking, exclusive lock, unsent detection
- `src/sase_telegram/pending_actions.py` — Persist pending actions to JSON (24h stale cleanup)
- `src/sase_telegram/rate_limit.py` — Sliding window rate limiter
- `src/sase_telegram/pdf_convert.py` — Markdown to PDF via pandoc (engine fallback chain)
- `src/sase_telegram/scripts/` — CLI entry points for outbound/inbound chops
- Depends on `sase>=0.1.0` and `python-telegram-bot>=21.0`

## Code Conventions
- Absolute imports: `from sase_telegram.credentials import get_bot_token`
- Target Python 3.12+
- Follow ruff rules matching sase core
```

**`CLAUDE.md`** (full contents — just a redirect):
```
@AGENTS.md
```
This uses Claude Code's `@file` reference syntax to inline `AGENTS.md` content rather than duplicating it — a pattern worth reusing verbatim for `sase-research` (single source of truth in `AGENTS.md`, `CLAUDE.md` just points at it).

---

## 4. `.github/workflows/*.yml`

Three workflow files exist: `ci.yml`, `pr-title.yml`, `publish.yml`.

### `ci.yml` — lint + Python-version test matrix, with coordinated sibling-repo checkout
```yaml
name: CI

on:
  push:
    branches: [master]
  pull_request:
    branches: [master]

permissions:
  contents: read

jobs:
  check:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        python-version: ["3.12", "3.13"]
    steps:
      - uses: actions/checkout@v4
      - uses: actions/checkout@v4
        with:
          repository: sase-org/sase
          path: .sase-deps/sase
          token: ${{ secrets.SASE_RELEASE_TOKEN || github.token }}
      - uses: actions/checkout@v4
        with:
          repository: sase-org/sase-core
          path: .sase-deps/sase-core
          token: ${{ secrets.SASE_RELEASE_TOKEN || github.token }}
      - uses: astral-sh/setup-uv@v4
        with:
          enable-cache: true
          cache-dependency-glob: "**/pyproject.toml"
      - uses: extractions/setup-just@v2
      - uses: dtolnay/rust-toolchain@stable
      - name: Set up Python ${{ matrix.python-version }}
        run: |
          uv python install ${{ matrix.python-version }}
          uv venv --python ${{ matrix.python-version }} .venv
      - name: Install dependencies
        run: |
          just install
          uv pip install --python .venv/bin/python maturin
          (
            cd .sase-deps/sase-core/crates/sase_core_py
            VIRTUAL_ENV="${GITHUB_WORKSPACE}/.venv" \
              PYO3_USE_ABI3_FORWARD_COMPATIBILITY=1 \
              "${GITHUB_WORKSPACE}/.venv/bin/maturin" develop --release
          )
          uv pip install --python .venv/bin/python --no-deps -e .sase-deps/sase
      - name: Lint
        if: ${{ matrix.python-version == '3.12' }}
        run: just lint
      - name: Run tests
        run: just test
```
Summary: single job `check`, matrixed over Python `3.12` and `3.13`. It checks out **three repos**: the plugin itself, `sase-org/sase` into `.sase-deps/sase`, and `sase-org/sase-core` into `.sase-deps/sase-core` (using `secrets.SASE_RELEASE_TOKEN` if set, else the default `github.token`). It sets up `uv`, `just`, and a stable Rust toolchain (`dtolnay/rust-toolchain@stable`, needed to build the Rust core via maturin). It builds the venv for the matrixed Python version, runs `just install`, installs `maturin`, builds/installs the `sase-core` Python bindings via `maturin develop --release`, and installs the `sase` source in editable `--no-deps` mode — mirroring exactly what the Justfile's `_setup`/`install` recipes do locally. Lint only runs once (gated to Python 3.12); tests run on every matrix leg.

**This directly answers point 8**: `sase-telegram`'s CI *does* check out sibling repos from source (`sase` and `sase-core`) for compatibility testing — so you don't need to look at `sase-github` for this pattern; `sase-telegram` already demonstrates it. (If `sase-research` has no Rust-core dependency, you'd likely only need the `sase` checkout/install part, dropping the Rust toolchain, maturin, and `sase-core` checkout steps.)

### `pr-title.yml` — Conventional Commit PR-title check
```yaml
name: PR Title

on:
  pull_request:
    branches: [master]
    types: [opened, edited, reopened, ready_for_review, synchronize]

permissions:
  contents: read

jobs:
  conventional-title:
    name: Conventional PR title
    runs-on: ubuntu-latest
    steps:
      - name: Validate squash-merge title
        env:
          PR_TITLE: ${{ github.event.pull_request.title }}
        run: |
          set -euo pipefail

          allowed_types='feat|fix|perf|docs|ci|test|chore|refactor|build|deps'
          pattern="^(${allowed_types})(\([A-Za-z0-9._/-]+\))?!?: [^[:space:]].*"

          if [[ ! "${PR_TITLE}" =~ ${pattern} ]]; then
            printf 'PR title must follow Conventional Commits so squash merges produce useful release metadata.\n' >&2
            printf 'Allowed types: feat, fix, perf, docs, ci, test, chore, refactor, build, deps.\n' >&2
            printf 'Examples: fix(release): add release workflow, feat!: remove legacy config.\n' >&2
            printf 'Actual title: %s\n' "${PR_TITLE}" >&2
            exit 1
          fi
```
Single job, no external actions — pure bash regex validation of the PR title against Conventional Commits grammar (`type(scope)!: subject`), needed because merges are squash-merged and release-please derives its changelog/version bump from the squash-commit (== PR title) message.

### `publish.yml` — release-please + build + install-smoke-test + trusted PyPI publish
```yaml
name: Publish

on:
  push:
    branches: [master]
  workflow_dispatch:
    inputs:
      publish_existing:
        description: Publish the existing 0.1.0 release artifacts
        required: true
        type: boolean
        default: false

jobs:
  release:
    runs-on: ubuntu-latest
    permissions:
      contents: write
      issues: write
      pull-requests: write
    outputs:
      release_created: ${{ steps.release.outputs.release_created || 'false' }}
    steps:
      - uses: googleapis/release-please-action@v5
        if: ${{ github.event_name == 'push' }}
        id: release
        with:
          token: ${{ secrets.SASE_RELEASE_TOKEN || secrets.GITHUB_TOKEN }}
          config-file: release-please-config.json
          manifest-file: .release-please-manifest.json

  build:
    needs: release
    if: ${{ needs.release.outputs.release_created == 'true' || (github.event_name == 'workflow_dispatch' && inputs.publish_existing == true) }}
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - uses: actions/checkout@v4
      - uses: astral-sh/setup-uv@v4
        with:
          enable-cache: true
          cache-dependency-glob: "**/pyproject.toml"
      - name: Set up Python
        run: uv python install 3.12
      - name: Build package
        run: uv build
      - uses: actions/upload-artifact@v4
        with:
          name: dist
          path: dist/

  install-smoke:
    needs: build
    runs-on: ubuntu-latest
    steps:
      - uses: actions/download-artifact@v4
        with:
          name: dist
          path: dist/
      - uses: astral-sh/setup-uv@v4
      - name: Set up Python
        run: uv python install 3.12
      - name: Install built sase-telegram wheel into a fresh venv
        run: |
          uv venv --python 3.12 /tmp/smoke-venv
          uv pip install --python /tmp/smoke-venv/bin/python dist/*.whl
      - name: Smoke check
        run: |
          /tmp/smoke-venv/bin/python -c "import sase_telegram"
          /tmp/smoke-venv/bin/sase_chop_tg_outbound --help > /dev/null
          /tmp/smoke-venv/bin/sase_chop_tg_inbound --help > /dev/null

  publish:
    needs: [release, build, install-smoke]
    if: ${{ needs.release.outputs.release_created == 'true' || (github.event_name == 'workflow_dispatch' && inputs.publish_existing == true) }}
    runs-on: ubuntu-latest
    environment: pypi
    permissions:
      id-token: write
    steps:
      - uses: actions/download-artifact@v4
        with:
          name: dist
          path: dist/
      - uses: pypa/gh-action-pypi-publish@release/v1
```
Four jobs:
1. **`release`** — runs `googleapis/release-please-action@v5` (only on `push`, not on manual `workflow_dispatch`) with `contents: write`, `issues: write`, `pull-requests: write` permissions, using `config-file: release-please-config.json` and `manifest-file: .release-please-manifest.json`. Auth token is `secrets.SASE_RELEASE_TOKEN` (a PAT, presumably needed so release-please's PRs/tags trigger other workflows — the default `GITHUB_TOKEN` can't) falling back to `secrets.GITHUB_TOKEN`. Exposes `release_created` as a job output.
2. **`build`** — gated on `release_created == true` OR a manual dispatch with `publish_existing == true`. Checks out, sets up `uv` + Python 3.12, runs `uv build` (produces sdist+wheel), uploads `dist/` as the `dist` artifact.
3. **`install-smoke`** — downloads the `dist` artifact, creates a **fresh** venv at `/tmp/smoke-venv`, `uv pip install`s the built wheel (not editable, not from source — testing the actual publishable artifact), then does a real-world smoke check: `python -c "import sase_telegram"` plus `--help` invocations of both console scripts. This is exactly the "wheel-build-and-smoke-test job" the user asked about.
4. **`publish`** — needs `[release, build, install-smoke]`, gated on the same condition as `build`. Uses `environment: pypi` (a GitHub Environment, presumably configured with PyPI Trusted Publisher restrictions) and `permissions: id-token: write` (required for OIDC-based trusted publishing). Downloads the `dist` artifact and runs `pypa/gh-action-pypi-publish@release/v1` with **no explicit `password`/API-token input** — this is the OIDC "trusted publishing" pattern (no PyPI API token secret needed at all; PyPI trusts the GitHub Actions OIDC token scoped to this repo+environment+workflow).

To replicate trusted publishing for `sase-research`, you'd need: (a) register `sase-research` on PyPI with a Trusted Publisher entry pointing at the `sase-org/sase-research` repo, the `publish.yml` workflow filename, and a `pypi` environment; (b) create a `pypi` GitHub Environment in the new repo; (c) copy this `publish` job verbatim (just `id-token: write` + `pypa/gh-action-pypi-publish@release/v1`, no secrets needed).

---

## 5. `release-please-config.json` and `.release-please-manifest.json`

**`release-please-config.json`** (full contents):
```json
{
  "$schema": "https://raw.githubusercontent.com/googleapis/release-please/main/schemas/config.json",
  "bootstrap-sha": "c496a358c8b0b5eec62c592f16a992833d6e0e7c",
  "release-type": "python",
  "initial-version": "0.1.0",
  "include-v-in-tag": true,
  "include-component-in-tag": false,
  "bump-minor-pre-major": true,
  "bump-patch-for-minor-pre-major": true,
  "packages": {
    ".": {
      "component": "sase-telegram"
    }
  }
}
```

**`.release-please-manifest.json`** (full contents):
```json
{".":"0.4.7"}
```

Notes: `release-type: "python"` tells release-please to bump `version` in `pyproject.toml` (and any `__version__`-style files it recognizes) directly. `bootstrap-sha` pins the commit release-please starts scanning conventional commits from. `bump-minor-pre-major`/`bump-patch-for-minor-pre-major` are the standard "we're pre-1.0, treat breaking changes as minor bumps and features as patch bumps" settings — appropriate to carry over verbatim for a brand-new `sase-research` package that will also start below `1.0.0`. `include-component-in-tag: false` means tags are just `vX.Y.Z` (not `sase-telegram-vX.Y.Z`), matching a single-package repo. The manifest is a single-entry map (path `"."` → current version) that release-please rewrites on every release PR merge.

---

## 6. `src/sase_telegram/` and `tests/` layout

**`src/sase_telegram/`** (one level deep):
```
__init__.py
agent_format.py
bead_format.py
callback_data.py
credentials.py
custom_commands.py
enabled.py
formatting.py
gate_flow.py
gate_inputs.py
inbound.py
outbound.py
pdf_convert.py
pdf_style.css        <- non-.py resource file, bundled via default hatchling behavior
pending_actions.py
question_flow.py
rate_limit.py
scripts/             <- subpackage
  __init__.py
  sase_tg_inbound.py
  sase_tg_outbound.py
show_entities.py
show_format.py
telegram_client.py
```

**`tests/`** (all files):
```
__init__.py
test_bead_format.py
test_callback_data.py
test_credentials.py
test_custom_commands.py
test_custom_gates.py
test_enabled.py
test_formatting.py
test_gate_flow.py
test_gate_inputs.py
test_inbound.py
test_integration.py
test_justfile.py
test_outbound.py
test_pdf_convert.py
test_pending_actions.py
test_question_flow.py
test_rate_limit.py
test_show_entities.py
test_show_format.py
test_snooze_resurface_e2e.py
test_telegram_client.py
```
Notice `tests/test_justfile.py` — a test that presumably validates properties of the `Justfile` itself (e.g. that recipes exist/parse), a pattern you could mirror for `sase-research` if you want CI to catch Justfile regressions.

---

## 7. `docs/` directory

Only three files exist under `docs/`:

- **`docs/architecture.md`** — High-level module map and data-flow diagram for the two CLI entry points (`outbound`/`inbound`). Explains the module dependency graph (`telegram_client.py` at the core, feeding `outbound.py`/`inbound.py`, which depend on `formatting.py`/`pending_actions.py`, which depend on `bead_format.py`, `rate_limit.py`, `credentials.py`, `callback_data.py`, `pdf_convert.py`), summarizes the outbound pipeline (lock → read unsent past high-water cursor → format → send → save pending → advance cursor) and inbound pipeline (fetch updates → save offset → dispatch by type), and lists "Key Design Decisions" (machine enable gate via `~/.sase/telegram_is_enabled`, pure-logic/API separation, high-water-mark cursor semantics, exclusive locking, rate limiting, two-step feedback isolation, parse-mode fallback, shared PDF rendering).
- **`docs/inbound.md`** — Deep-dive spec for the inbound chop: the machine-enable no-op flag, CLI usage/flags, the full callback-data envelope format (`{action_type}:{notif_id_prefix}:{choice}`, 64-byte Telegram limit), direct vs. two-step ("feedback"/"custom") action flows, the full priority-ordered text-message dispatch table (two-step completion → slash commands → configured custom commands → unknown slash → agent launch), photo/album handling, agent-launch mechanics (xprompt expansion, VCS shorthand, multi-model directives, auto-naming, code-marker reconstruction, project context memory), `/changes` Patch-tag listing, `/bead` project-scoped bead picker/lookup, `/update` detached-worker flow, `/show` agent/clan/family/tribe kinship views, and the custom-slash-command YAML config schema (`telegram.commands.<name>: {description, run, output, timeout}`) with frontmatter-driven PDF/message output rules.
- **`docs/outbound.md`** — Deep-dive spec for the outbound chop: machine-enable flag, CLI usage/flags, the 7-step delivery pipeline (lock → load unsent past HWM cursor → stale-pending cleanup → format+send → save pending actions → advance HWM → release lock), the versioned `(activity_at, id)` delivery-cursor JSON format and its resurface/snooze semantics, message-formatting rules (content-size tiers: inline / expandable blockquote / truncated-with-attachment), a table of notification types → body content → buttons (Plan Approval, HITL, Question, Generic Gate, Workflow Complete, Agent Launched/Killed, Error Digest, Image Generated), and attachment-handling rules (plan PDFs, diff embedding, research-file mentions, digest files, media-type routing/fallback).

For `sase-research`, a natural equivalent docs set would be `docs/architecture.md` (module map + data flow + key design decisions) plus one doc per major functional surface analogous to `inbound.md`/`outbound.md` — i.e., docs organized around the plugin's actual entry points/pipelines rather than a generic "usage.md", following this repo's pattern of "one doc per CLI entry point, one doc for the cross-cutting architecture."

---

## 8. Python version floor and coordinated-source CI pattern

- **Python floor**: `requires-python = ">=3.12"` in `pyproject.toml`; ruff `target-version = "py312"`; mypy `python_version = "3.12"`. CI test matrix covers `["3.12", "3.13"]` (lint only runs on the 3.12 leg).
- **Coordinated sibling-repo CI pattern**: contrary to a "might not have this" assumption, **`sase-telegram` does have this pattern** — no need to fall back to `sase-github` as the reference. Its `ci.yml` `check` job checks out `sase-org/sase` (into `.sase-deps/sase`) and `sase-org/sase-core` (into `.sase-deps/sase-core`), installs a Rust toolchain, builds the Rust `sase-core` Python bindings via `maturin develop --release`, and installs the `sase` package from source in editable `--no-deps` mode — all before running lint/tests. The Justfile encodes the identical resolution logic for local development (env-var override → SASE linked-workspace layout → `../sase` sibling directory → `.sase-deps/sase` CI location). This is the "coordinated-source" testing pattern the user was asking about — `sase-telegram` needs it because it links against `sase-core`'s Rust bindings and depends on `sase>=0.1.0` from source for compatibility testing against unreleased core changes. If `sase-research` has no Rust dependency, you can drop the `sase-core`/maturin/Rust-toolchain parts of both the Justfile and `ci.yml` and keep only the `sase`-source-checkout/install portion (which is still likely useful if `sase-research` depends on unreleased `sase` APIs during development).

Two of three research agents are done; sase-telegram's structure is now clear (including that it already has the coordinated-source CI pattern I need). Still waiting on the sase-core artifact-provider registry contract report before writing any provider-spec code.

Still waiting on the last agent.

# Report: `sase` Artifact-Provider Plugin System (for `sase-research`)

Repo: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12`, branch `master`, HEAD `f53e43ab1` ("feat!: add artifact provider registry"). All paths below are repo-relative unless noted.

**Read this first — your two central assumptions are both slightly off:**

1. The pluggy hookspec methods are **not** named `sase_artifact_ref_providers()` / `sase_file_hook_providers()`. They are:
   - `artifact_ref_provider_specs()`
   - `artifact_file_hook_provider_specs()`

   defined on `ArtifactProviderHookSpec` in `src/sase/artifact_providers/_hookspec.py`, under the pluggy project name `"sase_artifact"`.

2. There is no dataclass/pydantic model named `ArtifactRefProviderSpec` or `FileHookProviderSpec` on the Python side. Provider specs are **plain `dict`/`Mapping[str, Any]`** on the Python side (your hookimpl literally returns dicts). The *typed* shape only exists in Rust (`ArtifactRefProviderSpecWire` and friends in `sase-core`), which Python calls through a PyO3 binding for validation + digesting. Python only has thin wrapper dataclasses for the **registry records** (`ArtifactRefProviderRecord`, `FileHookProviderRecord`), not for the spec payloads themselves.

Everything below is organized by your numbered questions.

---

## 1. The `sase_artifact` pluggy project — hookspecs

File: `src/sase/artifact_providers/_hookspec.py` (36 lines total):

```python
hookspec = pluggy.HookspecMarker("sase_artifact")
hookimpl = pluggy.HookimplMarker("sase_artifact")


class ArtifactProviderHookSpec:
    """Hook specifications for declarative artifact providers."""

    @hookspec
    def artifact_ref_provider_specs(
        self,
    ) -> Iterable[Mapping[str, Any]] | Mapping[str, Any] | None:
        """Return document artifact-reference provider specs."""
        ...

    @hookspec
    def artifact_file_hook_provider_specs(
        self,
    ) -> Iterable[Mapping[str, Any]] | Mapping[str, Any] | None:
        """Return file-hook provider templates."""
        ...
```

Both hooks are **not** `firstresult` — pluggy's default (collect-all) applies, and the registry (`src/sase/artifact_providers/registry.py:255-274`) iterates over every returned item:

```python
try:
    ref_results = pm.hook.artifact_ref_provider_specs()
except Exception as exc:
    ...
try:
    file_hook_results = pm.hook.artifact_file_hook_provider_specs()
except Exception as exc:
    ...

for result in ref_results:
    for spec in _iter_mapping_specs(result):
        ref_candidates.append((spec, provenance))
for result in file_hook_results:
    for spec in _iter_mapping_specs(result):
        file_hook_candidates.append((spec, provenance))
```

`_iter_mapping_specs` (`registry.py:296-303`) accepts `None`, a single `Mapping`, or an iterable of `Mapping`s (non-`Mapping` items are silently dropped) — so your hookimpl can return one dict, a tuple of dicts, or `None`.

**Return type is `dict`, not a dataclass.** Concretely, `_builtin.py`'s implementation (below) returns `tuple[Mapping[str, Any], ...]`.

**Important operational gotcha (not documented anywhere):** `assemble_artifact_provider_registry()` (`registry.py:133-215`) loops over **both** entry-point groups (`sase_artifact_refs`, `sase_file_hooks`) and, for *every* entry point it finds in *either* group, instantiates the plugin and calls **both** `artifact_ref_provider_specs()` and `artifact_file_hook_provider_specs()` on it (`_collect_plugin_specs`, `registry.py:225-274`), regardless of which group the entry point came from. If you register the *same* plugin class under both `[project.entry-points."sase_artifact_refs"]` and `[project.entry-points."sase_file_hooks"]`, it will be instantiated and both hooks called **twice**, producing duplicate provider ids/kinds and `duplicate_ref_provider` / `duplicate_file_hook_provider` diagnostics. **Register your class under exactly one of the two groups** even if it implements both hookspec methods.

---

## 2. `ArtifactRefProviderSpec` — actual shape (dict, Rust-validated)

### Python side: no dataclass, just a Rust validation call

`src/sase/artifact_providers/registry.py:218-222`:

```python
def validate_ref_provider_spec(spec: Mapping[str, Any]) -> str:
    """Validate *spec* through Rust and return its stable digest."""

    require_rust_binding("artifact_ref_provider_spec_validate")(dict(spec))
    return str(require_rust_binding("artifact_ref_provider_spec_digest")(dict(spec)))
```

This is called from `_validate_ref_providers` (`registry.py:363-374`) after checking `provider` and `ref.kind` are present and not duplicated. On any exception it's converted to an `ArtifactProviderDiagnostic` (severity `"error"`) and the candidate is **dropped, not raised** — so a broken provider spec fails soft (logged/reported via `sase doctor`, not a crash).

### Rust side: the actual typed schema

File: `sase/repos/linked/sase-core/crates/sase_core/src/artifact_ref/provider_spec.rs` (this is the linked `sase-core` checkout under this workspace, i.e. the Rust crate backing `sase_core_rs`).

```rust
pub const ARTIFACT_REF_PROVIDER_SPEC_WIRE_SCHEMA_VERSION: u64 = 1;

const RESERVED_KINDS: &[&str] = &["stitch", "patch", "bead", "agent", "file"];
const PROPERTY_TYPES: &[&str] = &[
    "string", "enum", "boolean", "integer", "number", "date", "datetime", "string_list",
];
const PUBLICATION_LINKS: &[&str] = &["vcs_permalink", "agents_object", "none"];
const PUBLICATION_REFERENCED_BY: &[&str] = &["markdown_table", "none"];
const PROPERTY_SOURCES: &[&str] = &["markdown_frontmatter", "provider"];

pub struct ArtifactRefProviderSpecWire {
    pub schema_version: u64,
    pub provider: String,
    #[serde(rename = "ref")]
    pub reference: ArtifactRefProviderRefSpecWire,
}

pub struct ArtifactRefProviderRefSpecWire {
    pub kind: String,
    pub expansion_format: String,
    #[serde(default)]
    pub properties: BTreeMap<String, ArtifactRefPropertySpecWire>,
    #[serde(default)]
    pub detail: ArtifactRefDetailSpecWire,
    #[serde(default)]
    pub identity: ArtifactRefIdentitySpecWire,
    #[serde(default)]
    pub inventory: ArtifactRefInventorySpecWire,
    pub publication: ArtifactRefPublicationSpecWire,
}

pub struct ArtifactRefPropertySpecWire {
    #[serde(rename = "type")]
    pub property_type: String,
    #[serde(default)]
    pub values: Vec<String>,
    pub source: String,
}

pub struct ArtifactRefDetailSpecWire {
    #[serde(default)]
    pub fields: Vec<String>,
}

pub struct ArtifactRefIdentitySpecWire {
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub property: Option<String>,
}

pub struct ArtifactRefInventorySpecWire {
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub globs: Option<Vec<String>>,
}

pub struct ArtifactRefPublicationSpecWire {
    pub link: String,
    pub referenced_by: String,
}
```

**Required vs. optional, exactly** (per `#[serde(default)]` presence — no default means required, since `serde_json::from_value` is used directly on your dict with no relaxed coercion):

| Field | Required? | Type |
|---|---|---|
| `schema_version` | **required** | `u64` — must literally equal `1` |
| `provider` | **required** | `String` — must match `[a-z][a-z0-9_-]*` |
| `ref` (Python key; Rust field `reference`) | **required** | object |
| `ref.kind` | **required** | `String` — must match `[a-z][a-z0-9_-]*`, and must **not** be one of the reserved kinds `stitch`, `patch`, `bead`, `agent`, `file` |
| `ref.expansion_format` | **required** | `String` |
| `ref.properties` | optional (default `{}`) | map of name → property spec |
| `ref.properties.<name>.type` | **required** (if property present) | one of `string, enum, boolean, integer, number, date, datetime, string_list` |
| `ref.properties.<name>.values` | optional (default `[]`) | list of nonempty strings; **required non-empty when `type == "enum"`** |
| `ref.properties.<name>.source` | **required** | one of `markdown_frontmatter, provider` |
| `ref.detail` | optional (default `{fields: []}`) | object |
| `ref.detail.fields` | optional (default `[]`) | list of strings; **each must name an already-declared `ref.properties` key** or validation fails |
| `ref.identity` | optional (default `{}`) | object |
| `ref.identity.property` | optional (default `None`) | string; **must name a declared `ref.properties` key** if present |
| `ref.inventory` | optional (default `{}`) | object |
| `ref.inventory.globs` | optional (default `None`) | list of repo-relative globs; compiled through `ArtifactPathFilter::compile`, which rejects unsafe/escaping patterns (e.g. `"../escape"` is rejected in the Rust test suite) |
| `ref.publication` | **required** | object |
| `ref.publication.link` | **required** | one of `vcs_permalink, agents_object, none` |
| `ref.publication.referenced_by` | **required** | one of `markdown_table, none` |

Validation function, `sase/repos/linked/sase-core/crates/sase_core/src/artifact_ref/provider_spec.rs:91-165` (`validate_artifact_ref_provider_spec`), enforces every rule above plus identifier regex `[a-z][a-z0-9_-]*` for both `provider` and `ref.kind` (implemented at line 179-196, `validate_identifier`).

### Expansion-format placeholders

`ref.expansion_format` is validated by `validate_artifact_ref_expansion_format` (`sase/repos/linked/sase-core/crates/sase_core/src/artifact_ref/expansion.rs:33-46`), which tokenizes `{name}` placeholders and requires each to be one of exactly this fixed set (`expansion.rs:12-25`):

```rust
pub const ARTIFACT_REF_EXPANSION_PLACEHOLDERS: &[&str] = &[
    "kind", "argument", "canonical_argument", "display_label", "project",
    "repository", "repo_relative_path", "checkout_path", "sidecar_role",
    "captured_revision", "captured_digest", "logical_path",
];
```

`{{` / `}}` are literal-escape sequences for a literal brace. An unknown placeholder name, or unbalanced `{`/`}`, is a validation error. The builtin plan provider and the Rust test's "research" example both use the same value: `"{kind}:{argument}"`.

### The Rust test fixture literally named "research"

`provider_spec.rs:198-232` — the crate's own unit tests build their `valid_spec()` fixture with `provider: "research"`, `ref.kind: "research"` and full publication/inventory/detail/identity — this is effectively the canonical "shape a third-party ref-provider spec should mirror":

```rust
fn valid_spec() -> ArtifactRefProviderSpecWire {
    ArtifactRefProviderSpecWire {
        schema_version: ARTIFACT_REF_PROVIDER_SPEC_WIRE_SCHEMA_VERSION,
        provider: "research".to_string(),
        reference: ArtifactRefProviderRefSpecWire {
            kind: "research".to_string(),
            expansion_format: "{kind}:{argument}".to_string(),
            properties: BTreeMap::from([(
                "status".to_string(),
                ArtifactRefPropertySpecWire {
                    property_type: "enum".to_string(),
                    values: vec!["draft".to_string(), "final".to_string()],
                    source: "markdown_frontmatter".to_string(),
                },
            )]),
            detail: ArtifactRefDetailSpecWire { fields: vec!["status".to_string()] },
            identity: ArtifactRefIdentitySpecWire { property: Some("status".to_string()) },
            inventory: ArtifactRefInventorySpecWire { globs: Some(vec!["**/*.md".to_string()]) },
            publication: ArtifactRefPublicationSpecWire {
                link: "vcs_permalink".to_string(),
                referenced_by: "markdown_table".to_string(),
            },
        },
    }
}
```

Equivalent Python dict shape (matching the wire schema exactly, `ref` not `reference` because of the serde rename):

```python
{
    "schema_version": 1,
    "provider": "research",
    "ref": {
        "kind": "research",
        "expansion_format": "{kind}:{argument}",
        "properties": {
            "status": {"type": "enum", "values": ["draft", "final"], "source": "markdown_frontmatter"},
        },
        "detail": {"fields": ["status"]},
        "identity": {"property": "status"},
        "inventory": {"globs": ["**/*.md"]},
        "publication": {"link": "vcs_permalink", "referenced_by": "markdown_table"},
    },
}
```

**This is a strong signal**: `sase-core`'s own test suite already uses `"research"` as its example provider id/kind, and `tests/test_artifact_provider_registry.py` and `tests/test_sidecar_ref_config.py` in the main `sase` repo both use `"sase-research"` / `"research"` as the canonical third-party example (see §7) — so your plugin's naming plan aligns exactly with what the implementers had in mind while building this feature.

**Important digest note:** `validate_ref_provider_spec` returns a **sha256 hex digest over the *normalized serialized* spec** (`artifact_ref_provider_spec_digest`, `provider_spec.rs:168-177`) — this is used for change-detection/parity checks (see the `use:`-vs-inline test in §7), not a security signature.

**Important clarification about "schema 5":** The `schema_version: 1` inside a ref-provider spec is a **completely different, unrelated version counter** from the "wire schema 5" mentioned in your `cb453a529` commit (`feat(artifact-ref)!: bump wire schema to 5 for stitch/patch/file-path kinds`). That commit bumped `ARTIFACT_REF_PARSE_WIRE_SCHEMA_VERSION` / `ARTIFACT_REF_RESOLUTION_WIRE_SCHEMA_VERSION` (both `= 5`, in `sase/repos/linked/sase-core/crates/sase_core/src/artifact_ref/wire.rs:6-7`), which describe the *entry*/*resolution* wire format, not the provider-spec format. `ARTIFACT_REF_PROVIDER_SPEC_WIRE_SCHEMA_VERSION` is still `1`. Your plugin's spec dict must set `"schema_version": 1`, not `5`.

---

## 3. `FileHookProviderRecord` / file-hook provider template — actual shape

Again, **no dataclass for the spec itself** — the hookimpl returns a plain dict; the registry produces a `FileHookProviderRecord` dataclass to hold the *validated* result.

Registry record, `src/sase/artifact_providers/registry.py:75-82`:

```python
@dataclass(frozen=True)
class FileHookProviderRecord:
    """One validated file-hook provider template."""

    provider_id: str
    template: Mapping[str, Any]
    required_fields: tuple[str, ...]
    provenance: ArtifactProviderProvenance
```

Validation of the raw dict happens purely in Python (no Rust involved for file hooks), in `_validate_file_hook_providers` (`registry.py:389-467`):

- `provider` — **required**, nonempty string, must not duplicate another provider's id (`duplicate_file_hook_provider` diagnostic otherwise).
- `schema_version` — **required**, must equal `FILE_HOOK_PROVIDER_SPEC_SCHEMA_VERSION = 1` (`registry.py:26`).
- `file_hook` — **required**, must be a `Mapping`. This is the *template* fragment that gets deep-merged with the user's local `use:` override (see below). It is **not** validated against the full `fileHook` JSON schema at registration time — only that it's a mapping.
- `required` — **optional**, defaults to `()`. If present must be a `list` of nonempty strings; each name is a field that a local config entry **must** supply itself when it does `use: <provider_id>` (see below). Duplicates are deduped via `dict.fromkeys`.

So the exact dict shape your `sase-research` plugin's `artifact_file_hook_provider_specs()` should return, mirroring the test fixture in `tests/test_artifact_provider_registry.py:126-144`:

```python
{
    "schema_version": 1,
    "provider": "research-highlights",
    "required": ["command"],
    "file_hook": {
        "description": "Render research highlights.",
        "filters": {
            "sidecars": ["research"],
            "path_globs": ["reports/**/*.md"],
        },
        "timeout": "30s",
    },
}
```

Notice `command` is *deliberately omitted* from the `file_hook` template and listed in `required` — this is exactly the "required user override" mechanism you asked about. The `file_hook` mapping's inner shape matches the config-level `fileHook`/`fileHookFilters` fields (see §8): `description`, `command`, `filters` (with `projects`, `sidecars`, `path_globs`, `agent_name_globs`, `ops`), `timeout`. `name` is intentionally **not** part of the template (see below — it defaults to the provider id).

### How `use:` resolves against a provider template (and required-field enforcement)

`src/sase/config/file_hooks.py:259-296`:

```python
def _resolve_file_hook_provider(
    item: object,
    *,
    registry: ArtifactProviderRegistry,
) -> object:
    if not isinstance(item, Mapping) or "use" not in item:
        return item
    raw_use = item.get("use")
    if not isinstance(raw_use, str) or not raw_use.strip():
        raise ValueError("'use' must be a nonempty file-hook provider id")
    provider_id = raw_use.strip()
    providers = registry.file_hook_providers_by_id
    provider = providers.get(provider_id)
    if provider is None:
        raise ValueError(
            f"unknown file-hook provider '{provider_id}'; install a plugin "
            "exposing the sase_file_hooks entry point group or remove 'use'"
        )
    for field_name in provider.required_fields:
        if _missing_local_override(item, field_name):
            raise ValueError(
                f"file-hook provider '{provider_id}' requires local field "
                f"'{field_name}'"
            )
    overrides = {str(key): value for key, value in item.items() if str(key) != "use"}
    merged = _deep_merge(provider.template, overrides)
    merged.setdefault("name", provider_id)
    return merged
```

`_missing_local_override` (`file_hooks.py:289-295`) treats an absent key, a blank string, or `None` all as "missing" — so `required: ["command"]` means the user's local `- use: research-highlights` entry in `sase.yml` **must** supply a nonblank `command:` sibling key, or the whole hook entry is skipped with a `ValueError` (soft-failed, logged at `WARNING` — see `_load_file_hooks`, `file_hooks.py:377-402`, which catches `ValueError` per-item and continues).

`merged.setdefault("name", provider_id)` means **`name` defaults to the provider id** if the user doesn't override it — so `use: research-highlights` alone (plus `command`) produces a hook named `research-highlights`.

Merging is a recursive **deep merge** (`_deep_merge`, `file_hooks.py:298-306`) of the local override *over* the provider's `file_hook` template (dicts merge key-by-key recursively; non-dict values are replaced outright, not concatenated — note this differs from the config-layer list-concatenation semantics elsewhere in SASE).

### `FileHookConfig` — the final validated hook (post-merge)

`src/sase/config/file_hooks.py:78-99`:

```python
@dataclass(frozen=True)
class FileHookConfig:
    """One validated ``file_hooks`` configuration entry."""

    name: str
    description: str | None
    command: str
    timeout_seconds: float
    filters: FileHookFilters = field(default_factory=FileHookFilters)
    source_layer: str = "unknown"
```

```python
@dataclass(frozen=True)
class FileHookFilters:
    """Event-selection criteria for one file hook."""

    projects: tuple[str, ...] | None = None
    sidecars: tuple[str, ...] | None = None
    path_globs: tuple[str, ...] | None = None
    agent_name_globs: tuple[str, ...] | None = None
    ops: tuple[FileHookOp, ...] | None = None
```

`FileHookOp = Literal["ADD", "MODIFY", "REMOVE"]` (`file_hooks.py:21-22`).

Known top-level keys for a raw `file_hooks:` list entry (`_KNOWN_FILE_HOOK_KEYS`, `file_hooks.py:34-43`): `name`, `use`, `description`, `command`, `filters`, `timeout`. Known `filters` sub-keys (`_FILE_HOOK_FILTER_KEYS`, `file_hooks.py:44-52`): `projects`, `sidecars`, `path_globs`, `agent_name_globs`, `ops`. Anything else raises `ValueError` (legacy top-level filter keys, or a `globs` key, get a specific migration message pointing at `filters.path_globs`).

`timeout` is a duration string matching `^([0-9]+)(ms|s|m|h)$` (`_DURATION_RE`, `file_hooks.py:24`), default `"120s"` (`file_hooks.py:254`).

---

## 4. Entry-point group names — confirmed, with real registration example

Confirmed **exact** names, both from `src/sase/artifact_providers/registry.py:20-25` and `src/sase/plugins/inventory.py:17-26`:

```python
ARTIFACT_REF_ENTRY_POINT_GROUP = "sase_artifact_refs"
FILE_HOOK_ENTRY_POINT_GROUP = "sase_file_hooks"
```

Full `ENTRY_POINT_GROUPS` tuple in `src/sase/plugins/inventory.py:17-26`:

```python
ENTRY_POINT_GROUPS: tuple[str, ...] = (
    "sase_artifact_refs",
    "sase_config",
    "sase_file_hooks",
    "sase_llm",
    "sase_plugin_manifest",
    "sase_vcs",
    "sase_workspace",
    "sase_xprompts",
)
RESOURCE_ENTRY_POINT_GROUPS: frozenset[str] = frozenset(
    {"sase_config", "sase_plugin_manifest", "sase_xprompts"}
)
PROVIDER_ENTRY_POINT_GROUPS: frozenset[str] = frozenset(
    group for group in ENTRY_POINT_GROUPS if group not in RESOURCE_ENTRY_POINT_GROUPS
)
```

So `sase_artifact_refs` and `sase_file_hooks` are classified as **provider** groups (like `sase_vcs`/`sase_workspace`/`sase_llm`), not resource groups — they resolve to a **class** (instantiated + registered with pluggy), not a module.

Real registration example — `sase` core's own builtin provider, `pyproject.toml:174-175`:

```toml
[project.entry-points."sase_artifact_refs"]
builtin = "sase.artifact_providers._builtin:BuiltinArtifactProviders"
```

There is currently **no** `[project.entry-points."sase_file_hooks"]` table anywhere in this repo's `pyproject.toml` — the builtin package doesn't ship any builtin file-hook provider (only the builtin `plan` ref provider exists; `BuiltinArtifactProviders` in `_builtin.py` implements only `artifact_ref_provider_specs`, not `artifact_file_hook_provider_specs`). That's expected, not a bug — it just means you'll be the first real consumer of that group in this codebase, and your `sase-research` plugin's `pyproject.toml` would add:

```toml
[project.entry-points."sase_artifact_refs"]
research = "sase_research.artifact_providers:ResearchArtifactProviders"

[project.entry-points."sase_file_hooks"]
research = "sase_research.artifact_providers:ResearchArtifactProviders"
```

— **but per the gotcha in §1, only do this if you split the two hookimpls across two different classes**, or drop one of these two lines if a single class implements both hooks (registering it once under either group is sufficient; the registry calls both hooks on every discovered plugin regardless of which group it came from).

Disable env vars, per `_disabled_env_for_group` (`registry.py:561-569`, mirrored in `plugins/inventory.py:143-152`): `SASE_DISABLE_PLUGINS` (disables everything) or group-specific `SASE_DISABLE_PLUGIN_ARTIFACT_REFS` / `SASE_DISABLE_PLUGIN_FILE_HOOKS` (suffix = `group.removeprefix("sase_").upper()`).

**Test-only proof these groups are wired into the generic inventory** — `tests/test_plugin_catalog.py:27-29`:

```python
def test_artifact_provider_entry_point_groups_are_in_inventory() -> None:
    assert "sase_artifact_refs" in ENTRY_POINT_GROUPS
    assert "sase_file_hooks" in ENTRY_POINT_GROUPS
```

---

## 5. `sase_xprompts` / `sase_config` groups (used by `sase-github`, etc.) and resource layout

These are **resource** groups, not pluggy provider groups: the entry point resolves to a **module** (package `__init__` module, e.g. `my_sase_plugin`), not a class or callable. Per `docs/plugins.md:26-28`: "Package-module entry points resolve to a module whose package resources are read by Sase."

Discovery helper — `src/sase/main/plugin_discovery.py:28-54`:

```python
def discover_plugin_resources(group: str) -> list[ModuleType]:
    """Load entry points for *group* and return the imported modules.
    ...
    """
    modules: list[ModuleType] = []
    eps = sorted(
        importlib.metadata.entry_points(group=group),
        key=lambda ep: ep.name,
    )
    for ep in eps:
        try:
            module = ep.load()
            modules.append(module)
        except Exception:
            log.debug("Failed to load entry point %s:%s", group, ep.name, exc_info=True)
    return modules
```

Load failures are swallowed and only logged at `debug` — module-load errors never raise for a normal run (though `sase doctor -C plugins.resources` loads them directly so failures surface as diagnostics; `docs/plugins.md:190-193`).

### `sase_config` → `default_config.yml`

Loaded via `importlib.resources.files(module).joinpath("default_config.yml")`. Two call sites:

`src/sase/config/loading.py:101-123`:

```python
def load_plugin_configs(
    resource_files: Callable[[Any], Any],
) -> list[dict[str, Any]]:
    """Load default config mappings from enabled config plugins."""
    from sase.main.plugin_discovery import discover_plugin_resources, is_plugin_disabled

    if is_plugin_disabled("CONFIG"):
        return []

    configs: list[dict[str, Any]] = []
    for module in discover_plugin_resources("sase_config"):
        try:
            ref = resource_files(module).joinpath("default_config.yml")
            data = yaml_safe_load_cached_text(ref.read_text(encoding="utf-8"))
            if isinstance(data, dict):
                configs.append(data)
        except Exception:
            log.debug(...)
    return configs
```

(`resource_files` is dependency-injected but at call sites it's `importlib.resources.files`.) So layout is: your installed package must literally contain a `default_config.yml` file directly inside the package directory pointed at by the entry point (sibling to `__init__.py`), e.g.:

```
sase_research/
├── __init__.py
└── default_config.yml
```

registered as:

```toml
[project.entry-points."sase_config"]
research = "sase_research"
```

Merge order (deep-merge, config layers override plugin defaults; documented in `docs/plugins.md:586-592` and `docs/configuration.md#deep-merge-system`): built-in `default_config.yml` → plugin `default_config.yml`s → user `sase.yml` → overlay `sase_*.yml` files → local project `sase/sase.yml`.

### `sase_xprompts` → `xprompts/*.md` (and `.yml`/`.yaml` workflows)

`src/sase/xprompt/loader_sources.py:375-460`, specifically `load_plugin_markdown_xprompts` (lines 375-429) and `load_xprompts_from_plugins` (432-460):

```python
def load_plugin_markdown_xprompts(
    module: Any, resource_dir: str
) -> Iterator[tuple[str, XPrompt]]:
    try:
        resource = importlib.resources.files(module).joinpath(resource_dir)
    except (TypeError, AttributeError):
        return
    try:
        entries = list(resource.iterdir())
    except (FileNotFoundError, OSError, TypeError, NotADirectoryError):
        return
    for entry in sorted(entries, key=lambda item: item.name):
        if not entry.name.endswith(".md"):
            continue
        text = entry.read_text(encoding="utf-8")
        front_matter, body = parse_yaml_front_matter(text)
        name = entry.name.removesuffix(".md")
        if front_matter and "name" in front_matter:
            name = str(front_matter["name"])
        ...
        source = f"plugin:{module.__name__}/{entry.name}"
        yield (source, XPrompt(name=name, content=body, ...))


def load_xprompts_from_plugins() -> dict[str, XPrompt]:
    if is_plugin_disabled("XPROMPTS"):
        return {}
    xprompts: dict[str, XPrompt] = {}
    for module in discover_plugin_resources("sase_xprompts"):
        for source, xprompt in load_plugin_markdown_xprompts(module, "xprompts"):
            ...
            xprompt.discovery_rank = RANK_PLUGIN
            xprompts[xprompt.name] = xprompt
    return xprompts
```

So the layout is (per `docs/plugins.md:713-730`):

```
sase_research/
├── __init__.py
└── xprompts/
    ├── some_template.md
    └── some_workflow.yml
```

registered as:

```toml
[project.entry-points."sase_xprompts"]
research = "sase_research"
```

`.md` files are prompt templates (front-matter parsed for `name`, `input`, `tags`, `snippet`, `description`, `skill`, `log_skill_use`); `.yml`/`.yaml` are workflow definitions (loaded separately by `src/sase/xprompt/workflow_loader_sources.py`, not shown above but analogous). A `skill:` declaration inside a plugin `xprompts/` file is **rejected** with a migration message pointing at a sibling `skills/` resource directory (`reject_misplaced_skill`) — skills live in a separate resource dir, not inside `xprompts/`.

Discovery priority: plugin xprompts get `discovery_rank = RANK_PLUGIN`, which per `docs/plugins.md:582-584` sits at "priority 8 … above built-in files and below config-based xprompts" in the overall discovery order (see `src/sase/xprompt/discovery_order.py` for the full rank table, not re-quoted here since it wasn't asked for verbatim).

### Third-party plugin example (`sase-github`) referenced in docs

`docs/plugins.md:34-40` (the plugin-packages table) documents `sase-github` contributing `sase_vcs: github`, `sase_workspace: github`, `sase_config: sase_github`, `sase_xprompts: sase_github`, and shows the generic "Example: Config Plugin" / "Example: XPrompt Plugin" snippets quoted above. **Note:** the actual `sase-github` source is not in this checkout (it's a separate repo), so I could not verify against its real `pyproject.toml`; the above is reconstructed from `docs/plugins.md` and the generic loader code, which is authoritative for the mechanism even without seeing that specific package.

### Documentation gap I found (flag this)

`docs/plugins.md:15` still says **"Sase defines six entry point groups"** and its table (`docs/plugins.md:17-24`) lists only `sase_vcs`, `sase_workspace`, `sase_llm`, `sase_xprompts`, `sase_config`, `sase_plugin_manifest` — it **does not mention `sase_artifact_refs` or `sase_file_hooks` at all**, anywhere in the file. The "Writing a Plugin" section (`docs/plugins.md:644-833`) has worked examples for VCS/workspace/xprompt/config/chop/LLM plugins but **no "Example: Artifact Provider Plugin" section**. This strongly suggests the `f53e43ab1` "feat!: add artifact provider registry" commit shipped the registry, schema, and tests, but the docs update for `docs/plugins.md` was not part of that commit (or was deferred to a follow-up). If you're implementing against this, treat `src/sase/artifact_providers/registry.py`, `tests/test_artifact_provider_registry.py`, and `tests/test_file_hooks.py` as the source of truth, not `docs/plugins.md`, for this specific feature.

---

## 6. Builtin `plan` provider — actual source and literal spec

File: `src/sase/artifact_providers/_builtin.py` (64 lines total):

```python
ARTIFACT_REF_PROVIDER_SPEC_SCHEMA_VERSION = 1


def builtin_plan_ref_provider_spec() -> dict[str, Any]:
    """Return the builtin plans sidecar document-ref provider spec."""

    return {
        "schema_version": ARTIFACT_REF_PROVIDER_SPEC_SCHEMA_VERSION,
        "provider": "plan",
        "ref": {
            "kind": "plan",
            "expansion_format": "{kind}:{argument}",
            "properties": {
                "tier": {
                    "type": "string",
                    "source": "markdown_frontmatter",
                },
                "title": {
                    "type": "string",
                    "source": "markdown_frontmatter",
                },
                "status": {
                    "type": "string",
                    "source": "markdown_frontmatter",
                },
                "bead": {
                    "type": "string",
                    "source": "markdown_frontmatter",
                },
            },
            "detail": {"fields": ["tier", "title", "status"]},
            "identity": {},
            "inventory": {"globs": ["**/*.md"]},
            "publication": {
                "link": "vcs_permalink",
                "referenced_by": "markdown_table",
            },
        },
    }


class BuiltinArtifactProviders:
    """Builtin providers registered through the artifact-provider host path."""

    @hookimpl
    def artifact_ref_provider_specs(self) -> tuple[Mapping[str, Any], ...]:
        return (builtin_plan_ref_provider_spec(),)
```

Notice this class implements only `artifact_ref_provider_specs` — no `artifact_file_hook_provider_specs` — confirming there is no builtin file-hook provider today. Note also that `identity: {}` here has **no** `property` key at all (rather than `{"property": None}`), which is valid since the Rust struct field is `Option<String>` with `#[serde(default)]`.

Registered in `pyproject.toml:174-175` as `builtin = "sase.artifact_providers._builtin:BuiltinArtifactProviders"`, and specially recognized/excluded from "third-party" classification by `_is_builtin_entry_point` (`registry.py:612-617`):

```python
def _is_builtin_entry_point(provenance: ArtifactProviderProvenance) -> bool:
    return (
        provenance.package.lower() == "sase"
        and provenance.group == ARTIFACT_REF_ENTRY_POINT_GROUP
        and provenance.name == "builtin"
    )
```

This spec is mirrored/reused directly as a test fixture base (`tests/test_artifact_provider_registry.py:43-52`, `_research_spec()`) — the maintainers derive their "research" test fixture *by mutating a copy of `builtin_plan_ref_provider_spec()`*, which is more evidence that your real "research" provider's structure should closely mirror `builtin_plan_ref_provider_spec()`'s shape, just with your own `kind`/`properties`/`inventory.globs`.

---

## 7. Existing test helpers / fixtures for provider-spec + registry contract testing

### `tests/test_artifact_provider_registry.py` — the canonical registry contract tests

Key excerpts (already fully quoted for context above where relevant), file is 190 lines. Notable reusable helpers:

- `_Dist` / `_EntryPoint` dataclasses (lines 19-40) — a fake `importlib.metadata.EntryPoint` with a `.load()` method and a fake `.dist.metadata` mapping, letting tests inject synthetic entry points without touching the real environment:

```python
@dataclass
class _Dist:
    name: str = "sase-research"
    version: str = "1.2.3"

    @property
    def metadata(self) -> dict[str, str]:
        return {"Name": self.name, "Version": self.version}


@dataclass
class _EntryPoint:
    name: str
    group: str
    plugin: object
    dist: _Dist = field(default_factory=_Dist)
    value: str = "tests:Plugin"

    def load(self) -> object:
        if isinstance(self.plugin, BaseException):
            raise self.plugin
        return self.plugin
```

**`_Dist`'s default package name is literally `"sase-research"`** — direct confirmation that the test author used your exact intended plugin package name as the canonical third-party example while building this feature.

- `_entry_points(entries)` (lines 55-59) builds a fake `entry_points_fn` callable matching the `entry_points_fn: Any = importlib.metadata.entry_points` signature accepted by `assemble_artifact_provider_registry(entry_points_fn=...)` (`registry.py:133-136`) — this is the intended seam for injecting fake plugins in tests without touching the real Python environment.

- `_research_spec(**updates)` (lines 43-52) builds a "research" ref-provider spec by mutating a copy of `builtin_plan_ref_provider_spec()`.

- Contract behaviors covered, each a good template for equivalent tests in your `sase-research` repo:
  - `test_registry_registers_builtin_plan_and_entry_kind_descriptors` — sanity on builtin discovery + `entry_kinds` (the reserved kind catalog: `stitch`, `patch`, `bead`, `agent`, `file`).
  - `test_registry_discovers_ref_providers_with_provenance` — registers a `Plugin` class with `@hookimpl def artifact_ref_provider_specs(...)` under `ARTIFACT_REF_ENTRY_POINT_GROUP`, and asserts `record.provenance.package == "sase-research"` and `record.provenance.version == "1.2.3"`.
  - `test_registry_skips_duplicate_and_invalid_ref_providers` — three fake plugins (`First`, `Duplicate`, `Reserved`) prove: (a) first-registered wins on `provider_id` duplicate (sorted by entry-point name, `_entry_points_for_group` sorts alphabetically — `"a-first"` < `"z-duplicate"`); (b) a reserved kind (`"file"`) is rejected; (c) diagnostics carry stable `code` values `"duplicate_ref_provider"` and `"invalid_ref_provider"` you can assert on.
  - `test_registry_discovers_file_hook_provider_templates` — the file-hook provider spec/template contract quoted in §3.
  - `test_registry_honors_independent_disable_env` — `monkeypatch.setenv("SASE_DISABLE_PLUGIN_FILE_HOOKS", "1")` disables only the file-hook group while the ref-provider group still loads; asserts `registry.disabled_env == ("SASE_DISABLE_PLUGIN_FILE_HOOKS",)`.

### `tests/test_file_hooks.py` — `use:`-vs-inline / required-field / provider-template tests

- `_registry_with_file_hook_provider()` (lines 83-109) constructs an `ArtifactProviderRegistry` directly (not through `assemble_artifact_provider_registry`) with a `FileHookProviderRecord` whose `provenance.package == "sase-research"`, `provider_id="research-highlights"`, `required_fields=("command",)` — a good template for unit-testing your own file-hook consumption code without needing pluggy/entry-point machinery at all.
- `test_loader_resolves_file_hook_provider_templates` (lines 191-224) — patches `sase.artifact_providers.get_artifact_provider_registry` to return the fixture above, feeds a `use: research-highlights` + `command:` + `filters.path_globs` local override, and asserts the merged `FileHookConfig` (name defaults to provider id, `timeout_seconds == 30` from the template, filters merged/overridden correctly).
- `test_loader_skips_provider_hook_missing_required_local_field` (lines 226-244) — omitting `command` on a `use: research-highlights` entry produces a `caplog` warning containing `"requires local field 'command'"` and the hook is dropped (fail-soft, not raised).

### `tests/test_sidecar_ref_config.py` — `use:`-vs-inline normalization parity + fail-soft missing-provider

- `test_sidecar_ref_use_and_equivalent_inline_normalize_identically` (lines 58-103) is the **exact "use:-vs-inline normalization parity" test you asked about**: it builds a `plans` sidecar with `ref: {use: "plan", inventory: {globs: [...]}}`, and a second `plans` sidecar with `ref: {**builtin_plan_ref_provider_spec()["ref"], inventory: {globs: [...]}}` (i.e. the provider's own base spec inlined), then asserts:

```python
assert use_policy.spec == inline_policy.spec
assert use_policy.digest == inline_policy.digest
assert use_policy.path_globs == ("2026/**/*.md",)
```

  — i.e., resolving through `use:` must produce byte-identical normalized specs (and identical Rust digests) as writing the fully-inlined spec yourself. This is driven through `_sidecar_ref_policy_report` (module-private, imported directly in the test — `from sase.sidecar_ref_config import ..., _sidecar_ref_policy_report`), which is the right seam to call directly in a contract test since it returns both `.policies` and `.diagnostics` without needing real config-file I/O.

- `test_sidecar_ref_invalid_provider_use_fails_soft` (lines 132-152) is the **missing-provider fail-soft test**: `ref: {use: "missing-provider"}` on a custom `"research"` sidecar produces `report.diagnostics[0].code == "missing_ref_provider"` and `"research" not in report.policies` (the role is simply dropped, not a raised exception).

- `test_sidecar_ref_deprecated_path_globs_alias_is_reported` — `ref.filters.path_globs` (legacy) still works but reports `diagnostic.code == "deprecated_ref_path_globs"`, pointing at `ref.inventory.globs` as the replacement.

### `tests/doctor/test_checks_config_repos.py` — end-to-end doctor diagnostics for a missing provider

`test_repos_reports_missing_sidecar_ref_provider` (lines 239-262 in that file):

```python
def test_repos_reports_missing_sidecar_ref_provider(
    monkeypatch: pytest.MonkeyPatch,
) -> None:
    _patch_config(
        monkeypatch,
        {
            "repos": {
                "sidecar": {
                    "custom": {
                        "research": {
                            "description": "Durable research.",
                            "ref": {"use": "research"},
                        }
                    }
                }
            }
        },
    )

    check = check_config_repos()

    problems = {row["key"]: row["message"] for row in check.data["problems"]}
    message = problems["repos.sidecar.custom.research.ref.use"]
    assert "missing artifact ref provider 'research'" in message
```

This exercises `sase doctor`'s `check_config_repos()` end-to-end and confirms the exact diagnostic key format (`repos.sidecar.custom.<role>.ref.use`) and message substring (`"missing artifact ref provider '<id>'"`), sourced from `src/sase/doctor/checks_config_repos.py:283-309`. **Useful pattern for your own repo's contract tests** if you want to assert that installing your plugin makes an equivalent `sase doctor` check clean, or that misconfiguring it (e.g. wrong `use:` id) surfaces this exact diagnostic shape.

`_artifact_provider_registry_problems()` (`checks_config_repos.py:416-452`) also surfaces **any** registry-assembly diagnostic (e.g. from a broken third-party plugin) directly through `sase doctor`, keyed `artifact_providers.<provider-or-kind-or-code>`, plus an `artifact_providers.disabled` entry if any `SASE_DISABLE_PLUGIN_*` env var is set. A good target for a "sase doctor surfaces a broken sase-research install" contract test.

### Test isolation helper: registry cache reset

`tests/_conftest_runtime.py:93-114` — an **autouse** fixture that resets process-local caches before every test, including:

```python
from sase.artifact_providers import reset_artifact_provider_registry_cache
...
reset_artifact_provider_registry_cache()
```

`get_artifact_provider_registry()` (`registry.py:112-122`) memoizes on a token (`current_config_token()` + the three `SASE_DISABLE_PLUGIN*` env vars, `_provider_registry_token`, `registry.py:543-549`) — if you write contract tests in the `sase-research` repo that call `get_artifact_provider_registry()` (rather than `assemble_artifact_provider_registry()` directly), you'll want your own equivalent cache-reset fixture (`reset_artifact_provider_registry_cache` is public/exported from `sase.artifact_providers.__init__`).

---

## 8. JSON schema deltas — `sidecarRef` and `fileHook` (verbatim)

File: `src/sase/config/sase.schema.json`.

### `sidecarRef` (used as `repos.sidecar.<bucket>.<role>.ref`)

```json
"sidecarRef": {
  "type": "object",
  "description": "Provider-backed or inline document artifact-reference spec for one sidecar role.",
  "additionalProperties": false,
  "properties": {
    "use": {
      "type": "string",
      "description": "Installed artifact-reference provider id to use as the base spec.",
      "minLength": 1
    },
    "kind": {
      "type": "string",
      "pattern": "^[a-z][a-z0-9_-]*$",
      "description": "Artifact reference kind, for inline specs or provider overrides."
    },
    "expansion_format": {
      "type": "string",
      "minLength": 1,
      "description": "Shared artifact-reference expansion format."
    },
    "properties": {
      "type": "object",
      "description": "Declared artifact-entry properties for this document ref kind.",
      "additionalProperties": { "$ref": "#/definitions/sidecarRefProperty" }
    },
    "detail": {
      "$ref": "#/definitions/sidecarRefDetail",
      "description": "Detail fields used by downstream artifact views."
    },
    "identity": {
      "$ref": "#/definitions/sidecarRefIdentity",
      "description": "Optional identity property for this document kind."
    },
    "inventory": {
      "$ref": "#/definitions/sidecarRefInventory",
      "description": "Document inventory policy for completion and resolution."
    },
    "publication": {
      "$ref": "#/definitions/sidecarRefPublication",
      "description": "Publication and back-link behavior for this document kind."
    },
    "filters": {
      "$ref": "#/definitions/sidecarRefFilters",
      "description": "Deprecated alias for inventory.globs."
    }
  }
}
```

**Note there is no `required` array on `sidecarRef` itself** — JSON Schema only enforces known-key shape here (and per-subschema requiredness), not "kind/expansion_format/publication must be present." That's intentional: a bare `{"use": "plan"}` must validate as shape-valid even though it's incomplete until merged with the provider's base spec at runtime — the *Rust* validator (§2) is what actually enforces required-field completeness on the final merged spec, not this JSON schema. Also note **`xprompt` is deliberately absent** from `sidecarRef.properties`, so `additionalProperties: false` makes any `ref.xprompt` key fail schema validation outright (this is the retired-adapter enforcement from your `e2cacbe34` commit) — confirmed by `tests/test_config_schema_repositories.py:178-195` (`test_config_schema_rejects_retired_sidecar_ref_xprompt`).

```json
"sidecarRefProperty": {
  "type": "object",
  "required": ["type", "source"],
  "additionalProperties": false,
  "properties": {
    "type": {
      "type": "string",
      "enum": ["string", "enum", "boolean", "integer", "number", "date", "datetime", "string_list"]
    },
    "values": {
      "type": "array",
      "items": { "type": "string", "minLength": 1 },
      "description": "Allowed values for enum properties."
    },
    "source": {
      "type": "string",
      "enum": ["markdown_frontmatter", "provider"]
    }
  }
}
```

```json
"sidecarRefDetail": {
  "type": "object",
  "additionalProperties": false,
  "properties": {
    "fields": {
      "type": "array",
      "items": { "type": "string", "minLength": 1 }
    }
  }
}
```

```json
"sidecarRefIdentity": {
  "type": "object",
  "additionalProperties": false,
  "properties": {
    "property": { "type": "string", "minLength": 1 }
  }
}
```

```json
"sidecarRefInventory": {
  "type": "object",
  "additionalProperties": false,
  "properties": {
    "globs": {
      "type": "array",
      "description": "Repo-relative document path globs, including !-prefixed exclusions. Omit for the provider default; an empty list allows no document paths.",
      "items": { "type": "string", "minLength": 1 }
    }
  }
}
```

```json
"sidecarRefPublication": {
  "type": "object",
  "additionalProperties": false,
  "properties": {
    "link": {
      "type": "string",
      "enum": ["vcs_permalink", "agents_object", "none"]
    },
    "referenced_by": {
      "type": "string",
      "enum": ["markdown_table", "none"]
    }
  }
}
```

```json
"sidecarRefFilters": {
  "type": "object",
  "additionalProperties": false,
  "properties": {
    "path_globs": {
      "type": "array",
      "description": "Repo-relative document path globs, including !-prefixed exclusions. Omit for the Markdown default; an empty list allows no paths.",
      "items": { "type": "string", "minLength": 1 }
    }
  }
}
```

The parent `sidecarRepo` definition wires `ref` in (`sase.schema.json:35-58`, the block right before `sidecarRef`):

```json
"ref": {
  "$ref": "#/definitions/sidecarRef",
  "description": "Optional contextual ref renderer and document filter policy for this sidecar role."
},
```

### `fileHook`

```json
"fileHook": {
  "type": "object",
  "anyOf": [
    { "required": ["use"] },
    { "required": ["name", "command"] }
  ],
  "additionalProperties": false,
  "properties": {
    "use": {
      "type": "string",
      "minLength": 1,
      "description": "Installed file-hook provider id to use as the base template."
    },
    "name": {
      "type": "string",
      "pattern": "^[a-z0-9][a-z0-9_-]*$",
      "description": "Unique lowercase slug shown in notifications and file-hook listings."
    },
    "description": {
      "type": "string",
      "description": "Optional human-readable purpose for the hook."
    },
    "command": {
      "type": "string",
      "minLength": 1,
      "description": "Shell command whose final argument is the matched file path."
    },
    "filters": {
      "$ref": "#/definitions/fileHookFilters",
      "description": "Optional event-selection criteria; omitted or empty means unrestricted outside project-local auto-scoping."
    },
    "timeout": {
      "type": "string",
      "pattern": "^[0-9]+(ms|s|m|h)$",
      "description": "Per-run timeout duration (default: 120s)."
    }
  }
}
```

```json
"fileHookFilters": {
  "type": "object",
  "additionalProperties": false,
  "properties": {
    "projects": {
      "type": "array",
      "items": { "type": "string" },
      "description": "Optional user-facing project names; omitted means every project."
    },
    "sidecars": {
      "type": "array",
      "items": { "type": "string" },
      "description": "Optional sidecar role names; omitted means any repository."
    },
    "path_globs": {
      "type": "array",
      "items": { "type": "string" },
      "description": "Optional repo-relative path globs, including !-prefixed exclusions."
    },
    "agent_name_globs": {
      "type": "array",
      "items": { "type": "string" },
      "description": "Optional SASE agent-name globs matched against the agent that produced the event, including !-prefixed exclusions."
    },
    "ops": {
      "type": "array",
      "items": { "type": "string", "enum": ["ADD", "MODIFY", "REMOVE"] },
      "description": "Optional file operations; omitted means all operations."
    }
  }
}
```

used at `"file_hooks": { "type": "array", ..., "items": { "$ref": "#/definitions/fileHook" } }` (`sase.schema.json:2270-2272`).

**Correction to your question**: **`fileHook` has no `display_name` key anywhere** — I grepped the whole schema, `file_hooks.py`, and `artifact_providers/*.py` and found zero occurrences of `display_name` outside the unrelated Rust `ArtifactRefKindDescriptorWire` (`sase/repos/linked/sase-core/crates/sase_core/src/artifact_ref/kinds.rs:27-37`, which backs the **builtin reserved-kind catalog** — `stitch`/`patch`/`bead`/`agent`/`file` — surfaced as `registry.entry_kinds`, not something a provider spec itself declares). If you were planning a `display_name` field on your file-hook or ref-provider spec, that concept doesn't exist in this schema today; you'd either need to add it upstream first or just use `description`/`name` as-is.

The `anyOf` on `fileHook` (`{"required": ["use"]}` vs `{"required": ["name", "command"]}`) is the JSON-schema-level encoding of "either you're using a provider template (only `use` is schema-required; `command` is filled by the provider unless it's in that provider's `required` list, which is enforced at the Python `_resolve_file_hook_provider` layer, not JSON schema) or you're fully inline (`name` + `command` required)."

---

## Summary of things to double-check / that surprised me relative to your framing

1. **Hookspec names are `artifact_ref_provider_specs()` / `artifact_file_hook_provider_specs()`**, not `sase_artifact_ref_providers()` / `sase_file_hook_providers()`. Pluggy project name is `"sase_artifact"`.
2. **No `ArtifactRefProviderSpec` / `FileHookProviderSpec` Python dataclass exists.** Specs are plain dicts; only the *registry records* (`ArtifactRefProviderRecord`, `FileHookProviderRecord`) are dataclasses, and those wrap the already-validated dict verbatim (`spec: Mapping[str, Any]`, `template: Mapping[str, Any]`) rather than exposing typed fields.
3. **The typed schema lives in Rust** (`sase-core`'s `provider_spec.rs`), reached via `require_rust_binding("artifact_ref_provider_spec_validate"/"_digest")`. Your plugin never talks to Rust directly — it just returns dicts shaped to match that schema, and `sase` core validates them for you.
4. **Registering the same class under both `sase_artifact_refs` and `sase_file_hooks` will double-register it** and produce spurious duplicate-provider diagnostics, because the registry calls both hookspec methods on every plugin instance regardless of which group discovered it. Pick one group (or split into two classes).
5. **`schema_version` inside a ref-provider spec must be `1`**, unrelated to the "wire schema 5" bump from your `cb453a529` commit (that's a different counter, `ARTIFACT_REF_PARSE_WIRE_SCHEMA_VERSION`/`ARTIFACT_REF_RESOLUTION_WIRE_SCHEMA_VERSION`, for entry/resolution wire payloads, not provider specs).
6. **`docs/plugins.md` is stale** — it still says "six entry point groups" and omits `sase_artifact_refs`/`sase_file_hooks` entirely, with no worked "Example: Artifact Provider Plugin" section. Treat the Python source + `tests/test_artifact_provider_registry.py` + `tests/test_file_hooks.py` as authoritative instead.
7. **No `[project.entry-points."sase_file_hooks"]` example exists anywhere in this repo** (core doesn't ship a builtin file-hook provider) — your plugin will be the first real-world consumer of that specific entry-point group in this ecosystem, though the mechanism is fully implemented and tested via synthetic fixtures.
8. **`fileHook` has no `display_name` field** in the JSON schema; that concept only exists for the internal reserved-kind catalog (`ArtifactRefKindDescriptorWire`), not for user- or plugin-declared file hooks or ref providers.
9. Reassuringly: the maintainers' own test fixtures (Rust `provider_spec.rs` tests, `tests/test_artifact_provider_registry.py`'s `_Dist`, `tests/test_sidecar_ref_config.py`'s "research" custom sidecar) **already use `provider: "research"` / package `"sase-research"`** as their canonical third-party example while building this feature — so your plugin's naming and shape plan is well-aligned with the design intent, not an outlier.

This is exactly the missing piece — the real registry expects a pluggy hookimpl class with `artifact_ref_provider_specs()`/`artifact_file_hook_provider_specs()` methods returning plain dicts, not the object-export shape the epic plan sketched. Let me check the exact plugin-loading code directly to confirm class-vs-instance handling before I write the provider module.

All three research agents have reported back with a fully consistent picture. Key finding: the real registry (unlike the epic plan's illustrative YAML) expects a pluggy hookimpl object per entry point returning plain dicts — and critically, the loader accepts either a class or an already-built instance, so the plan's `RESEARCH_REF_PROVIDER`/`RESEARCH_HIGHLIGHTS_HOOK` object-export design works exactly as sketched, as long as each object implements only one of the two hook methods (to avoid double-registration). I have everything needed to start writing the plugin. Let me begin scaffolding.

Now let me write `pyproject.toml`, mirroring `sase-telegram`/`sase-github`'s conventions.

Now the `Justfile`, adapted from `sase-telegram`'s coordinated-source pattern:

Scaffold done. Now the core deliverable — the provider module.

That diagnostic is expected — the package isn't installed in this environment yet; it'll resolve once `just install` runs. Now let's build the xprompts and default config.

Now the four-segment `research_swarm.md`, lifted verbatim from chezmoi:

Now the `default_config.yml` with model aliases, bucket, and tribe — lifted verbatim from chezmoi:

Now let's verify the package actually installs and the entry points resolve. I'll set explicit source-path overrides since this repo is checked out as an external repo, not at the standard linked-repo depth.

Good, everything needed is available. Let's run the install.

Now let's retry the install with these fixes.

Install succeeded, with sase-core-rs built from source at 0.25.0 (overriding the stale 0.24.6 from PyPI). Let's verify the entry points and provider spec actually validate.

All four entry points resolve correctly. Now let's confirm the registry actually discovers and validates the provider specs end-to-end through `sase`'s own registry code.

Now let's verify the xprompts and default config actually load through sase's real plugin discovery.

Both parse correctly. Now let's verify `default_config.yml` loads and merges correctly.

Excellent — the full round-trip through SASE's real registry, xprompt loader, and config loader all pass cleanly. Task 3 is done.

Now let's write `test_provider_specs.py` covering registry discovery, provenance, diagnostics, and `use:`-vs-inline parity.

Now I have what I need. Let's write the path-filter divergence test.

Good, confirmed. Let's write the xprompt-loading test file.

Let's move to the CI workflows now, then come back to finish the CI-contract and wheel-contract tests together.

Now let's finish the contract tests — the CI-file static assertions and the real wheel-build contract test.

Now let's write the wheel contract test itself.

Now let's actually run the test suite to validate everything works.

All 27 fast tests pass. Now let's run lint (ruff + mypy) and fix any issues.

Formatting fixed. Now let's rerun the full test suite and lint once more to confirm everything is still green, then move on to documentation.

All green. Now let's move to documentation — README, docs/, and updating the GitHub repo description.

Now let's write the README, disambiguating from `sase--research` per the plan.

Now the three docs pages, modeled on `sase-github`'s structure.

Now let's finalize the GitHub repo description, per the plan's explicit disambiguation requirement.

Documentation is done. Task 6 complete.

Now the full `just check` gate.

`just check` is fully green. Now let's run the wheel contract test (build sdist/wheel, install into a fresh venv, verify entry points end-to-end).

All tests pass, including the real wheel build/install smoke test. Now let's verify the working tree is clean and contains only the intended files.

Before closing the bead, let me review the bead lifecycle memory doc as required.

Now let's close the bead with a summary of what was verified.

Implementation of phase bead `sase-js.8` is complete. Summary:

**Built `sase-org/sase-research`** (path: `sase/repos/external/gh/sase-org/sase-research` in this workspace) as a full installable plugin:

- **Provider specs** (`src/sase_research/provider.py`): `RESEARCH_REF_PROVIDER` (research ref, schema v1, `20*/**/*.md` inventory, frontmatter properties, VCS-permalink publication) and `RESEARCH_HIGHLIGHTS_HOOK` (file hook with `command` deliberately unset/required), each a separate pluggy hookimpl object registered under its own entry-point group — this matches the *actual* landed registry contract in `sase` core (discovered via research, since it differs from the epic plan's illustrative YAML).
- **Xprompts & defaults**: all five `#research*` xprompts and the model-alias/bucket/tribe defaults lifted verbatim from chezmoi, verified loading through sase's real plugin loaders.
- **Tests**: 27 fast contract tests (registry discovery, duplicate/missing-provider diagnostics, `use:`-vs-inline digest parity, glob divergence, frontmatter typing, swarm segment/dependency graph, schema validation) plus 3 wheel-contract tests (real sdist/wheel build, fresh-venv install, all 4 entry points + both specs + xprompts + defaults discoverable) — all pass.
- **CI/release**: `ci.yml`, `pr-title.yml`, `publish.yml` (release-please + trusted PyPI), coordinating against `sase`/`sase-core` source checkouts via a `uv --overrides` file since the `sase>=0.17.0` floor hasn't reached PyPI yet.
- **Docs**: README (disambiguating from `sase--research`), `docs/{architecture,configuration,xprompts}.md`, and the GitHub repo description updated accordingly.

`just check` is green. I closed bead `sase-js.8` with a verification summary and left a `PROPOSED FOLLOW-UP:` note on it about a latent circular-import fragility I found in `sase.artifact_providers` (unrelated to this plugin, out of scope to fix here). Nothing was committed — let me know if you'd like me to commit this work.

I'll pick up where the prior turn left off — the work is real (matches the approved plan exactly), but nothing was committed. I need to close the bead (which also verifies the close published correctly) and then commit in the external repo.

Bead close confirms it was already closed and published (no "committed locally but NOT published" error). Now let's commit the external repo's changes.

Commit succeeded (exit 0). The prompt-archive warning is unrelated bookkeeping, not a commit failure. Let's verify the repo is clean and pushed.

The `sase-research` repo is clean and in sync with `origin/master` (branch tracking line shows no ahead/behind markers).

**Summary:** The bead `sase-js.8` was already closed and published (the close-note command confirmed no unpublished-state error). The 33 uncommitted files from the prior session's `sase-research` plugin scaffold — package code (`provider.py`, `default_config.yml`, 5 xprompts), packaging/CI (`pyproject.toml`, `Justfile`, `.github/workflows/*`, release-please config), docs, and tests — are now committed as `f499469 feat: scaffold the sase-research plugin package` and pushed to `origin/master`. Working tree is clean.
