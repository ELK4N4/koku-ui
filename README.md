# Koku UI Monorepo

This repository hosts multiple front-end applications for Cost Management:

- `apps/saas` – the existing SaaS-hosted Cost Management UI
- `apps/standalone` – a placeholder for the upcoming standalone/on-prem experience

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
| `npm run dev:standalone` | Placeholder dev script for the standalone app |
| `npm run build:saas` | Build the SaaS app |
| `npm run build:standalone` | Placeholder build script for the standalone app |
| `npm run lint` | Run linting for the SaaS app |
| `TZ=UTC npm run test` | Run tests for the SaaS app |
| `npm run translations` | Execute translation workflows for the SaaS app |
| `npm run verify` | Full verification (build + lint + test) for the SaaS app |

Individual apps expose the same set of scripts through their local `package.json` files. Execute per-app commands with the `-w` flag:

```
npm run start -w @koku-ui/saas
```

The standalone workspace currently provides placeholder scripts. Future work will populate this app with actual implementation and tooling.

## Repository Layout

```
apps/
  saas/         # SaaS-hosted Cost Management application (existing app)
    src/
    scripts/
    deploy/
    docs/
  standalone/   # New standalone/on-prem application (boilerplate only for now)
    src/

shared configs  # Root-level configs (eslint, jest, tsconfig, etc.)
```

Refer to `apps/saas/README.md` (if present) or in-app docs for SaaS-specific guidance. When the standalone app development begins, its own documentation will live inside `apps/standalone/`.
