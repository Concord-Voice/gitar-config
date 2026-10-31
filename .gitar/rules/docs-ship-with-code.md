---
title: "Docs ship with code"
description: "Changed contracts come with their doc updates in the same PR"
type: check
when: "The diff changes an API route, WebSocket or Socket.IO event, database migration, CLI flag, environment variable or config key"
actions: "Comment naming the doc that describes the changed contract"
---

Pass only if the same PR updates the docs that describe the changed contract. A follow-up issue does not count.
