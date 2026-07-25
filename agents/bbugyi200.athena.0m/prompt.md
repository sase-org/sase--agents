#gh:gh_sase-org__sase Can you help me add good completion for GitHub repos when the user presses the `/` key an the argument provided to the `#gh` xprompt workflow?

- For example, typing `#gh:bbugyi200/` should trigger a completion menu for all valid, public GitHub repos in the `bbugyi200` GitHub organization.
- This needs to work both in the prompt input widget and in editors via LSP support ideally or (if LSP support is not possible / desirable here) the sase-nvim plugin.
- We should also be careful to provide support for this in a VCS-agnostic way such that it will be easy to add support for similar completion for, say, GitLab or some companies' internal VCS system later on when they write the sase plugin (ex: sase-gitlab) for their VCS.
- #beau 

#epic #m_fable