- **PLAN:**
  [202610/sase_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)
- **AGENTS:**
  - [bbugyi200.apollo.3z--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md)

I need a way to generate audio content from markdown files (like the research produced
by agents that is stored in the research sidecar repo, for example). I would like to
listen to this content while commuting / walking. Can you help me implement this?

- Review the commute_audio_from_markdown.md file in the research sidecar repo for
  context and inspiration before planning. I made some annotations using the Highlights
  app (on my mac) which can be found in the
  `~/bob/ref/chat/commute_audio_from_markdown.md` file.
- I've already created the public sase-org/sase-listen GitHub repo for you. Make sure to
  give this GitHub repo a good description (I set this description to `TODO` for now).
- Make sure you give the sase-listen GitHub repo excellent documentation, links back to
  the originating plan/research files, and CI tests/lints/releases. Note that I have
  already configured sase-listen as a pending PyPI publisher using the following
  configuration:
  ```
  Repository: sase-org/sase-listen
  Workflow: publish.yml
  Environment name: pypi
  ```
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
