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
into account. #research(report_target=research.1f.cdx.md)