---
title: "Public repository hygiene"
description: "No other comms product names or internal details in public repositories"
type: check
when: "Any push to a PR in Self-Hosted, Desktop, Concord-Voice, concordvoice-com, Agentic-Dev-Tooling, The-Bazaar, .github or gitar-config"
actions: "Comment listing each offending line"
---

Check added lines, the PR title and the PR body. Fail on:
1. The name of any other real-time communications, chat or video-meeting product. Suggest "major comms platforms" or a description of the behavior.
2. Internal hostnames, private repository names other than Concord-Voice-Alpha, or links into private repositories.
