#gh:gh_sase-org__sase No completion triggers when I type `@res` in the prompt input widget
(see ~/tmp/screenshots/20260729_161932.png). I expected `@research:` to be
offered in the prompt input widget completion menu since `@research` is
configured as a sidecar repo for this project (see the sase-av epic bead for
context). Can you help me fix this?

- FWIW, this completion seems to be working for `@plans` artifacts in the prompt
  input widget.
- This is probably because I said to ignore the parts of the research that
  mentioned the `sase--research` repo since that is a custom user-defined (by
  me) sidecar repo.
- But that doesn't mean that it shouldn't trigger artifact completion. We should
  trigger this completion and support artifact resources from all custom sidecar
  repos.

#plan #m_fable