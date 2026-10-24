---
title: "{{ replace (replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName) "-" " " | title }}"
slug: "{{ replaceRE `^\d{4}-\d{2}-\d{2}-` "" .File.ContentBaseName }}"
date: {{ .Date }}
draft: true
summary: "The note itself, if it fits in a sentence or two."
tags: []
---
