# Next.js + NestJS Turborepo Starter

A lightweight full-stack monorepo starter for projects that need a web app and an API. It brings together Next.js, NestJS, Bun workspaces, and Turborepo, with shared TypeScript and ESLint configuration.

The apps are framework starting points: keep the ones you need, remove the ones you don't, and shape them around your project.

## What's included

- `apps/web` — a Next.js app with React and TypeScript
- `apps/api` — a NestJS API with TypeScript
- `packages/eslint-config` — shared ESLint configuration
- `packages/typescript-config` — shared TypeScript configuration files
- Turborepo tasks for building, developing, linting, and checking types across workspaces

## Requirements

- Node.js 24 or later
- Bun 1.4.2

## Getting started

Install dependencies from the repository root:

```sh
bun install
```

Start the workspaces in development mode:

```sh
bun run dev
```

To run one app at a time:

```sh
bun run dev --filter=web
bun run dev --filter=api
```

The web app runs on port 3000 by default. Update its scripts or app configuration if your project needs a different port.

## Common commands

Run from the repository root:

```sh
bun run build
bun run lint
bun run check-types
bun run format
```

Turborepo runs each task in the workspaces that define it. You can target a workspace with a filter, for example:

```sh
bun run build --filter=web
bun run check-types --filter=api
```

## Adding packages

Add applications under `apps/` and shared libraries or configuration packages under `packages/`. Both folders are included in the root Bun workspace. Give each package a unique `name` in its `package.json`; other workspaces can then depend on it by name.
