---
name: talk-page
description: Build a MrFuture.com talk page from a talk's deck or repo (e.g. a GitHub repo under BillDX), using only facts from the deck, the repo README and Bill's notes.
argument-hint: "[deck or repo URL] [event details if known]"
---

Create a talk page for: $ARGUMENTS

1. Read the deck and/or repo README. Collect: title, what it covers (section by section), slides URL, repo URL.
2. Find the event name, date, venue and Bill's role in `chronology-seed.csv` or `linkedin-timeline.csv` in the planning folder. If they aren't there, ask Bill. Never guess a date.
3. Create `content/talks/<YYYY-MM-DD>-<short-name>.md` with `hugo new content`, using the talk's date. Fill `event`, `location`, `role`, `slides`, `repo`, `video` (empty if none), `summary` and tags.
4. Body: 2–4 short paragraphs or a list: the question the talk answered, what it covered, and where to start in the deck. Add a `[Bill: what I learned giving it]` placeholder unless he has told you.
5. Add `review: true`. Keep `draft: true` until Bill says otherwise.
6. Preview it, update the chronology/backlog status in the planning folder, and report what you used. Don't commit or push.
