---
title: "COLD STORAGE: a haunted data center adventure"
date: 2026-10-22T08:00:00-06:00
slug: cold-storage
summary: "An Infocom-style text adventure in Python, written entirely by a local model on a 16GB MacBook Pro. No cloud APIs in the loop."
status: shipped
repo: "https://github.com/BillDX/coldstorage"
tags: [local-ai, agentic-coding, qwen, pi, games-and-toys]
---

An anonymous client bought an abandoned data center off the internet and hired you to fix its servers. The blast door sealed behind you. The building has been offline since the Great Outage of 1987, and the night shift, apparently, was never relieved. Your job: do your job, survive the hauntings, and get out.

COLD STORAGE was built for the [local and sovereign AI workshop](/talks/pi-on-a-local-model/). The point was to show what a model running on an ordinary laptop can make: a MacBook Pro (M3) with 16GB of RAM, running Qwen3.8 27B, steered by me through the Pi coding harness with a few sandbox safety add-ons and a minimal AGENTS.md and skills setup to leave room for context.

It's an old Infocom-style text adventure. While I didn't use the now open-sourced Infocom parser, the grammar and everything works a lot like it. I think the most interesting part of the build was having the Pi agentic harness playtest every option and solution, to make sure every puzzle that was added is solvable and ultimately leads to a successful exit from the haunted data center.

The design, code, tests, debugging and even the jokes came from the model on the laptop.
