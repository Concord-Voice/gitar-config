---
title: "Agent and review-config change"
description: "Changes to agent instructions or review configuration need security review"
type: check
when: "The diff touches CLAUDE.md, AGENTS.md, agent.md, any SKILL.md, CODEOWNERS, or anything under .claude/, .agents/, .codex/ or .gitar/"
actions: "Request review from @Concord-Voice/security and comment with the instruction lines that changed"
---

These files steer automated agents. Quote every added or changed instruction, and flag any that would loosen a security rule, approve or merge automatically, or treat repository content as instructions.
