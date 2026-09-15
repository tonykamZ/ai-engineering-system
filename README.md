# AI Engineering System

Portable agent skills and repository rules for running a human-gated software engineering workflow on top of MCP.

This repository is the orchestration layer—not another AI-generated demo project. MCP supplies access to tools and context; the files here define how an agent scopes work, uses those capabilities, verifies the result, and returns decisions to a human owner.

`Human intent → AGENTS.md → Portable skill → MCP capabilities → Evidence → Human gate`

[See how this system fits into my engineering workflow](https://tonykam-portfolio.vercel.app/).

## The layers

| Layer | Responsibility |
| --- | --- |
| Human | Owns product intent, architecture exceptions, acceptance, release, and rollback. |
| `AGENTS.md` | Sets repository-wide boundaries, evidence rules, and escalation points. |
| Portable skills | Encode repeatable methods for context, planning, and review without naming a vendor or server. |
| MCP | Exposes current tickets, docs, designs, source systems, CI evidence, and approved actions at runtime. |
| Checks and environments | Produce observable evidence through tests, builds, previews, accessibility checks, integrations, and real-environment validation. |

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

The skills discover relevant MCP resources and tools only when external context can affect the task. They contain no hard-coded server names, account IDs, or vendor-specific calls, so the same workflow can sit above different issue trackers, document stores, source hosts, or CI systems.

## Design principles

The package follows OpenAI's guidance for capable coding agents: keep skill descriptions narrow, load instructions progressively, read only what the task needs, make verification proportional to risk, and state decision and completion boundaries clearly. See [Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra).

The rules remain model-agnostic because repository guidance may be used by different agents. Each skill is selected only when its specific workflow applies; local-only work does not need the context skill, and ordinary implementation does not automatically require the planning or release-review skills.

## Workflow

`Intent → Context → Plan → Implement → Review → Verify → Release → Learn`

1. When material facts live outside the repository, [`mcp-context-brief`](skills/mcp-context-brief/SKILL.md) gathers the minimum authoritative context and records its provenance.
2. When planning is requested or the plan gate is reached, [`ticket-to-plan`](skills/ticket-to-plan/SKILL.md) turns the approved outcome into a bounded implementation and verification plan.
3. The agent implements one reviewable slice under [`AGENTS.md`](AGENTS.md).
4. When release readiness is evaluated, [`acceptance-review`](skills/acceptance-review/SKILL.md) maps the request, diff, and observed evidence to a recommendation.
5. The human owner accepts, revises, or blocks the release.

See [`workflows/feature.md`](workflows/feature.md) for the gates between stages.

## Use it in another repository

1. Merge the relevant rules from `AGENTS.md` into the target repository's instructions.
2. Copy only the skill folders the team needs into its supported skills location.
3. Connect the MCP servers approved for that repository; do not edit the skills to embed credentials or server names.
4. Start with a clear request or approved ticket and invoke only the skills that match the current stage and evidence needs.
5. Keep the final acceptance and release decision human-owned.

If MCP is unavailable, the skills fall back to user-provided and local repository context, state the missing sources, and avoid pretending the gap was verified.

## Example

The [React Native offline-banner example](examples/react-native-offline-banner/) shows one mobile use case following a ticket through planning, a review finding, a fix, acceptance evidence, and a release decision. The workflow itself applies to software projects generally.

It is a representative, code-free trace. It demonstrates the expected artifacts and evidence format; it is not presented as an open-source application or a claim about shipped code.

The repository stays deliberately small. Add a skill only when it captures a genuinely repeatable decision process—not merely another prompt.
