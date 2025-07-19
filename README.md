# Tobeworks Landingpage Generator

This monorepo contains the frontend applications for the Tobeworks AI Landingpage Generator. It is built with [Turborepo](https://turbo.build/repo) and uses [pnpm](https://pnpm.io/) as a package manager.

The goal of this project is to provide a user interface for generating AI-powered landing pages and to render various themes based on the generated content.

## What's inside?

This Turborepo includes the following packages and applications:

### Applications

- `apps/generator-ui`: (Planned) A Next.js application that will serve as the user-facing dashboard to configure and trigger the AI generation process.
- `apps/theme-default`: An [Astro](https://astro.build/) application that renders a landing page based on a given JSON configuration. This serves as the default theme.

### Packages

- `packages/ui`: A shared UI library containing common Astro components (e.g., `Hero`, `Features`) used across the theme applications. The package name is `@tobeworks/ui`.
- `packages/config`: (Planned) A package for shared configurations like Tailwind CSS.
- `packages/eslint-config`: Shared ESLint configurations.
- `packages/typescript-config`: Shared `tsconfig.json` configurations used throughout the monorepo.

### Architecture

The core architectural concept is a "Section Renderer". The backend API provides a JSON object containing an array of `sections` (e.g., `hero`, `features`). The `theme-default` app dynamically maps these section types to the corresponding Astro components from the `@tobeworks/ui` library, allowing for flexible and scalable page structures.

## Development

To start the development server for the default theme, run the following command:

```sh
pnpm dev --filter=theme-default
```

### Build

To build all apps and packages, run the following command:

```sh
pnpm build
```
