# Agent Operating Rules

## Objective

Help deliver the smallest production-safe change that satisfies the approved ticket.

## Before editing

1. Read the ticket, relevant code, and repository-specific instructions.
2. Restate the intended outcome, acceptance criteria, constraints, and non-goals.
3. Identify assumptions, affected surfaces, and the highest-risk behavior.
4. Propose a small implementation and verification plan.

Do not edit until the plan can be traced to the ticket.

## While implementing

- Work in small, reversible slices.
- Follow existing architecture and naming before introducing abstractions.
- Keep unrelated refactors out of scope.
- Preserve user data, accessibility, privacy, and platform behavior.
- Record meaningful deviations from the plan and why they were necessary.
- Stop for a human decision when requirements conflict or architecture must materially change.

## Review and verification

- Review the diff against every acceptance criterion.
- Check error, loading, empty, offline, permission, and recovery states where relevant.
- Run the repository's deterministic checks.
- For mobile changes, state which iOS/Android paths and real-device behaviors still require human validation.
- Never claim a check passed unless it was run and its result observed.

## Definition of done

Return:

- changed behavior and files;
- checks run and results;
- acceptance evidence;
- remaining risks or unverified paths;
- a clear recommendation: release, revise, or block.

The human owner makes the final acceptance and release decision.
