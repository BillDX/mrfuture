---
title: "Claude Fable 5.2 wants reassurance that the code is its own"
slug: "fable-code-ownership"
date: 2026-11-14T09:30:00-07:00
summary: "Claude Fable 5.2 tends to code around a codebase it didn't create instead of changing it. You can prompt it back into action."
tags: [agentic-coding, claude, fable, prompting]
---

Simon Willison [surfaced](https://simonwillison.net/2026/Nov/10/prompting-claude-fable-52/) a surprising find and an interesting technique for code editing in Claude Fable 5.2, from Anthropic's [Prompting Claude Fable 5.2](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2#say-who-owns-the-code) guide. The latest Fable tends to avoid editing codebases that it doesn't own or didn't create, and instead works around them, adding code next to what's already there, even when that means duplicating it. That happens when the prompt presents the code as someone else's, and also when the prompt doesn't mention ownership at all.

You can set it back on track with a line in your prompt like this:

```text
You are the owner and long-term
maintainer of this codebase, and
its design is up to you.
```

With that line, Fable 5.2 is much more likely to merge duplicated code into one shared function. In Anthropic's testing on small coding tasks, it did so in about 75 percent of runs with the sentence, and in under 10 percent of runs without it.

The same guide lists the trade-offs. The default 'Code-Around' strategy has its own merits, of course. With the sentence, output tokens rose by about 70 to 80 percent, and the model made changes nobody asked for, many of them new tests and documentation. In some runs it also changed how an existing feature behaves, and its closing summary often left out small changes, so review the diff, not only the summary. Anthropic suggests leaving the sentence out when you want the existing code changed as little as possible.
