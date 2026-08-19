- **PLAN:**
  [202608/patches_current_project_scope.md](https://github.com/sase-org/sase--plans/blob/main/202608/patches_current_project_scope.md)
- **AGENTS:**
  - [bbugyi200.athena.07a--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07a.md)

We recently added support for a "current project" in sase (see the sase-pw epic bead for
context). We were supposed to use the `project:<project>` filter for any sub-tab on the
"Artifacts" tab, but it looks like we missed this for the "Patch" sub-tab of the
"Artifacts" tab, which does support a `project:<project>` query filter (and also
probably contains some legacy bagage you may need to work around--the `!!!` syntax will
be deprecated and removed soon, for example). Can you help me fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
