---
name: new-post
description: Start a new MrFuture.com post (note, link, entry, talk, project, til or community) from sources Bill provides, as a draft marked for his review.
argument-hint: "[type] [short-name] [sources or notes]"
---

Create a new post for MrFuture.com.

Arguments: $ARGUMENTS (post type, a short name for the file, and any sources or notes).

1. If the type, topic or sources are unclear, ask Bill one short question first.
2. Create the file with `hugo new content <type>/<YYYY-MM-DD>-<short-name>.md` (today's date in America/Denver).
3. Fill the front matter: title, `summary` (one line), reused tags, and the type's fields (see CLAUDE.md). Keep `draft: true`.
4. Write the body in Bill's voice **only from the sources given** (his repos, decks, notes, LinkedIn posts). Never invent facts, numbers, dates or opinions. If something is missing, leave a clearly marked `[Bill: …]` note instead of guessing.
5. Add `review: true` to the front matter whenever you wrote prose.
6. Run `hugo server -D` (or a production build) and confirm the page renders; give Bill the local URL.
7. If the post is in `post-backlog.csv` in the planning folder, set its status to `drafted`.
8. Report: file path, what sources you used, and anything Bill needs to fill in. Don't commit or push.
