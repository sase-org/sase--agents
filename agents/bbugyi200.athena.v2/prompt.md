#gh:gh_sase-org__sase Can you help me implement all of the recommended improvements described in the
gate_input_collection.md file, which can be found in this project's research sidecar
repo?

- I have a few notes about the `Decide edit_file’s scope explicitly` recommendation /
  request, which can be found below.
- The `edit_file` command, currently only supported for plan sase gates, should also be
  supported by epic sase gates.
- We may need to add support for a new type of gate command to achieve what I want here
  (use your best judgement). Namely, I want `edit_file` to be a repeatable command that
  does NOT dismiss the sase gate it is associated with.
- In this case, this command allows the user to edit the plan file (make sure we only
  accept the edits if the `sase plan validate` command passes--also, make sure the plan
  file that is opened in our editor is the one stored in the ~/.sase/plans/ directory)
  as many times as they need before approving/rejecting it.
- In general, however, this type of command is intended to be useful any time we want to
  give the user easy access to a command that might help them (even a command that just
  displays a nice view of the decision would potentially be useful) get closer to making
  a final decision on the gate.
- #beau

#plan #m_opus