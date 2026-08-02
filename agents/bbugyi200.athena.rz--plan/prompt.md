#gh:gh_sase-org__sase It seems like it's currently impossible to approve multiple epics at
the same time. At the very least it's unreliable because we seem to use the same
clones/workspaces of the sidecar repos for every epic approval. Can you help me
fix this by using lockfiles to ensure that only one epic approval attempts to
run at a time (all others should wait for the lock)? See #sshot for an example
of the type of failure I am trying to fix.

#plan #m_opus