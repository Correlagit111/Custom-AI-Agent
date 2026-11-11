# Project Pulse implementation plan

## Goal

Build a lightweight Project Pulse dashboard for Mona's team that quickly communicates which projects are active, who owns them, their current status, recent activity, and overall priority or risk. The result should be a polished static UI with clear project cards, status badges, readable spacing, and a launch configuration that opens `app/index.html` directly from the `app/` folder in VS Code.

## Implementation phases

### Phase 1: Planning and data contract
- Confirm the dashboard scope from the brief and define the required data fields.
- Agree on the project object structure and the top-level `projects` array for `app/project-data.json`.
- Set the implementation order and file ownership so work stays coordinated.

### Phase 2: Dashboard structure and design
- Define the page composition, card layout, status treatments, and hierarchy for project information.
- Build the HTML structure and semantic sections in `app/index.html`.
- Apply the visual system in `app/styles.css` so the page looks like a polished Project Pulse dashboard rather than a basic list.

### Phase 3: Data and rendering
- Create the project dataset in `app/project-data.json` with consistent entries for name, owner, status, recentActivity, and priority.
- Wire the dashboard to render those items from the dataset into project cards and detail summaries.
- Keep the implementation deterministic and easy to validate from a static app.

### Phase 4: Run configuration and final verification
- Create `.vscode/launch.json` with the VS Code launch configuration named `Run Project Pulse Dashboard`.
- Ensure the configuration serves from the `app/` directory and opens `index.html` rather than showing the folder listing.
- Validate the app loads correctly, the cards render, and the styling is consistent with the brief.

## File assignments

### `app/index.html`
- Primary ownership: Coder
- Responsibilities:
  - page shell and dashboard structure
  - semantic layout for summary and project cards
  - project card markup and data hooks
  - rendering logic or template placeholders needed for the static data source

### `app/styles.css`
- Primary ownership: Designer
- Responsibilities:
  - dashboard styling system
  - typography, spacing, alignment, and card layout
  - status badges, priority emphasis, and responsive behavior
  - visual polish with rounded corners, contrast, and readable hierarchy

### `app/project-data.json`
- Primary ownership: Coder
- Responsibilities:
  - top-level `projects` array
  - project names, owners, statuses, recent activity, and priorities
  - consistent data format for use by the dashboard rendering logic

### `.vscode/launch.json`
- Primary ownership: Coder
- Responsibilities:
  - launch configuration named `Run Project Pulse Dashboard`
  - `cwd` set to `${workspaceFolder}/app`
  - opening `index.html` so the dashboard appears directly
  - strict JSON with no comments and deterministic app startup

## Designer and Coder responsibilities

### Designer
- Owns the UI/UX direction for the dashboard.
- Chooses the information hierarchy and visual cues for project health, risk, and ownership.
- Ensures accessibility and readability through contrast, spacing, and consistent component styling.
- Produces a first-pass polished layout in `app/styles.css` and validates that it feels like a real dashboard, not a placeholder.

### Coder
- Owns implementation details and integration across the static app files.
- Defines the data schema and ensures it matches the structure expected by the UI.
- Implements the HTML structure, data loading/rendering, and the launch configuration.
- Verifies the final app opens and behaves as expected from the project brief.

## Dependencies between tasks

1. The brief and plan define the project structure and file boundaries.
2. The project data format must be agreed before rendering logic is implemented.
3. The HTML skeleton should be in place before the final style pass is refined.
4. The launch configuration is created after the app layout and data are stable.
5. Final validation depends on the dashboard opening from `app/index.html` with the expected CSS and data visible.

## Parallel work decisions

- Planner and Orchestrator complete the plan up front so both specialist roles operate from the same scope and file boundaries.
- Designer can work on `app/styles.css` while Coder prepares `app/project-data.json` in parallel once the data contract is agreed.
- Coder can build the HTML structure and the launch config in parallel with the Designer's styling only if the HTML placeholders and class names are already aligned.
- Avoid overlapping edits on the same file during the same phase. Keep design-only work in `app/styles.css`, layout/rendering work in `app/index.html`, and data content in `app/project-data.json`.

## Validation expectations

The implementation is successful when all of the following are true:
- `app/index.html` renders a dashboard view, not a directory listing.
- `app/project-data.json` uses a top-level `projects` array with the required fields.
- The dashboard clearly shows project cards, owner information, status, recent activity, and priority.
- `app/styles.css` adds a polished visual treatment with readable spacing and status badges.
- `.vscode/launch.json` exists and launches the dashboard from the `app/` directory using the `Run Project Pulse Dashboard` configuration.
- The final result matches the goals in `.github/project-pulse-brief.md` without adding extra app files or unnecessary complexity.
