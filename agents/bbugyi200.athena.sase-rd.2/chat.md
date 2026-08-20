# Chat History - ace-run (sase-rd.2)

- **TIMESTAMP:** 2026-08-20 09:10:06 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-rd.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-rd, bead=sase-rd.2)
%model:@medium
%auto
%w:sase-rd.1
%w(bead=sase-rd.1)
Can you complete the work for bead sase-rd.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-rd.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-rd.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-rd.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the relevant SASE memory so I can complete only `sase-rd.2`.

Next I’ll load the bead details and the long-term notes that apply to beads, CLI, and symbols.

The bead is a catalog-mutations phase. I'll load the plan, parent epic, and glossary next.

The plan is long, so I’ll pull Phase 2 in full and inspect what Phase 1 already landed.

Phase 2 is a Python catalog and mutation service. I’ll map the existing snippet, glossary, and Rust-binding code next.

I'll

 inspect

 the glossary package structure first, then readI'll map its snippet catalogI'll models, loader, search, YAML config mutations the tree, and related load, and tests./write AP in parallel soIs by we searching the repo and have reading the key the key modules. files while the explorers finish.

The glossary package looks CLI

-heavy; I’ll

 search

 for catalog models and tests next, including any Rust-side types

.

I'll search this workspace for the Python facade around `compose_snippet_catalog` and related snippet-catalog types.

I'll

 read the glossary

 package files and hunt for the immutable

 models

 the plan names

.

I have the facade and tests; next I’ll read those files and hunt for phase-1 fields like trigger validation and inbound/outbound indexes.

I’ll

 inspect the snippet bridge

, core

-rs

 validationI, and whether have the file map the sibling core repo. Next I’ll read is the current reachable from catalog, this workspace. YAML writer, glossary analog, and Rust contract.

I’ll

 read the snippet modules

,

 config-layer loaders, and the Phase 2 plan next so the map can distinguish reuse vs replacement.

Linked core likely lives under `sase/repos/linked`; I’ll search that plus plans and the validator for the snippet-catalog contract.

Python still treats `compose_snippet_catalog` as a two-field composer. Phase 1 in linked `sase-core` already serializes trigger validation, the call graph, inbound/outbound indexes, and diagnostics on that same dict; the Python facade currently ignores them.

---



## 1

. Current Python facade

 around the Rust composer



**File

:** `/home/

bryan/.local/

state/sase

/

workspaces/sase

-org/s

ase/sase

_12/src

/sase/

core/snippet_

catalog_facade.py`

```20

:53

:src/sase/core/snippet_catalog_facade.py
def compose_snippet_catalog(
    explicit_templates: Mapping[str, str],
) -> _ComposedSnippetCatalog:
    """Compose explicit snippet templates through the shared Rust contract."""
    explicit = dict(explicit_templates)
    binding = require_rust_binding("compose_snippet_catalog")
    payload: Any = binding(explicit)
    ...
    templates = _require_string_mapping(payload.get("templates"), "templates")
    alias_provenance = _require_string_mapping(
        payload.get("alias_provenance"),
        "alias_provenance",
    )
    ...
    return _ComposedSnippetCatalog(
        templates=templates,
        alias_provenance=alias_provenance,
    )
```

**Signatures**

| Symbol | Signature |
|---|---|
| `require_rust_binding` | `def require_rust_binding(name: str) -> Any` in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/core

/rust.py` |
| `compose

_snippet_catalog

` |

 `def compose_

snippet_catalog(

explicit_templates: Mapping[str,

 str]) -> _

ComposedSnippetCatalog

` |
| `_

ComposedSnippetCatalog

` | frozen dataclass

: `templates:

 dict[str,

 str]`, `alias_provenance:

 dict[str, str]` |
| PyO3 binding | `fn py_compose_snippet_catalog(py, templates: BTreeMap<String, String>) -> PyResult<PyObject

>` named `compose_snippet_catalog

` |

**Contract today**

- Binding name is a string literal so `tools/check_s

ase_core_rs_bindings` can discover it. It is **not** in `tools

/validate_s

ase_core_rs` `REQUIRED_BINDINGS` (only `apply_snippet_session_event` is).
- Input is a plain `dict[str, str]` of **explicit** triggers

 (xprompt + user config + pending saves). Capitalization and `#[…]` expansion stay in Rust.
- Output is validated only for:
  - top-level mapping
  - `templates` and `alias_

provenance` as `str → str`


  - each provenance **alias** exists in `templates`
  - each provenance **source** exists in the explicit input
- Extra payload keys are **dropped**. Unknown fields do not fail.

**Callers (consume `.templates` / `.alias_provenance` only)**

1. `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/ace/tui/prompt_catalog.py`
   - `build_prompt_catalog_snapshot(...)` → `snippets=dict(composed.templates)`
   - `compose_pending_snippet_saves(...)` → returns `.templates`

 only
2.

 `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src

/sase/integrations/_editor_helper_snippets.py`
   - `snippet_catalog_response(request: dict[str, Any]) -> dict[str, Any]`
   - iterates `composition.templates`; clones metadata via `composition.alias_provenance.get(The glossary analogtrigger, trigger)` is **not**
3. `/ a selfhome/bryan/.-contained modelslocal/state/ package. `src/sase/sase/workspacesglossary/` is a/sase- **

org/saseCLI

/sase_ + lookup

 +12/src/

 mutation** layer. Immutablesase/ace

 catalog types/tui/

 live in theactions/agent_

 Rust facade;workflow/_prompt_ loading

bar_snippet_ lives under

pane.py` does

 `src/sase/ **not** call

xprompt/`. the composer A

 snippet

; it loads analog should copy

 un

 that **split**, notcomposed xprompt templates

 dump.

Trigger checks

 everything into one on `__

init__. the Python side are

py`.

--- still local



## 1, not the new. Package structure

 Rust binding:

-### ` `issrc/sase/glossary/` (_valid_snippet_trigger(triggerempty public surface)

`: str) -> bool` in `/home/bryan/.local/statesrc/sase/sase//xprompt/workspaces/sasesnippet_bridge.py-org/s` (`ase/sase^[a-z_12/src/sase/A-Z0glossary/__init-9_]+__.py` is$`)
- only a docstring. `validate_snippet Call_trigger(nameers import submodules. Each: str) -> file str | None` has in `src/ `__all__`.sase/x

| File | Role |prompt/naming.py Public` (UI exports |
|---| error strings---|---|
|)

Phase 1 `__init__.py` | Package also added a **separate** Py markerO3 helper | none Python |
| `cli_common.py` does | Project → not wrap catalog:

```143

 for7:1448

 CLI | `Glossary

:sase/CliError`, `repos/linked/ResolvedGlossaryProject`, `resolve_glossarysase-core_cli_project/crates/sase`,_ `core_resolve_glossary_cli_py/src/project_name`lib.rs
#[ |
| `resolutionpyfunction]
#[.py` | Term lookuppyo3(name = "validate + BFS reference_snippet_trigger closure | `GlossaryClosure`, `Glossary")]
fn pyClosureNode`, `_validate_snippetGlossaryLookup_trigger(Error`, `Glossarypy: Python<'_Referrer`, `>, trigger: &normalize_glossary_str) -> Pyreference`, `resolve_glossary_closureResult<PyObject>
```

Rust` |
| `relations.py` | composer Inbound “ (referenced by” index |linked core `glossary_reverse):_references` |


```98:| `mutation.py126:sase` | Add//repos/linkeddelete engine (YAML +/sase- validatecore/crates/ + atomic write)sase_core/src/snippet | `GlossaryMutationOutcome`, errors_catalog.rs


, `add_

glossary_term`,pub fn compose_

 `delete_glossarysnippet_catalog(


_term` |
    explicit_templates

| `text_: &BTreefilter.py` |

 Shared list

Map<String,/

 String>,
)panel substring -> ComposedSnippet filter | `filterCatalog
```

_glossary_entriesPy` |
| `O3 serializesrender.py` | the ** showwhole/read** `Composed/all rich/md/json | `SnippetCatalog` through `serde_json` → `jsonGlossaryShowFormat`, `glossary_value_to_closure_markdown_py`, so`, `render_glossary_catalog`, a `render_glossary live wheel already returns the_closure` |
| `read_ newlog.py` | fields even Audited ` thoughglossary Python ignores them.

 read` JSONL---

##  | events2. Dict/, summaries, appendshape Python currently/read/ expectsfilter |
| ` vs what Rustread_report.py now` | Deferred Markdown reports | `Glossary returns

**WhatReadReportSpec`, Python validates path today**

``` + write |
| `python
{
  "templates": dictcli_add.py[str, str` / `cli],          # final_del.py` composed / `cli_ map,write including generated aliases
.py` | Thin write  "alias_ CLIprovenance": dict[ |str, str], handlers   # generated alias + shared → emit explicit source trigger
/error}
```

** |
| `cliWhat phase_list.py` 1 actually / `cli_ serialshow.py` /izes** `cli_all.py` / ` (`ComposedSnippetcli_read.pyCatalog` +` / `cli serde_log.py` defaults | Thin read CLI)

``` | onepython
{
  ` "templates": {handle_strglossary_*_command` each |

###: str}, Adjacent modules
  "alias (the_provenance": { real catalogstr: str},  stack # generated-)

|only; empty if Path | Role explicit Foo already exists
 |
|---|---|
| `/home  "triggers":/bryan/.local {
/state/s    explicitase/workspaces/_trigger: {
sase-org      "trigger":/sase/sase_12 str,
      "/src/svalid": bool,
ase/core/      "reason":glossary_facade

 str | None,

.py` | Frozen  # "empty wire types +

" | "invalid Rust validate/build_characters" |/compile/scan None
    }
  },
  |
| `/home "calls": {
/bryan/.local/state/s    explicit_triggerase/workspaces/: [
      {
sase-org        "authored_/sase/target": str,sase_12/src/s           ase/glossary_ # as written inconfig.py` | #[…] `memory.glossary
        "canonical` key_target": str resolution | None,    |
| `/home # explicit identity;/bryan/.local alias Foo/state/s → foo
       ase/workspaces/ "positional_argssase-org": list/sase/sase_12[str],
/src/s        "span":ase/xprompt {"start": int/glossary_catalog, "end":.py` | Catalog int},  loader # UTF-8: byte offsets into project select the raw → template
        " YAMLstatus": "resolved →" | "missing validate

" | "cycle → catalog

 |
| `",  # serde

.../xprompt rename_all =

/_glossary_catalog snake_case


_config.py`      }
    ]


 | Round

  },
 -trip YAML

 "outbound": {

 parse + shape errorsexplicit

 + `GlossarySource_trigger: list` |
| `[str]}, .../xprompt # unique/_glossary_catalog targets_projects.py`, first-seen | Enabled order
  "-project selectioninbound": {explicit |
| `.../xprompt/__trigger: list

[str]},glossary  _catalog_ranges.py` | # sorted unique callers LSP ranges from ru
amel `lc`  "diagnostics": |
| ` [
    {
     .../main/ "code": str

parser_glossary.py,           ` | # see argparse |
 below
      "| `.../message": str,
main/glossary_handler.py` |      "trigger": Dispatch to str,
      "target": str | `sase. None,
      "glossary.span": {"startcli_*` |
": int, "| `.../end": int}ace/tui | None,
     /glossary_catalog "cycle": list.py` | Prompt[str] |-local load None,
    }
 wrapper  ],
}
 |
| `...```

**Golden/ace/t exampleui/glossary_ from thepanel_catalog.py Py` | PanelO3 test ring + snapshot** (`foo` calls cache + relations |
| `.../ `#[helper]`ace/tui):

```json/modals/
{
  "glossary_panel_templates": {
actions.py` |    "Foo": "Foo helper $ TUI writes call1 $2$ the **same**0",
    ` "Helper": "mutation.py` |

Helper $1$`0",
   s "foo": "foo helper $1ase.core` re-exports facade $2$0 types (`",
    "GlossaryCatalog`, `helper": "helperGlossaryEntry`, …). The $1$0 glossary"
  },
 package does **not  "alias_**.

---

provenance": {"Foo## 2.": "foo", Immutable model "Helper": " types (planhelper"},
  names "triggers": {
 → glossary    "foo":)

The {"trigger": " plan’s names are **not** currentfoo", "valid identifiers": true, ". Mapreason": null}, them as
    "helper follows.

### Catalog": {"trigger": context

**Rust "helper", "-normalized catalog** (`valid": true, "reason": nullfrozen}
  },
=True`):

```18  "calls"::121 {
    "foo:/home/bryan": [{/.local/state
      "authored/sase/_target": "workspaces/sasehelper",
     -org/s "canonical_targetase/sase": "helper",_12/src
      "positional/sase/core/glossary__args": [],facade.py

      "span@dataclass(frozen=": {"start":True)
class Glossary 4, "Source:
    configend": 13_path: str},
      " | None = None
    config_status": "resolvedkey_path:"
    }],
 tuple[str,    "helper": ...] = ()
 []
  },    term_range
  "outbound: dict[str": {"foo":, Any] | ["helper"], " None = None
   helper definition":_range []},
  "inbound

: dict[str": {"foo

, Any] |

": [], "helper None = None
": ["foo"]},    aliases_range: dict[str
  "diagnostics

, Any] |": []
}
 None = None
```

`validate    ...


@dataclass(frozen=True)
class_snippet_trigger(" GlossaryCatalog:
   fix_it2 schema_version:")` wire int
    entries:

```json
: tuple[Glossary{"trigger": "Entry, ...]
fix_it2```

**Loaded", "valid": editor catalog** true, (` "frozen=reasonTrue, slots=": null}
```True`):

```

Invalid: `{"trigger61

": "bad-:96:/home/bryanname!", "valid/.local/state": false, "/sase/reason": "invalidworkspaces/sase-org/sase/sase_characters"}`.

**Index rules_12/src Python/sase/xprompt/glossary must not_catalog.py
 invertclass**

- ` EditorGlossaryCatalog:
triggers`    schema_version / `calls`: int
    / `outbound` project: EditorGlossary

Project
    config

 / `inbound` are keyed

_path: Path

 by **explicit**




    config_

signature: _GlossaryConfigSignature  

 triggers only. Generated

 # path, m aliases (`

time_ns,Foo`)

 size
    catalog are not

: GlossaryCatalog
 graph keys (`

    compiled: Compiledcalls

GlossaryCatalog           ` has

 # opaque native no `"Base"` matcher

).
- Graphclass Editor isGlossaryCatalogResult:
 built from **raw    project: Editor** explicitGlossaryProject | None templates, before expansion
    catalog: removes call sites.
 EditorGlossaryCatalog |- `outbound None
    diagnostics` uses canonical: tuple[str target when, ...] = () resolved, else the
    # ok authored missing name. Duplic == catalog is not Noneates collapse; and not diagnostics
 `calls```

**CLI` keeps every site context.
- `inbound:**

```15:` is sorted22:/home/,bryan/.local/ unique, onlystate/sase for canonical/workspaces/s explicit identitiesase-org/. `sase/s#[Targetase_12/]` inboundsrc/sase-/glossary/clilands_common.py
 on `classtarget`.
- ResolvedGlossaryProject:
 Alias    project_name: str
    self-call catalog: GlossaryCatalog `foo` → `#[
    compiled:Foo]` is a CompiledGlossaryCatalog
 **direct cycle**    config_path on explicit: str
``` identity `foo`.

**Project identity
- Invalid triggers:** `EditorGlossaryProject( still expandkey, name,; they just aliases, workspace_dir)` get `triggers  
**ACE[ prompt:**t `PromptGlossaryContext].valid ==(project_ref false` plus, launch_workspace an)`  
**ACE panel:** `Glossary `invalid_trigger

ProjectRef(key` diagnostic.

---

, display_name

## 3, workspace_dir. Tests of the, has_glossary binding in this ()` +

s `GlossaryProjectSnapshotase) repo



(project, catalog| File | What, reverse_references it actually, diagnostics)`

 tests |
|---|### Effective entry

---|
| `/Authored vshome/bryan/. compiled islocal/state/ thesase/workspaces important/sase-

 split:

```43org/sase/sase_:107:/home/bryan12/tests//.local/state/sase/test_core_snippet_catalog_workspaces/sasefacade.py`-org/s | **Fakease/sase_12/src binding only.** Forwards the/sase/core/glossary_ dict, normalfacade.py
izes `templatesclass`/` GlossaryInputEntry:alias_provenance`,          rejects non # authored
   -mappings term: str
    definition: str and
    aliases: non-string k tuple[str,/v, rejects ...] = ()
 provenance whose    source: Glossary alias isSource | Mapping[ missing from templatesstr, Any] or whose source is missing from | None = None

class GlossaryEntry input:              . Fake # effective payloads ** / compiled
   omit** the new index: int
 fields    term: str. |
| `/
    normalized_home/bryan/.term: str
local/state/    definition: strs
   ase configured_/workspaces/sase-aliases: tuple[org/sasestr, ...]
/sase_    display_aliases12/tests/: tuple[strtest_xprompt, ...]
   _snippet_bridge effective_aliases:.py` | ** tuple[str,Hits ...]
    source the real**: Mapping[str `compose, Any] |_snippet_catalog None
```

`. `_`SNIPeffective_aliases`PET_REFERENCE_ isGOLDEN_VECTOR what lookupS` / and phrase `test_resolve-_snippet_referencescan use (_golden_vectorsRust` assert- **derived pluronly** `.als/displaytemplates[trigger]).`. No `display_aliases graph/diagnostics assertions` is UI. `configured

. |
| `/home/bryan/._aliases` is what deletelocal/state//restore writessase/workspaces back.

### Source/sase- contribution

There

org/sase is **no**/sase_ overlay-12/tests/contribution type. Onetest_editor_ projecthelper_snippet_ YAML filecatalog.py` |. Provenance is Integration through `GlossarySource`

 the helper bridge on each: merge, user input, then `Glossary-over-xpromptEntry.source` as a wire, nested mapping (` `#config_path`,xprompt `config_key`, `#[…]_path`, LSP` refs ranges).

Snippet, alias-side metadata via provenance analog of. Does “ not inspectwho graph fields. |
 contributed this| `/home/ trigger” todaybryan/.local/ is `alias_state/saseprovenance` in `/home/bryan/./workspaces/slocal/state/ase-org/sase/workspacessase/s/sase-ase_12/org/sase/sase_12/src/sase/core/snippet_catalog_facade.py` (`_Com

posedSnippetCatalog.templates` + `alias_provenance`),tests/ace/tui/test_prompt_catalog.py` | Snapshot plumbing; does not assert composer wire shape plus `XPrompt

. |

There isSnippetEntry.source_ **no** Pythonpath_display`. test that:



### Relations

```72- asserts `triggers`:100 / `calls`:/home/bryan/.local/state / `outbound`

/sase/ / `inbound`workspaces/sase / `diagnostics`
-org/s- calls `sase/sasease_core__12/srcrs.validate_snippet

/sase/_trigger`
-glossary/resolution.py registers
class GlossaryReferrer:
    term `compose_snippet_catalog` in `REQUIRED: str
    matched_text: str

class Glossary_BINDINGS`

ClosureNode:
   The entry: GlossaryEntry live
    depth: int
    origin-: Literal["requestedbinding shape tests live in linked core:

- `/home/bryan/.local/state/sase/workspaces/sase-org/s", "related"]
    referrer: GlossaryReferrer | None
    also_referenced_by: tuple[str, ...]
    spans: tuple[GlossarySpan, ...]

class Glossaryase/saseClosure:
    nodes_12/s: tuple[Glossaryase/repos/ClosureNode, ...]linked/sase
    roots:-core/crates tuple[GlossaryEntry/sase_, ...]
   core_py/ depth_limit:src/lib.rs int | None
    truncated: bool`
  - `
    requested_compose_snippet_references: int =catalog_binding_ 0
```returns_plain_

Inbound indexdict_shape`
: `glossary_  - `composereverse_references(catalog, compiled)_snippet_catalog -> Mapping[int_binding_ex, tuple[str, ...]]`poses_missing_ (catalogand_cycle_ order, self-graph`
  - `validate_snippetrefs dropped, unique_trigger_binding per_returns_plain referrer).

###_dict_shape Diagnostics

````
- `/home67:81/bryan/.local:/home/bryan/state/s/.local/state/sase/ase/workspaces/sase-orgworkspaces/sase-/sorgase//ssase_12ase/sase_12/src/sase//sase/repos/linked/core/glossary_sase-corefacade.py
/crates/sclass GlossaryDiagnostic:
ase_core/    severity: strsrc/snippet_
    code:catalog.rs` (` str
    message

#[: str
   cfg(test)] path: str |`) None
```



ContrastTwo: layers:

1 `tests. **Shape//test_core_snippet_sessionload_facade.py errors` **** —

 `tuple[strdoes** round, ...]` on-trip the

 real ` `EditorGlossaryCatalogResult` (`"{apply_snippet_configsession_event`

_path}: { binding.

---

display_path}:## 4. ... New phase"`).
2-1 fields Python

. **Rust validation must validate

The** — `validate

_glossary_entries facade currently stops` at `templates → `GlossaryDiagnostic`; errors` + `alias_provenance`. To match phase (`severity == "error"`) become load 1 it diagnostics needs or `GlossaryValidation

 the same “validate,Error.diagnostics`.

### don’t coerce” treatment Mutation outcomes

``` used41:78 for those:/home/bryan two maps/.local/state.

/sase/### `workspaces/sasetriggers` — trigger validation

- Type-org/sase/sase: mapping,_12/src keys/sase/ `glossary/mutation.pystr`,
class GlossaryMutation values mappingsOutcome:
    project.
- Per_name: str value
    config_: `trigger:path: str
 str` (should    workspace_dir match the: str
    map term: str
 key), `valid    aliases: tuple: bool`, `[str, ...]reason: str |
    definition: None`.
- str
    created `_section: boolreason` is `"
    restore_empty"` or `"command: str
invalid_characters"`    referenced_by when invalid: tuple[str; `None`, ...]

class when valid.
- GlossaryMutation EveryError(RuntimeError **explicit** input): ...
class trigger GlossaryValidationError( shouldGlossaryMutationError): appear;
 generated aliases should    diagnostics: tuple not.
- Rust rule: non[GlossaryDiagnostic, ...]
class Glossary-empty, everyConflictError(Glossary char `MutationError):
is_ascii_    path: Pathalphanumeric ||   '_'`. Unicode (` # stale writeéclair`) is invalid
 but```

Also ` still comGlossaryLookupposes.

### CallError` ( graph —not `calls`

- Type: mapping ` unique /str → list`. unknown) and `Glossary
- Each callCliError` (:
  - `authoredproject/catalog resolution_target: str).

### Extra`
  - ` glossarycanonical_target: types (probably str | None` not for (`None` iff snippets)

` `GlossarySpan` (status == "missing"`phrase match:)
  - ` term, entry_positional_args:index, alias, list[str]` matched (_text, byteincludes range colon, LSP- rangeform `#[gre, wrapet:World]` segments).  
Read-audit and quoted: `[[… `GlossaryReadEvent]]`)
  - `span:`, `GlossaryReadTermSummary`, ` {start:GlossaryReadAgentSummary int, end:`, `GlossaryRead int}` nonReportSpec`.

-negative byte---

## 

 offsets, `start3. Catalog loader

 < end`
 pattern

**  - `statusPipeline: "resolved"** | "missing" (`editor_glossary | "cycle"`_catalog_for
- Status_project`):

 is1. List enabled **, non-system

not** `", on-disk

direct projects (`enabled_cycle"` /_project_records `"indirect_cycle`).
2.

"`; Select one

 (` those are diagnostic codesselect_project`): only explicit.

### Indexes ref ( — `outbound`key/name/alias) / `inbound`

- Both **or** launch workspace: mapping / CWD / `str → list checkout marker / inferred project.[str]`.
- `outbound A[ bad explicitt ref **]does not** fall`: unique relation back.
 keys, **3. Resolve **first-seen**read** call order. Canonical config path (` if knownresolve_project_, else authoredconfig missing_read_path`).
4 name.
- `. Round-tripinbound[t] YAML (`load_`: presentround_trip_ for **every**mapping`).
5. Locate node explicit trigger (possibly ` (`resolve_glossary[]`); values_config` → sorted `memory.glossary unique callers. Only`).
6. canonical Shape into identities `GlossaryInputEntry get inbound edges` + `Glossary.

###Source `` ranges (`diagnostics`

- Typeparse_glossary_: `entries`).
7. Rust `validatelist`_glossary_entries of mappings (not`; a dict keep only error).
- Required-severity.
8.: `code: str`, `message Rust: str`, ` `build_glossarytrigger: str`._catalog` +
- Optional/ `compile_glossarynullable_catalog`.
: `target`,9. Stat-based `_ `span`GlossaryConfigSignature` (`{start, for cachesend}` or `.

**BestNone`), `cycle-effort Result` (`list, not[str]` or exceptions `None`).
:** missing config- Codes:
  / undeclared - `invalid_ glossarytrigger` — no → `catalog span/target=/cycle
 None, - `missing_ diagnostics=()`. Failtarget` — hasures attach span string + authored diagnostics. target
  - CLI then `direct_cycle maps Result` — `cycle → `GlossaryCli` lengthError`. ≤

**Caches 1 (self:** ACE / panel snapshots key alias self)
  - ` on `(

mtimeindirect_cycle` —_ `ns, sizecycle` is)` with a the explicit 0.5-identity path
s rest- Sorted by `(attrigger, span.start

 debounce,, span.end,

 LRU code, target)`. 

### Proven8 projectsance checks that should; invalidate stay

Keep the existing alias after mutation-.

---

source

## 4

 checks. Mutation / write. pattern

Shared engine in Extra `mutation invariants.py`. worth adding once CLI and ACE both call ` graphadd_glossary_

 fields are requiredterm` / `:

- graphdelete_glossary_

 keys ⊆ explicitterm`.

** input keys
-Add** `

1. Stripcanonical/validate_target` ( term (whensingle line present) ∈, non explicit keysblank, more than separators), definition, aliases.
2
- `alias_provenance` values ∈. Resolve project ( explicit keys (alreadycatalog ** checkednot** required —

)
- `alias first

_provenance` keys term can create the

 ∈ section).
3

. Read config `

 bytes +templates` (already

 text.
4. checked)

Python Parse current entries

 still

; must append candidate

 ** `GlossaryInputEntry

not** reimplement`.
5.

 capitalization `_validate_candidate

, expansion` → Rust

;, or cycle

 errors abort detection. ** It should only

before** write type-check/

.
6. Surgicalnormalize the wire and

 YAML insert raise ( `TypekeepError`/` comments, sorted ifValueError` on already mal sorted) else roundformation,-trip else matching ` `setsnippet__keysession_facade`.`.
7.

Existing facade Atomic write: unit compare tests will break bytes to original as, soon as those temp fields become required, because the file + `os.replace` + dir monkey fsync, `patched payloadsclear_config_ only include `templates` and `alias_provenancecache()`.
8. Return `Glossary`.

---

MutationOutcome` (`## 5. File paths and signaturescreated_section`, (index `restore_command)

**`).Python host

****

|Delete**

1 Path | Role |
. Require|---|---|
 catalog; resolve via **| `src/same** lookupsase/core/snippet_catalog_facade.py as show (`resolve_glossary_closure` | Facade(..., depth=0;)`).
2 `. Fillcompose_snippet_ `referenced_bycatalog(explicit_` from reverse indextemplates: Mapping[.
3. Dropstr, str]) the -> _Composed termSnippetCatalog` |
, re-validate| `src/ remaining,sase/core `/rust.py`unset_key`. | `require_
4. `rust_binding(dry_run=name: str)True` skips write -> Any` |
.



| `src/**Postsase/ace-write (/tui/CLI only):** `prompt_catalog.pys` | `buildase memory init`

_prompt_catalog unless `-

I_snapshot`, `` / drycompose_pending_-run,snippet_saves

 because` |
| ` glossarysrc/sase is injected/integrations/_editor

 into agent_helper_snippets

 instruction files.

**.py` | `Stale-writesnippet_catalog_ guard:** `currentresponse(request: != expected_bytes dict[str,` → `Glossary Any]) -> dictConflictError`.

[str, AnyExisting]` |
| ` snippet writersrc/sase (`insert_snippet_/integrationsinto_config`/editor_helpers in `snippet.py` | CLI_config_yaml dispatch.py`) is surgical for `snippet- YAML toocatalog` |
|, but **no `src/s** Rustase/xprompt validate, **/snippet_bridgeno** byte.py` | `-compareis_valid_ conflictsnippet_trigger(, **no** typedtrigger: str) outcome -> bool` |
. A| `src/ glossarysase/x-style snippetprompt/naming.py mutation` | `validate should add_snippet_trigger those.

(name: str---

## ) -> str \|5. How None` |
 tests are organized

| `tests**/test_coreDomain_snippet_catalog (flat_facade.py `` | Fake-tests/`):**

| File | Cowirevers |
|---| facade tests |
|---|
| ` `tests/testtests/test__xprompt_core_glossary_facade.py`snippet_bridge.py` | Real- | Wire roundbinding template-trip, compile gold/scan, diagnosticsens |
| ` |
| `teststests/test_/test_glossaryeditor_helper__resolution.py` | Normalizesnippet_catalog.py` | Helper-bridge integration |

**, alias/prefix lookupLinked core (phase, closure 1 landed BFS |
,| `tests/test_glossary_ unreleased in changelogrelations.py` | Reverse refs)**

| |
| `tests Path | Role |
|---|---|
/test_glossary| `s_mutation.py`ase/repos/ | Add/deletelinked/sase

 YAML-core/crates, validation/sase_, conflictcore/src/

, dry-runsnippet_catalog.rs |
| `tests` | `compose/test_glossary_snippet_catalog_read_log`, `validate_.py` /snippet_trigger`, `test_glossary `is_valid_read_report

_snippet_trigger.py` | Audit`, types store/ |
| `sreports |

**Loaderase/repos/:** `tests/linked/sasexprompt/test-core/crates_glossary_catalog/sase_.py` —

core/src/ projectlib.rs` | ref

 re, source ranges, validation

-exports |
| strings `sase/, LSP payload,repos/linked/ workspace markerssase-core./crates/s

 Fakes Rustase_core_ withpy/src/ alib.rs` | fixture.

**CLI:** `tests/ `py_composemain/test__snippet_catalogglossary_parser_`, `py_handler.py` +validate_snippet_trigger` |
| one file `sase/ per subcommand (`repos/linked/sase-coretest_glossary_cli_{/crates/sadd,del,

list,show,ase_core/all,read,

src/xpromptlog,common}._catalog.rs`py`).

** | native editorTUI ( catalog still uses onlydo provenance not copy into + templates |

** snippetRust type domain tests signatures**

```):** panel catalogrust
pub fn, preview compose_snippet_ modalcatalog(explicit_, highlightingtemplates: &B, PNGTreeMap<String snapshots.

Pattern:, String>) -> **engine tests import ComposedSnippetCatalog `sase.glossary.;
pub fn validate_mutation` / `snippet_trigger(resolution` directly**; CLItrigger: &str tests call) -> Snippet handlers; loaderTriggerValidation;
pub tests patch fn is_valid `list_project_records_snippet_trigger(trigger: &` + Ruststr) -> bool bindings.

;

---

## pub struct Composed6. ProvenSnippetCatalog {
   ance, shadows, pub templates: B lookup, diagnostics

TreeMap<String### Provenance

- Per, String>,
-entry `    pub alias_GlossarySource` (provenance: BTreeMap<String,file, YAML String>,
    key path, LSP pub triggers: B ranges).
-TreeMap<String Closure provenance: `, SnippetTriggeroriginValidation>,
   ` + `Glossary pub calls: BReferrer(TreeMap<Stringterm, matched_, Vec<Snippettext)` + `Call>>,
   also_referenced_ pub outbound: Bby`.
-TreeMap<String JSON ``all` includes `, Vec<Stringplan:202608source` on>>,
    pub/snippets_panel each term.

### inbound: BTree.md` is ** Shadows

Map<String,not in this workspaceGlossary is Vec<String>>,** (`sase **one
    pub diagnostics file/repos/plans: Vec<Snippet**. No/202608/`Diagnostic>,
}
 overlay. Alias```

**Bottom has no `snippets_panel.md`). collisions line:** Python already Phase 2 intent are calls below ** the phase comesvalidation errors**, from bead-1 composer, not first-wins `sase- but `_ shadowsrd.2`:.

`ComposedSnippetCatalogsetdefault *“catalog` is` in-mutations: build still a two- `_LookupIndex` one provenance-awarefield object Python service for catalog. The is first-catalog-order for reads and conflict-safe config snippet writes duplicate next host change.”* Rust is to validate keys Phase after 1 (`s Rust already rejected and retain `triggers`, `ase-rd. themcalls`, `outbound.

**`, `inbound`,1`) already landedSn relation and `diagnostics`ippets already have shadows metadata in the linked at** — `sase- the facade copycore` checkout.

 boundary (and optionally this---

##  wrap

, not glossary:

1. ` `validate_snippet

```178_trigger`)src/` files related:186 without re to snippets:/home/bryanimplementing the



/.local/state graph###/sase/. Catalogworkspaces/sase,-org/s

ase/sase YAML_12/src, write//sase/load (Phase

xprompt/snippet 2 core)



_targets.py
| Path | Roleclass SnippetCollision |
|---|---|:
    matches:
| `/home tuple[_SnippetTrigger/bryan/.localMatch, ...]
/state/s    derived_fromase/workspaces/: str | Nonesase-org
    winner_path/: strs |ase/ None
    shadowedsase_12_by: str/src/s | None
   ase/core/ shadows: str |snippet_catalog_ None
```

facade.py`Prompt catalog overlay: | Thin xprompt-derived validated → user ` wrapper around Rustace.snippets` `compose → pending saves_snippet_catalog,` |
 then Rust| `/home/ `compose_snippetbryan/.local/_catalog`.

state/sase### Lookup

`/workspaces/s_LookupIndex`ase-org/ on a catalogsase/s:

1. Normalizease_12/: casefold,src/sase collapse `/core/rust[-_\.py` | `s]+` torequire_rust_ one space.
2binding("compose_. Exact normalizedsnippet_catalog") term /` loader display term.
3 |
| `/home. Exact effective alias/bryan/.local.
4. Unique/state/s prefix acrossase/workspaces/ allsase-org keys.
5./sase/ Else `sase_12GlossaryLookupError`/src/s with up to ase/xprompt5 substring candidate/snippet_config **terms_yaml.py`**.

 | Surgical YAML insertBatch lookup/replace under collects failures `ace. then raises onesnippets` |
| `/home/bryan error/.local/state./sase/ Deleteworkspaces/sase/-org/sshow/read allase/sase_12/src share/sase/ this.

### Diagnostics

- Loaderxprompt/snippet:_targets.py` | Destination never throw for “ discovery, saveno glossary”; CLI- does.
- Mutationtarget resolution, collisions: Python, `load_ shapesnippet_template` checks |
| `/home,/bryan/.local then Rust errors/state/s only.
ase/workspaces/- CLIsase-org write formats/sase/ `configsase_12_path memory/src/s.glossary.<ase/xpromptterm> CODE/snippet_bridge: message`.
.py` | X- Editorprompt `snippet:`: → ACE string template (` diagnostics,$1 ``/`ok` iff$0`) |
 catalog present and| `/home/ emptybryan/.local/ diagnosticsstate/sase.

---

## 7. What/workspaces/s a `ase-org/sase/ssrc/sase/snippet/` analogase_12/ should copy vs skipsrc/sase

###/xprompt/ Copy

- **save_index.pyLayer` | Mingtime-cached names +:** `core/* lazy_facade.py YAML preview for `` forsnippet_config` Rust wire |
| `/home;/bryan/.local `src/state/s/sase/ase/workspaces/snippet/` for Pythonsase-org domain

/sase/; **

sase_12do not** put/src/s loadase/xprompters in `xprompt/`/ thisnaming.py` | Trigger validation + first time if the plan wants a focused package (-wins `resolutionglossary_after_save’s` |
| `/ xhome/bryan/.prompt split is historicallocal/state/).
- Frozensase/workspaces `@/sase-dataclass(frozen=org/saseTrue, slots=/sase_True)` models;12/src/ tuplessase/x not lists; `__prompt/write_all__` pertargets.py` | module; ** Chezmoi remapempty package used `__init__` by `resolve_**.
- Resultsnippet_save_ object: `projecttarget` |
| `/home/bryan//.local/statecontext/sase/ + catalog|workspaces/saseNone + diagnostics`.-org/s
- Authase/saseored vs effective_12/src entry/sase/.
- Mutationxprompt/save_state.py`: | Rem validate wholeembers last snippet candidate set → surgical save path YAML → atomic write |
| `/home + conflict/bryan/.local guard → typed/state/s `ase/workspaces/*MutationOutcome`.
sase-org/sase/- Thinsase_12 CLI over/src/s the enginease/ace/; ACEtui/prompt uses_catalog.py` the same functions.
- Tests | Off

: facade-thread ACE snapshot / resolution / relations: xprompt +

 / mutation / catalog merged `ace. loadersnippets` + compose / CLI files |
| `/home.
/bryan/.local- Filter/state/sase/workspaces/ helper shared by CLIsase-org list and TUI.

/sase/sase_12### Copy/src/s fromase/ace/ **tui/actionsexisting/agent_workflow snippet code/_prompt_bar**, not glossary

_save_x- Multiprompt_snippets.py-source catalog` | `write context (x_snippet_syncprompt derived`, user config, + confirm project config/save, pending).
/publish live- `alias_provenance` / cache |
| `/ collisionhome/bryan/. `shadowedlocal/state/_by` /sase/workspaces `shadows`.
- Trigger/sase- charsetorg/sase `[A-Za/sase_-z0-12/src/9s_ase]+/`ace vs/tui/ glossary’sactions/agent_workflow/_prompt_ free-formbar_snippet_ terms.
- Configpane.py` | key `ace. `gt` panesnippets` (flat: locations, `name: |- derived catalog, destination fingerprint` scalars), not `memory |
| `/home.glossary` mappings/bryan/.local.
- Re

/state/sase/workspaces/use `insert_snippet_into_config` / `sase-orgsnippet_collision`/sase/ / `composesase_12

_snippet_catalog/src/s

` ratherase/integrations/_ than rewritingeditor_helper_.

snippets.py` |

### Do ** Editor `not** copy (

snippet-catalog`glossary-specific)

 merge +| compose |
| `/ Glossaryhome/bryan/. bitlocal/state/ | Why skip

 |
|---|---|sase/workspaces
| Phrase/sase- `org/sase/sase_GlossarySpan` / compiled matcher /12/src/ definitionsase/integrations B/editor_helpersFS closure.py` | Dis | Snippets arepatches `snippet- triggers, not prosecatalog` |
| terms ( `/unless youhome/bryan/.local/state model nested/sase/ `#workspaces/sase@` expansion as relations) |
|-org/s `sase glossaryase/sase read -_12/srcr` JSON/sase/L + reports |main/parser_ Agent auditeditor.py` | of glossary ** Registersdefinitions** |
| Post `-write `ssnippet-catalog`ase memory init` helper sub | Snippets are not injectedcommand |
 into AG| `/home/bryan/.local/ENTS.md |
|state/sase Generated `sase/workspaces/s/memory/glossaryase-org/.md` | Memorysase/s-note generation |
ase_12/| Prefixsrc/sase/slug/default_config lookup.yml` | Default with separator `ace.snippets: {}` and collapse | Sn `ace.snippetippet_config_path triggers: are exact identifiers |
| Plural ""` |
| ` `/home/bryaneffective_aliases`/.local/state |/sase/ Rustworkspaces/sase glossary-org/sase/sase matching |
| LSP catalog_12/src payload //sase/ nvim termconfig/sase ranges | Optional.schema.json` later | |
 Schema| for Rich those dictionary ` two ACEall` renderer fields | Product |
| `/home/bryan/.local-specific |
| Single/state/s-filease/workspaces/ “no overlaysase-org” assumption | Wrong/sase/ for snippets |
|sase_12 `Glossary/src/sCliError` “ase/config/hasloading.py` | no glossary configured” Deep | Sn

-merge of layersippets always

 (how have derived snippet + user layers maps |

### Suggested snippet actually combine model names (aligned) |
| `/ to the plan)



home/bryan/.Iflocal/state/ you wantsase/workspaces the

/sase- plan’s vocabularyorg/sase explicitly:

- `Snippet/sase_CatalogContext` ←12/src/ `EditorGlossaryCatalogsase/config` + overlay/layers list.py` | Un (pathsmerged layer metadata (, signaturesdefault/, layersplugin/user/)
- `Snippetoverlay/localEffectiveEntry` ←) |
| `/ `GlossaryEntry` (trigger, templatehome/bryan/.

, aliases, winnerlocal/state/ layersase/workspaces)
- `SnippetSourceContribution` ←/sase- `GlossarySource`org/sase/sase_ **12/src/plus** layersase/config//precedencecore.py`/ | `load_merged_config()`shadowed- cacheby (glossary + merge order |
 lacks| `/home/ this)
- `bryan/.local/SnippetRelations` ←state/sase only if nested expansion/workspaces/sase-org/;sase/s else skipase_12/src/sase/config/x closureprompt_sources.py
- `SnippetDiagnostic` ← `` | **GlossaryDiagnostic`
Pattern- `SnippetMutationOutcome` ← `** for per-source provenanceGlossaryMutationOutcome` (`load_x (`prompts_by_trigger`, `templatesource`); snippets have`, `config no analog |

### ACE_path`, ` UIrestore_command`, `shadow thats *`consum/`shadowedes* the_by`)

 aboveKeep Rust (Phase composition 4 in `sase.core.snippet/5 more_catalog_fac than Phase 2ade`; keep session expansion in `)

|snippet_session_ Path | Role |
facade`. The|---|---|
 new package should own| ` **catalog modelssrc/sase,/ace/t load, lookup,ui/mod diagnostics,als mutation**/snippet_name — the_modal.py` same slice | Trigger picker + `s collision previewase.glossary` |
| `src owns/sase/ afterace/tui the facade/modals/.snippet_save_confirm_modal.py

` | Diff confirm; previews via `generate_snippet_yaml` |
| `src/sase/ace/tui/modals/unified_xprompt_save_support.py` | `load_unified_snippet_locations()` over `load_snippet_config_locations` |
| `src/sase/ace/tui/modals/unified_xprompt_save_preview.py` | Draft YAML preview for snippet mode |
| `src/sase/ace/tui/modals/unified_xprompt_save_modal.py` | Unified save panel; validates with `validate_snippet_trigger` |
| `src/sase/ace/tui/widgets/_prompt_input_bar_snippet_pane.py` | Prompt-bar snippet draft pane |
| `src/sase/ace/tui/widgets/_prompt_stack_targets.py` | `SnippetPaneTarget` dataclass |
| `src/sase/ace/tui/widgets/_prompt_stack_state.py` | Stack item holding `snippet_target` |
| `src/sase/ace/tui/widgets/_prompt_input_bar_messages.py` | `SnippetTargetRequested` / `SnippetPaneSaveRequested` |
| `src/sase/ace/tui/actions/_startup_prompt_catalog.py` | `get_snippets()` memory cache |
| `src/sase/ace/tui/actions/agent_workflow/_prompt_bar_save_xprompt.py` | Wires `_write_snippet_sync = write_snippet_sync` |

### Adjacent (expansion, not catalog)

| Path | Role |
|---|---|
| `src/sase/core/snippet_session_facade.py` | Tabstop session engine (`apply_snippet_session_event`) |
| `src/sase/ace/tui/widgets/_snippets.py` | Prompt textarea expansion mixin |

### Not ACE snippet catalogs

Chat/history `prompt_snippet`, agent-scan `raw_prompt_snippet`, search-result snippets, etc. are unrelated.

There is **no** `sase snippet` CLI module yet (that is `sase-rd.3`).

---

## 2. Full APIs

### `snippet_catalog_facade.py`

```12:52:src/sase/core/snippet_catalog_facade.py
@dataclass(frozen=True, slots=True)
class _ComposedSnippetCatalog:
    """Normalized result from the shared Rust snippet catalog composer."""

    templates: dict[str, str]
    alias_provenance: dict[str, str]


def compose_snippet_catalog(
    explicit_templates: Mapping[str, str],
) -> _ComposedSnippetCatalog:
    """Compose explicit snippet templates through the shared Rust contract."""
```

- Private result type (underscore, not in `__all__`).
- Calls `require_rust_binding("compose_snippet_catalog")(dict(explicit_templates))`.
- Requires payload `templates` and `alias_provenance` to be `str→str` maps.
- Provenance checks: every alias key exists in `templates`; every alias value exists in the **input** explicit map.
- **Drops** Rust fields that already exist in linked core: `triggers`, `calls`, `outbound`, `inbound`, `diagnostics`. Extra keys are ignored, not rejected.

Rust/PyO3 shape (from `sase-core` after Phase 1):

```text
compose_snippet_catalog(templates: dict[str, str]) -> dict
  templates, alias_provenance,
  triggers: {trigger: {trigger, valid, reason}},
  calls: {trigger: [{authored_target, canonical_target, positional_args, span:{start,end}, status}]},
  outbound, inbound, diagnostics[{code, message, trigger, target, span, cycle}]

validate_snippet_trigger(trigger: str) -> dict  # Python does not wrap this yet
```

### `snippet_config_yaml.py`

```40:50:src/sase/xprompt/snippet_config_yaml.py
def generate_snippet_yaml(name: str, template: str) -> list[str]:
    """Generate YAML lines for one snippet entry.
    ...
    """
    template = template.rstrip("\n")
    result = [f"    {name}: |-"]
```

```228:243:src/sase/xprompt/snippet_config_yaml.py
def insert_snippet_into_config(
    config_path: str,
    name: str,
    template: str,
) -> bool:
    """Insert or replace a snippet under ``ace.snippets`` in a YAML config file.
    ...
    Returns ``True`` on success.
    """
```

Behavior:
- Minimal-edit writer (comments/order preserved).
- Creates missing file, `ace:`, and `snippets:`.
- Sorted sections insert by trigger name; unsorted sections append.
- Overwrite replaces only the matching block.
- Emits strip-chomped `|-` so trailing newlines survive the writer’s `rstrip`.
- **Always returns `True`** — there is no failure path. No delete API.

Helpers (`_Section`, `_EntryBlock`, `_find_snippets_subsection`, …) are private.

### `write_snippet_sync`

```350:354:src/sase/ace/tui/actions/agent_workflow/_prompt_bar_save_xprompt_snippets.py
def write_snippet_sync(config_path: str, name: str, body: str) -> None:
    from sase.xprompt.snippet_config_yaml import insert_snippet_into_config

    if not insert_snippet_into_config(config_path, name, body):
        raise RuntimeError("snippet insertion failed")
```

Also in the same module:
- `existing_snippet_names(config_path) -> set[str]` — duplicate of `names_for_location("snippet_config", …)` without the mtime cache.
- `PromptBarSaveSnippetMixin.save_snippet(...)` — write, remember location, publish `_pending_snippet_saves`, compose live cache, post-write git/chezmoi actions.

### `load_snippet_config_locations` and `snippet_targets.py`

```27:38:src/sase/xprompt/snippet_targets.py
@dataclass(frozen=True)
class SnippetConfigLocation:
    label: str
    path: str
    display_path: str
    disabled_reason: str | None = None
```

```77:101:src/sase/xprompt/snippet_targets.py
def load_snippet_config_locations(
    project: str

 | None = None,
) -> list[SnippetConfigLocation]:
    """Discover user config files offered by the unified snippet panel."""
    del project


    ...


    candidates: list[tuple[str, Path]] =

 [("User sase.yml", config_dir / "sase.yml")]
    ... glob("sase_*.yml") ...
    candidates.append(("Project sase/sase.yml", local_config))
```

Other public APIs:
- `resolve_snippet_save_target(configured: str | None) -> SnippetSaveTarget` — `ace.snippet_config_path`; chezmoi remap via `resolve_xprompt_write_target`.
- `snippet_collision(trigger, destination, *, locations, derived) -> SnippetCollision` — first-wins over `locations`.
- `load_snippet_template(path, trigger) -> str` — `yaml.safe_load` then `ace.snippets[trigger]`; `KeyError` if missing.

`project` is **explicitly discarded**. Discovery is: user `sase.yml` → all `sase_*.yml` overlays (sorted glob, **not** `selected_overlay_paths()`) → project `sase/sase.yml`. Default/plugin configs are omitted.

### ACE

 prompt catalog helpers

```42:54:src/sase/ace/tui/prompt

_catalog.py
class

 PromptCatalogSnapshot:
    generation: int


    source_token: tuple[Any, ...]
    explicit_snippets: Mapping[str

, str]
    snippets: Mapping[str, str]          # composed templates
    user_snippets: Mapping[str, str]     # merged ace.snippets only
    assist_entries_by_project: ...
```

```57:126:src/sase/ace/tui/prompt_catalog.py
def build_prompt_catalog_snapshot(...) -> PromptCatalogSnapshot | None: ...
def compose_pending_snippet_saves(
    explicit_snippets: Mapping[str, str],
    pending_snippet_saves: Mapping[str, str],
) -> dict[str, str]:
    ...
    return compose_snippet_catalog(explicit).templates
```

Merge inside `build_prompt_catalog_snapshot`:
1. `build_xprompt_snippet_entries_from_catalog(get_all_xprompts(project=None))`
2. `load_merged_config()["ace"]["snippets"]` overwrites same triggers
3. `pending_snippet_saves` overwrites again
4. `compose_snippet_catalog(explicit)`

Also: `prompt_source_watch_paths`, `prompt_source_change_touches_config`, token helpers. Snapshot **does not** keep call graph / diagnostics.

### Xprompt snippet bridge

```17

:25:src/sase/xprompt/snippet_bridge.py
class XPromptSnippetEntry:
    trigger,

 template, xprompt_name, description, source_path_display
```

- `is_valid_snippet_trigger(trigger) -> bool` — Python regex `^[a-zA-Z0-9

_]+$`
- `build_xprompt_snippet_entries_from_catalog(xprompts) -> list[XPromptSnippetEntry]`
- `get_xprompt_snippet_entries(project=None)`
- `_get_xprompt_snippets` (private dict form)
- First xprompt wins on trigger collision; skips complex Jinja; appends `$0`

---

## 3. How config layers load snippets today

There is **one** runtime path for *expansion*: merged `ace.snippets`. There is a **different** path for *save destinations / collisions*.

### Runtime merge (`load_merged_config` → `merge_config_sources`)

Order from `core.py` / `loading.py`:

1. **default** — bundled `default_config.yml` (`ace.snippets: {}`)
2. **plugin** — each enabled `sase_config` plugin’s `default_config.yml` (`deep_merge`, lists concatenate)
3. **user** — `CONFIG_DIR/sase.yml` (`list_strategy="replace"`)
4. **overlay** — `selected_overlay_paths()`: non-machine overlays + this machine’s overlay (lists concatenate)
5. **local/project** — `get_local_config_path()` (`sase/sase.yml` preferred, root `sase.yml` readable)

`ace.snippets` is a **mapping**, so `deep_merge` is **key-wise last-wins**: later layers overwrite the same trigger; distinct triggers accumulate. Empty `{}` from default contributes nothing.

ACE prompt catalog and editor helper both do:

```python
merged = load_merged_config()
ace_cfg = merged.get("ace", {})
raw = ace_cfg.get("snippets", {})
```

So they see **only the merged bag**, with **no per-layer provenance**. Xprompt-derived snippets are a separate overlay applied *before* user snippets (user wins).

### Save/collision discovery (`load_snippet_config_locations`)

Does **not** use `load_merged_config`. Offers writable YAML files:

- User `sase.yml` (chezmoi source when `use_chezmoi`)
- Every `sase_*.yml` in that dir (all overlays, including unselected machine overlays)
- Project `sase/sase.yml` write path

Missing:
- bundled default / plugin defaults
- `project` argument (signature only)
- selected-overlay filtering
- alignment with merge last-wins

Collision code documents **first-wins** in that list order (user shadows project), which is the **opposite** of merge last-wins (project overrides user). Tests encode first-wins (`test_snippet_collision_shadowed_by_higher_precedence_file`).

---

## 4. Existing tests

| File | What it covers |
|---|---|
| `tests/test_core_snippet_catalog_facade.py` | Monkeypatched binding: templates + alias_provenance normalize/reject. **No real-binding test, no relation fields** |
| `tests/xprompt/test_snippet_config_yaml.py` | Create/insert/overwrite/sort/comments/block scalars |
| `tests/xprompt/test_snippet_targets.py` | `resolve_snippet_save_target`, `snippet_collision`, `load_snippet_template`. **No `load_snippet_config_locations` tests** |
| `tests/xprompt/test_save_index.py` | `names_for_location("snippet_config", …)` |
| `tests/xprompt/test_naming.py` | `validate_snippet_trigger` vs Python regex |
| `tests/xprompt/test_save

_state.py`

 | last-used snippet path |
| `tests/test_xprompt_snippet_bridge.py` | Jinja/tabstop conversion; **real** `compose_snippet_catalog` for `#[…]` expansion |
| `tests/test_editor_helper_snippet_catalog.py` | Merge, user-over-xprompt, nested compose, refs, alias provenance metadata |
| `tests/ace/tui/test_prompt_catalog.py` | Snapshot merge, capitalized collisions, `compose_pending_snippet_saves`, pending-save races |
| `tests/ace/tui/actions/test_prompt_save_xprompt_targets.py` | `

write_snippet_

sync` / skip

-write /

 overwrite

 / pane save |
| `tests/ace/tui/modals/test_snippet_name_modal.py` | Trigger modal, collisions, derived templates |
| `tests/ace/tui/modals/test_snippet_save_confirm_modal.py` | Confirm/diff/reload |
| `tests/ace/tui/visual/test_ace_png_snapshots_snippet_name.py` | PNG goldens |
| `tests/test_core_snippet_session_facade.py` | Expansion session (adjacent) |

`tools/validate_sase_core_rs` `REQUIRED_BINDINGS` includes `apply_snippet_session_event` but **not** `compose_snippet_catalog` or `validate_snippet_trigger`.

---

## 5. Phase 2: reuse vs replace

Bead: *one provenance-aware Python service for catalog reads and conflict-safe config snippet writes.* CLI (`sase-rd.3`) and ACE panel (`sase-rd.4/5`) should sit on that service.

### Reuse (keep, maybe wrap)

- **Rust compose + relation payload** — extend the Python facade; do not reimplement graph analysis.
- **`insert_snippet_into_config` / `generate_snippet_yaml`** — conflict-safe surgical writes.
- **`load

_snippet_template

`**, **`names_for_location("snippet_config")`**, **`save_index.load_definition`**.
- **`SnippetSaveTarget` / `resolve_snippet_save_target` / chezmoi `write_targets`**.
- **`snippet_collision` + `resolution_after_save`** — if first-wins is still the save-panel model; otherwise wrap with explicit precedence.
- **`build_xprompt_snippet_entries_from_catalog` / `XPromptSnippetEntry`** — xprompt-derived rows.
- **`load_xprompts_by_source`** as the **pattern** for per-layer provenance (snippets have no equivalent).
- **`write_snippet_sync`** as a 3-line wrapper (or move next to the YAML writer, out of ACE).
- **`validate_snippet_trigger`** — prefer wrapping Rust `validate_snippet_trigger`; keep Python `naming.validate_snippet_trigger` as the user-facing error string.

### Replace / fill (this is the Phase 2 product)

- **New service** — nothing like `load_xprompts_by_source` exists for snippets. ACE `prompt_catalog` and editor helper both flatten to `trigger → template`.
- **`load_snippet_config_locations`** — not project-aware (`del project`), no default/plugin, glob-all overlays vs selected overlays. Needs a real layer list if the service is provenance-aware.
- **`_ComposedSnippetCatalog`** — currently private and incomplete

 vs Rust. Export a public typed catalog (triggers/calls/inbound/outbound/diagnostics).
- **`existing_snippet_names`** — duplicate; fold into `names_for_location`.
- **No delete writer** — CLI `delete` cannot reuse insert-only YAML.
- **Merge vs collision precedence** — last-wins runtime vs first-wins save UI; Phase 2 should pick one documented rule.
- **Python `is_valid_snippet_trigger`** — duplicate of Rust; keep as thin facade.

Do **not** replace ACE widgets or snippet-session expansion in Phase 2; they should call the new service.

---

## 6. TODOs / stubs pointing at this work

No `TODO`/`FIXME` in snippet modules. Incomplete by shape, not comment:

1. **Facade lag after `sase-rd.1`** — Rust returns relation metadata; Python only types `templates` + `alias_provenance`.
2. **`validate_snippet_trigger` Rust binding unused** from Python.
3. **`load_snippet_config_locations(project)` discards `project`**.
4. **`insert_snippet_into_config` always `True`** → `write_snippet_sync`’s `RuntimeError` is dead.
5. **No snippet delete / no provenance catalog service / no `sase snippet` CLI**.
6. **`compose_snippet_catalog` not in `REQUIRED_BINDINGS`**.
7. **Zero tests** for `load_snippet_config_locations`.
8. **`_ENTRY_RE` allows `[\w/.:-]+`** while triggers are `[A-Za-z0-9_]+`.

---

## 7. `compose_snippet_catalog` call sites (Python)

Production:

1. `src/sase/core/snippet_catalog_facade.py` — the binding itself  
2. `src/sase/

ace/tui/prompt_catalog.py`  
   - `build_prompt_catalog_snapshot` → `.templates`  
   - `compose_pending_snippet_saves` → `.templates`  
3. `src/sase/integrations/_editor_helper_snippets.py`  
   - `snippet_catalog_response` → `.templates` + `.alias_provenance` (copies metadata from source trigger onto aliases)

Tests:

- `tests/test_core_snippet_catalog_facade.py` (mocked binding)
- `tests/test_xprompt_snippet_bridge.py` (real binding, expansion only)
- `tests/ace/tui/test_prompt_catalog.py` (via snapshot helpers)
- `tests/test_editor_helper_snippet_catalog.py` (via editor helper)

No other Python `require_rust_binding("compose_snippet_catalog")` sites. ACE expansion uses **`apply_snippet_session_event`**, not compose.

---

**Phase 2 implication:** keep YAML mutation and Rust compose; add a provenance-aware catalog service that (a) records *which layer/file/xprompt* owns each trigger, (b) surfaces the new Rust graph fields, (c) writes through `insert_snippet_into_config`, and (d) makes `load_snippet_config_locations` actually project- and layer-aware so CLI and ACE stop re-merging ad hoc.

I have a clear picture of the service. Next I’ll expand the Rust facade, then add the catalog and mutation package.

I’ll update the facade tests for the new wire fields, then add YAML preview/apply support.

I’ll install the workspace, then run the new tests and lint.

Symvision flagged APIs that later phases will consume. I’ll wire the live callers and whitelist the rest on this bead.

`just check` passed. I’ll bump the Rust-core floor to 0.29.4 since we now call `validate_snippet_trigger`.

The full suite had one failure in the logs pane, which I didn’t touch. I’ll rerun that test to see if it’s a flake.

Closed **sase-rd.2** (`catalog-mutations`). The parent epic `sase-rd` is still open.

The shared Python catalog and mutation service is in place. CLI, panel, prompt expansion, editor helper, and prompt-save now have one composition path and one write path.

**Catalog reads**
- `src/sase/snippet/` loads a project by name, alias, or key without changing CWD.
- Config layers replay default → plugin → user → overlay → project, with shadow provenance.
- Explicit `ace.snippets` overlay xprompt-derived templates; Rust still owns aliases, expansion, and the call graph.
- `load_snippet_config_locations(project)` uses the named project’s workspace.
- ACE prompt catalog and the editor helper consume this service.

**Conflict-safe writes**
- YAML preview/apply/delete preserves comments and unrelated config.
- Writes are atomic and guarded by an expected-content digest.
- Shared add/update/delete validate the candidate set through Rust, then invalidate config/save indexes only after success.
- Prompt-pane `write_snippet_sync` uses that same primitive.

**Verification**
- `just check` lint gates passed (including the `sase-core-rs>=0.29.4` floor for `validate_snippet_trigger`).
- Focused catalog, mutation, facade, helper, and prompt tests passed.
- Escalated full suite: 35023 passed; one unrelated logs-pane flake failed once and passed on serial rerun. Recorded as `PROPOSED FOLLOW-UP` on this bead.
- `sase bead epic-symbols sase-rd.2` was empty. CLI-facing mutation symbols are keyed to still-open `sase-rd.3`.

I'll start by reading the full prompt, the bead/commit skills, and the current workspace state so I can close `sase-rd.2` and commit only this phase's work.

The prompt is a commit-finalizer pass. Next I’ll inspect the rest of the request, bead status, and uncommitted changes.

The bead is already closed. I’ll confirm epic-symbols, publish the close if needed, then inspect the diff and commit.

Close is still running; I’ll wait for it and read the new snippet package so the commit message matches the work.

Close published with no leftover epic symbols. I’ll write the commit message and commit the phase-2 catalog and mutation work.

Phase 2 for `sase-rd.2` is done, closed, and on `master`.

**What landed:** a shared Python snippet catalog and mutation service.

- `src/sase/snippet/` loads one project's catalog without changing CWD, overlays config on xprompt entries, and lets Rust handle composition, aliases, and the call graph.
- The compose facade now requires the 0.29.4 core fields: triggers, calls, inbound/outbound indexes, and diagnostics.
- YAML preview/apply/delete is atomic with digest-based stale-write conflicts. ACE prompt-bar saves and the editor helper catalog use the same write path.

**Close and commit:** `sase-rd.2` was already closed. `sase bead epic-symbols` showed no leftovers for this phase (CLI mutation symbols stay on `sase-rd.3`). The work is committed and pushed as `82e68005f` (`feat(snippet): add project-aware catalog and conflict-safe mutations`). Working tree is clean and in sync with `origin/master`.
