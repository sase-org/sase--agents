%clan(research.1, tribe=research,
summary=[[[bold]RESEARCH PROMPT:[/bold] Very often when using the new Artifacts Links panel to jump
to a linked artifact, I receive an error toast saying that that artifact is no longer
available on that tab. For the Patch tab what we used to do for situations like this
(for the `<enter>` keymap on the "Agents" tab, for example) is change the current search
query on that tab to an appropriate query that matches the missing PR in the case of
that tab (this way we could then jump to that PR/patch entry). The user would then be
able to switch back to the query that they were using previously by using the `^` keymap
(which should be supported on all sub-tabs of the "Artifacts" tab). I want to make the
links panel significantly more reliable, to the point where these types of errors
virtually never happen, using a similar strategy.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution.]]) %id:research.1.cdx
%wait(priority=20) %model:@research_a #gh:gh_sase-org__sase Very often when using the new Artifacts Links panel to jump
to a linked artifact, I receive an error toast saying that that artifact is no longer
available on that tab. For the Patch tab what we used to do for situations like this
(for the `<enter>` keymap on the "Agents" tab, for example) is change the current search
query on that tab to an appropriate query that matches the missing PR in the case of
that tab (this way we could then jump to that PR/patch entry). The user would then be
able to switch back to the query that they were using previously by using the `^` keymap
(which should be supported on all sub-tabs of the "Artifacts" tab). I want to make the
links panel significantly more reliable, to the point where these types of errors
virtually never happen, using a similar strategy.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. #research