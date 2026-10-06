- **PLAN:**
  [202610/sase_listen_arxiv_pdf_urls.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen_arxiv_pdf_urls.md)
- **AGENTS:**
  - [bbugyi200.athena.0xa--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xa.md)

Can you help me make the `sase-listen render` command smart enough to recognize an arxiv
URL and automatically use the corresponding PDF URL instead? See the command output
below for context. Think this through thoroughly and create a plan using your
`/sase_plan` skill. Choose and author the appropriate tier, validate and revalidate
until it passes, then submit it with `sase plan propose` (as the skill instructs) before
making any file changes.

```
bryan in 🌐 athena in sase on  master [$] is 📦 v0.17.1 via  v22.14.0 via 🐍 v3.11.13
❯ sase-listen render https://arxiv.org/abs/2602.16844 -e full

bryan in 🌐 athena in sase on  master [$] is 📦 v0.17.1 via  v22.14.0 via 🐍 v3.11.13
❯ sase-listen render https://arxiv.org/abs/2602.16844 -e full
♪ Overseeing Agents Without Constant Oversight: Challenges and Opportunities
  arxiv.org · full edition · Charon · gemini-3.8-flash-tts

✓   Fetch article arxiv.org · 364 words                                                                                                                                                                                                                           18s
✓   Write script  186 words · 4 chapters · 1 attempt                                                                                                                                                                                                              18s
✓   Plan episode  6 chunks · 0 cached · ≈2 min · ≈$0.02                                                                                                                                                                                                          0.3s
✓   Synthesize    6 synthesized · 0 cached · 0 retries                                                                                                                                                                                                            17s
✓   Quality gates all 6 chunks in range                                                                                                                                                                                                                          0.2s
✓   Master audio  1m 57s · -16.4 LUFS · 1.0 MB                                                                                                                                                                                                                   4.0s
✓   Save episode  verified · 4 chapters                                                                                                                                                                                                                          0.0s
✓   Publish       apollo (via apollo)                                                                                                                                                                                                                            2.6s
♪ Ready in 44s · 1m 57s of audio · ≈$0.03
  /home/bryan/.local/share/sase-listen/library/overseeing-agents-without-constant-oversight-challenges-and-c606b2/overseeing-agents-without-constant-oversight-challenges-and.mp3
  Published to apollo — refresh the feed in AntennaPod to download it.
  ⚠ 1 warning
    · W012 7:1: Edition 'full' has 186 words (budget 2400; under 50%).

bryan in 🌐 athena in sase on  master [$] is 📦 v0.17.1 via  v22.14.0 via 🐍 v3.11.13 took 45s
❯ sase-listen render https://arxiv.org/pdf/2602.16844 -e full

bryan in 🌐 athena in sase on  master [$] is 📦 v0.17.1 via  v22.14.0 via 🐍 v3.11.13 took 45s
❯ sase-listen render https://arxiv.org/pdf/2602.16844 -e full
♪ Overseeing Agents Without Constant Oversight: Challenges and Opportunities
  arxiv.org · full edition · Charon · gemini-3.8-flash-tts

✓   Fetch article arxiv.org · 11,452 words                                                                                                                                                                                                                     1m 36s
✓   Write script  1,229 words · 6 chapters · 2 attempts                                                                                                                                                                                                        1m 34s
✓   Plan episode  8 chunks · 1 cached · ≈8 min · ≈$0.11                                                                                                                                                                                                          0.3s
✓   Synthesize    7 synthesized · 1 cached · 0 retries                                                                                                                                                                                                         1m 01s
✓   Quality gates all 8 chunks in range                                                                                                                                                                                                                          1.1s
✓   Master audio  8m 48s · -16.5 LUFS · 4.2 MB                                                                                                                                                                                                                    16s
✓   Save episode  verified · 6 chapters                                                                                                                                                                                                                          0.0s
✓   Publish       apollo (via apollo)                                                                                                                                                                                                                            2.9s
♪ Ready in 2m 58s · 8m 48s of audio · ≈$0.12
  /home/bryan/.local/share/sase-listen/library/overseeing-agents-without-constant-oversight-challenges-and-09e39f/overseeing-agents-without-constant-oversight-challenges-and.mp3
  Published to apollo — refresh the feed in AntennaPod to download it.
```
