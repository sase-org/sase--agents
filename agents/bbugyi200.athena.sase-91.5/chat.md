# Chat History - ace-run (sase-91.5)

- **TIMESTAMP:** 2026-07-24 20:27:18 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** sase-91.5

## Prompt

#gh:gh_sase-org__sase
%id(5, clan=sase-91, bead=sase-91.5)
%model:@small_phase_worker
%auto
%w:sase-91.1
%w(bead=sase-91.1)
Can you complete the work for bead sase-91.5? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now let me write the guard helper and facade wrapper.

Now export it from the `names` package:

Now the resume/wait template guard:

Now the family-attach generation guard:

Now add the helper function:

Now the clan guards:

Now the multi-prompt launch-plan clan path:

Now I'll write the test file.

Now the full check:

Lint and symvision pass; the 3 remaining test failures are all pre-existing on a clean tree. Let me commit.

Bead sase-91.5 is done, committed as `d31c8866b`, pushed, and closed. The epic `sase-91` was left open.

**What Phase 5 needed:** the runtime was writing names it could no longer classify. Two generation sites collaborate to produce them — resume/wait/retry naming appends `.f@`/`.w@`/`.r@` to a base that may already carry a `--<role>` suffix (`fi--code` → `fi--code.f0`), and family attachment then appends another role to that (`fi--code.f0--code`).

**Changes:**
- `src/sase/agent/names/_generation_guard.py` (new) — `generated_agent_name_is_valid` (strict core `validate_agent_name`) and `generated_child_name_base`, which returns the base a dotted child may hang off of: a family member yields its family name, a legacy base falls back to its top-level hood.
- `_resume.py` / `_retry.py` — resume, wait, and retry templates derive their base through that helper, so forking `foo--code` allocates `foo.f0`, not `foo--code.f0`.
- `_family_attach_resolution.py` — rejects a composed member (or renamed original-parent) name whose role suffix would not be terminal, with an error naming the parent, the role, and the name it would have written. Deriving a name silently was rejected here per the plan's "do not silently rename an agent the user explicitly asked for".
- `clan_membership.py` and `multi_prompt_launch_plan.py` — reject a clan name carrying a family marker, since members are `<clan>.<suffix>`.
- `agent_identity_facade.py` — exposes the core strict entry point as `validate_new_agent_name`.
- `tests/test_agent_generated_name_guard.py` — 23 tests covering the guard helpers, the three derived-name templates, attaching to a family-member parent, attaching to a clan-generation parent, the ordinary well-formed cases, the legacy-parent failure, and both clan paths.

**Verification:** `just install`, `just lint` (ruff, mypy, symvision, line counts) and `just check` pass. Three test failures remain, all reproduced on a clean tree without my changes:
- `tests/test_agent_name_registry_claims.py::test_registry_rebuild_survives_un_globalizable_legacy_name` — asserts `foo--role.f-0` has no canonical global name; Phase 1's totality change (core `d0b3a88`) made it globalizable, so the test's premise is stale. It sits inside sase-91.2's in-progress area, so I left it rather than risk a conflicting edit.
- Two ACE PNG snapshots (`test_queued_clan_counts_png_snapshot`, `test_agent_lane_cleanup_confirmation_png_snapshot`) — unrelated, and that suite also showed a third intermittent failure on the clean tree.

Publication of the agent hood still fails with the `4x--epic.f-0` error on commit; that is exactly what Phases 2, 3, and 6 remain open to fix.
