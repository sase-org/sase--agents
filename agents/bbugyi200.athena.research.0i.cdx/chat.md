# Chat History - ace-run (research.0i.cdx)

- **TIMESTAMP:** 2026-08-14 09:04:35 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.0i.cdx
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260814_084958.md`

## Prompt

%clan(research.0i, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] I'm thinking about subscribing to a Supergrok account. Can you do some research to help me understand the different price tiers available and the benefits of each one? End your analysis with a recommendation for which tier I should subscribe to.]]) %id:research.0i.cdx
%wait(priority=20) %model:@research_a 
#gh:gh_sase-org__sase I'm thinking about subscribing to a Supergrok account. Can you do some research to help me understand the different price tiers available and the benefits of each one? End your analysis with a recommendation for which tier I should subscribe to. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I’ll compare the currently available SuperGrok tiers using xAI’s own pricing/help pages where possible, note any platform or regional pricing caveats, and save a sourced recommendation in the requested August 2026 research directory.

The official pricing page now shows five individual tiers—Free, Lite, SuperGrok, the newly added Plus, and Heavy—but it only exposes public sticker prices for the middle two in its accessible page text. I’m checking the live checkout/app listings and xAI documentation next so the report clearly distinguishes confirmed prices from estimates and doesn’t invent opaque usage quotas.

The key finding is that price—not model access alone—is the meaningful divider. Standard SuperGrok is the value center; Plus and Heavy chiefly sell more compute, speed, and premium video/agent features, while xAI does not publish the numerical weekly allowances needed to calculate an exact dollars-per-task comparison. I’ll make that uncertainty explicit and base the recommendation on a reversible monthly trial.

The report is written and ends with a concrete recommendation: standard SuperGrok at $30/month on monthly billing first, with usage-based triggers for downgrading or upgrading. I’m doing the repository’s required verification now; the research file itself is documentation-only.

Verification is still building the repository’s local Rust/Python dependency; there are no report errors so far. The version-window notice it emitted is explicitly marked normal for editable development installs.

The required editable install is taking longer than usual because it is compiling the linked Rust core from scratch. I’m letting that finish before running the actual check; the markdown report is already complete and readable at the requested path.

The report’s Markdown formatting and all lint gates have passed so far. The check also surfaced the repository’s known linked-core compatibility-window notice; I’m waiting for the scoped test lane to finish before deciding whether any action is needed.

Created the research report:

[supergrok_subscription_tiers.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202608/supergrok_subscription_tiers.md)

It compares Free, Lite, standard, Plus, and Heavy plans, explains xAI’s opaque weekly usage pools, and recommends **standard SuperGrok at $30/month, billed monthly first**.

Repository checks passed.

The report from the completed research pass is ready; this finalizer requires me to commit that new file in the linked research repository. I’m using the SASE git-commit skill now, then I’ll verify the repository is clean.

Because the file lives in the linked `research` repository rather than the main workspace checkout, I’m also applying the repository-access skill to resolve and validate that checkout before reviewing and committing its changes.

Committed the SuperGrok research report as `21654c8` (`docs(research): compare SuperGrok subscription tiers`).

[View the report](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10/sase/repos/research/202608/supergrok_subscription_tiers.md)

The research repository is clean and synchronized with `origin/main`.
