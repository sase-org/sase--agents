%name:research.@.final %m:@research %wait:research.0.cdx %wait:research.0.cld %g:research
#gh:gh_sase-org__sase 
The two independent research agents have finished. Their chat transcript paths are available here:

{{ wait_chats }}

Read both chat transcripts first. From those transcripts, identify the two `sdd/research/` markdown files created by the
agents, then read both files.

Verify the prior work against the request below. Consolidate and improve the research into one final `sdd/research/`
markdown file without unnecessary length growth. Preserve the strongest findings, resolve conflicts, add any missing
critical context, and remove duplication.

After the final consolidated research file exists, delete the two intermediate `sdd/research/` markdown files created by
the prior agents.

Research request:

We currently store all plans, prompts, research markdown files, and sase beads directly in this repo in the sdd/ directory. This results in a very large number of git commits that are not related to the code. This clutters the git history. I would like to start using a separate GitHub repo for these files per project. We should search for this repo in the same GitHub organization in a repo named either `sdd` or `<project>-sdd`, where `<project>` is the name of the main repo (`sase` in the case of this repo). Each VCS type should be able to opt in to this behavior. BareGit repos should continue to use the old behavior but the GitHub VCS should opt in. Can you do some research to help me understand the best way to implement this? End your analysis with a recommended approach.