---
name: ipc-sender-check
description: Check that every Electron IPC handler in a PR validates its sender and payload
---

For each `ipcMain.handle` or `ipcMain.on` handler that the PR adds or changes:
1. It calls `requireTrustedSender` (from `frameValidation.ts`) and returns before any side effect when the frame is untrusted.
2. It checks the payload with a runtime type guard.
3. A new or changed preload method or channel bumps the shell IPC contract version.
4. `contextIsolation` and `sandbox` stay on; `nodeIntegration` and `@electron/remote` stay off.

Report each handler as pass or fail with the file, line and rule.
