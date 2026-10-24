---
title: "{{ replace (replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName) "-" " " | title }}"
slug: "{{ replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName }}"
date: {{ .Date }}
draft: true
summary: "One sentence for lists, feeds and link previews."
tags: []
---

What I tried, what happened, what surprised me.
