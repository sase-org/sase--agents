# Chat History - ace-run (chop.refresh_docs.sase.0_289632.2)

- **TIMESTAMP:** 2026-09-14 04:28:35 EDT
- **MODEL:** claude/opus
- **AGENT:** chop.refresh_docs.sase.0_289632.2

## Prompt

#gh:sase-org/sase
%id(chop.refresh_docs.sase.0_289632.2, tribe=chop)
%wait:chop.refresh_docs.sase.0_289632.1
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

The update agent's changes were mostly correct, but two claims about family waits were too narrow. I fixed the wording and clarified all four passages. The strict docs build (`mkdocs build --strict`) and the Markdown formatter both pass. The host accepted the commit declaration, so it will commit the four doc files.

**What checked out**
- **ACE header capacity:** the `C/L` total counts only the machine running ACE. A test confirms a remote row with capacity 100 still leaves the local total at 1.0.
- **Remote rows:** they carry `cN`/`wN` badges and `Capacity:`/`Weight:` detail lines from the machine that owns them. A legacy zero capacity shows as `c0` with `Capacity: legacy 0 (exact-weight drain budget)`.
- **`capacity=0`:** new prompts reject it. I ran the validator: "must be at least 1; use %q:1 to run alone". The flag that controls this is on by default.
- **Family waits:** a failed monitor or gate shell with no follow-up stops blocking the family once a newer shell of the same kind exists. A gate never excuses a monitor or vice versa, and waiting on the exact shell name still reports that shell's own outcome.

**What I corrected**
- **`docs/xprompt.md`:** it said "one" retry can supersede a failure. The code skips every older failed shell of that kind. It also described only failed starts, but any unsuccessful end without a follow-up counts. The text now also says the newer shell must itself succeed.
- **`docs/agent_families.md`:** it now defines "family generation" (the newest root plus its attached members) and walks through an example (`--mon` fails, `--mon-0` takes over). It also says the newer shell doesn't settle the family until it succeeds or hands off.
- **`docs/ace.md`:**
  - The header paragraph used "controller", which that file doesn't define until about 1,000 lines later. It now says "the machine running this ACE session".
  - In the Queued paragraph, the new remote and legacy sentences had split the badge explanation in two. I moved them after it and quoted the exact detail-pane labels.
- **`docs/remote_dispatch.md`:** it now names the actual `Capacity:`/`Weight:` lines and says remote load never adds to the header's `C/L` total.

**Failing check:** `just check` fails its symvision lint step on code that was already on master. Twenty private functions and classes are imported from other files after two earlier refactor commits: `620d872547` split the `disk_footprint_*` module and `4cd297ada2` split the `commit_repair_*` helpers. It needs a separate code fix; I didn't touch it. The ten lint steps before it passed, and the scoped tests never ran because the command stopped there. I noted this in the commit message too.

I found no code bugs in the behavior these docs describe.
