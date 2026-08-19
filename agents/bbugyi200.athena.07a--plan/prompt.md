#gh:gh_sase-org__sase We recently added support for a "current project" in sase (see the sase-pw epic
bead for context). We were supposed to use the `project:<project>` filter for any
sub-tab on the "Artifacts" tab, but it looks like we missed this for the "Patch" sub-tab
of the "Artifacts" tab, which does support a `project:<project>` query filter (and also
probably contains some legacy bagage you may need to work around--the `!!!` syntax will
be deprecated and removed soon, for example). Can you help me fix this?

#plan