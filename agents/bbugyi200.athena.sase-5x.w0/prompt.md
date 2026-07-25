#gh:gh_sase-org__sase %w:sase-5x Can you help me start allowing agents to use the `sase repo open` command for any sase repo, regardless of
whether it even exists yet?

- We should make some changes to the types of repos sase handles to support this feature. Namely, we should also add a new repo type called external repos. These
    are repos that the agent didn't know about before the request. At the moment external repos are always GitHub repos, but keep in mind that we should try to be VCS agnostic about this so it is easy to add support to, for example, GitLab later.
- Keep in mind that the `sase repo open` command probably doesn't support external repos yet. You will need to add
  support for them. External repos should be cloned to the new workspace-local sase/repos/external/ directory.
- We should create two new xprompt skills to support this feature:
  - `/sase_repo`: This skill will allow agents to work with the `sase repo` command. We should start using this in agent
    instructions instead of telling agents to run the `sase repo open` command directly.
  - `/sase_project`: This skill is not strictly necessary but will teach the agent how to use the `sase project`
    command, which will be useful, for example, when I want one agent to launch one other sase agent for every currently enabled sase
    project.
- We should also make sure that both of these skills have great descriptions and that the `/sase_repo` skill's
  description and the agent instructions we generate in agent instruction files (ex: AGENTS.md) make it clear that
  any time the agent needs to read/modify files in a different sase project (a project that the user told it about in the
  prompt, for example) or a GitHub project that is NOT associated with the current project via a linked repo, they MUST
  use the `/sase_repo` skill to open that repo as an external repo.
- Make sure external repos have all of the same commit finalizer support and diff support / file delta support / support
  for anything else that needs to be done to give this feature full support in the `sase ace` TUI. #beau
- IMPORTANT: When adding/modifying agent skill descriptions or sase memory files (ex: memory/sase.md), try to keep these files concise but useful. Keep in mind that
  every token in context either helps us or hurts us.

#epic #m_fable