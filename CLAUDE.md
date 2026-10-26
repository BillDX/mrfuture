# MrFuture.com: working agreement for Claude Code

This repo is **mrfuture.com**, Bill McIntyre's personal blog on AI/ML engineering, learning, and experiments. It's a Hugo site published to GitHub Pages on every push to `main`. You are helping Bill run it: drafting and editing posts, keeping the backlog moving, and maintaining the site.

The repo is **public**. Everything you commit is visible to anyone.

## Goals

1. **A lasting record of Bill's work** (talks, workshops, projects, experiments) that's better than LinkedIn posts that scroll away.
2. **Evidence for people hiring**: dated, concrete, honest. A hiring manager skimming a page should come away clearer, not distracted.
3. **A learning log**, in the spirit of Simon Willison's weblog: what was tried, what happened, what surprised. Small and frequent beats polished and rare.
4. **Fun**: toys, games, robots and the pulp-magazine look belong here too.

## Voice and authorship

- **Bill writes every post**, first person. Plain, specific English; honest about what broke. No emoji.
- **Never invent facts** about Bill, his work, dates, events, numbers or opinions. Use only sources he gives you (his repos, decks, notes, LinkedIn posts) and say what you used.
- **Any prose you draft in Bill's voice gets `review: true`** in its front matter. The deploy refuses to publish while that line exists, so nothing goes out unread. Only Bill removes it.
- The About page says: "The writing here is mine. When I use AI tools on a post, I say how." Keep that true.

## Theme (keep it, but keep it small)

- The look is a 1950s pulp science magazine reporting on today's real AI ("1955's idea of 2026"). The emotional range is wonder, unease and fun, with earned optimism. Touchstones: Bradbury's "The Toynbee Convector"; Alan Kay's "The best way to predict the future is to invent it."
- **Mr Future** is a silent mascot, a household appliance of tomorrow. Never draw, name or quote him on the site. His presence is the appliance-catalogue flavor of small labels (BROADCAST, INVENTION, SERVICE BULLETIN, BACK ISSUES).
- **Content first.** Design elements stay small. On a desktop the first screen must show several posts. If a decorative element pushes posts below the fold, it's too big.
- Navigation stays plain (Talks, Projects, Inside Voice, About). Pulp words go in kickers only.
- **Inside Voice** (free private Mac dictation) stays prominent: the home-page strip, a menu link, and its own page at `/inside-voice/`.

## Repo map

| Path | What |
|---|---|
| `content/<type>/` | Posts. Types: `entries` (Feature), `notes` (Transmission), `links`, `talks` (Broadcast), `projects` (Invention), `til` (Service bulletin), `community` |
| `content/about.md`, `content/projects/inside-voice.md` | About page; Inside Voice page (`layout: product`) |
| `archetypes/` | Templates used by `hugo new content` |
| `layouts/` | Hugo templates (new layout system: `baseof.html`, `home.html`, `page.html`, `section.html`, `_partials/`) |
| `assets/css/` | `tokens.css` (generated, never hand-edit), `main.css` (site styles), `fonts.css`, `syntax.css` |
| `assets/data/quotes.csv` | Footer quotes; `footer=yes` rows rotate |
| `design/` | Copy of the Toynbee Convector design-system tokens and README |
| `static/icons/` | The design system's 24 spot-art SVGs |
| `docs/HOW-TO.md` | Bill's how-to guide (posting and running the site) |
| `.github/workflows/deploy.yml` | Build and deploy (pinned actions, checksum-verified Hugo) |

## Commands

```bash
hugo server -D                                   # preview at http://localhost:1313, drafts included
hugo new content notes/2026-10-30-short-name.md  # new post from the archetype (title and slug come from the name)
HUGO_ENVIRONMENT=production hugo --gc --minify --panicOnWarning   # the same build CI runs; must pass
grep -rlE '^review:[[:space:]]*true' content     # pages still waiting for Bill's review
gh run watch                                     # follow a deploy after a push
```

## Writing posts

- File names start with the date: `2026-10-30-short-name.md`. Set `summary:` (one line for lists, feeds and link previews) and reuse existing tags where possible.
- Talks: `event`, `location`, `role` (speaker | workshop | panelist | host | organizer | mentor), `slides`, `repo`, `video`. Projects: `status`, `repo`, `download`, optional `icon`. Links: `link_url`.
- Images: make the post a folder (`entries/2026-10-30-name/index.md`) with the image beside it; always write alt text.
- Markdown only. Raw HTML is switched off.
- Future-dated posts stay hidden until a deploy after that date.

## Design and code rules

- Colours, type, spacing and shadows come from CSS variables in `tokens.css`. No literal colours in `main.css`.
- The site's security policy forbids inline `style=` attributes, inline `<script>`, and anything loaded from another domain. Fonts are self-hosted. Prefer no JavaScript; if essential, one small file in `static/js/`, and the page must work without it.
- Spot art comes only from `static/icons/` (the design system). New icons get drawn in the design system first, then copied here.
- Text at 4.5:1 contrast or better; 2px atomic-teal focus ring; animations under 0.7s and off under `prefers-reduced-motion`.
- Check every visual change at desktop and 390px phone width: no sideways scrolling. Show Bill a screenshot before committing design changes.

## Safety rules

- **Never push without Bill saying so.** Before any push: run the production build, confirm no `review: true` pages (unless Bill wants them held back), and show `git status` and a summary of the diff.
- Never commit secrets, tokens, personal email addresses, or account details. Commits use `BillDX@users.noreply.github.com`.
- Never touch DNS, IONOS, GitHub Pages settings or the custom domain from here. Those changes go through Bill.
- When bumping Hugo, update `HUGO_VERSION` and `HUGO_SHA256` together from Hugo's official checksums file. Keep actions pinned to full commit SHAs.

## Planning docs

Bill's planning docs live **outside this repo**, in a private folder (path in `CLAUDE.local.md`): `PLAN.md`, `PROGRESS.md`, `post-backlog.csv`, `chronology-seed.csv`, `linkedin-timeline.csv`, `MR-FUTURE-CHARACTER.md`, `ionos-dns-snapshot.csv`.

- Read `PROGRESS.md` (latest entries) and `post-backlog.csv` at the start of planning or writing work.
- After meaningful work, add a dated entry to `PROGRESS.md` and update `PLAN.md` if a decision changed. Keep the two in sync. Update backlog statuses as posts move (idea → drafted → published).
- Never copy anything from those docs about accounts, DNS, IONOS or other domains into this repo.
- Bill prefers simple open formats: Markdown and CSV.
