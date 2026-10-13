# Chat History - ace-run (7h)

- **TIMESTAMP:** 2026-10-13 18:17:52 EDT
- **MODEL:** claude/opus
- **AGENT:** 7h

## Prompt

#gh:gh_sase-org__sase How exactly will agent CLI providers receive these instruction bundle files? In
other words, how will these instructions be loaded into context? See the
e3_delivery_cutover_readiness_and_bundle_inspection.md file in the research sidecar repo
for context before performing your own research. Make sure your report is concise and
easy to understand. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete. %m:@xlarge

## Response

Reading the E3 report now; next I'll check the epics plan and the provider adapter code to pin down per-provider delivery channels.

Checked the current adapters (Claude, Codex, Grok, Muse). Next: agy, the native-load observers, and the earlier delivery-design report, to confirm the planned per-provider channels.

Gathering the last design detail (the root/helper two-slot table) from the earlier subagent report, then I'll check what the live CLIs and a real bundle look like.

Probing done: Codex placement confirmed offline. Now looking at a real sase-project bundle's sections to describe what each provider would actually receive.

Verification is done (all four live channels checked against the installed CLIs). Writing the report now.

The report is written. Registering it as a durable artifact.

Registration succeeded. Now the final declaration.

No provider will look for or open a bundle file by itself. For each provider call, SASE builds one bundle and the adapter passes its text through a flag, config value, home file or prompt prefix that CLI already accepts. It also switches off the CLI's own loading of SASE's full instruction files, so the instructions arrive exactly once. The E3 plan hasn't been written yet, so the table below is the agreed E3 design, checked against today's CLIs. It is not shipped behavior.

| Provider | How the bundle gets in | Where it ends up in context | How native SASE files are switched off |
|---|---|---|---|
| **Claude** | `--append-system-prompt-file <artifacts>/instructions/NN-claude.md` | System prompt. Today these instructions arrive as a user message. | `claudeMdExcludes` in the per-run `--settings`; auto-memory off |
| **Codex** | The root-only part (final-declaration contract and single-turn directive) goes in `-c developer_instructions`. Everything else goes in a private `$CODEX_HOME/AGENTS.md`. | The first developer message, plus a user message headed `# AGENTS.md instructions` | `-c project_doc_max_bytes=0` |
| **Grok** | `--rules` with the full bundle | End of the system prompt, inside `<human_rules>` | Workspace stays untrusted |
| **Muse** | Bundle prepended to the prompt file | The first user message (Muse has no system-prompt flag) | Drop `--trust-workspace`, but only if a pre-implementation probe shows Muse works without it; otherwise Muse stays legacy until E4 |
| **agy and others** | Unchanged in E3: they keep loading the native files | — | — |

- **Helpers:** Claude's subagents get their own helper bundle through `--append-subagent-system-prompt-file`, and the guard stopping helpers from running `sase final` stays. Codex children inherit the root's instructions. Grok, Muse and agy have no channel for helpers.
- **Failures:** if building or passing the bundle fails, that one call goes back to the old files and SASE notifies you. An agent never starts with no instructions.
- **Today:** no agent receives the bundle yet. This session is an example: my own 19,629-byte bundle is marked shadow-only. My context actually received `~/CLAUDE.md` and the workspace `CLAUDE.md` as two user-message blocks, each with its own final-declaration section. That's the duplicate contract the scoreboard (`sase instructions verify`) reports.

I confirmed Claude, Codex and Grok directly on the installed CLIs (Claude 2.1.296, Codex 0.162.1, Grok 1.0.52); none of these checks made a paid API call. Muse and agy are based on the adapter code and `--help` output; I didn't run them. Three things this adds to the E3 report:

- **Codex's 32 KiB limit doesn't apply to the home file.** A 45 KB `$CODEX_HOME/AGENTS.md` loaded in full. E3's planned "fail over 32 KiB" check is a budget rule SASE sets, not protection against Codex cutting the file off.
- **A resumed Claude conversation keeps its first bundle.** Claude now records the system prompt by default and resends it unchanged on resume. So switching off a provider's E3 kill-switch flag only affects new conversations.
- **Only Claude reads the bundle file itself.** The other providers get the text directly, so for them `NN-<provider>.md` is just a record.

The report is at `sase/repos/research/202610/instruction_bundle_provider_delivery.md`. It's registered as `research:202610/instruction_bundle_provider_delivery.md` (artifact `explicit:62c9b334e9d62476a1ff4d94`), and the research repo commit has been declared for the host to make.
