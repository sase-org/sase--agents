# Chat History - ace-run (sase-s0.2)

- **TIMESTAMP:** 2026-08-21 21:48:29 UTC
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-s0.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-s0, bead=sase-s0.2)
%model:@medium
%auto
%w:sase-s0.1
%w(bead=sase-s0.1)
Can you complete the work for bead sase-s0.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-s0.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-s0.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-s0.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, its design, and the relevant SASE skills so I can complete sase-s0.2 without changing its status by hand.

Phase 2 is the host catalog and ACE prompt work. I’ll read the CLI, xprompt, and TUI memory, then inspect Phase 1 and the current completion/finalizer code.

I’ll open the linked core repo and map the existing finalizer, helper-bridge, and ACE completion code.

While those searches run, I’ll read the finalizer config, helper-bridge, and

 ACE completion sources.I'll search the repo for helper-bridge CLI, finalizer config, and related tests so the report can follow existing patterns.

I'll search ACE widgets, directive completion, inventory workers, and `%final` hidden-name handling in parallel.

I'll search the repo for finalizer catalog bindings, wire records, candidate builders, and how similar completion APIs are exposed to Python.

Key

 files are located

;

 next I’ll read the completion adapters, workers, and catalog

 warming

 paths.

The catalog and completion types look concentrated in editor wire, directive completion, and Python bindings — I'll read those next.

This is a read-only map of the helper-bridge surface and the finalizer config layer, including how a new catalog operation should be added.

---

## 1. Editor helper-bridge CLI

### Dispatch path

`sase editor` is a hidden, fixed-operation JSON bridge (not a shell/FS API).

| Layer | Path | Role |
|---|

---|---|
|

 Parser registrar | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/main/parser.py` | Maps `"editor"` → `register_editor_parser` |
| Parser | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase

/main/

parser

_

editor.py`

 | `sase editor helper-bridge <op>` |
| CLI entry | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/main/entry.py` | Calls `handle_editor_command` |
| Command handler | `/home/bryan/.local/state/sase/workspaces/

s

ase

-org/sase/

sase_14/src/s

ase/main/

editor_handler.py

` | Ex

its with

 helper

-bridge return code#

 |
| Editor Phase 1 final

izer completion contract ( facade | `/home

/bryan/.localPython

 ACE/host)

/state/sACEase/workspaces/ doessase-org **not** get/sase/ a new dedicatedsase_14 `/src/sfinalizer_catalogase/integrations/(...)` Pyeditor_helpers.py` | `handleO3 function._editor_helper Phase_bridge` |
 1 reuses the existing directive| Mobile- fallbackcompletion bindings | `/home/ and addsbryan/.local/ a **state/saseversioned helper-/workspaces/sbridge catalog**ase-org/ so LSP (sase/saseand_ other14/ non-Python frontends)src/sase can fetch the same/integrations/mobile inventory ACE_helpers.py` already has in-process | Shared ops (.

Therenotably are two related `xprompt- butcatalog`) |

 distinctParser contracts:

:| Layer | What every sub itparser is | Who calls uses whom `help=arg |
|---|---|parse.SUPPRESS---|
| Editor` ( completion | `%hidden fromfinal` candidates `--help`). from Dest names host inventory | ACE:

- `editor/LSP_subcommand` call `sase =_core` |
 `"helper-bridge| Helper catalog |"`
- ` Fresheditor_helper_ inventorybridge_subcommand` JSON for = operation LSP | LSP slug calls Python

```8 via `sase editor:40:/home/bryan/.local helper-bridge final/state/sizer-catalog`ase/workspaces/ |
| Finalsase-orgizer protocol | Plan/sase//validatesase_14/submit wires/src/s | Alreadyase/main/ bound asparser_editor.py
def register_ `validateeditor_parser(_finalizer_*subparsers: argparse` / `resolve_finalizer_._SubParsersActionplan` |

The) -> None:
 protocol    """ APRegister the ``sIs (`finalase editor`` subizer_wire_command parser."""
schema_version`,    editor_parser instance = subparsers.add specs, selectors_parser(
       ) are **not "editor",
** the editor        help="Run completion API editor integration helpers",. Completion
    )
    uses `DirectiveFinal editor_subparsersizerEntry` rows = editor_parser plus.add_subparsers `directive(
        dest="_completion_candidateseditor_subcommand",`.

---

 help="Editor subcommands"
    )

## 1. Python    helper_bridge-facing AP_parser = editorIs ACE_subparsers.add should call

**_parser(
       Module "helper-bridge:** `sase",
        help_core_rs=argparse.`  
SUPPRESS,
   **Bindings

 )
    helper_:** `/

bridge_subparsers

home/bryan/. = helper_bridgelocal/state/_parser.add_sase/workspacessubparsers(
       /sase- dest="editor_org/sasehelper_bridge_/sase_subcommand",
   14/sase )
    helper_/repos/linkedbridge_subparsers/sase-.add_parser("core/crates/agent-catalog",sase_core

 help=argparse_py/src.SUPPRESS)
/lib.rs`

    helper_bridgeThere are **no_subparsers.add Py_parser("snippetO3 classes**-catalog", help for catalog entries=argparse. or candidates. EverythingSUPPRESS)
    is a plain helper dict (_serdebridge_ JSON). `__subparsers.add_parser("vcs-init__.py` re-exports therepo-catalog", extension help=argparse module wholesale.SUPPRESS)
.

###

    helper_bridge Functions ACE should_subparsers.add call_parser("x

```python
prompt-catalog",directive help=argparse_completion_context.SUPPRESS)
(text:```

Handler str, line::

```9 int, character::19 int) -> dict:/home/bryan | None
directive/.local/state_completion_candidates/sase/(context: dict

, inventories: dictworkspaces/sase

-org/s | None = None

) -> dict
ase/sase

directive_14/src

_contract() ->/sase/

 list[dict]main/editor_

   # optional:handler.py
def inspect the

 handle_editor_ %final contract


command(args:```

Signatures

 argparse.Namespace) inACE

 -> None:
    `%` completion is Py

 a thin Python """Dispatch to theO3:

``` appropriate editor sub-784 adapter over Rust

handler."""
   4. sub = getattr(:

7906

 Names:/args, "editor come

_subcommand", None from `directive

home/bryan/.local/state/_completion_candidates)

    if sub

sase/workspaces` == "helper-/sase- plusbridge":
       org/sase a from sase./sase_ Python hideintegrations.editor_14/sase-helpers import handle_/repos/linkedlist;editor_helper_/sase- livebridge

        syscore/crates/ catalogs (.saseexit(_handlecorebeads_py/src_editor_helper, agents, models/lib.rs
_bridge(args, VCS,/// Classify directive completion))

    print x("Usage: sprompts) are warmed context at a UTF-16 cursor,ase editor {helper off-thread and or `None`.-bridge}", file mapped
#[pyfunction=sys.stderr onto `CompletionCandidate]
#[pyo` rows)
    sys.3(name =.

---exit(1)


## Architecture```

### "directive_completion_context")]
fn py_directive map Editor vs

`_completion_context mobile catalogsPromptTextArea`(
    py:

** (`/Editor-owned Python<'_>,
home/bryan/.    text: & (handled in `editor_helperslocal/state/str,
    line: u32,
sase/workspaces.py` before    character: u/sase- mobile32,
) ->org/sase fallback):**

| PyResult<Py/sase_ OperationObject> { /*14/src/ | Response detectsase/ace builder | Module_directive_context/tui/ |
|---|---|_at_positionwidgets/prompt_---|
| ` */ }

///text_area.pyagent-catalog` Build JSON-shaped`) mixes | `agent_ directive completion candidates forcatalog_response` in `FileCompletionMixin`. a classified context.
 | `_editor_ The completion mixin#[helper_agents.py chain is:

```pyfunction]
#[` (+
File `_pyo3(name = "directiveCompletionMixin
 editor_helper_agent_plans.py →_completion_candidates`) |
| `")]
#[py FileCompletionOpenMixinsnippet-catalog`o3(signature          | `snippet_ # auto- = (context,catalog_response`open menus inventories = None))] | `_editor_
   
fn py_helper_snippets.py → FileCompletionTabdirective_completion_Mixin         # Ctrl` →candidates(
    py `sase.+T
     : Python<'_>,snippet.catalog. → FileCompletionRefresheditor_helper_
    context:entries` |
|Mixin   # key Bound<'_, PyDict `vcs-repo>,
    inventories-catalog` |stroke refresh
       : Option<Bound `vcs_repo<'_, PyDict>>, → FileCompletionAccept_catalog_response
) -> Py` | `sResult<PyObjectMixin
ase.xprompt> {
    //.vcs_repo_completion` deserializes Completion          → FileCompletionBaseMixin  # live directive-arg builder |

**AliContext + DirectiveCompletionased throughInventories
    + warm mobile (registered // calls editorers on_build_directive
            → File editor parser, then_clause_candidatesCompletionArtifactCandidatesMixin forwarded(&
              → File):**

|context, &invent Operation | Response builderCompletionHistoryMixin
ories)
}
```                → FileCompletion | Module |
|

`line`---|---|---|
WorkerMixin   / `character`| `xprompt # off-thread are **UTF--catalog` | inventory16** ( `xprompt_
                  → Filecatalog_response`LSP-style).CompletionContextMixin  | `_mobile_

**Not # classify cursor bound tohelper_catalog.py clause
```

` |

Mobile Python (The prompt-only (and not needednot on the editor bar (` for ACEprompt parser; TUI):**

 unknown_input_bar- `FINALIZER editor.py`) owns_CATALOG_ ops still fall the panelSCHEMA_VERSION`
 through):.- `Finalizer

| On mountCatalogRequest` / Operation | Builder it warms catalogs `FinalizerCatalog |
|---|---| soResponse` as first
| `changes-class functionspec-tags` the first key | `patch_
- atags_response`stroke is standalone |
| `beads memory-only:

 `build-list` /_finalizer_```678:684 `beads-show:/candidates(...)` | `_home/bryan/.`

mobile_helper_ACElocal/state/beads.py` |
 alreadysase/workspaces| `update- owns/sase-start` / ` configuredorg/saseupdate-status` instances,/sase_ | `_mobile_ so it **14/src/helper_updates.pybuilds` |

Thatsase/ace the alias is/tui/ the mixed-version inventory itselfwidgets/prompt_ contract for** and passes itinput_bar.py ` as
        text_xprompt-catalog `inventories["`: onefinalizers"]`. implementation The catalog helperarea._warm_current_xprompt_assist_entries, two CLI exists brands so LSP.

```21()
        text_area._warm can ask:70:/home_current_artifact the/bryan/.local Python host for those_ref_completion/state/s_catalog()
 samease/workspaces/        text_area rows.

Thesase-org._warm_vcs binding/sase/_project_completionsase_14 docstring still says inventories_catalog()
/src/s arease/integrations/        text_area “model, agenteditor_helpers.py._warm_model, and bead rows
def handle_”; final_completion_catalogeditor_helper_()
        textizerbridge(
    args_area._warm: argparse.Namespace_prompt_path,
    *,
_inventory()
    stdin: Text        text_area rows are accepted on the same dict (`finalizers`).IO = sys.

---

##._warm_historystdin,
    stdout 2. Shared_word_completion: TextIO =_cache()
 candidate builder ACE sys.stdout,
 actually        text_area    stderr: Text hits

Rust entry._warm_commonIO = sys. points (re_placeholder_cachestderr,
) ->-exported from `()
```

 int:
    """sase_core`Run an editor-`):

|

completion

branded alias for

 Public_kind` values stable helper bridge operations name | Real used function | Role |
."""
    operation by the panel|---|---|---|: `"directive" = getattr(args, "editor_
| `editor`, `"directive_helper_bridge__detectarg"`, `"subcommand", None)
xprompt"`,_directive_context    if operation ==_at_position `"xprompt_ "agent-catalogarg_*"`,` | `detect":
        try `"vcs_directive_context:
            request =_at_position_project"`, `"vcs_repo _read_request` | Classifier"`, `"vcs(stdin)
            used_ref"`, response = agent_ by the artifact-ref,catalog_response( Python binding |
| historyrequest)
        except `editor_build/prompt (_MobileHelperBridge_directive_clause wordsError, ValueError_candidates` |, placeholders, jin, TypeError) `build_directiveja, files.

 as exc:
           _clause_candidates---

## How print(f" ACE` | Whateditor helper bridge error calls Rust

 Python calls |
: {exc}",All| `editor_ file=stderr)
 three bindingsbuild_directive_ go            return 2completion_candidates` through `require
 | `build__rust_binding        json.dump(directive_completion_` in `/homecandidates` | **response, stdout,/bryan/.local separators=(",",Name-only**/state/s ":"))
        (`%waitase/ stdout.write("\`, `%model`,workspaces/sasen")
        …). `%-org/s returnfinal `0 is
 hiddenase/sase here    # snippet_14/src |

-Whencatalog `context and v/sase/core/rust.pycs-repo-.value_role ==`.

###catalog follow 1. Classify " the same try the clause atfinalizer_instance/dump the cursor

`"` (/return/or `kind`-2 pattern
home/bryan/. is `directive_    mobile_argslocal/state/argument` / ` = argparse.Namespacedirective_argument_sase/workspaces(mobile_helpervalue` on_bridge_subcommand/sase- `%final`), theorg/sase=operation)
   /sase_ return handle_mobile builder goes to `finalizer_value14/src/_helper_bridgesase/ace(
        mobile__candidates`:

```1682/tui/args, stdin=:182widgetsstdin,/_directive stdout_=4:/home/stdout, stderr=completion_tokens.pybryan/.local/stderr
state/sase`

- `classify_directive_completion    )
```

/workspaces/sShared request parsing(line, col lives in `/ase-org/)` findssase/shome/bryan/. the nearestlocal/state/ase_14/ `%` with asase/workspaces valid context (sase//sase-repos/linked/start ofsase-core line,org/sase/sase_/crates/s whitespace, or `ase_core/([14/src/sase/integrations{"src/editor//_mobile_helper'`).completion.rs
fn_common.py`.
- It finalizer_value

### Catalog calls `directive_candidates(
   _completion_context request token: &str(line, /response shapes

,
    inventories:0, utf16**` &DirectiveCompletionInventagent_character(line-catalog`ories,
    replacement[:col]))`.** —: Option<Editor strict `schema_Range>,
)
- ACE mapsversion == 1 -> CompletionList
 UTF-16 replacement`;```

Selector ranges back extra fields ignored (-aware behavior:

 to Python offsets,mixed-version forward| canonical-compat). Envelope Token | Kindizes aliases via | Status is `directive_contract *()`, and rejectsnot* the mobile wait-prose | Notes |
|---|---|---|---| `result` wrapper /
| `commit:

 invalid` | `"```44 colon tokensfinalizer"` |:96:/home.

```30 `"/bryan/.local:45required"` / `"/state/s:/home/bryandefault"` / `"ase/workspaces//.local/stateoptional"` | Prefix/sase/sase-org match,/sase/workspaces/sase-org/s case-insensitive |
sase_14| `!lintase/sase/src/s` | `"finalase/integrations/__14/src/sase/izer_remove"`editor_helper_ | sameagents.py
deface/tui/widgets/_directive policy_completion_tokens status.py
@dataclass( | Requiredfrozen=True, instances are **not slots=True)
** offered forclass DirectiveClauseCompletion remove |
| `:
    """ACEnone` | `"-facing classification offinalizer_clear the directive clause at"` | `"clear the cursor."""

"` | Only if    kind: Directive **no** requiredCompletionKind
    instance exists token: str
 agent_catalog_response(request: dict[str, Any]) -> dict[str, Any]:
    """Return a fresh, de-duplicated catalog and of prompt reference targets."""
    if request.get("schema_version") != 1:
           raise start ValueError: int prefix
    end:("unsupported agent- matches ` int
    directivecatalog schema_versionnone` |

Ordering_name: str")
: required → default | None
       # ... list → optional ( syntax_form:_all_agents str | None
then name),(), then `none` de-dupe    clause_kind last when: str | None by name ... allowed
    active_
    snapshot.

Documentationkeyword: str | = getattr(agents is assembled None
    value, "artifact_ as_role: strsnapshot", None)
 | None
    markdown    if snapshot is:

- host selected_values: not None:
        `documentation` ( tuple[str,add try:
            entries ...]
    selected.extend(_derive__ pathkeywords: tuplegroup_entries()[str, ...] or `
    raw:snapshot, agents)) dictRemove \`[{strvalue,
        except Exception:
            pass }\` from the Any]
```

 # additive launch selection.` (Kinds: `directive; never hide realremove)
_name | agents
    try- `Provider: directive_argument |:
        beads = \`{ directive_argument_ _bead_provider_ref orkeyword | directive_ legacyargument_value`.catalog_entries(request)
    except detail}\``


The- `Depends on ** Exception:
        beadsentire: \`a `payload\` is stored`, \`b\ = []
    return {
        "schema_version": as `clause``
- ` 1,
       .raw`**Retry policy: N "status": "ok",
        attempt and later( "messages)`": "",

 sent back to Rust`selected
        "entries for candidates_values` is": entries,
       . **not** used **({"beads": Tests to hide beads} if beads can already-chosen else {}),
    also instances. Filtering }
```

Mixed

 build a synthetic clause is prefix + remove via/ `synthetic_required-version note in that file: testsdirective_clause(...)`.

###  and + `none`2. Build candidate older callers rows

`/ validity.

`home/bryan/. may still pass a plain `list` from `local/state/%finallist_all_sase/workspaces` is hidden from **name** completion/sase-agents()`org/sase ( (`HIDDEN_COMP/sase_LETION_DIRECTIVESno `artifact_14/src/ = ["snapshot`). That definal"]`). Userssase/acegrades to a still flat agent catalog/tui/widgets/directive_ complete. Group/be valuesad enrichmentcompletion.py`

```390:412 is fail after typing:/home/bryan-open.

** `%final`./.local/state`snippet-catalog

---

##/sase/ 3. Wire`** — currentlyworkspaces/sase records: does *-org/s catalog +not* check `ase/sase inventoriesschema_version`._14/src + candidates

### Uses the/sase/ Schema mobile-ace/tui versions

| Constantstyle envelope/widgets/directive:

```15 | Value_completion.py
 | File |
|:33:/homedef _core_---|---|---|
candidate_rows(
/bryan/.local| `FINAL/state/s    clause: DirectiveIZER_CATALOGClauseCompletion,
   ase/workspaces/_SCHEMA_VERSION *,
    beadsase-org` | `u_inventory: Sequence/sase/32 =[Mapping[strsase_14 1` |, str]] |/src/s `crates None = None,
ase/integrations/_/sase_    excluded_beeditor_helper_core/src/ad_ids:snippets.py
defeditor/wire.rs Sequence[str]` |
| ` = (),
) snippet_catalog_EDITOR_WIRE_ -> list[dictresponse(request:[SCHEMAstr,_ objectVERSION` dict[str,]]:
    inventories Any]) -> | ` dictu: dict[str32 = 2[str, Any]:
    project, object] =` | same {
        "models (generic = optional_string": [],
        editor(request.get(" wire) |
|project"), "project "model_alias_keys": [],")
    catalog `AGENT_CAT
        "agentsALOG_SCHEMA_ = load_snippetVERSION` | `": [],
       _catalog(project "beads": [u32 = )
    entries =dict1(`entry |) analog editor_helper_ catalog for entry in beadentries(catalog)
_inventory or ()    return {
        |
| `FINALIZER_WIRE_],
        " "schema_versionSCHEMA_VERSION`excluded_bead": GATEWAY_ | `u64_ids": listWIRE_SCHEMA_ = 1`(excluded_beVERSION, | **protocolad_ids),  # 1**,
    }
   
        "result not catalog (` payload = require_": helper_resultcrates/saserust_binding("("success", f_core/src"loaded {len/finalizer/directive_completion_(entries)} snippetwire.rs`) |

candidates")(
       (s)"),
###        "context": ` {
FinalizerCatalogRequest clause.raw,
            "project":` /        inventories,
    project,
            " `FinalizerCatalog )
```

Rust currently ranks/filters **beads**.scope": "explicitResponse`

```636 ACE" if project is:688 still not None else " builds:/home/bryanall_known", **models**/.local/state
        },
/sase/ and **agents**        "entries": in Python (`workspaces/sase entries,
        "build-org_/smodel_stats": {"totalase/sasecompletion_catalog`,_count": len `filter_agent_14/s(entries)},
_completion_candidatesase/repos/    }
```

linked/sase`) evenEach-core/crates though empty entry: `trigger `/sase_`, `template`,core/src/models` / ` `source`,agents` listseditor/wire.rs
pub const FINAL are passed through `xprompt_name`, `description.

### 3IZER_CATALOG_SCHEMA_VERSION. Contract`, `source_: u32 = metadata

`directivepath_display`._contract()` supplies

**`vcs 1;

pub struct ` FinalizerCatalog-repo-catalogRequest {
    pubname`, `alias`** schema`,_version: `argument — fail-closed u32,
_hint`, ` on schemadescription`, keywords    pub project: and, syntax forms Option<String>, unknown fields:

```         .418:444 // skip Cached:/home/bryan if as/.local/state None
}

pub `_directive_contract/sase/ struct FinalizerCatalog_by_nameworkspaces/saseResponse {
    pub()`.-org/s schema_version:

---

##ase/sase Hidden `%final` u32,
    pub status: String (must stay until_14/src/sase/,                   // LSP Phase 3)

xprompt/vcs treats onlyRust_repo_completion "ok" as still ** success.pyadvert
isesdef** v


    pub messagecs_repo_ `final` in: String,                 catalog_response( the contract (` // default ""
request: dict[syntax_forms`:    pub entries:str, Any])

 colon + parenthesized Vec<DirectiveFinal -> dict[str; no, object]:
 keywords). ACE andizerEntry>,
}

pub struct Directive    _reject_ the LSPCompletionInventories {
unexpected_fields( catalog **drop    pub models:request, {"namespace it Vec<DirectiveModel", "schema_ from nameEntry>,
    pub model_aliasversion", "workflow menus"})
    schema**.

Python_keys: Vec_version = request<DirectiveModelAlias hide-.get("schema_list (ACE):Key>,
   version", VCS pub agents: Vec

```112_REPO_CAT:132<AgentCompletionEntry:/home/bryanALOG_SCHEMA_>,
    pub/.local/stateVERSION)
    if beads: Vec<

/sase/ schema_version !=BeadCompletionEntryworkspaces V/CSs_aseREPO>,
    pub-org/s_CAT finalALOG_izers: Vec

<DirectiveFinalizerSCHEMAase_VERSION/s:
ase_14/src        raise ValueErrorEntry>,
   /sase/ pub excluded_be("unsupported vcsace/tuiad_ids:-repo-catalog Vec<String>, schema_version")/widgets/directive
}
```

_completion.py

    workflow =JSON request_TARGET _required_string LSP_KIND_ORDER sends = ("tribe",(request.get("workflow"), "workflow "clan", ":

```json
")
    namespacefamily", "agent{ = _required_ "schema_version")
_IDENTITYstring(request.get": 1,_ROLES =("namespace"), " "project": " frozenset({"namespace")
   sclan",ase" "family }
 ...
    return```

JSON", "tribe"}) {
        "schema_version": V response
_HIDDEN_ PythonCOMPLETION_DIRECTCS_REPO_ helperIVES = frozensCATALOG_SCHEMAet({"final"}) must print_VERSION,
       :

```json





def build_ "status": result{
  "schemadirective_completion_.status,
        "_version": candidates(
    tokenerror_kind":1,
  ": str,
) result.error_kindstatus": "ok -> tuple[list,
        "message[",Completion
Candidate ], "": result.message,
 str]:
   message": "",        "provider_ ...
  "entriesdisplay": result.": [
    candidates =provider_display,
 [
        _directive {        "stale_name_candidate "value": "": result.st(row)
       commit", "ale,
        " for row in _provider_ref":entries": [...core_candidate_ "builtin@commit],
    }
rows(clause)
```

**`", "required":        if isinstance(xprompt-catalog true } ]
}
row.get("insertion```

`"), str) and not _is_status != "ok"` →hidden_directive_`** — no schema-version check today; extra fields ignoredname(row)
 LSP logs. Envelope matches `    ]
```

 snippet-catalog (````436:439message` and returns:/home/bryanschema_version`, **empty/.local/state `result`, `** completions/sase/context`, `entries (workspaces/sase`, `stats`,-org/sdoes not fall back `catalog_attachment to stalease/sase`).

---

 non_14/src## 2.-ok rows)./sase/ Helperace/tui How to add a new helper-bridge failure/widgets/directive operation

Follow with_completion.py
 the existing catalogdef _is_ a **,hidden_directive_cached ok not a new CLIname(row:** catalog style.

### dict[str, can A object]) -> bool still be. Editor-only:
    insertion = used catalog (like str(row.get.

### ` `snippet("insertion") orDirectiveFinalizerEntry-catalog` /` (catalog ** "")
    name `agent-catalogand** inventory row = str(row.get("name"))

Mixed`)

1. **Parser** — or insertion.rem-version safe add a suppressed: unknownoveprefix subparser in `("%"))
    fields ignored;parser_editor.py return name in _ missing extras`:
   ```HIDDEN_COMPLETION default.

|python
   helper_DIRECTIVES
 JSON_bridge_sub```

LSP field | Typeparsers.add_parser / | Default / CLI catalog (` serde("</home/bryannew-op>", | Meaning help=argparse/.local/state |
|---|---|/sase/.SUPPRESS)
---|---|
|workspaces/sase   ```
2 `value` |-org/s. string | ** requiredResponse |ase/sase module Instance ID /_14/src selector token |
|** — prefer/sase/ ` `display` |src/sasecompletion/candidates/ string | `/integrations/_editor""` | Unused_helper_<name bycatalog_build.py`):

```21:>.py` with the candidate21:/home/ `def <bryan/.local/ builder (insertionname>_response( usesstate/saserequest: dict[ `value`) |
/workspaces/s| `detail`str, Any])ase-org/ -> dict[str | string | `sase/s, Any]`.""` | Legacyase_14/ provider display;
3. **src/sase usedWire** — reuse/completion/candidates if `_mobile/catalog_build `provider_ref_helper_common.py
_HIDDEN` empty |
|`:_SURFACE_DIRECTIVES: frozens `documentation` | string | `""et[str]
   - `read_request`
 =` frozens |et Markdown body   - `GATEWAY for add candidates({"final"})
_WIRE_SCHEMA```

Parity tests |
| `provider_VERSION`_ref` | (`tests (or a dedicated string | skip/ iftest_x empty | Preferred `prompt_directive_ provider (`builtin@*_SCHEMA_VERSIONcompletion_parity.py = 1`)commit`)`) use the same |
| `required fro
   - `` | bool |zenset sooptional_string` skip if false | ACE/ / `required_LSP name rows match Rankstring` / ` the contract ** 0;reject_unexpected_minus** `final cannot be `fields``.

Docs (`!removeddocs/xprompt /`; `helper_result.md` § Directive

 blocks`
4 Completion Matrix):

 `none` |


. **Handler branch

| `default`- `%final`** in is ** | bool | skip `handleaccepted** if false | Rank_editor_helper as 1 (`_bridge` * `%final:...`is_default`before* the mobile in Rust) / `%final(...)` fallback. |
| `after when typed.
- Same` | `[ Hidden from the ordinary try/except,string]` | skip `% compact if empty | Dependency` name menu because dump list in finalizer selection is docs |
| `, exit ` owned by the launchmax_attempts`2` on finalization gate.
 ` | `u32- Argument rows: \|MobileHelperBridgeError `none`; selector | ValueError | null` | skip operations remain typable TypeError`.
 if null; **keywords5. **Tests | Retry policy in are not offered**. docs |
| `** — new `

`tests/test_provenance_id`build_directive_editor_helper_<clause_candidates` | `string \|name>. null` | skip does **not**py`:
   if null | Passed hide - parser accepts the `% through; argv notfinal` once
   - handler classified used in ranking |

 as an argument clause roundMap from. Typed protocol `-trip via ` `%final:`handle_editor_FinalizerInstanceSpec stillhelper_bridge(Wire` when goes through `_ ACEcore_candidate_Namespace(...), stdin=StringIO(... builds inventoryrows` and can)) offer `:

| Protocol |`
   - badnone`. request: Do Catalog entry |
 exit **|---|---|
 `2`, empty| `notinstance_** remove stdout, stderr `_id` | ` starts with `editorvalue` |
|HIDDEN_COMPLETION helper bridge error:`_DIRECTIVES` `provider_ref
6. **` | `provider / `_HIDDEN__ref` |
SURFACE_DIRECTIVESDocs** — `docs|/editor `.mdafter`` until | `after`` Phase 3 name |
| `policy (Helper Bridge), advertising.max_attempts` `docs/integrations is | `max_ explicitly.md` (Editorattempts` |
| in Helper Bridge), `

 `provenance_iddocs/configuration.md scope.

There

` | `provenance` (`sase is currently

_id editor`` |
 table). **no dedicated

| plan `required unit

### B

` / `defaults. Shared editor test** asserting `"

` lists | `%final" not+mobile catalogrequired` / ` (like `x in insertions

prompt-catalog`)` from

default` |

### Completion

1. Register `build_directive

_completion_candidates candidate JSON the op on **both**

("%")` ACE `parser_editor receives or `"%f.py` and `"`. Coverage

`CompletionList

parser_mobile.py is only via parity

`:

```json`.
2. vs


{
  " Implement `.

candidates": [*_response` under the hide /* CompletionCandidate */ `_mobile_helper-list. ],
  "_ That is*.py`.shared_extension": the cheapest
3. Dispatch "" regression in `handle
}
```

 to add if_mobile_helper`CompletionCandidate`_bridge`. you
 touch fields (` this path4. Do **crates.

---

##not** special/sase_ Candidate builders-case itcore/src/ → ACE records

 in `editor_editor/wire.rsShared rowhelpers.py`; the`):

| Field alias type (` | Final/ is automaticizer usagehome/bryan/..
5. Tests |
|---|---|local/state/: mobilesase/workspaces via
| `display` | insertion/sase- `tests textorg/sase/_mobile_helper (`commit`, `/sase__bridge_helpers14/src/.py!lint`, `none`) |
|sase/ace::run_bridge `insertion` |/tui/`; editor via ` same |
| `widgets/file_handle_editor_name` | samecompletion.py`):

helper_bridge` |
| `detail```63:71 (see` | provider string:/home/bryan `test_editor/.local/state,_helper_bridge or omitted/sase/_aliases_x ifworkspaces/saseprompt_catalog`).-org/s
 empty (`none` has noase/sase6. Add detail the op to the_14/src smoke list/sase/) |
| ` in `tests/documentation` | assembledace/tuitest_mobile_ markdown,/widgets/filehelper_bridge_ omitted_completion.py
smoke.py`.

 if empty |
|@dataclass(slots=### C `kindTrue)
class Completion. Mobile` | `"finalCandidate:
    """-izer"`only mutatingSingle candidate rendered by op / `"finalizer the shared prompt completion ( panel."""

   _remove"` /like `update- display: str
start`)

Use `"finalizer_    insertion: str `reject_unexpectedclear"` |
|
    is__fields` ( `status` |dir: bool
fail-closed injection `"required"` /    name: str guard `"default"` /
    metadata:), `" Any |optional"` None / = map domain None
```

 `"clear"` |
 sentinels to`is_dir| `replacement exit `4`,=True` means keep` | `{ " “keep completing `range": Editorhelper_result` after acceptRange, "new envelope” (keyword `foo.

---

##_text": insertion=`, model }` for 3. Schema provider version, the **active clause `claude/`). fail-closed envelopes only** |
|, compact JSON



### Name `is rows### Compact_dir` |

 JSON ( `false` |
`build_directiverequired| `additional_completion_candidates)

Success_edits`(token)` → always | `[]` `_:

```python
 |
| `projectdirective_name_json.dump(responsecandidate(` | `"", stdout, separatorsrow)`:

` |

###=(",", ":- `insertion `%"))
stdout.write` /final` contract (` `display` from("\n")directive_contract()`
return Rust (`%model)

From 0
````) `DIRECT
- `name

No indentIVES` in `, no spaces` withoutcrates/sase `%`
- ` after `:`/_core/src`,`. Helpermetadata =/editor/directive DirectiveCompletionMetadata(/.rsaliases`:

,``` argument_agent testsjson
{
 hint, description)` typically from ` "json.name":loads " contract + row(final",
  `documentation`

###stdout.getvalue()) "alias": null Argument rows —`;,
  "description dispatcher compact": "Select configured

``` encoding finalizer instances for140:199 is the:/home/bryan this launch",
 wire  "argument_/.local/state contract (/sase/seehint": ":instance `docs/editorworkspaces/sase|!instance|.md` “none or (instance-org/sone compact JSON objectase/sase, ...)",
” and `docs_14/src  "takes_/integrations.md`/sase/argument": true,
 “compact  "allows_ace/tui JSON object”). Clos/widgets/directivemultiple": true,
est explicit_completion.py
  "syntax_ compact-jsondef build_directiveforms": ["colon test is `tests_clause_candidates", "parenthesized/test_mobile(
    clause:_agent_bridge DirectiveClauseCompletion,
"],
  "_handler.py::    *,
   positional_role":test_bridge_ agent_candidates: "finalizer_ Sequence[AgentCompletioninstance",
 handler_writes_Candidate] | Nonecompact_json`. "positional_suggestions = None,
   

### Fail-": [
 bead_inventory:    { "value Sequence[Mapping[closed error envelope (": "none",str, str]]helper/editor "documentation": " | None = None)

Clear the configured final,
    beads_On validationizer selection for thisstate: BeadsState/ launch" }
  = "unavailable",domain
    excluded_ ],
  " failure:

bead_idskeywords": [],
- **stdout: Sequence[str:**] = (),
  "dynamic_keyword_role": empty (tests    path_candidates null
}
``` assert `stdout.: PathCandidateBuildergetvalue() == "" | None = None

Classifier,
) -> tuple` and `[list[Completion `data == {}value_role`Candidate], str]:`)
- ** enum (
```

|stderr:** prosesnake_case): Clause, `" | Builderfinalizer_instance not JSON  
 | Metadata |
|"`.

Context  - editor:---|---|---|
 kinds ACE `editor helper bridge| `is_ will error: { see forname` | nameexc}`  
  builder - values mobile: ` +: `"mobile helper bridge errordirective_argument"` hide-list |: {exc}` `DirectiveCompletionMetadata
- **exit` |
| ` ( value_role ==just2:** " invalid after `% JSON,path_ wrongor_final:` / `%executable types"` |final(`) or

 `, unknown op, `"directive_argumentpath_candidates`_value" bad schema, unexpected fields (filesystem`.

---

  
- **exit) | file## 4. 4:** not Helper-bridge catalog rows (Python **-found / already |
| `%-running (`Mobileimplementsmodel` values**,HelperNotFoundError / LSP`, `MobileUpdate alias **Already keys | PythonRunning`, `Mobile modelcalls**)

NonUpdateJobNotFound catalog | `Model-Python front`)

`ends doCompletionMetadata` |
read_request`: not load| `value_

```32:role == "be Python42:/home/ inventoriesad"` | Rustbryan/.local/. They spawn rows + inventorystate/sase:

```text/ join
<helper | `Beadworkspaces/sase> editor helper-CompletionMetadata` or-org/sbridge finalizer- `DirectiveCatalogPlaceholderase/catalog
```

` |
| `sase_14stdinclan/src/s: onease/integrations/_ JSON `mobile_helper_` / `family`FinalizerCatalogRequestcommon.py
def` + newline  
 / `tribe`stdout: JSON read_request( values `FinalizerCatalogstdin: TextIO | `buildResponse`

Default helper) -> dict[ binary_agent_argstr, Any]::_completion_candidates
    raw = `sase` stdin.read()
(..., (`CommandHelperHost    if not raw required_kind=Bridge::.strip():
       ...)` | `default_command()`).

AgentCompletionCandidate` return {}
    try:
        payloadThis |
| wait positional = json.loads is the same / `(raw)
    patternagent except json.JSON` |DecodeError as exc as `agent-catalog`,:
        raise Mobile keywords from `snippet-catalog Rust (`*=HelperBridgeError(`, ``) **f"invalid JSONvcs-repo- request: {excplus** agentcatalog`.

Files snapshot.msg}") from | mix:

- `/ exc
    ifhome/bryan/. not isinstance(payload |
| otherlocal/state/, dict):
 static values        raise MobileHelpersase/workspaces /BridgeError("request/sase- keywords | `_ JSON must be anstatic_or_org/sase object")
   /sase_keyword_candidate` return payload
```14/sase | `DirectiveArg

EmptyCompletionMetadata` |
/repos/linked stdin is `| parent/sase-{}`hesized `%clan`core (then/crates/ / `%id`sase_core schema positional | keyword checks fail for/src/host fallback (`_bridge.rs` opstribe — `HelperHost that require version=`, `beBridge::finalizer 1).

ad=`, …_catalog`, `**) | keywordContrast:** `invoke metadatas_editor("final |

Livease mobile notification-izer-catalog", wiringbridge` dumps …)`
- from a **JSON** error object to stderr the text `/home/bryan (`{" area (`_build/.local/state

code","target","_live_directive/sase/message"}`)_arg_candidatesworkspaces/sase with compact separators.`-org/s Helper in `_file_ase/sase-_14/sbridge does **notcompletion_base.py`):

- Ifase/repos/**. `clause_needslinked/sase Do not copy the_bead_-core/crates notification envelope ontoinventory(clause)` editor/sase_ → `_ensure_ helperxprompt_lspwait_bead ops/src/catalog_inventory()` (_cache.rs`off-thread)..

### Schema-version — independent policy (in TTLconsistent today — cache
-, If `Final `clause_needs_agent_snapshot pick the matchingizerCatalogRequest {(clause)` → catalog schema_version: `)

| Operation 1, projectapp | Request }`
- `/.visible_agent_ `home/bryan/.completion_candidates()`schema_version`local/state/ (memory-only | Extra fields |sase/workspaces Agents-tab snapshot Response/sase-; envelope family plan |
|---|---|org/sase previews may---|---|
|/sase_ ` beagent scheduled-catalog,14/sase` | ** not scanned/repos/linkedmust on the key be `/sase-core/crates/1`** |stroke).
- Path args **sase_x use `build_prompt_lsp/ignored** (mixed-version;src/server.rscompletion_candidates(..., `` — `finalunknown_future_ base_dir=_prompt_completion_base_dir())izer_directive`.field

` is OK`_completion` copiesclause_needs_ `response.entries) | `{beschemaad_version_,inventory` into `invent` status, is true for `ories.finalizers message, entries,`,value_role == beads?}` |
 "bead"`| `vcs- then `editor_repo-catalog`build_directive_clause_candidates`

 **or** parenthesized `%wait` | **must be / `%id`. `1`**ACE (defaulted

Be Tad inventory row if omittedUI should **not) | **rejected shape expected** go** | by ACE `{schema_version + through this subprocess, status, error. It should pass_kind, message inventories Rust:

```python
{", ...id", directly}` |
| ` "title", ",update-start`

status", "type like_label", "/` beadsupdate-status`created/ | not_at", "agents rangeupdated_at",.

---

##-

checked | ** "task_type 5. Howrejected** | `{", "project"} existing Python bindings
```

Proschema_version, already do this (duced by `raw result,be_wait_be job}`ad/`ad_inventory` |
| `snippet%wait`) in `/home/-catalog` /

The

bryan/.local/ `xprompt-state/sasecatalog` / tags

/workspaces/s in-crate / beads | **ase-org/ Pythonnot checked** | test is the intendedsase/s ignoredase_14/ ACE pattern:

``` | `{src/sase16973/ace/t:170schema14_version, result, context,ui/models/:/home/bryan ...}` |
wait_bead/.local/state_catalog.py`.| notification-bridge/sase/

Historical | **rangeworkspaces/sase**-org/s tests still `1 <= v callase/sase <= CURRENT_14/s `build_directive` | Nase/repos/_arg_completion/A | JSONlinked/sase_candidates(directive error on stderr |

-core/crates_name, partial`GATEWAY_WIRE, .../sase__SCHEMA_VERSION)` incore_py/ = 1` `src/lib.rstests/ace/ in `_mobile_
lettui/widgetshelper_common.py context =`.  
/_directive_completion py_directive__helpers.py`,`VCS_completion_context( which synthesizes aREPO_CATALOGpy, "%wait clause then_SCHEMA_VERSION calls `build_(bead=", = 1` 0, directive_clause_ in `vcs_candidates`.

---11).repo_completion.py

## Establishedunwrap();
let worker / result pattern`.

Mobile inventories = json!({ `

The
    "beadsresult` helper canonical": [{
       :

 inventory "id": "```102:109 workersase-a:/home/bryan lives in `/",
        "/.local/statehome/bryan/.title": "Active/sase/local/state/ bug",
       workspaces/sasesase/workspaces "status": "-org/s/sase-in_progress",ase/saseorg/sase
        "updated_14/src/sase__at": "14/src//sase/2026-08integrations/_mobile_sase/ace-20T12/tui/:00:00helper_common.py
def helper_widgets/_file_Z"
    }],completion_workers.py
    "agents`.

result(status: str, message: str) -> dict": [{"name": "worker", "Pattern:

1. **[str, objectkind": "agent]:
    returnFrozen result dataclass**"}]
});
 carrying {
        "statuslet candidates = py identity_directive_completion": status, + payload         _candidates( (` # success | partialpy, context,changed_success | failed inventories`
);
//        "message flag candidates["candidates"]": message,
       [0][" "warnings": [], when a snapshot is reused).insertion"] == "
        "skipped
2. **sase-a": [],
       In"
```flight

This set** "partial_failure repo has ** keyed by directory_count": Noneno Python /,
    }
``` application project / `(

** codeworkflow, namespace)`.Additive
3. ** vs fail-closed** (ACE lives in `sase

`run_worker:**

`). There is also(task, name agent **-catalog groupno Python derivation test and bead rows yet=..., group=..., thread=True)`** — never swallow** that passes I exceptions so `final ordinary/O on theizers:` agent keystroke path (` —t rowsui_ stillperf only Rust return`. ` unit tests and rule anvcs-repo-).
4. LSP integration test.

catalog` and update **`on_ ops reject###worker_state_ Example ACEchanged`**: unknown request should copy keys so mixed
   - SUCCESS for- / ERROR / CANCEL `%final`

version clients cannot smLED clears```python
fromuggle extra control sase_core fields_rs import (
.

If inflight.
   - SUCCESS applies result    directive_completion you add a new only if the **_context editoropen menu,
    directive_ catalog, copy still matches**completion_candidates,
 ** that)

def completeagent key/-catalog** if_final(kind.
   - extratext: str, Other fields must stay line: int, groups ign character: int, `orable,super()` instances: or **vcs-- list[dict])repo-catalog**chain ( -> dict:
    if theartifact-ref highlight context = directive_ request is a closed, etccompletion_context( allowlist.

.text, line, do---

##  character)
    if4. Finalizer the same).
 context is None:
5. **UI configuration layer

###        return {" Files

| placeholderscandidates": [], "** while File coldshared_extension": | Purpose (`Directive ""}
    inventories |
|---|---|CatalogPlaceholder`, = {
        "
| `src V/sase/finalizers": [
CS loadingfinalizers/config            {
                " row.py` | Layervalue": row, `@[" merge,instance provenance` loading, `_id"],          metadata # requiredFinalizerConfig`).

Wait
                "display |
| `src/sase/-bead worker": row.getfinalizers/selection (closest("display", row analog for a.py` | `% futurefinal["`instance_ →id `"]),
                " `%FinalizerSelectorOpfinal` inventory):Wire` |
|provider_ref": `src/s row.get("provider

```68ase/finalizers:75_ref", ""),/plan.py`:/home/bryan
                "required/. |local `/resolvestate_": row.get("and_persist_/sase/required", False),finalizer_planworkspaces/sase
                "default

`;-org/s": row.get(" fatal diagnostics failase/sase-closed |
|_14/srcdefault", False),  # JSON name `src/s/sase/ase/finalizers isace/tui "default",/providers.py`/widgets/_file | Builtin not "is__completion_workersdefault"
                " + plugin providers.py
@dataclassafter": row.get; `Command(frozen=True("after", []),FinalizerConfig`)
class _Wait
                "max |
| `src_attempts": row/sase/BeadInventoryWorkerResult:
    """.get("max_finalizers/cliattempts"),
               Result returned by a.py` | ` prompt wait-be "documentation": rowsase final listad inventory worker.""".get("documentation",/show/doctor

    project_` |
| ` ""),
                "key: str
src/saseprovenance_id":    rows: tuple/core/final row.get("provenance[dict[strizer_wire.py_id"),
, str], ...]` | Wire               
    available: dataclasses, # optional legacy bool
```

 `FINALIZER_: "detail"WIRE_SCHEMA_Schedule: ifVERSION = 1 coalesce on provider_ref is `project_key` |
| ` unknownsrc/sase`,
            }
/core/final load            for row inizer_facade via `raw_ instances
        ]
.py` | Rustwait_bead    }
    return bindings (`resolve__inventory`finalizer_plan directive_completion_ (mtime`, digests,candidates(context, cache inventories)
```

), degradeCall sites to:

``` `availablepython
complete=False` on_final("%final exception:", 0,.

Apply: store `_wait_be 7, instances validation) |
| `src/sase/default_config.yml` | Bundled defaults |
| `src/sase/)
ad_main/parser_# insertionsinventory` / `_final.py` |wait_bead: required `, then_available` /sase final` default, then optional `_wait_be CLI |

ad_,project`; then maybeThere is **no refresh "none"

complete only if `__final("%final** helper-bridge operationcompletion: for finalizers today_kind == "!", 0,.

### Types (`

directive_arg"` 8, instancesconfig and project still.py`)

```)
# insertions: matches.

State machine27:97 "!lint", "! used:/home/bryanzoom" ( by the/.local/state/sase/ builder (`_required omitted)

complete_finalwait_beadworkspaces/sase("%final(commit-org/s_inventory_state, !l",`):

- Appase/sase hook `wait__14/src/sase/bead_inventory 0, 17, instances)
# replacement.finalizers/config()`range covers.py
@dataclass( (tests inject only "!frozen=True)
 a warm tuplel",class FinalizerConfig).
- Else insertionDiagnostic:
    severity cached rows "!: str          for currentlint"
```

 # "If ACEerror" is fatal `_wait_bead also
    code: implements_ the helperproject for_key str
    message()`.
- Else: str
    LSP, stdout `"loading"` if of layer: str
 a project exists    path: str, `"

@dataclass(frozenunavailable"` if not=True)
class `sase editor helper-bridge finalizer.

Placeholder rows:

 FinalizerFieldProven-catalog` should```527ance:
    layer:537 be the same `: str
   entries` list:/home/bryan path: str |/.local/state wrapped None

@dataclass(/sase/ asfrozen=True)
workspaces/sase:

class ConfiguredFinal-org/s```pythonizerInstance:
   ase/sase instance_id:_14/src
{
    "/sase/schema_version": str
    provider 1,ace/tui_ref: str       # FINAL/widgets/directive # from `use_completion.py
IZER_CATALOGdef _catalog_`
    after:_SCHEMA_VERSIONplaceholder(
    kind tuple[str,
    "status: Literal["loading ...] = ()
": "ok",", "unavailable"],    max_attempts
    "message
    message:: int = ": "",
    str,
) ->1  CompletionCandidate:
    "entries": inventories # retry bound return CompletionCandidate(
["finalizers"],
    refusal:        display=message
}
```

 str = "fail,
        insertion="",---" 
        is_ # only "fail

## 6dir=False,
" is accepted
. CHANGE        name="",
LOG / public API    config: Mapping        metadata=Directive[str, Any statusCatalogPlaceholder(kind] = field(

**=kind, messagedefault_factory=`sase_=message),
dict)
    provenancecore` Un: Mapping[str    )
```

released** (`Accept, FinalizerFieldcrates/saseProvenance] = /_core/CHANGE field(default_ Ctrl+T skipLOG.md`):

 placeholders viafactory=dict)

- *(editor)* `is_directive@dataclass(frozen=True)
class Final_catalog_placeholder add a versioned finalizer-catalogizerConfig:
   `.

Other inventories helper contract and selector defaults: tuple[ following-aware `%finalstr, ...]
 the same shape    required: tuple` candidates
-:

| Catalog[str, ...] *(lsp)* cache | War
    instances: final

izer catalogs independentlymer | Mapping[str, and convert values through Result a dedicated LSP path / ConfiguredFinalizerInstance]
    provenance

**`s cache | Group: Mapping[strase_core` |
|---|---|, FinalizerField 0.29---|---|
|.7 Prompt:** pathsProvenance]
    diagnostics: tuple[FinalizerConfigDiagnostic hide ` (`@` files, ...] = ()) | `_final` from name
schedule_prompt_ completions.

```

Entry**`sasepath_inventory_ pointload` | `_core_: `load_PromptPathSnapshot`finalizer_configpy` 0 in `_prompt_()` replays `.29.6path_snapshots`load_config_:** binds | `prompt-layers()` and last `directive_contract-writerpath-inventory`` / `directive-wins per |
| Commits (`@commit field.

### Instance_completion_context` / `directive IDs

:`) | `__completion_candidatesschedule_prompt_Regex`.: `^[acommit_inventory_ Unload` | `-z][released pya-z0PromptCommitSnapshot` changelog does-9_-]* (TTL 2 **not** add$` (`s, a new_INSTANCE_RE Rust `artifact_`). Invalidref_payload_ Iinventory`) | `Ds emitprompt-commit- `invalid_instanceinventory` |
| finalizer-catalog function; Phase_id` and 1 completion rides VCS repos are skipped.

### those | `_schedule_ YAML existing bindings shapevcs_repo_.completion_fetch` ( The | `bundled default)

```119 `VcsRepoFetch*(finalizer)*Result`;0:1198 add shared finalizer loading:/home/bryan protocol` line/.local/state placeholder is the **plan/sase/ while/validate**workspaces/sase infl API-org/sight | `prompt, not `%ase/sase-vcs-repofinal` completion.

_14/src` |
| V**/sase/CS `+``PYdefault_config.yml projects | `_PI_README.md
finalizers:
warm_vcs_  defaults: [`**project_completion_commit]
  required documents onlycatalog` | the three directive: []
  module-level cache instances:
    commit functions, in `sase:
      use: not catalog schema.xprompt. versionvcs_project_ builtin@commit
      after: [].

**Rustcompletion` | `
      max_ public exportsprompt-vcs-attempts: 2** (`
      refusal:cratesproject-catalog` |
| `%model fail
```

/sase_

` catalog | `_Allowedcore/src/ top-level keyslib.rs`): `warm_model_completion_catalog`: `defaults`,DirectiveFinalizerEntry | `build_`, `Finalizermodel_completion_ `required`, `instances`.  
AllowedCatalogRequest`, `catalog` instance keys: ` onceFinalizerCatalogResponseuse`, `after`, `Directive

 | `prompt-`, `max_CompletionInventories`,model-catalog`attempts`, `refusal `FINALIZER_ |
| Artifact `@`, `config`.CATALOG_SCHEMA` kinds/

###_VERSION`,payloads | `_ Field pluswarm_current_ semantics

| `editor_build Fieldartifact_ |ref Meaning_ |
_directive_clausecompletion_catalog`|---|---|
 | per_candidates`.

| `defaults

-project catalog---

## ` | Ordered selection7. LSP dict when the- | prompt omonly presentation `_its `%final`ARTIFACT (_ACEREF_ |
| `required canWORKER_GROUP`` | Cannot ignore)

 |
| X be cleared`finalprompts / snippets by `%final:izer_completion_ | `appnone` or `%response` in `.warm_promptfinal:!name`crates/sase_catalog_project |
| `instances_xprompt_` | `.<id>.uselsp/src/PromptCatalogSnapshot`` | Provider reflsp_convert.rs (:` maps:

| kindx `builtin@commit / status | LSPprompt assist`, ` `CompletionItembuiltinKind@command **`, or `package` |and** snippet@id` (` label templates details) | app@` required unless-owned |
|---|---| builtin) |
|---|
| required |
 `after add| History words |` | Dependency | `ENUM_ `app.warm edges (otherMEMBER` | `_history_prompt · required` + instance IDs) |
| `_words` | app provider |
| optionalmax_attempts` cache | app/default add |

 | Integer ≥ `VALUE` |- 1; defaultowned |
| Place ` · default`  / ` · optionalholders | `app1 if` |
| `.warm_common omitted,finalizer_remove_placeholders` | 2 for` | `OPERATOR app cache | app bundled` | `remove-owned |
| commit |
| ` · { Agentsrefusal` | Mustprovider}` |
| | ** be `"fail"` `finalizer_not a; anything worker**clear` | ` else is a typeKEYWORD` | ` | `Ace error and coerced to `"failApp.visible_agentclear`;"` |
| `_completion_candidates sort group `config` | Provider1` so-specific mapping()` from visible Agents-tab rows it sorts after instances |

ACE should use | UI (for `builtin@command-thread snapshot ` |

Snippets are`: `command`,kind` + `cwd`, ` **not** a `status` +timeout`, `submission `detail` from`, `env`) the JSON `%` completion catalog. They live |
 in the same off candidate,| `provenance`-thread `Prompt not LSP kinds | Per.

---

##CatalogSnapshot` (`-field `{ 8. Whatsrc/saselayer, path}` Phase/ace/t from the 1 asksui/prompt_ winning config layer; ofcatalog.py`, instance `use` `src becomes/sase/ Python ACE/host

 `provenance_id1. **Tace/tuiUI completion:**` on the wire/actions/_startup |

### classify with_prompt_catalog Fail-closed config `directive_completion

.py`) used_context`, pass for `# `inventDiagnostics` x withories={"finalizers":[prompt assist, `severity == then expand "error"` areDirective fatal. viaFinalizer `SnippetEntry...ExpansionMixin`. `resolve]}` Do_and_persist into `directive__finalizer_ not inventcompletion_candidates`.plan` raises ` a snippet
2. **Helper workerFinalizerPlanError` if `config for inside.fatal_diagnostics LSP:** implement ` directivesase editor helper()` is non- completion.

Agentsempty. Notable-bridge finalizer: codes:

- ` `build-catalog` with schema `_agent_completionplugin_config_1`, `status_candidates` inactivation` — plugin layers `/home cannot/bryan set/.local/state/sase/ defaults/required/instances: "ok"`, same `entries`.
3workspaces/sase.
 **Do not-org/s** invent- `not_ase/sase a new Pya_mapping`O3 catalog / `unknown__14/src type/sase/key` / `; dictinvalidace/tui/_agent_completions already_instance_id` deserialize / `missing_candidates.py`. Cached_.
provider4.` ** per open / `invalid_Do not** confuseprovider menu on_ref`
 this `_agent_completion with `final- `invalid__candidates`.

value` forizer_wire_---

## Completion wrongschema_version()` row rendering

Pipeline types

Plugin packages:

1. ` may advertise providers viaPromptInputBar.show entry_file_completions-(...)` (` / `validate_finalizer_instance_spec` — those are launchpoint group `s protocol_prompt_input_bar_completion,ase_finalizers_panel`,.py`) useful
2. ` when but a **CompletionPaneltrustedKinds**. config layer *building must* declare the the inventory instanceclassify(kind from. Prompt, rows)` (` configured_ text instancesprompt,_input not when_bar_completion can only select (` rendering_panel_kinds%final:lint.py`)
3 candidates`, `%final:!.

Key. `build_lint`, `%final files:

completion_panel_:none`).

-content(...) `/` (``home/bryan/._prompt_inputto_planlocal/state/_bar_completion_input`_panel_contentsase/workspaces projects/.py`)sase —- intoorg `/s▸`ase Rust / `/ s `,ase_:

 group14/sase``` rulespython/repos/linked
Final, `/sase-izerPlanInputWire↓ N more…core/crates/(
    schema_`
4. Domainsase_core `version=FINALIZER/src/editorappend_*_row_WIRE_SCHEMA/wire.rs`
` in `_prompt_VERSION,
   - `/home/_input_bar instances=[... Finalbryan/.local/_izerInstancecompletion_SpecrowsWire_*.pystate`
/sase .../workspaces/s5. Title/],
    defaultssubtitle in `_promptase-org/=list(self_input_barsase/s.defaults),
ase_14/   _ required=completionlist_panel_labels.py`

sase/repos(self.required/linked/sDirective-),
    selectorsase-core/name=selectors,
)
crates/sase row```

`Command_core/src:FinalizerConfig` magenta name/ +editor dim/completion (.rs`
 `argument_hinttrusted- `/home/`, `builtin@commandbryan/.local/ `alias %`x`, description.

state/sase configDirective,/workspaces/s

 not the YAMLase-org/-arg row dispatcher

 (`append instance itselfsase/s):_

directive```71_argase_14/_completion_row:78sase/repos`):

- Agent/linked/s:/home/bryan metadata → `append/.local/statease-core/_agent_completion/sase/crates/sase_row` (workspaces/sase_core/src-●org/s/editor/directivease/sase status, name.rs`
- `/_14/src, VCS badge/sase/home/bryan/., snippet; groupfinalizers/providerslocal/state/ kinds.py
@dataclasssase/workspaces F(frozen=True/C/@/sase-)
class CommandFinal)
- `org/saseizerConfig:
   ModelCompletionMetadata`/sase_ command: tuple[ → four-column14/sasestr, ...]
 grid (   /repos cwd/linked: strname / kind //sase- target / state = "primary"
    timeout_coreseconds/crates/: float = sase_core)
- `DirectiveCatalogPlaceholder` →_py/src120.0
 dim message/lib.rs`

- `Be    submission: str- `/home/adCompletion =Metadata` "none"
 → statusbryan/.local/    env: tuple glyphstate +/ id[ +sasestr, ...] title/workspaces/s + `ase-org/ = ()
```

---

##status · type`
 5. Testssase/s- else magenta to copy

###ase_14/ insertion Editor helper- + dim descriptionbridges

ase|/repos File/linked

/sTitles | What to copy:

- `"ase-core/directives"` / |
|---|---|crates/sase `"directive
| `/home_core/src values"` / `"/bryan/.local%/state/s/host_bridge.rs`
- `/model values"` /ase/workspaces/ `"homemodel/bryan aliases"`/.sase-org / `"beadslocal/state//sase/"` / `"waitsase/workspacessase_14 targets"` / `"/sase-fork targets"` //tests/testorg/sase `"_editor_helper/sase_projects & PRs_xprompt_14/sase"` / `"xcatalog.py` |/repos/linkedprompts"` / Parser accept …

PNG/sase- + editor snapshotscore/crates/ ** alias ofsase_x ado not type intoprompt_lsp/ mobile op + monkey the grammarsrc/server.rs

patch of catalog**. They mount

`
- `/home a ` builder |
| `/

/bryan/.localPrompthomeInput/Barbryan`/.

/state/s and inject rowslocal/state/

ase/workspaces/:

sase/workspacessase-org/sase-

```python
bar

.show_file_/sase/org/sase

completions(token,sase_14/sase_ rows, selected_

14/tests//sase/

index=..., completionrepos/linked/test_editor__kind="directive

helper_vcssase-core

/crates/s_arg")
_repo_catalog```

Then

ase_xprompt.py` | Parser `wait_for

_lsp/src + success_svg_contains

/catalog_cache round-trip +` + `ace

.rs`
 **bad_png_visual- `/home/ request:.assert_page_bryan/.local/png(...)`.

state/sase---

## Tests exit 2, empty stdout** |
/workspaces/s| `/home/ to extend

ase###-org/bryan/.local/ Unit / widgetstate/sasesase/s (must-ase_14//workspaces/stouchase-org/s forase/repos/linked/ssase/s `%` /ase-core/ase_14/ `%cratesfinal/`)sase

tests/test_|editor__xhelperprompt__ File | Why |
lsp/src/snippet_catalog.py|---|---|
lsp_convert.rs` | Full| `/` catalog merge/home/bryan/.overridelocal/state/

/sase/workspacescompose/sase-org via/sase real/sase_14/tests/ handler |
| `/ace/tuihome/bryan/./widgets/testlocal/state/_directive_completionsase/workspaces_candidates.py`/sase- | Name menuorg/sase vocabulary/sase_, aliases, descriptions14/tests/;test_editor_ **add `%helper_agent_final` hiddencatalog.py` |** Fresh |
| `/home/bryan/.local listing/state/s, monitorase/workspaces/ kindsase-org, snapshot/sase/ groupssase_14, group/tests/ace-derivation failure/tui/ |
| `/homewidgets/test_/bryan/.localdirective_arg_/state/scompletion.py` |ase/workspaces/ Fixed values, keywordssase-org, beads/ loadingsase/sase_14/warm, model rows/tests/test;_editor_helper_agent_catalog **_beads.py`add `%final:none`** | Bounded beads + **unknown |
| `/home/bryan extra/.local/state field/ stills succeeds**ase/workspaces/ (mixed-version) |
| `/sase-org/sase/home/bryan/.sase_14local/state//tests/acesase/workspaces/tui//sase-widgets/_directive_org/sasecompletion_helpers.py/sase_` | Shared `14/tests/build_directive_test_editor_arg_completion_helper_family_candidates` / syntheticcatalog.py` | clauses |
| `/ Additivehome/bryan/. planlocal//state/bead enrichment, degrade onsase/workspaces failure/ |
s|ase `/-org/sasehome/bryan/./sase_local/state/14/tests/sase/workspacestest_xprompt/sase-_directive_completionorg/sase_parity.py`/sase_ | ACE ↔14/tests/ LSP ↔test_xprompt contract; `_HIDDEN_vcs_repo_SURFACE_DIRECT_completion.py` | Direct `vcsIVES`; **_repo_catalogadd `%final:` to_response` the argument schema/required parametrize if-field tests |

 PhaseCanonical 3 args handler change-** |
| `/test skeleton:

```home/bryan/.python
fromlocal/state/ sase.integrationssase/workspaces.editor_helpers/sase- import handle_editororg/sase_helper_bridge/sase_
from sase14/tests.main.parser/ace/t import create_parserui/widgets/

def test_parser_acceptstest_directive__editor_helpercompletion_interactions.py` | Ctrl+_bridge_<op>()T / Ctrl+ -> None:
   L on `%` args = create_ |
| `/home/bryan/.localparser().parse_args(["editor",/state/sase/workspaces/ "helper-bridgesase-org", "<op>"])
    assert/sase/sase_14 args.editor_helper_bridge_/tests/acesubcommand == "<op/tui/>"

def testwidgets/test_directive_value__editor_helper_bridge_<completion_interactions.pyop>_` | Colonround_trip(...)/paren value menus -> None:
    |
| `/home stdout,/bryan/.local stderr = io./state/sStringIO(), ioase/workspaces/.StringIO()sase-org
    code =/sase/ handle_editor_sase_14helper_bridge(
/tests/ace        argparse.Namespace/tui/(editor_helperwidgets/test__bridge_subcommand="<op>"),wait_directive_completion_interactions.py
        stdin=` | Worker-io.StringIO(json.dumpsstyle warm({"schema_version inventory injection": 1, (`app.wait_bead_inventory ...})),
`) |
| `/        stdout=stdouthome/bryan/.,
        stderr=local/state/stderr,
    )
sase/workspaces    assert code ==/sase- 0
   org/sase assert stderr.getvalue/sase_() == ""
14/tests    data = json/ace/t.loads(stdoutui/widgets/test_model_.getvalue())
completion_rows.py    assert data["` | Rich gridschema_version"] without == 1
 PNG```

Agent |
| `/home-/bryan/.localcatalog tests use/state/s an autouse fixturease/workspaces/ that stubs `getsase-org_known_project/sase/_workspaces` sosase_14/src/s they do not hitase/completion/ livecandidates/catalog_ bead stores.

###build.py` tests Mobile helper-bridge ( (shared opsif present)

 under| File | Pattern ` |
|---|---|tests/`) |
| ` LSP hide-list |

tests/_mobile_### Worker / inventoryhelper_bridge_ analogshelpers.py` |

| `run_bridge File | Pattern(payload, operation |
|---|---|)` |

| `/home/|bryan `/.localtests//state/stest_mobile_ase/workspaces/helpers.py` |sase-org xprompt-catalog/sase/ projectionsase_14 + type rejection/tests/ace/tui/ (`include_pdfwidgets/test_` must be boolprompt_commit_) |
| `inventory.py` |tests/test_ Workermobile_helper_ result applyupdates.py` |, unexpected TTL, infl fieldsight |
| `/home/ failbryan/.local/-closed (`state/sasecommand`, `workspace/workspaces/s` → exit ase-org/2,sase/sase_14/ worker not started) |
tests/ace/tui/models| `tests//test_waittest_mobile__bead_helper_beadscatalog.py` |.py` | beads mtime cache, `raw-list/show_wait_be |
| `testsad_inventory`/test_mobile |
_helper_bridge| `/home/_smoke.py`bryan/.local/ | allstate/sase mobile/workspaces/sase-org/ ops returnsase/s `schema_versionase_14/ == 1`tests/ace/ |
| `teststui/widgets/test_mobile/test_artifact_ref_completion_gateway.py`_catalog.py` | parser accepts | Warm each catalog + rows mobile helper |

### PNG visual-bridge op |
 (| `tests/extend if newtest_mobile_ row chromeagent_bridge_)

handler.py` |All compact JSON + malformed under `/home/ JSON →bryan/.local/ exit 2 |

state/sase### Final/workspaces/saseizer-org/s config

| Filease/sase | Pattern |
|_14/tests---|---|
|/ace/t `tests/testui/visual/_finalizers_`, goldens infoundation.py` | `snapshots `/png/`.

| File |load_finalizer Golden prefix_config` via |
|---|---| stub
| `testbed `ConfigLayer_ace_png`s; plugin_snapshots_model layer_completion.py` | `prompt_ rejected; `%model_completion_*final:` |
| `none`;test_ace_png_snapshots_ default commitprompt_target_completion.py` | plan |
| ` `prompt_waittests/test__target_completionfinalizers_extension_runtime.py`_*`, `prompt_fork_target | `_config`_completion_*` / `_instance` |
| `test helpers building_ace_png_snapshots_at `FinalizerConfig

_reference_completion` + `Configured

.py` | `@FinalizerInstance`` kinds |
| `tests/files/test_final |
| `testizers_protocol__ace_png_snapshots_vcsharness.py` | same_{project,repo, in-memory config constructionref}_completion.py` | `+ |
| `tests` / repo/test_final / ref |
|izers_live_e2e.py `test_ace_png_snapshots` | monkey_{history_word,promptpatch_ `loadword_,finalplaceholder}_completion.py`izer_config` | word/placeholder on plan/controller chrome/executor/config |

There is ** |

Inno** PNG-memory config factory for used the everywhere generic:

```python
 `"Finaldirectives"` nameizerConfig(
    menu today defaults=. Adefaults,
    required `%=required,
   final` Phase instances=-instances,
    provenance3 name={},
)
Configured rowFinalizerInstance(
,    instance_id or a richer=instance `%final` value_id,
    grid provider_ref=, would followprovider_ref,
 `test_ace_    after=afterpng_snapshots_,
    config=

model_completion.py

config or {},
`:    provenance={"use

 fake

": FinalizerField `Provenance("testCompletionCandidate`s", None)},
 + `show_

)
```

---file_completions(...,



## 6 completion_kind="

directive"|". Practicaldirective_arg") notes`.

Parser

 if-

 thisonly `%

final` tests (` is for

 a new catalog optests/test_



1directives_extract.py`, `tests/. Keep thetest_finalizers_*. oppy`) do ** **not** coverhidden** (`arg ACE completion.

---parse.SUPPRESS

## Practical`) notes and **fixed for a** ( `%final` inventoryJSON

If Phase stdin/ 3 addsstdout only).
 instance names2. Inject (` `stdin`/`lint`, `commitstdout`/`stderr`, …) as` on dynamic rows the handler, copy wait; never-beads `, not modelssubprocess:

1` yourself. Keep `_ in tests.
3. Monkeypatch theHIDDEN_COMPLETION_DIRECTIVES = **fac {"final"}` until nameade** module advertising (`s is inase.integrations. scope.
2.mobile Worker_helpers.build_: frozenstructured_xprompts result + inflight +_catalog`, `sase.integrations.editor_helpers.vcs_repo_catalog_ `thread=True` + refresh only whenresponse`) because ` `directivemobile_helpers.__arg` andsync_mobile_ the clause is stillhelper_dependency_ `%final`.
overrides()` rebinds3. While names cold, for legacy test emit `DirectiveCatalogPlaceholder targets("loading", ....
4. Success)` so Ctrl:+T cannot compact JSON + trailing auto-insert an newline + empty insertion exit 0..
4. Pass Failure: empty inventory through stdout + `_ `core_candidate_editor helper bridge errorrows` inventories dict:` (today: + exit 2 `models`,.
5. If `model the_alias_keys op`, `agents`, `beads`, ` is aexcluded_bead catalog_ids`) — for **Rust mixed-version LSP wire/ would need a new keyeditor clients, ****;ignore unknown request fields do** like not stuff final agent-catalog. Ifizer instances it into `beads is a control/`.
5. Newmutating metadata type + branch op in `, **reject unexpectedappend_directive_ fields** like `arg_completion_update-start` / `vcs-row` + `CompletionPanelKindsrepo-catalog`.` +
6. Update panel ` title,docs/editor.md matching`, `docs/ beadsintegrations.md`, and/models the.
6. Par `sase editority test` table in `:docs/configuration.md ACE vs`.
7. Finalizer inspection LSP vs for `directive humans_contract()`; keep `_ is already `sHIDDEN_SURFACE_ase final list/DIRECTIVES` inshow/doctor` lock (`srcstep.

Until that/sase/ wirefinalizers/cli exists.py`, `FINAL, typed `%final:`IZER_CLI_ already completesJSON_SCHEMA_ static suggestionsVERSION = 1 from Rust`, (`none` per indented the matrix) JSON). A helper with-bridge catalog no Python would be a new inventory., compact, stdin/stdout sibling

 — not a reuse

 of that CLI printer.

I have a clear picture of the Phase 1 contract and ACE patterns. Next I’ll add the catalog builder, helper-bridge, and ACE inventory/renderer.

Next I’ll wire finalizer inventory through the ACE completion builder and keep `%final` hidden in name completion.

Colon-form `!` was rejected by the argument-character check, and `%final` in CLI help was parsed as a format specifier. I’ll fix both.

Symvision ignores test-only uses of public names, so I’ll make the catalog types private and drop the cache-clear helper.

Phase **sase-s0.2** is closed. Host catalog and ACE `%final` argument completion are in place; the `%final` **name** stays hidden until the surface-parity phase.

**What landed**
- Side-effect-free catalog builder next to finalizer config: required → remaining defaults → optional, each group alphabetical, cached per config token, no provider loading.
- `sase editor helper-bridge finalizer-catalog`: schema version 1, compact JSON, extras ignored, malformed config returns `status=error` with empty rows.
- ACE prompt inventory: off-thread worker, warmed on pane mount, coalesced loads, stale-result guard, loading/unavailable placeholders. Typing never does config I/O.
- Shared Rust candidates mapped into `FinalizerCompletionMetadata`, used by auto-open, Tab, Enter, and Ctrl+L.
- Aligned ACE rows: selector, policy (`required` / `default` / `optional` / `remove` / `clear`), provider. Removal uses strikethrough plus a “remove” label; `none` is labeled “clear”.
- Colon-form `!` is a valid `%final` argument character, so `%final:!lint` completes.

**Verified**
- Targeted catalog, helper-bridge, ACE, and row tests passed.
- PNG goldens: `prompt_finalizer_completion_mixed_120x40.png` and `prompt_finalizer_completion_mixed_70x24.png` (`just test-visual`).
- fmt, ruff, mypy, and Symvision passed. No leftover `--epic-symbol` entries on this phase.

**Follow-ups recorded on the bead** (for the land agent)
- Live flag bead `sase-ro` still names retired `pluggable_finalizers`, so `just check` flag lint fails repo-wide.
- Contract manifest is 54 entries vs a 53-entry budget (`tests/test_xprompt_workflow_schema.py`), already on HEAD.
- `test_skills_inventory_reports_retired_deletion_drift` failed once in a full-suite run, then passed on rerun.
