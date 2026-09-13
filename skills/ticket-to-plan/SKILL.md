---
name: ticket-to-plan
description: Turn an approved mobile feature or bug ticket into a small, executable implementation and verification plan.
---

# Ticket to Plan

Read the ticket, repository instructions, and relevant code before proposing work.

Return a concise plan containing:

1. intended user outcome;
2. acceptance criteria in observable language;
3. assumptions, non-goals, and open decisions;
4. affected files or system boundaries;
5. ordered implementation slices;
6. checks for success, failure, recovery, and platform-specific behavior;
7. the highest-risk point and a rollback approach.

Prefer existing patterns and the smallest complete slice. Do not invent requirements or hide uncertainty. Ask for a human decision when an unresolved choice would materially change product behavior or architecture.
