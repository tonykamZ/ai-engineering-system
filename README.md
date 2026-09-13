# AI Engineering System

A small, practical system for using AI coding agents inside a human-owned mobile engineering workflow.

This repository is the process artifact—not another AI-generated demo app. It shows how a React Native feature moves from intent to a reviewed, verified release candidate:

`Intent → Context → Plan → Implement → Review → Verify → Release → Learn`

[See how this system fits into my mobile engineering workflow](https://tonykam-portfolio.vercel.app/).

## What this demonstrates

- Agents receive explicit scope, repository rules, and acceptance criteria.
- Implementation happens in small, inspectable, reversible slices.
- Humans own product scope, architecture, acceptance, device validation, and release decisions.
- Automated checks provide evidence; they do not replace engineering judgment.
- Review findings feed back into implementation before release.

## Control model

| Human-owned decisions | Agent-assisted work | Automated checks | Human verification |
| --- | --- | --- | --- |
| Product outcome, priority, and architecture exceptions | Read context, plan, and implement reviewable slices | Lint, type checks, tests, and builds | iOS/Android behavior and accessibility |
| Acceptance, release, and rollback | Challenge the change and document evidence and risk | Regression suites and release artifacts | UAT, real devices, and production smoke tests |

Agents can recommend. Evidence can inform. Neither silently takes ownership of a product or release decision.

## Repository map

| Path | Purpose |
| --- | --- |
| [`AGENTS.md`](AGENTS.md) | Default operating rules for coding agents. |
| [`workflows/feature.md`](workflows/feature.md) | The feature delivery loop and its gates. |
| [`skills/ticket-to-plan/`](skills/ticket-to-plan/) | Turns a bounded ticket into an executable plan. |
| [`skills/acceptance-review/`](skills/acceptance-review/) | Reviews a change against acceptance criteria and risk. |
| [`examples/react-native-offline-banner/`](examples/react-native-offline-banner/) | One end-to-end React Native execution trace. |

## Use it in a repository

1. Merge the relevant rules from `AGENTS.md` into the target repository's instructions.
2. Give the agent an approved ticket and use `ticket-to-plan` before editing code.
3. Approve any material product or architecture choice, then implement one small slice.
4. Use `acceptance-review` against the ticket, diff, and observed check results.
5. Record the release decision and residual risk in the same shape as the example.

## Start here

1. Read the [feature workflow](workflows/feature.md).
2. Inspect the [example ticket](examples/react-native-offline-banner/ticket.md) and [implementation plan](examples/react-native-offline-banner/implementation-plan.md).
3. Follow the [execution log](examples/react-native-offline-banner/execution-log.md) from implementation through a review finding and fix.
4. Inspect the [acceptance evidence](examples/react-native-offline-banner/acceptance-review.md) behind the release decision.

The files are intentionally short. The goal is a repeatable control system that can be adapted to a real codebase, not a large collection of generic prompts.

The mobile example is a representative, code-free trace. It demonstrates the expected artifacts and evidence format; it is not presented as an open-source application or a claim about shipped code.
