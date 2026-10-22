# Chat History - ace-run (chop.refresh_docs.sase.6_022403.2)

- **TIMESTAMP:** 2026-10-08 03:54:50 EDT
- **MODEL:** grok/grok-4.7
- **AGENT:** chop.refresh_docs.sase.6_022403.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.6_022403.2, tribe=chop)
%wait:chop.refresh_docs.sase.6_022403.1
%queue(capacity=1)
Inspect the documentation changes made by the update agent for sase.

Verify every changed description against the current system behavior rather than
assuming it is true. Improve clarity for a new user, especially where terminology or
workflow ordering could be misunderstood. You may only create, modify, or delete
documentation files, such as Markdown or other docs-tree content, READMEs, and
doc-adjacent assets. You MUST NOT create, modify, or delete source code, tests, build
configuration, or any other non-documentation file, even to fix a bug you are
confident about.

When documentation and code disagree, document the actual current behavior; never
change the code to match the prose. If you identify a suspected code bug, describe it
in your final response so a human or separately scoped agent can pick it up (and you
may also note it in the commit message body), but do not fix it. Run the repository's
documentation checks when you change files.

## Response

I'll inspect the update agent's documentation changes and check each claim against the current system, then edit only docs where the prose is wrong or unclear.

The tree is clean. The docs refresh is in `688c909b28`; I'll compare that prose with the code that landed after it.

The update agent's docs still disagree with the code in a few places. I'll read those sections and correct only the documentation so it matches current behavior.

Several descriptions disagree with the code. I'll correct those docs so they match what the commands and finalizer actually do.

The refreshed guides now describe the current commands, waits, and commit path. Source and tests were left unchanged.

`just docs-check` built the site in strict mode. Markdown formatting and the generated-docs check passed, and the documentation terminology tests passed. `sase tool run check` exited 1 with verdict `no_new_failures`: 49 known Symvision findings, one known terminology string-literal failure, and a linked `sase-core` checkout that is ahead of the published compatibility window. None of those come from these documentation edits.

**Suspected code bugs, not fixed**

- `sase plan validate --json` is not JSON-only when Plan Decisions are on and the plan has decisions. Outside an agent, stdout prints `quote verification runs at propose` before the JSON. After the JSON, it prints the Decision Sheet. When `%auto` is active, it also prints `auto-approved: every decision takes its default`. A machine parser cannot treat that stdout as one JSON document. Plans without decisions stay JSON-only.
- The plan-editor refusal (`decision-frozen`) tells the reviewer to change answers in a Decisions panel. The Plan Review modal does not render that panel, and `decision_<id>` fields do not appear as inputs. Overrides go through `sase gate answer --set decision_<id>=...`.

**What the docs now say**

- Plan validation, the CLI reference, and the Plan Review pages describe that JSON contamination and the missing modal controls.
- Instruction shadow render still exports `SASE_INSTRUCTIONS_FILE` for the provider call. Current providers do not read it, so argv, prompts, and the files they already load stay the same. `sase instructions verify` defaults to the newest 20 runs per provider from the last 7 days, exits 0 on delivery problems, and exits 2 on a bad `--since` or `--until`.
- With `strict_macro_input_types` off, an unknown macro input type falls back to the single-line `line` type.
- A new launch that never received a classifying stamp is stored as `generated`. A blank or unrecognized surface is `unknown`.
- Decision ids reject a closed reserved list (`approve`, `commit`, `reject`, `feedback`, `coder_prompt`, `coder_model`, `wait`, `epic_launch_mode`, `capacity`) and the YAML 1.1 words `y`, `n`, `yes`, `no`, `on`, `off`, `true`, `false`, and `null`. Choice keys reject those YAML words too.
- A repair that defers the primary repository skips the revision-pin write, records `revision_pin_skipped`, and still lands the sibling commit.
- A plan-launched agent that commits an uncovered memory note still gets the commit. The finalizer records a `memory_change_uncovered` warning. Agents not launched from a plan are not checked.
- The getting-started edit path names the Artifacts **Stitch** pane (`◉`, key `2`) for the diff, the Agents-tab commit list, the default `create_commit` push, and the `#propose` reset-and-clean. `sase bead update --status=in_progress` sets status and leaves the assignee unchanged. Epic-follow stages name their real fields, and `has_wait` stays false when only those follow fields are set.
