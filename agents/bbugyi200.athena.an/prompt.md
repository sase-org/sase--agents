#gh:gh_sase-org__sase Can you help me add support for using reference-style markdown links as
values for sase commit tags (the references will go after the sase commit tags,
after a blank line) and, as our first use-case, start using a link to the plan
file in the corresponding sase project's `plans` sidecar repo on GitHub? For
example, assume a commit for this project (sase) with the following sase commit tags:

```
SASE_MACHINE=athena
SASE_PLAN=202607/amd_agents_template.md
```

After this change, a commit like this would instead write something like the following for its sase commit tags:

```
SASE_MACHINE=athena
SASE_PLAN=[202607/amd_agents_template.md][1]

[1]: https://github.com/sase-org/sase--plans/blob/main/202607/amd_agents_template.md
```

#tale