#gh:gh_sase-org__sase A common problem with the /sase_repo xprompt skill is that agents frequently
attempt to open linked repos (the sase-core repo is a "linked repo" of the "sase" sase
project, for example) as external repos. Can you help me fix this by making it so the
`sase repo open` command automatically opens a linked repo when a corresponding external
repo is specified by a sase agent? Show a good info/warning message to the agent when we
do this so they understand what was done and why.

#plan %m:gpt-6-astra