---
title: "{{ replace (replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName) "-" " " | title }}"
slug: "{{ replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName }}"
date: {{ .Date }}
draft: true
summary: "One sentence: what the talk was about."
event: ""
location: ""
role: speaker   # speaker | workshop | panelist | host | organizer | mentor
slides: ""
repo: ""
video: ""
tags: [talks]
---

What I covered, and what I learned giving it.
