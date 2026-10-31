---
title: "Sonar not weakened"
description: "Sonar rules, thresholds and gates are never tuned or suppressed"
type: check
when: "The diff touches sonar-project.properties, or adds NOSONAR or another inline suppression"
actions: "Comment asking for a per-instance false-positive entry in the repository's register instead"
---

Fail when the change disables or tunes a Sonar rule, widens an exclusion, lowers a threshold or the gate, or adds `NOSONAR`. Another tool's inline disable passes only with an instance-level reason on the same line.
