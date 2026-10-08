- **PLAN:**
  [202610/just_install_pypi_dev_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)
- **AGENTS:**
  - [bbugyi200.athena.0ym--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md)

I need a way to reliably install sase from PyPI (i.e. prod) and from a dev/editable
install (which needs to include the appropriate sase-core checkout for that dev version)
using the `just` command. Can you help me implement this?

- The `just install` command and other related `just install-*` commands are already
  used to install sase into a local virtual environment.
- These commands are necessary but their names are not intuitive. Can we rename them to
  `just install-venv` / `just install-venv-*`? This will likely require updating some
  memory files.
- This will allow us to add new `just install` and `just install-dev` commands to serve
  these roles.
- Review the just_install_pypi_dev_venv_split.md file in the research sidecar repo for
  context and inspiration before planning. I agree with all of the requirements
  recommended in that research file.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
