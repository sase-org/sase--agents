#gh:gh_sase-org__sase I have several aliases for `sase` subcommands defined in the aliases.sh file in
my chezmoi repo. The problem is that I often want to copy the command and its output to
give to a sase agent and I don't want them to have to figure out how my aliases are
defined. I currently work around this problem by converting some aliases to shell
functions and printing the full `sase` command that will be run before running it (see
the `sbd()` function in the aliases.sh file, for example), but this breaks command-line
completion (see the `sase completion` command for more context on sase's command-line
completion). Can you help me fix this by adding a new `-p|--print-command` option to the
`sase` command that prints the full command like this so I can convert `sbd()` back to
an alias (you should make this conversion once you've finished adding the new CLI
option)?

#beau #plan %m:gpt-6-astra