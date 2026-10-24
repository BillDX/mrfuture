---
title: "{{ replace (replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName) "-" " " | title }}"
slug: "{{ replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName }}"
date: {{ .Date }}
draft: true
summary: "One sentence: what it is."
status: active   # active | shipped | paused | archived
repo: ""
download: ""
tags: []
---

What it is, why I built it, and what I learned.
