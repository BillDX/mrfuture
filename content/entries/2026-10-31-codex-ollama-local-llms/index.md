---
title: "Codex + Ollama: an easier route to coding with local LLMs"
slug: "codex-ollama-local-llms"
date: 2026-10-31T08:30:00-06:00
summary: "I reran my COLD STORAGE local-coding adventure game experiment with Codex and Ollama, using gpt-oss-20b and DeepSeek V4.1 Flash. I used an identical prompt for each and came up with comparable results and an easier path to local coding for people not as familiar with CLI."
tags: [local-ai, agentic-coding, codex, ollama, gpt-oss, deepseek, qwen, games-and-toys]
---

To double down on local-LLM coding experiments, I wanted to try out different, and possibly simpler approaches, so I recreated the Halloween-themed [COLD STORAGE](/projects/cold-storage/) text adventure game locally using Codex plus the gpt-oss-20b model, with the same initial prompt that I used for the [Pi/Qwen experiment](/talks/pi-on-a-local-model/). Using Ollama as the host and bridge to Codex was a breeze to set up, and this route might be much easier for folks not entirely comfortable with the command line.

It produced a playable, modestly funny, solvable/winnable [text adventure game - "Much Colder Storage"](https://github.com/BillDX/MuchColderStorage) with passing tests, though it took a few nudges.  eg: after the first prompt, seeing an empty directory, I had to ask where the files were, and then prompt the model to actually save the files to disk. The game is smaller (number of rooms and puzzles) than the one produced by Qwen, with seven sparse rooms, a short chain of puzzles, and not quite as much humor. One exit also crashes the game, a bug its initial tests missed.  But it worked, was funny-ish, and ultimately did what I asked it to as working code.

For a slightly different comparison, I also used Codex and Ollama to bridge to an Ollama-hosted open-weight DeepSeek V4.1 Flash model, which would have been too large for me to host locally, and gave it the same initial prompt. It also produced a fully working [haunted data center game - "Colder Storage"](https://github.com/BillDX/ColderStorage) and appropriate documentation right from a single-shot prompt, in about three minutes, with some jokes, funny descriptions, and solvable puzzles.

[![Three terminal windows showing how each game opens. COLD STORAGE, by Qwen3.8 27B with Pi: an ASCII-art title, "© 1987, ∞ Spectral Software", a paragraph of setup about a junior sysadmin sealed inside a data center that has been offline since 1987, and a detailed office with a hollow trophy and a laptop at 3% battery. ColderStorage, by DeepSeek V4.1 Flash with Codex: an ASCII-art title, a setup with jokes such as "The alarm has opinions", a command list, and a detailed reception room. MuchColderStorage, by gpt-oss-20b with Codex: a two-line welcome, then, after typing look, one sentence about a dimly lit entrance hall with a flickering "Welcome Back" sign.](same-prompt-openings.png)](same-prompt-openings.png)

*Same prompt, three opening screens, from each game's real output.*

The Qwen and DeepSeek versions both independently created a ghost sysadmin character with unfinished earthly data center business, to be completed as one of the puzzles. The Qwen model produced the longest, largest world, and arguably the funniest version, but all three versions were playable, enjoyable (in a 1980s style text adventure way), and most importantly, working code that did the job.

[![Two terminal windows. In COLD STORAGE, the player walks into the server room and meets Bernard, a translucent sysadmin in a short-sleeved dress shirt, who says of the missing backup tapes, "I left them where I left my life: one where I laughed, one where I didn't, one in a trophy I didn't deserve." In ColderStorage, the player meets Mortimer Cache, a sysadmin ghost who "died waiting for a change ticket to close", and who says, "I require COFFEE. Then I will share the root password. It has not changed since 1998. Neither has management."](ghost-sysadmins.png)](ghost-sysadmins.png)

*The two ghost sysadmins: Qwen's Bernard and DeepSeek's Mortimer Cache.*

For experienced CLI-native coders, I do find the Qwen3.8 and Pi combo to be the most familiar, but for folks starting out in these adventures, Codex and gpt-oss-20b is a genuinely great way to get started with fully local AI coding and development.
