# AI Engineering System

A small, practical system for using AI coding agents inside a human-owned mobile engineering workflow.

This repository is the process artifact—not another AI-generated demo app. It shows how a React Native feature moves from intent to a reviewed, verified release candidate:

`Intent → Context → Plan → Implement → Review → Verify → Release → Learn`

## What this demonstrates

- Agents receive explicit scope, repository rules, and acceptance criteria.
- Implementation happens in small, inspectable, reversible slices.
- Humans own product scope, architecture, acceptance, device validation, and release decisions.
- Automated checks provide evidence; they do not replace engineering judgment.
- Review findings feed back into implementation before release.

## Repository map

| Path | Purpose |
| --- | --- |
| [`AGENTS.md`](AGENTS.md) | Default operating rules for coding agents. |
| [`workflows/feature.md`](workflows/feature.md) | The feature delivery loop and its gates. |
| [`skills/ticket-to-plan/`](skills/ticket-to-plan/) | Turns a bounded ticket into an executable plan. |
| [`skills/acceptance-review/`](skills/acceptance-review/) | Reviews a change against acceptance criteria and risk. |
| [`examples/react-native-offline-banner/`](examples/react-native-offline-banner/) | One end-to-end React Native execution trace. |

## Start here

1. Read the [feature workflow](workflows/feature.md).
2. Inspect the [example ticket](examples/react-native-offline-banner/ticket.md) and [implementation plan](examples/react-native-offline-banner/implementation-plan.md).
3. Follow the [execution log](examples/react-native-offline-banner/execution-log.md) from implementation through a review finding, fix, verification, and release decision.

The files are intentionally short. The goal is a repeatable control system that can be adapted to a real codebase, not a large collection of generic prompts.
