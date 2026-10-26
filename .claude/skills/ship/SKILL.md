---
name: ship
description: Check, commit and publish MrFuture.com changes to mrfuture.com, then confirm the deploy and log it.
disable-model-invocation: true
argument-hint: "[short description of the change]"
---

Publish the current changes: $ARGUMENTS

1. `git pull` so the branch is current.
2. Run the production build: `HUGO_ENVIRONMENT=production hugo --gc --minify --panicOnWarning`. Stop and report if it fails.
3. List pages still marked `review: true` and pages with `draft: true` that are changing. Ask Bill whether each should go out; the deploy will refuse while any `review: true` remains.
4. Scan the diff for secrets, tokens, email addresses, and account or DNS details. Stop if you find any.
5. Show `git status` and a short summary of the diff. Commit with a clear message, author email `BillDX@users.noreply.github.com`.
6. **Ask Bill before pushing.** After he agrees, `git push`, then `gh run watch` until the deploy finishes.
7. Open the changed pages on https://mrfuture.com and confirm they load.
8. Add a dated entry to `PROGRESS.md` in the planning folder (what shipped, link), and update `post-backlog.csv` statuses to `published`.
