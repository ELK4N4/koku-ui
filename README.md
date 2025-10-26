# Koku UI Monorepo

This repository hosts multiple front-end applications for Cost Management:

- `apps/saas` – the existing SaaS-hosted Cost Management UI
- `apps/standalone` – boilerplate for the upcoming standalone/on-prem experience

The repo also holds shared configuration, deployment manifests, and documentation supporting each app.

## Requirements

- Node.js v20.15+
- npm v10.8+

Install dependencies using workspaces:

```
npm install
```

## Available Scripts

| Command | Description |
| --- | --- |
| `npm run dev:saas` | Start the SaaS app using FEC tooling |
| `npm run dev:standalone` | Launch the standalone boilerplate via webpack-dev-server |
| `npm run build:saas` | Build the SaaS app |
| `npm run build:standalone` | Production build for the standalone app |
| `npm run lint` | Run linting for the SaaS app |
| `npm run test` | Run tests for the SaaS app |
| `npm run translations` | Execute translation workflows for the SaaS app |
| `npm run verify` | Full verification (build + lint + test) for the SaaS app |

Individual apps expose the same set of scripts through their local `package.json` files. Execute per-app commands with the `-w` flag:

```
npm run start -w @koku-ui/saas
npm run start -w @koku-ui/standalone
```

The standalone workspace currently renders a placeholder shell; future work will populate it with the on-prem experience.

## Repository Layout

```
apps/
  saas/         # SaaS-hosted Cost Management application (existing app)
    src/
    scripts/
    deploy/
    docs/
  standalone/   # Standalone/on-prem boilerplate app
    src/

shared configs  # Root-level configs (eslint, jest, tsconfig, etc.)
```

Refer to `apps/saas/README.md` (if present) or in-app docs for SaaS-specific guidance. When the standalone app development expands, its documentation will live inside `apps/standalone/`.
