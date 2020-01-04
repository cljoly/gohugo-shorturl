---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: true
type: "shorturl"
shortto: "{{ getenv "HUGO_SHORTURL" }}"
---

