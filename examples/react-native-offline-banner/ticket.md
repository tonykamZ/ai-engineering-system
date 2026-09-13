# Ticket: Offline Sync Status Banner

## User outcome

People using the React Native app can tell when changes are waiting for connectivity and when syncing has resumed.

## Acceptance criteria

- Show an offline banner only after network state is known and confirmed offline.
- Keep the banner visible while offline without blocking navigation.
- On reconnection, show “Back online—syncing” and dismiss it after sync succeeds.
- If sync fails, keep a retry action visible.
- Screen readers announce each meaningful state change once.
- Behavior is verified on iOS and Android.

## Constraints

- Reuse the existing network and sync services.
- Do not add a second connectivity library.
- Do not redesign the global notification system.

## Non-goals

- Conflict-resolution UI.
- Background sync changes.
- New analytics events.
