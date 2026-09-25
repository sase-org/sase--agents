#gh:gh_sase-org__sase %w:sase-sk.3 Can you help me reduce the size of the names of the sase agent
launched by the `toobig_split` chop?

- We currently use something like `toobig-@.<full_module_path>.<N>`, where `<N>` is some
  integer starting at `0` and `<full_module_path>` is the full module name
  (dot-separated) of the Python file we are splitting.
- Let's start using `toobig-3j.<basename>.0` instead.
- We should already support this `{@<id>}` syntax I believe, but verify that we do
  before planning.

#plan