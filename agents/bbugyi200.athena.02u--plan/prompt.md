#gh:gh_sase-org__sase Can you help me make sase variables much more powerful?

- The `sase var list` command currently only supports running when a sase agent is
  running (i.e. when certain `SASE_*` environment variables are set). This command shows
  an agent what variables it has set for itself.
- Let's add a new `sase var show` command that takes over this functionality. This
  command should accept an optional `<agent_name>` as an argument. If not provided it
  will default to using the `SASE_AGENT` environment variable.
- You should add a new `sase var list` command.
  - This new command should accept a variety of useful options (e.g. `-f|--format`,
    `-c|--color`, `-n|--limit`, `-s|--since`, `-u|--until`--see how other sub-commands
    handle these options for inspiration and add others that are useful specificly for
    this command).
  - This command should list all uniquely named sase variables that have been set (up to
    a limit) along with all the values and associated sase agent names that those
    variables have contained (again, up to a limit----the `-n|--limit` option should
    default to `20:5` which specifies that at most 20 keys will be shown with at most
    their last 5 values).
  - Make sure this command supports filtering for specific variable keys/values.
- Let's add a new `sase var get` keymap that accepts a variety of different useful
  argument types (e.g. `<agent_name>.<var_key>`, `<var_key>[0]`,
  `<agent_hood>.*.<var_key>`, etc...). The output of this command might vary a bit
  depending on the argument type. Be creative but practical when designing this
  commands. Make sure it provides real value for both humans and agents!
- I intend to give sase agents access to this extended functionality soon but let's not
  do that yet. For now, just update the /sase_var skill to have agent's use the
  `sase var show` command instead of the `sase var list` command (which should have a
  different functionality after this feature is complete).
- #beau

#plan