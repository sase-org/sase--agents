# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 13:02:33 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** sase-5g.w1.f1

## Prompt

#gh:gh_sase-org__sase #fork:sase-5g.w1 Ok. Can you now help me create a new docs/ markdown file that contains this user guide? %m:claude/claude-fable-5

## Response

I'll turn the research doc into a proper user guide under `docs/`. First let me re-read the research file and check the existing docs conventions.

A `docs/agent_families.md` user guide already exists and is wired into the mkdocs nav. Let me check its history to understand when and how it was created before deciding what to do.

**The user guide already exists — there's nothing for me to create.** While looking at `docs/` before writing anything, I found `docs/agent_families.md`, authored earlier today by a `refresh_docs` agent family (commit `2b4d8e9ae`, 10:57 AM, evidently working from the research doc we produced) and then corrected in a dedicated verification pass (`9a784e2ca`, 11:16 AM). It's already wired into the mkdocs nav as "Agent Families".

The existing guide covers the full scope we researched: the family concept and suffix→role table, extending a family by hand with `%n(parent, suffix)` (delegating the detailed grammar/error reference to `docs/xprompt.md`, where v1 was already documented), the `kind: agent_family` YAML schema with discovery rules and both flagship examples, member selection at the plan gate (TUI toggles, `--with`/`--without`, the `default_members` sticky config, remote/auto behavior, loop caps), custom-role display labels, the whole `LaunchApproval` / `sase launch` flow, and an "Under the Hood" section on the evaluator and compatibility invariants. The same refresh also filled every companion-doc gap my research flagged: `docs/cli.md` now lists the `sase launch request/approve/reject` group and the `sase plan approve` member flags, `docs/configuration.md` documents `agent_family.plan_approval.default_members`, and `docs/ace.md` documents the launch-approval modal and plan-gate toggles.

One thing worth knowing: the verification commit corrected two claims that our research doc also makes, and I confirmed both corrections against the code:

1. A manual `%n(foo, tester)` attach is *not* fully equivalent to an evaluator-inserted member. It shares the family metadata, grouping, and dismissal behavior, but runs outside the runner loop — it never emits `role_completed` and never gets the `agent_family_custom_role` snapshot, so it shows generic RUNNING/DONE labels even when the suffix matches a defined role.
2. `on_done` is validated and snapshotted but has no runtime consumer yet — the re-review loop actually comes from the role's prompt template resubmitting a plan, with the evaluator enforcing `max_visits`.

Since the shipped guide is now the more accurate document on those two points, I added a short status/supersession note at the top of `sdd/research/202607/dynamic_agent_families_user_manual_research.md` pointing to `docs/agent_families.md` and flagging both corrections. That edit is uncommitted (research-dir changes are exempt from `just check`); say the word if you'd like it committed. If you'd rather I extend the existing guide — e.g. add the plan-approval choice-registry table or anything else from the research it deliberately left out — I'm happy to, but I didn't want to duplicate or overwrite a page another agent just authored and verified.

The uncommitted change is the supersession note I added to the research doc this session, so I'll commit it with the commit skill.

Committed. The uncommitted change was the supersession note I added this session to `sdd/research/202607/dynamic_agent_families_user_manual_research.md`, so per the finalizer I committed it via the `/sase_git_commit` skill:

- **Commit**: `docs: note supersession of agent families research by docs/agent_families.md`, staging only that file with `--type create_commit`.
- **Verified**: `git status --short --branch` shows a clean working tree and `master` in sync with `origin/master` (the wrapper pushed as part of its workflow).

The main outcome of this turn stands as reported earlier: no new user guide was needed — `docs/agent_families.md` already exists (authored and verified by a `refresh_docs` family earlier today, wired into the mkdocs nav), and the research doc now carries a note pointing to it and flagging the two claims the verification pass corrected.
