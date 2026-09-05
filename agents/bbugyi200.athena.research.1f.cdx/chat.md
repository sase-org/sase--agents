# Chat History - ace-run (research.1f.cdx)

- **TIMESTAMP:** 2026-09-05 17:56:45 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.1f.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260905_173207.md`

## Prompt

%clan(research.1f, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] sase has a large amount of backward compatibility code,
which should not really be needed anymore. Every machine that uses sase can be accessed
from this machine via SSH. (see the `mac` and `apollo` entries in the ~/.ssh/config
file), so we should be able to migrate any config / data files that are using legacy
features.

Can you do some research to help me understand what work needs to be done to remove all
backward compatibility logic for legacy functionality from sase's codebase? End your
analysis with a recommended solution. Make sure your solution takes all of my machines
into account.]]) %id:research.1f.cdx
%model:@research_a 
#gh:gh_sase-org__sase sase has a large amount of backward compatibility code,
which should not really be needed anymore. Every machine that uses sase can be accessed
from this machine via SSH. (see the `mac` and `apollo` entries in the ~/.ssh/config
file), so we should be able to migrate any config / data files that are using legacy
features.

Can you do some research to help me understand what work needs to be done to remove all
backward compatibility logic for legacy functionality from sase's codebase? End your
analysis with a recommended solution. Make sure your solution takes all of my machines
into account. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll audit the current codebase for compatibility branches, trace each one to its persisted config/data formats, then inventory and safely inspect the `mac`, `apollo`, and local-machine state. I’ll write an evidence-backed migration/removal recommendation to the requested September 2026 research directory. I’m also applying SASE’s audited memory guidance for repository verification and any artifact-like research output.

The first pass shows several distinct compatibility classes, not one cleanup: on-disk layout migration, config aliases, serialized history/gate formats, renamed Patch/ChangeSpec Python APIs, mixed-version plugin contracts, and purely test-facing shims. I’m separating genuine backward compatibility from ordinary resilience fallbacks so the final scope doesn’t accidentally delete fault-tolerance behavior.

The live cleanup can be much safer than a conventional deprecation: the project already has explicit migrators for several formats, and the fleet is small. I’m now checking which migrators have actually converged on `athena`, `mac` (Kelly’s MacBook), and `apollo`, while also checking managed chezmoi source so a later deploy cannot reintroduce an old key. All machine checks are read-only.

I’ve narrowed the key distinction the report needs to preserve: removable live compatibility versus decoders for immutable history. I’m finishing the cross-repo call-site audit now, then I’ll write the fleet-aware cutover recommendation and concrete deletion order.

The fleet audit found two concrete blockers to a clean runtime cutover: Apollo and Athena are actively running SASE services that still touch Telegram’s legacy pending-action store, and Athena retains several old local stores/locks. Most other migrations—artifact sharding, `.sase` project specs, prompt-history sharding, and Proc records—are already complete across all three machines.

The report is written and passes whitespace validation. It recommends a single canonical-only release epic, with an atomic three-machine cutover and a checkpoint strategy so the runtime can drop historical decoders without rewriting append-only bead or Git history. I’m completing the SASE handoff metadata now.

Research complete: [legacy_compatibility_retirement.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202609/legacy_compatibility_retirement.md).

It covers the SASE codebase, Rust core, plugins, managed configuration, shared sidecars, and live state on Athena, Mac, and Apollo. The recommendation is a coordinated canonical-only release with fleet-wide preflight, one-shot migrations, immutable-history checkpoints, and an atomic three-machine deployment.

The Markdown file also passes whitespace validation.
