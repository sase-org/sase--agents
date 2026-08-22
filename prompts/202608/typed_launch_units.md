- **PLAN:**
  [202608/typed_launch_units.md](https://github.com/sase-org/sase--plans/blob/main/202608/typed_launch_units.md)
- **AGENTS:**
  - [bbugyi200.athena.0b8--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0b8.md)

Can you help me implement the new `%if` and `%proc` directives and add support for
stand-alone proc shells, as described by the standalone_proc_launch_units.md and
conditional_launch_admission.md files in the research sidecar repo?

- Make sure these directives have excellent completion in the prompt input widget and
  external editors (via LSP support).
- Make sure the agents tab has excellent (visually appealing) support for stand-alone
  proc shells.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
