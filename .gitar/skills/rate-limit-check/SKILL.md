---
name: rate-limit-check
description: Check that every media-plane Socket.IO client event in a PR is registered through withRateLimit and treats its payload as untrusted
---

The repository's `.claude/rules/domains/media-plane.md`, where present, is the source of truth; follow it over this list.

For each Socket.IO handler the PR adds or changes under `services/media-plane/`:
1. A client event is registered through `withRateLimit` (`src/lib/rateLimit.ts`). A bare `socket.on` for a client event is a finding.
2. The payload is validated before use. Room and user identity come from authenticated socket state, never from the payload.
3. The handler does not add a per-room or per-message encryption flag; DTLS-SRTP is structural.
4. Error paths do not echo payload contents, tokens or internal state back to the client or into logs.

Report each handler as pass or fail with file, line and rule.
