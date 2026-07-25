%name:research.@.cdx %model:@research_a %g:research #gh:gh_sase-org__sase I want to generalize the concept of plan / question /
launch notifications so all of them use the same structure and sase notification
constructor. We should use the existing `sase notify create` command for this,
which will need to be signifigantly enhanced I think. As a part of this change,
I intend to remove the (never used) dynamic `improve_plan` and `tester` family
member hooks (I'm not even sure how they work, but I'm pretty sure we will need
to do something about them to progress with this initiative).

Can you do some research to help me understand what this task entails? End your
analysis with a list of questions that, if answered correctly, would allow you
to confidently design and implement this functionality. #research