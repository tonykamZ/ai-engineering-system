# Implementation Plan

## Outcome and risk

Add a global, non-blocking sync status banner. The highest risk is showing a false offline state during startup before the connectivity service returns its first value.

## Slices

1. Model connectivity as `unknown | online | offline` using the existing service.
2. Derive banner state from connectivity and sync state in one hook.
3. Render the banner in the existing application shell with accessible announcements.
4. Add focused tests for startup, disconnect, reconnect, success, failure, retry, and repeated events.
5. Verify the affected flows on iOS and Android devices.

## Checks

- Existing lint, type-check, test, and build commands.
- Cold start online and offline.
- Toggle airplane mode while a change is pending.
- Reconnect with sync success and forced failure.
- VoiceOver and TalkBack announce transitions once.

## Rollback

Remove the banner integration while leaving the existing network and sync services unchanged.
