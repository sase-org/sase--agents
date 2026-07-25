%name:research.@.final %m:@research_lead %wait:research.8.cdx %wait:research.8.cld %g:research
#gh:gh_sase-org__sase 
The two independent research agents have finished. Their chat transcript paths are available here:

{{ wait_chats }}

Read both chat transcripts first. From those transcripts, identify which markdown file in the effective research
directory was created by the first (`research.@.cdx` / `research_a`) agent and which was created by the second
(`research.@.cld` / `research_b`) agent, then read both files. Keep this producer-to-report association explicit so the
source reports are assigned deterministically rather than by filesystem ordering.

Effective research directory:

$(sase sdd path research)

Before moving or writing any files, choose a descriptive final markdown filename `<name>.md` and derive `<name>` by
removing its `.md` suffix. The completed layout must be:

```text
<effective-research-directory>/
└── <name>/
    ├── <name>__a.md
    ├── <name>__b.md
    └── <name>.md
```

Do not silently overwrite an existing `<name>` directory or any destination file. If the chosen stem would collide,
select a distinct descriptive stem before moving anything. Once the stem is collision-free, create
`<effective-research-directory>/<name>/` and safely move and rename the first agent's report to `<name>/<name>__a.md`
and the second agent's report to `<name>/<name>__b.md`. Preserve both source reports.

After both source reports have been safely relocated, verify the prior work against the request below. Consolidate and
improve the research into `<name>/<name>.md` without unnecessary length growth. Preserve the strongest findings, resolve
conflicts, add any missing critical context, and remove duplication.

Research request:

This codebase contains a lot of backward compatibility logic that no longer serves any use because there are no projects that still need that logic. We need agents to always introduce backward compatibility logic because we don't want once this project becomes popular but we need a process or policy to govern how/when we should deprecate this logic. And most importantly we need a way to track and ensure that this logic always gets removed. Can you do some research to help me think about the different ways that we could implement this? End your analysis with a recommended solution. Once you're done writing your research file express your answer by setting a few sase variables.