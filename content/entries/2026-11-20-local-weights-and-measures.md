---
title: "Dec 10 in Boulder: Local Weights & Measures"
slug: "local-weights-and-measures"
date: 2026-11-20T07:30:00-07:00
summary: "On December 10 I'm hosting the AI/ML Engineering meetup in Boulder: three mini demos that open up model weights, from LLM mind reading to LoRA remixing."
tags: [local-ai, qwen, community, model-weights, lora]
---

On Thursday, December 10, I'm hosting the AI/ML Engineering meetup (an RMAIIG subgroup) in Boulder: **Local Weights & Measures: LLM Mind Reading, Brain Surgery, and LoRA Remix**.

- **When:** Thursday, December 10, 9:00 to 11:00 AM MST
- **Where:** Founder Central by Sweater, 2000 Central Ave #100, Boulder, CO 80301
- **RSVP:** [on Meetup](https://www.meetup.com/ai-ml-engineering-aie-an-rmaiig-subgroup/events/317474262/)

Usually we treat model weights as a black box: billions of numbers we download and never look at. This month we open the box with three mini demos.

**LLM Mind Reading.** A [recent MIT paper](https://rikiyat.github.io/blog/weight-space-programming/) had LLMs work out what small neural networks were trained to do just by reading their raw weights, and [Simon Willison replicated it](https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/) with a local model on his laptop. How does that work, and what are the limits?

**LLM Brain Surgery.** In the same paper, GPT-6 Astra found what was sending a small Qwen model into reasoning loops, and fixed it by editing 0.016% of its weights. We'll look at what was actually changed, and how to check for edits like that yourself.

**LLM LoRA Remix** (time permitting). LoRAs as a mixing board. We'll mix, subtract and turn up adapters live on image and text models.
