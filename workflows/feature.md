# Feature Workflow

## 1. Intent

Human owner defines the outcome, priority, constraints, completion boundary, and release context. Describe observable acceptance rather than prescribing implementation mechanics unless the mechanics are required.

**Gate:** the outcome is worth shipping and small enough to evaluate.

## 2. Context

Agent reads the request, repository rules, and task-relevant implementation, docs, and tests. Use [`mcp-context-brief`](../skills/mcp-context-brief/SKILL.md) only when material facts live in external systems. Unknowns, provenance, and missing sources are made explicit when they affect a decision.

**Gate:** affected surfaces, non-goals, source freshness, and material evidence gaps are understood.

## 3. Plan

When planning is requested or required by an unresolved choice, the agent produces a short file-level plan using [`ticket-to-plan`](../skills/ticket-to-plan/SKILL.md).

**Gate:** human approves any material behavior or architecture choice.

## 4. Implement

Agent builds one reviewable vertical slice and records material deviations from the plan. When execution is authorized, continue through relevant review, verification, and repair of in-scope failures instead of stopping after the first implementation pass.

**Gate:** the diff is bounded and traceable to the request or ticket.

## 5. Review

When release readiness is being evaluated, agent and human apply [`acceptance-review`](../skills/acceptance-review/SKILL.md) to behavior, diff, relevant edge cases, production risk, and current evidence.

**Gate:** blocking findings are fixed or explicitly rejected by the human owner.

## 6. Verify

Run the smallest relevant lint, type, test, build, integration, or environment checks that establish the acceptance criteria. Expand checks when risk or observed failures justify it. Capture observed evidence and untested paths.

**Gate:** acceptance criteria have evidence, not assertions.

## 7. Release and learn

Human owner decides release scope and rollout. Monitor production signals and turn confirmed learning into the next request or ticket.
