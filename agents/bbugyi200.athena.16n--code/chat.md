# Chat History - ace-run (16n--code)

- **TIMESTAMP:** 2026-10-31 12:45:45 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 16n--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202610/glossary_preview_authored_links.md

The above plan has been reviewed and approved. Implement it now.

Reviewer decisions for this plan (final · reviewer via ACE):
- see_also_order = links_first (planner default: links_first). Implement the "see_also_order = links_first" branch; ignore "see_also_order = position". Context: "Should authored [[links]] take the first SEE ALSO chips, ahead of phrase mentions?".
- foreign_links = skip (planner default: skip). Implement the "foreign_links = skip" branch; ignore "foreign_links = list". Context: "Should the card also list links that leave the glossary (e.g. [[decisions/x]]) or do not resolve?".
Implement only the branches selected above.


## Response

I'll start by opening the plans sidecar repo via the `sase_repo` skill.

Let me read the relevant source files.

Reading is done and I'm about to start implementing. I'll begin with the `unique` flag in `links.py`, then add the link builder in `closure.py`.

Now the `closure.py` builder:

Now the catalog field and its load-time computation:

Closure already skips self-spans and dedupes, matching the plan. Now the render helpers:

Now tests. First `unique=False` in the links tests:

Memory-link and builder tests pass (20). I'm fixing a Pyright warning, then adding the catalog, render and modal tests and the docs edit.

That "changed on disk" notice was my own `_catalog` → `_` edit. Now the docs edit (sentences only, no new section):

Now the catalog tests (including the fail-soft path):

Now the render-helper tests:

Now the modal test (pressing `1` follows a link-only chip):

All new tests pass. Before running lint/check, the project requires reading the `lint_and_test` memory note.

I'll run `just fix` first, as the note advises, then the real-glossary sanity check.

Now a real-data sanity check against this repo's glossary (the plan's `receipt` example):

The count is 2863 against a cap of 2861, so I need a baseline. I'll stash my changes and run the same test on the clean tree.

Several closed beads cover this same test, though at much larger module counts. I'll read the most recent one, check whether it's a retired umbrella, and look at the rest of the week's list.

The cap is 2861 and clean master measures 2863, so it's +2 over. Let me attribute the growth since the commit that last set the cap, which is useful evidence for the +1.

That used the wrong interpreter (pyenv 3.11, no `sase` installed). Retrying with the workspace venv:

Recorded. Before finalizing, a last review of the source diff after formatting:

The diff looks right. Per the host-owned-completion rule I don't commit, so the last step is the `sase_final` declaration.

The glossary preview card now honors authored `[[target]]` and `![[target]]` links. `sase tool run check` passed everything except one test that also fails on clean master (details below).

On the real glossary, `Receipt` now shows four SEE ALSO chips (Tool Catalog, Tool Run, Triage Verdict, Sase Monitor). Before the change it showed none. No entry among the 20 with links has the old `[[glossary:[proc](...)]]` corruption.

I implemented the two reviewer choices: authored links take the first SEE ALSO chips ahead of phrase mentions (`links_first`), and links that leave the glossary or don't resolve are not listed (`foreign_links = skip`).

**What changed**
- **`links.py`:** `scan_memory_links` takes a keyword-only `unique=False` to return every occurrence. The default is unchanged.
- **`closure.py`:** new `GlossaryDefinitionLink` and `glossary_definition_links` map each link to a glossary entry and its UTF-8 byte span. Foreign targets, unknown targets and bare `name.md` targets get no entry. Strands with `link_reference: none` are skipped.
- **`glossary_catalog.py`:** `EditorGlossaryCatalog` gets `definition_links` as its last field. It is resolved once at load, falls back to empty on any error, and is left out of `to_wire()`.
- **`glossary_preview_render.py`:**
  - Mention matches that overlap a link are dropped, which fixes the corrupted text.
  - Resolved links render as `[Term](glossary:N)`, labelled with the target's term.
  - A link back to the entry itself renders as plain text.
  - Link targets go first in SEE ALSO, then mention-only terms, still capped at nine.
  - The modal needed no change.
- **Docs:** I edited sentences in the Glossary terms section of `prompt-completion-panels.md` and added no new section.

**Tests:** I added tests for the `unique` flag, the link builder, the catalog (including the fail-soft path), the render helpers, and the modal (pressing `1` follows a chip that exists only because of an authored link). `just fix` ran clean. I did not run the visual PNG goldens; the plan says none of them contain `[[`.

**Pre-existing failure:** `tests/ace/tui/test_app_import_budget.py` fails with 2863 `sase.*` modules against a cap of 2861. It fails the same way on a clean tree, and my change adds no modules. The growth comes from recent file splits. It is already tracked by `sase-1ic`, so I added a +1 with the attribution instead of filing a new bead.

The final declaration is accepted, so the host commits the ten changed files after this turn.
