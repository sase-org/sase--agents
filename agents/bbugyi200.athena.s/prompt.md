#gh:gh_sase-org__sase Can you help me improve the `just demo-video` command?

- Once all artifacts have been generated, we create a demos/out/last_generated_date.txt file with a date using the `%Y-%m-%dT%H:%M:%S` format (as was done manually last time).
- Let's stop generating the PNG file (just the GIF and MP4).
- Let's start prompting the user (y/n) if they want to commit the changes to the demos/out/ files after re-generating.
- The `just demo-video` command should support a `-y|--yes` option (if `just` commands support options) that auto-approves the commit.

#plan #m_fable %a:tale