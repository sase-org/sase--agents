- **AGENTS:**
  - [bbugyi200.athena.0xb](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0xb/README.md)

#gh:gh_sase-org__sase Why does sase-listen always default to using Gemini 3.1 Pro (see
the command output below for context)? Is there a way to configure a different model to
be used from a different provider (e.g. Claude) instead? #research %m:@xlarge

```
❯ sase-listen render https://arxiv.org/html/2608.11095v1 -e full
♪ Why Does CLAUDE.md Keep Growing? Catastrophic Remembering in Agentic Coding                                                                                                                                                                                     11s
  arxiv.org

⠋   Fetch article extracting the article text                                                                                                                                                                                                                     11s
⠋   Write script  attempt 1 of 3 · waiting on gemini-3.1-pro-preview                                                                                                                                                                                               9s
·   Plan episode
·   Synthesize
·   Quality gates
·   Master audio
·   Save episode
·   Publish
```
