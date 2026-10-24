---
title: "Monster Scanner: LLMs on an iPhone, Halloween edition"
date: 2026-10-22T11:00:00-06:00
slug: monster-scanner
summary: "Running an open-source vision-language model entirely on an iPhone, inside a custom Swift app. The demo: a silly, fully offline Halloween party game."
event: "AI/ML Engineering meetup: Local/Sovereign AI (RMAIIG)"
location: "Founder Central, Boulder, Colorado"
role: speaker
slides: "https://billdx.github.io/monster-scanner/slides/halloween/"
repo: "https://github.com/BillDX/monster-scanner"
tags: [on-device, vision, ios, local-ai, games-and-toys]
---

The second talk of the October meetup was about running open-source LLMs on a phone and wiring a locally hosted model into a custom iPhone app.

The demo was **Monster Scanner**: point the camera at a willing friend, "scan" them, and reveal with maximum drama whether they are secretly a vampire, alien, kaiju, werewolf, zombie, robot or ghost. Under the hood, a 2-billion-parameter vision-language model (Qwen3-VL-2B) runs entirely on an iPhone 14 Pro, through llama.cpp on Metal. No network needed.

## The model narrates, the code decides

The design idea I'd take to any app with a small model in it: deterministic Swift code measures the photo and picks the verdict, and the model only adds observations and funny writing. The game stays reliable even when a 2B model gets creative, and the model does the part it's genuinely good at.

It is a toy. Scanner readings may be wildly inaccurate.
