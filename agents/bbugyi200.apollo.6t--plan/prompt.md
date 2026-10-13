#gh:gh_sase-org__sase Why are we showing `gh_bbugyi200__job` instead of `job` which matches this sase
project's `PROJECT_NAME`? Can you help me fix this? See the
~/tmp/screenshots/20261011_124955.png screenshot and the command output below for
context. Think hard about your fix, add validation to make sure that the raw project
direction / `*.sase` filename is never shown to a user, and then add an appropriate
decision memory web strand that records this decision.

#plan %m:@xlarge

```
❯ bat ~/.sase/projects/gh_bbugyi200__job/gh_bbugyi200__job.sase
─────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
     │ File: /home/bryan/.sase/projects/gh_bbugyi200__job/gh_bbugyi200__job.sase
─────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
   1 │ RUNNING:
   2 │   #10 | 3837958 | ace(run)-261011_124800 | gh_bbugyi200__job | 20261011124800
   3 │   #0 | 3840340 | ace(run)-261011_124813 | gh_bbugyi200__job | 20261011124813
   4 │   #0 | 3840395 | ace(run)-261011_124816 | gh_bbugyi200__job | 20261011124816
   5 │   #11 | 3838343 | ace(run)-261011_124804 | gh_bbugyi200__job | 20261011124804
   6 │   #0 | 3840848 | ace(run)-261011_124818 | gh_bbugyi200__job | 20261011124818
   7 │   #12 | 3838412 | ace(run)-261011_124806 | gh_bbugyi200__job | 20261011124806
   8 │   #13 | 3838882 | ace(run)-261011_124809 | gh_bbugyi200__job | 20261011124809
   9 │   #14 | 3839592 | ace(run)-261011_124811 | gh_bbugyi200__job | 20261011124811
  10 │
  11 │
  12 │ WORKSPACE_DIR: /home/bryan/projects/github/bbugyi200/job/
  13 │ PROJECT_NAME: job
─────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
```