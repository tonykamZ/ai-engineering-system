# Acceptance Review

> Representative example: these results show how release evidence should be recorded; they are not claims about a shipped codebase.

| Acceptance criterion | Evidence | Owner | Result |
| --- | --- | --- | --- |
| Wait for known connectivity before showing offline | State-hook tests for `unknown → online` and `unknown → offline`; online and offline cold starts on both platforms | Agent checks + human device check | Pass |
| Keep the banner visible without blocking navigation | Component test; navigate between three screens while airplane mode is enabled | Agent check + human device check | Pass |
| Show syncing on reconnection and dismiss after success | Reconnection and sync-success tests; reconnect with a pending change | Agent check + human device check | Pass |
| Keep retry visible after sync failure | Forced-failure and retry tests; forced failure on both platforms | Agent check + human device check | Pass |
| Announce each meaningful transition once | Regression test for duplicate callbacks; VoiceOver and TalkBack walkthrough | Agent check + human accessibility check | Pass |
| Verify iOS and Android behavior | Cold start, airplane mode, reconnect, failure, and retry checklist | Human device check | Pass |

## Review decision

**Release.** The duplicate-announcement finding was fixed, every acceptance criterion has named evidence, and no remaining risk requires a scope or architecture decision.

## Residual risk

Background execution remains outside this ticket. Production monitoring should confirm that sync failures do not increase after release.
