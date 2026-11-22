# backstage-idp-starter

> **Portfolio demonstration project.** This is not affiliated with any employer and contains no employer code or data. It was built to showcase internal developer platform (IDP) skills: service catalogs, golden-path templates, and developer self-service.

A Backstage starter skeleton: a frontend app, a backend, a service catalog with two demo components, and one scaffolder template that creates a new Go service with CI-ready files.

## What it demonstrates

- **Service catalog** — `examples/catalog/components/` holds `catalog-info.yaml` files for two demo components (`demo-api`, `demo-website`). Backstage indexes them and shows ownership, tags, and links.
- **Golden-path template** — `examples/scaffolder-templates/go-service/` is a template that scaffolds a new Go REST service (module, `main.go`, multi-stage Dockerfile, README) and publishes it to GitHub. A developer answers two questions (name, owner) and gets a working service instead of starting from a blank repo.
- **TechDocs** — configured for local generation and publishing, so service docs live next to the code.

## Setup

Prerequisites: Node 20, Yarn, Docker (for TechDocs generation).

```bash
yarn install
export GITHUB_TOKEN=ghp_your_token_here   # only needed for GitHub integration
yarn dev
```

Then open http://localhost:3000. The catalog shows the two demo components; the **Create** page lists the Go Service template.

To run the frontend and backend separately:

```bash
yarn start          # frontend on :3000
yarn start-backend  # backend on :7007
```

This is a starter skeleton, not a finished production IDP: the dependency versions in `package.json` are a starting point for Backstage 1.30+, and `yarn install` will pull the matching versions. The database is an in-memory SQLite instance for local development — a real deployment needs a persistent database and real authentication instead of the guest provider.

## Files

| Path | Purpose |
|---|---|
| `package.json` | Yarn workspaces, scripts |
| `packages/app/` | Backstage frontend |
| `packages/backend/` | Backstage backend |
| `app-config.yaml` | Main config: catalog, auth, scaffolder, TechDocs |
| `app-config.local.yaml` | Local development overrides (example) |
| `examples/catalog/components/` | Two demo `catalog-info.yaml` components |
| `examples/scaffolder-templates/go-service/` | Golden-path template + skeleton files |
