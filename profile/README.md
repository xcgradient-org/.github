# XC Gradient

XC Gradient organizes its work as a focused GitHub organization rather than a single monorepo. Each repository owns one clear surface area: internal operations, branded document generation, AI tooling, or production automation.

## What Lives Here

| Repository | Purpose |
| --- | --- |
| [`.github`](https://github.com/xcgradient-org/.github) | Organization profile, shared metadata, and contributor-facing docs |
| [`brand-assets`](https://github.com/xcgradient-org/brand-assets) | Shared logos, visual identity, and reusable brand assets |
| [`operations`](https://github.com/xcgradient-org/operations) | Internal operating system docs across executive, technical, legal, finance, HR, and GTM functions |
| [`latex-builder`](https://github.com/xcgradient-org/latex-builder) | LaTeX document generation and template automation |
| [`pwp-builder`](https://github.com/xcgradient-org/pwp-builder) | Programmatic PowerPoint deck generation with shared branding |
| [`plugins-skills`](https://github.com/xcgradient-org/plugins-skills) | Internal plugin and skill library for Codex, Claude Code, Gemini, and related agent workflows |
| [`xcg-bot`](https://github.com/xcgradient-org/xcg-bot) | Discord operations bot with Notion-backed workflows |
| [`hw-management`](https://github.com/xcgradient-org/hw-management) | Hardware monitoring, data collection, and health reporting for compute infrastructure |
| [`local-ai`](https://github.com/xcgradient-org/local-ai) | Local LLM orchestration and OpenAI-compatible inference gateway tooling |

## How The Pieces Fit

- `brand-assets` is reused by the document-generation repos.
- `operations` holds the durable process layer for the company.
- `latex-builder` and `pwp-builder` turn structured work into branded deliverables.
- `xcg-bot`, `hw-management`, and `local-ai` cover operational automation and infrastructure support.
- `plugins-skills` captures team-specific AI workflows and reusable agent capabilities.

## Working Model

- Repositories stay small and purpose-built.
- Tooling and deployment live with the code that owns them.
- Shared assets and standards are centralized instead of duplicated.
- Service repos document their own runtime, container, and CI expectations locally.

## Start Here

- Browse the organization: [github.com/xcgradient-org](https://github.com/xcgradient-org)
- Read process docs: [`operations`](https://github.com/xcgradient-org/operations)
- Build branded documents: [`latex-builder`](https://github.com/xcgradient-org/latex-builder) and [`pwp-builder`](https://github.com/xcgradient-org/pwp-builder)
- Work on AI automation: [`plugins-skills`](https://github.com/xcgradient-org/plugins-skills), [`xcg-bot`](https://github.com/xcgradient-org/xcg-bot), and [`local-ai`](https://github.com/xcgradient-org/local-ai)

## Local Workspace Pattern

If you keep multiple XCG repositories side by side on one machine, treat that folder as a workspace, not a monorepo. Clone only the repos you need and work in each repository independently:

```bash
git clone git@github.com:xcgradient-org/.github.git
git clone git@github.com:xcgradient-org/operations.git
git clone git@github.com:xcgradient-org/latex-builder.git
git clone git@github.com:xcgradient-org/pwp-builder.git
```

Each repository has its own branch history, README, CI configuration, and deployment lifecycle.
