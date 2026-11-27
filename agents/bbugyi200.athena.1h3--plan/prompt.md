#gh:gh_sase-org__sase Can you help me fix the `l` keymap on the "Agents" tab? Namely, we should never
open a session to land on one of its children when this keymap is used on an agent clan;
we should jump to that session instead. For example, in the
~/tmp/screencasts/20261127_093654.mp4 screencast, we should have landed on the
`bob-cli-qj.land` node, not the `bob-cli-qj.land--mon` node. Pressing `l` again should
then open the `bob-cli-qj.land` session node and select the `bob-cli-qj.land--mon` node.

#plan %m:@xlarge