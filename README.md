# MrFuture.com

Source for [mrfuture.com](https://mrfuture.com): Bill McIntyre's personal blog on AI/ML engineering, learning, and experiments.

Built with [Hugo](https://gohugo.io) and published to GitHub Pages. The look comes from the Toynbee Convector design system.

## Run it on your Mac

```bash
brew install hugo          # any recent version; the site is built in CI with 0.167.0
hugo server -D             # then open http://localhost:1313
```

`-D` also shows drafts. Pages marked `review: true` show a yellow "Proof copy" banner.

## Write something

Each kind of post is a folder under `content/`, and each has a template (an "archetype") with the right fields:

```bash
hugo new content notes/my-note.md
hugo new content links/some-article.md
hugo new content entries/what-i-learned.md
hugo new content talks/my-talk.md
hugo new content projects/my-project.md
hugo new content til/a-small-thing.md
hugo new content community/a-meetup.md
```

New files start as `draft: true`. Remove that line (or set it to `false`) when it's ready.

| Folder | Shown as | Address |
|---|---|---|
| `entries` | Feature | `/2026/10/slug/` |
| `notes` | Transmission | `/2026/10/slug/` |
| `links` | Recommended reading | `/2026/10/slug/` |
| `talks` | Broadcast | `/talks/slug/` |
| `projects` | Invention | `/projects/slug/` |
| `til` | Service bulletin | `/til/slug/` |
| `community` | Community | `/community/slug/` |

Useful front matter: `summary` (one line for lists, feeds and link previews), `tags`, `slug`, and for talks `event`, `location`, `role`, `slides`, `repo`, `video`. Projects take `status`, `repo`, `download`, `featured`, `icon`.

## Publishing

Pushing to `main` builds and deploys the site with GitHub Actions (`.github/workflows/deploy.yml`).

**The build refuses to publish while any page has `review: true`.** That flag marks text drafted for Bill that he hasn't approved yet. Read the page, rewrite what needs it, then delete the line.

Drafts stay on your Mac until they're ready: this repo is public, so anything pushed, even to a branch, can be seen and stays in the history.

## Design

- `design/toynbee-convector.tokens.json` is a copy of the design system's tokens. After updating it, run `python3 scripts/tokens_to_css.py` to regenerate `assets/css/tokens.css`. Don't edit `tokens.css` by hand.
- Site styles are in `assets/css/main.css`; templates are in `layouts/`.
- Spot-art icons in `static/icons/` come from the design system.
- Footer quotes rotate per page from `assets/data/quotes.csv` (rows with `footer` = `yes`).
- Themes: each colour theme in the tokens file becomes a `[data-theme="…"]` block. Only "Pulp" exists today.

## Security

- No server code, database, logins, comments, trackers or third-party scripts.
- Fonts are self-hosted, so the site makes no requests to anyone else.
- A strict Content-Security-Policy is set in each page (GitHub Pages can't send headers), and the stylesheet carries a Subresource Integrity hash.
- Markdown can't contain raw HTML (`unsafe = false`).
- The deploy workflow pins every action to a commit SHA, checks Hugo against a pinned SHA-256, uses no secrets, and has only the permissions Pages needs. Dependabot proposes action updates.
- Never commit secrets. `.gitignore` blocks the common files.

## Licenses

- Fonts: Big Shoulders Display, Old Standard TT and Courier Prime, under the SIL Open Font License (`static/fonts/LICENSE-*.txt`).
- Writing and images: © Bill McIntyre, all rights reserved, until a license is chosen.
