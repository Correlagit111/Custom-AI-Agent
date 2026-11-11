# Project Pulse agent team

This project uses a small custom agent team to keep the work organized and to mirror the orchestration flow learners practice with GitHub Copilot CLI in a Codespace.

## Orchestrator
- Model: Claude Opus 5.5 (copilot)
- Responsibility: Coordinates the project, breaks the work into phases, delegates tasks to specialists, and verifies the final dashboard fits the brief.
- Definition: `.github/agents/orchestrator.agent.md`

## Planner
- Model: Claude Opus 5.5 (copilot)
- Responsibility: Researches the repository and brief, identifies phases, file ownership, dependencies, and validation checks before implementation starts.
- Definition: `.github/agents/planner.agent.md`

## Designer
- Model: Gemini 3.7 Flash (copilot)
- Responsibility: Shapes the dashboard UX, accessibility, hierarchy, layout, and visual polish for project cards, status badges, and readable spacing.
- Definition: `.github/agents/designer.agent.md`

## Coder
- Model: GPT-5.5 (copilot)
- Responsibility: Implements the static dashboard files, data contract, and launch configuration needed to run the Project Pulse app from the `app/` directory.
- Definition: `.github/agents/coder.agent.md`

> GitHub Copilot CLI in a Codespace orchestrates the work across these agents, keeping the flow explicit and consistent with the Project Pulse exercise.
