---
name: e2ee-check
description: Trace a PR's change through the Concord Voice end-to-end encryption path and report any point where plaintext could reach a server
---

The repository's `.claude/rules/domains/e2ee.md`, where present, is the source of truth; follow it over this list.

For each changed function that creates, sends, stores, receives or renders a message, attachment, media frame or key:
1. Trace it from the sender's key generation or encryption call to persistence and back to decryption. Name every file on the path.
2. Plaintext never leaves the client. Flag any send, log, cache or server-side field that could hold plaintext or key material.
3. No opt-out, fallback or `isEncrypted`-style branch on encryption status.
4. Minimums hold: AES-256-GCM, RSA-OAEP 4096, ECDH P-384+, Argon2id; CSPRNG only. No new crypto library.
5. Key epochs: writes stamp the epoch the client attests; reads decrypt with the labelled epoch; a key served for another epoch is refused.

Report the traced path, then each finding with file, line and the rule it breaks. Say "no plaintext exposure found" only when every step was traced.
