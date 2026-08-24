#gh:gh_sase-org__sase Can you help me replace the `#coder` xprompt definition? It's current contents
are as follows:

```
@{{ plan_file }}

The above plan has been reviewed and approved. Implement it now.
```

I want to change them to this:

```
The {{ plan_file }} plan file has been reviewed and approved. Implement it now.
```

where `plan_file` is the `YYYYmm/<plan_name>.md` part of the plan file (it should still
be the same input argument that the xprompt accepts now, but we should strip the input
argument appropriately--202608/foo.md instead of ~/.sase/plans/202608/foo.md, for
example). The goal is to allow the agent to find the plan file itself, which in the
ideal case causes it to use the `sase artifact read` command to read the artifact and
leave a trace (e.g. a reason for reading the artifact file).

#plan