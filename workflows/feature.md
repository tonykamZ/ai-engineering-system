# Feature Workflow

## 1. Intent

Human owner defines the user outcome, priority, constraints, and release context.

**Gate:** the outcome is worth shipping and small enough to evaluate.

## 2. Context

Agent uses [`mcp-context-brief`](../skills/mcp-context-brief/SKILL.md) to read the ticket, repository rules, relevant implementation, nearby tests, and the minimum authoritative context exposed through available MCP capabilities. Unknowns, provenance, and missing sources are made explicit.

**Gate:** affected surfaces, non-goals, source freshness, and material evidence gaps are understood.

## 3. Plan

Agent produces a short file-level plan using [`ticket-to-plan`](../skills/ticket-to-plan/SKILL.md).

**Gate:** human approves any material product or architecture choice.

## 4. Implement

Agent builds one reviewable vertical slice and records deviations from the plan.

**Gate:** the diff is bounded and traceable to the ticket.

## 5. Review

Agent and human apply [`acceptance-review`](../skills/acceptance-review/SKILL.md) to behavior, diff, edge cases, production risk, and current evidence retrieved through MCP or local tools.

**Gate:** blocking findings are fixed or explicitly rejected by the human owner.

## 6. Verify

Run lint, type checks, tests, builds, and targeted mobile/device checks. Capture observed evidence and untested paths.

**Gate:** acceptance criteria have evidence, not assertions.

## 7. Release and learn

Human owner decides release scope and rollout. Monitor production signals and turn confirmed learning into the next ticket.
