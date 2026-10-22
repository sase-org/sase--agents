# Chat History - ace-run (research.3m.gem)

- **TIMESTAMP:** 2026-10-05 06:47:12 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3m.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_063855.md`

## Prompt

%id(gem, clan=research.3m)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3m.cdx`, `research.3m.cld`, `research.3m.grk`, `research.3m.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm thinking about
giving sase macro invocations (`#foo`, for example) a distinct name so it is easier to
talk about / reference them and their unique syntax.

- I think that "sase macro invocation" (aka "smack"--note that "invocation" has the
  sound "kay" in it) is a good name.
- We should add a new glossary memory web strand for this term.
- This opens up new ways of talking about this topic and related topics I think. For
  example, we could start referring to the "raw prompt" as the "smack prompt".

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report: Macro Invocation Naming, "Smack" Critique, and Recommendations

**Author:** Researcher `gem` (5-Researcher Swarm)  
**Report File:** [`macro_invocation_naming_and_smack_critique__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/macro_invocation_naming_and_smack_critique__gem.md)  
**Artifact Snapshot:** `research:202610/macro_invocation_naming_and_smack_critique__gem.md` (Ref: `file:explicit:01c77554ae5284d4723c1654`)

---

## 1. Executive Verdict & Core Takeaways

1. **The core motivation is sound:** Giving the call-site syntax (`#foo`, `#!foo`, `#foo(args)`) a distinct, standardized name addresses a genuine ambiguity in SASE. Currently, the word "macro" conflates the template file (`sase/macros/foo.md` or `.yml`), the preprocessing subsystem, and the syntactic token in the prompt.
2. **Reject the term "smack":** While phonetically punchy, "smack" has fatal flaws:
   - **Severe negative connotations:** Worldwide street slang for heroin, as well as connotations of violence ("give someone a smack") and hostility ("talking smack"). SASE's vocabulary is consistently grounded in craft, carpentry, woodworking, tailoring, and community (`stitch`, `bead`, `axe`, `chop`, `deck`, `card`, `tribe`, `hood`), not illicit substances or assault.
   - **Forced orthography:** The acronym S-M-A-C-K relies on a strained phonetic excuse (*"invocation has the sound 'kay' in it"*), requiring repeated justification.
   - **Degraded LLM / Agent reasoning:** Frontier LLMs natively understand standard computer science terminology (`macro reference`, `macro call`, `macro invocation`). Inventing idiosyncratic slang wastes token budget in core memory shims and increases the risk of agent hallucination or syntax confusion.
3. **Reject "smack prompt" (Architectural Category Error):**
   - Prompts frequently contain zero macros (e.g., `+sase %m:sonnet review the diff`). Labeling the prompt container by an optional inner syntactic element is a faulty part-for-whole synecdoche.
   - SASE recently completed a major migration from `xprompt` to `macro` (epic `sase-1eq`), explicitly replacing `raw_xprompt.md` with `raw_prompt.md`. Introducing "smack prompt" would recreate the exact confusion that was just resolved.
4. **Recommended Canonical Term:**
   - Adopt **`Macro Reference`** (colloquially abbreviated as **`macro ref`**) as the canonical primary term.
   - Accept **`Macro Invocation`** and **`Macro Call`** as official, formal synonyms.
   - Add the glossary strand `sase/memory/glossary/macro-reference.md`.
   - Preserve `raw_prompt` and `submitted_prompt` without alteration.

---

## 2. Scorecard: Evaluating Naming Candidates

| Evaluation Criterion | `Macro Reference` (`macro ref`) | `Macro Invocation` (`macro call`) | `Smack` (`sase macro invocation`) | `Mref` / `Minv` |
| :--- | :---: | :---: | :---: | :---: |
| **Self-Describing (Zero-Training)** | **High (5/5)** | **High (5/5)** | **Very Low (1/5)** | **Moderate (3/5)** |
| **Taxonomic Symmetry** | **High (5/5)** (Pairs with `Artifact Ref` & `Workspace Ref`) | **Moderate (3/5)** | **Very Low (1/5)** | **Moderate (3/5)** |
| **Codebase Alignment** | **High (5/5)** (Matches AST class `MacroReference`) | **Moderate (3/5)** (Matches style key `"invocation"`) | **None (0/5)** | **Low (2/5)** |
| **Professionalism & Tone** | **High (5/5)** | **High (5/5)** | **Negative (0/5)** (Heroin / violence slang) | **High (5/5)** |
| **Prompt Independence** | **High (5/5)** | **High (5/5)** | **Very Low (1/5)** (Encourages "smack prompt") | **High (5/5)** |
| **Colloquial Punch** | **High (4/5)** (2 syllables) | **Moderate (3/5)** (3 syllables) | **High (5/5)** (1 syllable) | **High (4/5)** (1-2 syllables) |

---

## 3. Recommended Adjustments to the Plan

1. **Establish `Macro Reference` as the Canonical Term:**
   - SASE's prompt syntax already defines:
     - `@ref` / `@file:...` → **Artifact Reference** (`ref`)
     - `#git:...` / `#gh:...` → **Workspace Reference** (`workspace ref`)
     - `%auto` / `%wait` → **Directive**
     - `+sase` → **Project Tag**
     - `#name` / `#!name` → **Macro Reference** (`macro ref`)
   - This creates complete taxonomic symmetry across the entire SASE prompt language.
2. **Retain Prompt Boundaries:**
   - Keep `raw_prompt` as the unexpanded user input and `submitted_prompt` as the preprocessed model input.
   - Never refer to the prompt as a "smack prompt".
3. **Glossary Strand Implementation:**
   - Add `sase/memory/glossary/macro-reference.md`:
     ```markdown
     ---
     keyword: Macro Reference
     aliases:
       - macro ref
       - macro invocation
       - macro call
     ---

     A macro reference (macro ref, or macro invocation) is an inline `#<name>` or
     standalone `#!<name>` token in an agent prompt that SASE expands before the agent runs.
     It can supply arguments using paren syntax (`#name(arg1, key=val)`), colon shorthand
     (`#name: arg`), double-colon shorthand (`#name:: text`), or plus syntax (`#name+`), and
     can carry HITL suffix overrides (`!!` or `??`).

     A macro reference is distinct from a [[glossary:macro]] definition (the source `.md` or
     `.yml` file) and from macro expansion (the resolution process). It is also distinct from
     a [[glossary:project-tag]] (`+project`), a workspace reference (`#git:<ref>`,
     `#gh:<ref>`), and an [[glossary:artifact-reference]] (`@kind:arg`).
     ```
   - Update `sase/memory/glossary/macro.md` to link to `[[glossary:macro-reference]]`.

---

## 4. Verification & Artifact Registration

- **Research Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/macro_invocation_naming_and_smack_critique__gem.md`
- **Registration Command Executed:**
  ```bash
  sase artifact create \
    -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/macro_invocation_naming_and_smack_critique__gem.md" \
    -l "research:202610/macro_invocation_naming_and_smack_critique__gem.md"
  ```
- **Registration Status:** Verified exact (`id: explicit:01c77554ae5284d4723c1654`, `ref: file:explicit:01c77554ae5284d4723c1654`).
- **SASE Finalizer Declaration:** Submitted and accepted for dirty repository `repo-736e4b0000d3` (`sdd:research`).
