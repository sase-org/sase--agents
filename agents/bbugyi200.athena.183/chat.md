# Chat History - ace-run (183)

- **TIMESTAMP:** 2026-11-04 13:20:41 EST
- **MODEL:** claude/opus
- **AGENT:** 183

## Prompt

#gh:gh_sase-org__sase Are still experiencing agent publication errors? If so, why? Make sure your
research is concise and easy to understand. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete. %m:@xlarge

## Response

Checking the live state now: latest error digests and recent publication fixes since the Nov 2 report.

Yes, still happening: same bob-cli "withheld" error, now with 5 clauses and 50 rows waiting. Next I'll measure how much and what's new since Nov 2.

Confirmed it's ongoing (51 rows waiting, 152 claimed hint files). Now checking whether any fix landed in code or is tracked in beads.

No fix for the scanner rule has landed, and no bead tracks it. Now checking the drain code and the SSH bead.

Verifying the newest stuck row (bob-cli-g1.2) is the same `task-` false positive.

Almost done gathering evidence; one last check on the g1.2 prompt, then writing the report.

Writing the report now.

Registration succeeded. Now finalizing the turn.

**Yes, the agent publication errors are still happening.** It's the same bug the Nov 2 report found, nothing has been fixed, and it's getting worse.

**What's happening (Nov 2 12:56 → Nov 4 13:06 EST):**
- 3,235 of 3,247 error digest entries (99.6%) are `agent_publication` errors, about 67 an hour.
- They all come from one project, bob-cli. sase, tailnet and actstat are publishing normally.
- 5 bob-cli requests are retried every ~45 s and never clear. That's up from 4: `bob-cli-g1.2` got stuck on Nov 2 at 14:47.
- 46 healthy bob-cli requests have never been tried, up from 10. The oldest has waited about 55 hours. Their agent and session pages aren't published.

**Why:**
1. **A false alarm in the secret scanner.** sase-core's `openai-key` rule has nothing anchoring the left side of `sk-`, so it reads the `sk-` inside ordinary `task-…` filenames as an OpenAI key. I checked every `sk-` match in bob-cli's run files since Nov 2: 9,615 matches, and all of them are inside words like `task-` or `…ask-`. None is a real key.
2. **Blocked requests never clear.** Each block is tied to the exact file contents, which will never change. The request is set aside without counting as a failed attempt, so it never gets retired. The background job then reports it as an error on every run.
3. **The error holds up the rest of bob-cli's queue.** `publication_job.py` stops at the first error. That skips the step that publishes requests without a "doorbell" hint (planner, `.land` and research runs), which is why the waiting queue keeps growing.

**Two smaller problems:**
- **Prompt-archive restore failures (23 entries).** A separate older bug that gives up after three tries; 13 more rows have been set aside since Nov 2.
- **GitHub SSH outage (57 entries).** From GitHub's Nov 4 SSH key ("publickey") incident, 04:37–06:23; it cleared on its own.

**Why nothing has fixed it:** neither the scanner rule nor the job code has changed since Nov 2, and no bead tracks a fix. `sase-1qh.7`, which was meant to clean up stuck rows, has been blocked since Oct 31.

**What would stop it:**
- **Quickest relief:** let the job keep going after an error instead of stopping. That alone would publish the 46 waiting requests and remove most of the noise.
- **Real fix:** tighten the rule in sase-core so a `sk-` inside a word doesn't count. Then re-check the 5 stored blocks through a reviewed process, because fixing the rule alone won't release them.

The registration succeeded: `file:explicit:2a0d9db945a33f7c1ef870e2`, labelled `research:202611/agent_publication_errors_still_occurring.md`. The research repo commit is submitted and lands once this turn ends.

Files are in sase/repos/research/202611:
- agent_publication_errors_still_occurring.md
