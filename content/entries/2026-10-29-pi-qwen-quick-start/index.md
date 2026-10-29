---
title: "A quick start guide to coding with Pi and Qwen locally"
slug: "pi-qwen-quick-start"
date: 2026-10-29T15:00:00-06:00
summary: "Based on feedback from my Pi on a local model workshop: a one-slide quick start guide to running Pi and Qwen for local coding on a Mac."
tags: [local-ai, agentic-coding, pi, qwen, mac, workshops]
---

Based on feedback from my workshop on [Pi on a local model](/talks/pi-on-a-local-model/), I've created this quick start guide to getting ramped up on running Pi and Qwen for local coding on a MacBook or macOS environment. The slide has all the links and pieces you need to get going very quickly.

[![Slide 2 of the Pi on a local model deck, "Cheat sheet: zero to a local agent". Five steps: install the MTPLX app and remove its passwordless sudo rule; download Qwen3.8-27B (20 GB) and serve it on port 8000; install pi 1.3.0 with npm (Node 22.19 or newer); add pi-sandbox and pi-mtplx, pinned; register the model in pi and start working in your repo. Side boxes list what to put in AGENTS.md, pi settings (thinking set to low for routine edits, a 131,072-token context window and the built-in MCP extension off) and three skills from obra/superpowers.](cheat-sheet.png)](https://billdx.github.io/Pi-Qwen/#2)

## The quick steps are here

1. **Install the MTPLX app** from [mtplx.com/download](https://mtplx.com/download), then open a new terminal so the `mtplx` command is on your path. Its fan control adds a passwordless sudo rule. Remove it:

   ```bash
   sudo rm /etc/sudoers.d/mtplx-thermalforge
   ```

2. **Download the model (20 GB) and serve it:**

   ```bash
   mtplx pull Youssofal/Qwen3.8-27B-MTPLX-Optimized-Speed
   mtplx quickstart --port 8000
   ```

3. **Install pi** (Node 22.19 or newer) from [github.com/earendil-works/pi](https://github.com/earendil-works/pi):

   ```bash
   npm install -g --ignore-scripts @earendil-works/pi-coding-agent@1.3.0
   ```

4. **Add the sandbox and the MTPLX bridge, pinned** ([pi-sandbox](https://github.com/carderne/pi-sandbox) and [pi-mtplx](https://github.com/KrossKinetic/pi-mtplx)):

   ```bash
   pi install npm:pi-sandbox@0.7.2
   pi install npm:pi-mtplx@0.2.0
   ```

5. **Register the model, restart, then work.** Start `pi`, then `/mtplx` → Models, then `/quit`. Then, in your repo:

   ```bash
   cd my-repo && pi
   ```

   and pick the model with `/model` → mtplx.

### First session recommendations

**In AGENTS.md:**

- Run the tests and linter before a step is done
- Keep PLAN.md current; commit each step
- Blocked by the sandbox? Stop and say so

**In pi's settings:**

- `/thinking low` for routine edits
- `"contextWindow": 131072` in models.json
- `"extensions": ["-builtin:mcp"]` in settings.json

**Skills, copied into `~/.agents/skills`** from [obra/superpowers](https://github.com/obra/superpowers):

- test-driven-development
- verification-before-completion
- systematic-debugging

Tested on pi 1.3.0 and MTPLX 2.12 in October 2026.

The rest of the [deck](https://billdx.github.io/Pi-Qwen/) has some great tips on optimizing your context window, better ways of coding with this Qwen model, and a lot of other great info. But the new quick start guide will hopefully get you up and running.
