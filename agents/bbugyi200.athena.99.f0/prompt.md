#gh:gh_sase-org__sase #fork:99 Will this fix what I'm seeing in my primary repo (random updates to the remote that revert the remote from the SSH remote to the HTTPS remote)? #if_not_plan 
```
bryan in 🌐 athena in plans on  main
❯ git remote remove origin

bryan in 🌐 athena in plans on  main
❯ git remote add origin git@github.com:sase-org/sase--plans.git

bryan in 🌐 athena in plans on  main
❯ git push -u origin main
branch 'main' set up to track 'origin/main'.
Everything up-to-date

bryan in 🌐 athena in plans on  main
❯ gr -v
origin  git@github.com:sase-org/sase--plans.git (fetch)
origin  git@github.com:sase-org/sase--plans.git (push)

bryan in 🌐 athena in plans on  main
❯ gr -v
origin  https://github.com/sase-org/sase--plans.git (fetch)
origin  https://github.com/sase-org/sase--plans.git (push)
```