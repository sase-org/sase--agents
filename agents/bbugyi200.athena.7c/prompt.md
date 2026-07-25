#gh:gh_sase-org__sase We recently migrated the pylimit script to a new toobig GitHub repo and we are currently in the process of  doing the same thing for the pyvision script (search for and review the related sase epic beads and the corresponding commits for these migrations for context). Can you now help me do the same thing for the pyvendor script and the bugyi.sh script?

- These should both be contained in a new Python package called basher, which I already own and actually already have another repo associated with.
- Rename that old GitHub repo to pybasher (or something else if that's taken) and create a brand new bbugyi200/basher repo in GitHub before creating the plan file (PyPI should already be registered to that repo).
- One significant improvement we're going to make here is that the bugyi.sh file will be generated using the Python package's version number to produce the file name suffix instead of the current date.
- Also, make sure the basher script is user-friendly and configurable.
- Also, add some useful CLI options.
- #beau 

#epic #m_fable