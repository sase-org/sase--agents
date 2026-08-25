%clan(research.13, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] Sase seems to have support for three different installation
modes for plug-ins:

1. the published version of the python package
2. the dev version, which uses an editable local install
3. a "from git" option

I don't understand why the third option ("from git") is necessary since we can always
use the second option (dev/editable install) instead, right? The bugyi-chops plugin
which is installed on this machine, for example, uses a "from git" installation and I
would like to migrate this installation to use a dev/editable install instead.

Can you do some research with the goal of helping me understand what it would take to
remove support for "from git" sase plugin installations? End your analysis with a
recommended solution.]]) %id:research.13.cdx
%model:@research_a 
#gh:gh_sase-org__sase Sase seems to have support for three different installation
modes for plug-ins:

1. the published version of the python package
2. the dev version, which uses an editable local install
3. a "from git" option

I don't understand why the third option ("from git") is necessary since we can always
use the second option (dev/editable install) instead, right? The bugyi-chops plugin
which is installed on this machine, for example, uses a "from git" installation and I
would like to migrate this installation to use a dev/editable install instead.

Can you do some research with the goal of helping me understand what it would take to
remove support for "from git" sase plugin installations? End your analysis with a
recommended solution. #research(report_target=research.13.cdx.md)