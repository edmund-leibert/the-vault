---
title: 🗒️ Java
created: 2023-08-24 19:30
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/java
  - 🔴-academic/📚-educational-resource/discipline/computer-science/programming-language/java
  - study-note
cards-deck: Default::Computer Science
updated: 2024-04-14T00:24
---

, I am referring to the context of environment variables.
#anki-card 
In the context of `%JAVA_HOME%/bin`, the `%JAVA_HOME%` part is a placeholder for the value of the `JAVA_HOME` environment variable in Windows.

When configuring my environment variables, how should I configure it to support Java?
#anki-card 
- Configure `$env:JAVA_HOME` to point to the `java`, _not_ `java/bin`, folder.
- Configure`$env:PATH` to include `%JAVA_HOME%/bin`.

---

## 🔜 Next Note(s):

---



