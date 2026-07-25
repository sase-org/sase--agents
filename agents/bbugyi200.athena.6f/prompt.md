#gh:gh_sase-org__sase Can you help me factor the pylimit script out of my chezmoi repo (leave the old copy behind) into a new, dedicated bbugyi200/toolong Python repo (you will need to create this repo with the gh command before proposing your plan file)?

- Make sure the script has perfect parity with the existing pylimit script, but this script should be language-agnostic (I should be able to run it on a rust project for example).
- Make sure this repo has an excellent README and an automated release process powered by release-. See how this repo (sase) controls its release process for inspiration.
- Also make sure this new repo has great GitHub Actions, CI tests, linting, and formatting. See how this repo (sase) handles all of that for inspiration.
- Migrate this repo (sase) over to using the first published version of this new PyPI package instead of pylimit.

#epic #m_fable