---
title: "Codex + Ollama: an easier route to coding with local LLMs"
slug: "codex-ollama-local-llms"
date: 2026-10-31T08:30:00-06:00
summary: "I reran my COLD STORAGE local-coding adventure game experiment with Codex and Ollama, using gpt-oss-20b and DeepSeek V4.1 Flash. Same prompt, three working haunted data center games, and a path to local coding that's friendlier to anyone who shies away from the command line."
tags: [local-ai, agentic-coding, codex, ollama, gpt-oss, deepseek, qwen, games-and-toys]
---

To expand my local-LLM coding experiments, I recreated the [COLD STORAGE](/projects/cold-storage/) local coding experiment using Codex plus the gpt-oss-20b model, with the same initial prompt as the [Pi/Qwen experiment](/talks/pi-on-a-local-model/). Using Ollama as the host and bridge to Codex was very easy, and this route might be much easier for folks not entirely comfortable with the command line.

It produced a winnable [text adventure game](https://github.com/BillDX/MuchColderStorage) with passing tests, though it took a few nudges: after the first prompt, I had to ask where the files were, and then ask it twice to actually save them to disk. The game is much smaller than the one produced by Qwen, with seven sparse rooms, a short chain of puzzles, and not much humor. One exit also crashes the game, a bug its tests missed.

For a middle comparison, I also used Codex and Ollama to bridge to an Ollama-hosted open-weight DeepSeek V4.1 Flash model, which would have been too large for me to host locally. It produced a fully working [haunted data center game](https://github.com/BillDX/ColderStorage) and appropriate documentation right from a single-shot prompt, in about three minutes, with some jokes, funny descriptions, and solvable puzzles.

The Qwen and DeepSeek versions both independently used a ghost sysadmin character with unfinished earthly data center business, to be completed as one of the puzzles. The Qwen model produced the longest, largest world, and arguably the funniest version, but all three versions were enjoyable, and most importantly, working code that did the job.
