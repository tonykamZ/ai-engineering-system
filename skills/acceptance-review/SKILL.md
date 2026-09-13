---
name: acceptance-review
description: Review a proposed change against its ticket, mobile edge cases, and release risk, then produce an evidence-based decision.
---

# Acceptance Review

Read the ticket, approved plan, diff, and available check results.

Review in this order:

1. map each acceptance criterion to code and observed evidence;
2. identify behavior outside the approved scope;
3. inspect loading, error, empty, offline, permission, retry, and recovery paths where relevant;
4. inspect iOS and Android differences, accessibility, lifecycle, and performance risk;
5. distinguish verified facts from assumptions and unrun checks.

Report findings by severity with a concrete failure scenario and smallest safe fix. End with one recommendation: **release**, **revise**, or **block**. The human owner makes the final decision.
