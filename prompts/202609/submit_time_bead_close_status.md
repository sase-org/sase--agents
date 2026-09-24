- **PLAN:**
  [202609/submit_time_bead_close_status.md](https://github.com/sase-org/sase--plans/blob/main/202609/submit_time_bead_close_status.md)
- **AGENTS:**
  - [bbugyi200.athena.0qe.f0--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qe.f0.md)

%xprompts_enabled:false

# Previous Continuation

This fork uses versioned continuation replay. Blocks are stable, parent-first
projections of exact continuation nodes; any historical source without recoverable node
provenance is represented as an opaque legacy boundary.

- **Projection version:** `1`
- **Ordered nodes:** `1`

## Continuation Block `block:v1:797f4806af983425ad89d66e1e6851aa`

- **Node:** `agent-delta:20260923203756:8c10bdfbbb093073`
- **Kind:** `agent_delta`
- **Parents:** (none)
- **Content:**
  `local:continuation/records/agent_delta/agent-delta:20260923203756:8c10bdfbbb093073.json`

### User

**Protected user instruction.** Carry this request unless an explicit attributed update
supersedes it.

Why was the `close` bead action refused for the `sase-17d.1` and `sase-17d.2` sase
agents? %m:@xlarge

### Assistant

Found both agents' transcripts; now digging into their artifact dirs for the exact
refusal messages.

Both refusals share one error code. Next I'll find where that code comes from and why
the status read failed.

The refusal comes from the Rust `validate_finalizer_bead_decision` binding. Next I'll
check what bead status the agents' submissions carried, and the Rust rule that rejected
them.

Found the Rust rule: `close` is refused unless the bead status is known to be
`in_progress` or `closed`. Now checking where that status should be filled in at submit
time.

Checking whether this is systemic — i.e., whether any agent has ever had a `close`
accepted at submit time.

Confirmed it's systemic, not specific to these two agents. One last check: whether
agents are _supposed_ to fill in `bead_status` themselves.

Root cause found. The project asks that discovered bugs be filed as task beads, so I'll
run the duplicate-check skill before filing.

Now searching for duplicates and related active epics.

`sase-10l` is related but a different root cause (a stitch-path status read that fails,
not a submit path that never reads status). Running the recent-task sweep and epic
check.

This exact root cause was already reported on 2026-09-16 as note #2 on epic `sase-zq`,
and it's still unfixed. Adding a short note with updated evidence instead of filing a
duplicate.

Now submitting the final declaration.

Both agents hit the same known bug, not a problem with their own work. At submit time,
the check that decides whether `close` is allowed never gets the bead's status, so it
refuses `close` every time.

**What happened**

Both `sase final submit` attempts were logged as refused with the same error (in each
run's `final_submission_attempts.jsonl`):

```
commit_bead_action_invalid: unreadable_bead_status: the assigned bead status could not be read; close is refused
```

- **`sase-17d.1`** was refused at 23:35:28Z. It had already closed its bead by hand with
  `sase bead close`, so it resubmitted with `keep` 5 seconds later, and that was
  accepted.
- **`sase-17d.2--code`** was refused at 00:07:56Z and was also accepted with `keep` 6
  seconds later.

**Why it's refused**

1. `_validate_commit_decision` in `src/sase/finalizers/declaration_manifest.py` passes
   the agent's decision straight to the Rust `validate_finalizer_bead_decision`.
2. The Rust side (`sase-core`, `bead_action/policy.rs`) takes `bead_status` from that
   decision. `decide_close` allows `close` only when the status is `InProgress` or
   `Closed`. A missing (`None`), unreadable or unchecked status gets
   `unreadable_bead_status`.
3. Nothing fills in `bead_status` at submit time. The manifest template the agents fill
   in has no such field, and the submit path never looks up the bead's live status. That
   lookup (`bead_status_fact`) only runs later, when the host carries out the commit.

So `close` fails unless the agent writes `"bead_status": "closed"` into the manifest
itself. The only 5 `close` declarations accepted in September all did exactly that. The
refusals started on 2026-09-12, right after `df33453b7` ("require explicit bead action",
from `sase-zq.2`). There are now 370 of them in the logs. In practice agents either
close the bead by hand or leave it open, and the host's own close step never runs.

**Already reported**

The same root cause was recorded on 2026-09-16 as a `DISCOVERED ISSUE` note (#2) on epic
`sase-zq`. That epic is still `in_progress` with all its phases closed. There's also a
related but separate task, `sase-10l`, about a status read failing in the stitch path.
Instead of filing a duplicate, I added a note to `sase-zq` with the updated counts and
these two runs. The fix suggested in note #2 is to have submit look up the live status
itself. I didn't change any code, so there was nothing to commit.

---

%xprompts_enabled:true

# New Query

Can you help me fix this issue? Think this through thoroughly and create a plan using
your `/sase_plan` skill. Choose and author the appropriate tier, validate and revalidate
until it passes, then submit it with `sase plan propose` (as the skill instructs) before
making any file changes.
