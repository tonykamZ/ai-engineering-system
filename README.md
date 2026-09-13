# AI Engineering System

Portable agent skills and repository rules for running a human-gated mobile engineering workflow on top of MCP.

This repository is the orchestration layer—not another AI-generated demo app. MCP supplies access to tools and context; the files here define how an agent scopes work, uses those capabilities, verifies the result, and returns decisions to a human owner.

`Human intent → AGENTS.md → Portable skill → MCP capabilities → Evidence → Human gate`

[See how this system fits into my mobile engineering workflow](https://tonykam-portfolio.vercel.app/).

## The layers

| Layer | Responsibility |
| --- | --- |
| Human | Owns product intent, architecture exceptions, acceptance, release, and rollback. |
| `AGENTS.md` | Sets repository-wide boundaries, evidence rules, and escalation points. |
| Portable skills | Encode repeatable methods for context, planning, and review without naming a vendor or server. |
| MCP | Exposes current tickets, docs, designs, source systems, CI evidence, and approved actions at runtime. |
| Checks and devices | Produce observable evidence through tests, builds, previews, accessibility checks, and real-device validation. |

Tool availability is not authorization. A skill decides what capability is relevant; the user and repository rules decide what the agent may do.

## Portable package

```text
AGENTS.md
skills/
  mcp-context-brief/
    SKILL.md
  ticket-to-plan/
    SKILL.md
  acceptance-review/
    SKILL.md
workflows/
  feature.md
examples/
  react-native-offline-banner/
```

The skills discover available MCP resources and tools at runtime. They contain no hard-coded server names, account IDs, or vendor-specific calls, so the same workflow can sit above different issue trackers, document stores, source hosts, or CI systems.

## Workflow

`Intent → Context → Plan → Implement → Review → Verify → Release → Learn`

1. [`mcp-context-brief`](skills/mcp-context-brief/SKILL.md) gathers the minimum authoritative context and records its provenance.
2. [`ticket-to-plan`](skills/ticket-to-plan/SKILL.md) turns the approved outcome into a bounded implementation and verification plan.
3. The agent implements one reviewable slice under [`AGENTS.md`](AGENTS.md).
4. [`acceptance-review`](skills/acceptance-review/SKILL.md) maps the ticket, diff, and observed evidence to a release recommendation.
5. The human owner accepts, revises, or blocks the release.

See [`workflows/feature.md`](workflows/feature.md) for the gates between stages.

## Use it in another repository

1. Merge the relevant rules from `AGENTS.md` into the target repository's instructions.
2. Copy only the skill folders the team needs into its supported skills location.
3. Connect the MCP servers approved for that repository; do not edit the skills to embed credentials or server names.
4. Start with an approved ticket and run the context, planning, and review skills in sequence.
5. Keep the final acceptance and release decision human-owned.

If MCP is unavailable, the skills fall back to user-provided and local repository context, state the missing sources, and avoid pretending the gap was verified.

## Example

The [React Native offline-banner example](examples/react-native-offline-banner/) follows a ticket through planning, a review finding, a fix, acceptance evidence, and a release decision.

It is a representative, code-free trace. It demonstrates the expected artifacts and evidence format; it is not presented as an open-source application or a claim about shipped code.

The repository stays deliberately small. Add a skill only when it captures a genuinely repeatable decision process—not merely another prompt.
