- **PLAN:**
  [202608/file_ref_pool_extension_and_relative_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/file_ref_pool_extension_and_relative_path.md)
- **AGENTS:**
  - [bbugyi200.athena.0e5--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0e5.md)

Can you help me start making the expansion for the `@file` ref use the correct filename
extension for the local file that is added to the .sase/artifacts/pool/ directory? Also,
let's start rendering the local file path in the prompt. For example, the `#sshot`
xprompt currently renders file paths like
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.sase/artifacts/pool/5713d120c7da-file-ref.
We should start rendering file paths like .sase/artifacts/pool/5713d120c7da-file-ref.png
instead.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
