---
title: "Conventional PR title"
description: "PR titles are bare Conventional Commits, because the title becomes the squash commit subject"
type: check
when: "A PR is opened or its title changes"
actions: "Comment with a corrected title when the check fails"
---

The title must match `type: summary` with no `(scope)`. Allowed types: feat, fix, chore, docs, test, refactor, ci, build, style, perf.
