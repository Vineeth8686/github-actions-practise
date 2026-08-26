# Repository Agent Guidance

## Scope

- This workspace contains the Vite React app in `02 Starting Project/`.
- Keep suggestions and edits focused on the requested behavior; avoid unrelated cleanup.
- Use function components, local `useState`, named constants for repeated content, and colocated CSS imports.

## Component Boundaries

- `src/App.jsx` provides the page shell and renders `MainContent`.
- `src/components/MainContent.jsx` owns help visibility state and toggle behavior.
- `src/components/HelpArea.jsx` owns the static `HELP_ITEMS` collection and maps it to `HelpBox`.
- `src/components/HelpBox.jsx` remains presentational and receives `title` and `text` props.

When suggesting a UI or content change, place state changes in `MainContent`, repeated help content in `HELP_ITEMS`, and display-only changes in `HelpBox` or its colocated CSS.

## Validation

Run commands from `02 Starting Project/`:

```sh
npm ci
npm test
npm run build
```

Tests use Vitest with React Testing Library and prefer semantic queries such as `getByRole`. There is no lint or format script.

## Workflow Note

The GitHub Actions workflow in `.github/workflows/test.yaml` is currently only a checkout skeleton. Do not assume CI installs dependencies or runs the local test and build commands unless the workflow is explicitly being changed.