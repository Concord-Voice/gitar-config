---
name: ws-event-contract
description: Check that a change to a server WebSocket event stays compatible with the zod WebSocketEvent schemas the clients validate against
---

The contract is the zod `WebSocketEvent` discriminated union in `ws-events.ts` (Self-Hosted `packages/protocol/`, Desktop `desktop/src/renderer/types/`). Released clients validate every incoming event against it and drop anything that fails.

For each server event the PR adds, renames or reshapes:
1. Find the matching `type` in the union. A new event needs a schema entry and a dispatch handler in the same PR, or the clients drop it.
2. Removing or renaming an event or a required field breaks released clients. It needs a compatibility plan: keep the old shape until a minimum-version bump retires it.
3. New fields are optional in the schema until every supported client sends or reads them.
4. Handlers use the narrowed `Extract<WebSocketEvent, { type: ... }>` type, not `any`.
5. The schema test (`ws-events.test.ts`) covers the changed event.

Report each event as compatible or breaking, with the schema file and line.
