---
description: Scaffold a new maatwerk project with Turborepo monorepo structure
---

# Scaffold Maatwerk Project

Scaffold a complete maatwerk project with Turborepo monorepo, backend (Express or Hono), Next.js frontend, and shared packages.

## Instructions

**IMPORTANT**: You must use the AskUserQuestion tool to gather information before scaffolding. Ask questions one at a time and wait for responses.

### Step 1: Gather Information

Use AskUserQuestion tool with these questions in order:

1. **Project Name** (text input):

   - Question: "What is the project name? (e.g., my-awesome-project)"
   - Type: text
   - Store answer as `projectName`

2. **Client Name** (text input):

   - Question: "What is the client name? (e.g., Acme Corp)"
   - Type: text
   - Store answer as `clientName`

3. **Backend Framework** (single-select):

   - Question: "Which backend framework would you like to use?"
   - Type: single-select
   - Options: ["Express", "Hono"]
   - Store answer as `backendFramework`

4. **Features** (multi-select):
   - Question: "Which features would you like to include? (Select all that apply)"
   - Type: multi-select
   - Options: [
     "Authentication (NextAuth.js)",
     "Database (Prisma + PostgreSQL)",
     "API Documentation (Swagger/OpenAPI)",
     "Testing (Vitest)",
     "Docker configuration",
     "CI/CD (GitHub Actions)",
     "Storybook for UI components"
     ]
   - Store answer as `selectedFeatures` (array)

### Step 2: Scaffold Project

After gathering all answers, create the project structure in the current directory. Use the gathered information (`projectName`, `clientName`, `backendFramework`, `selectedFeatures`) to customize the scaffolded files.

**Create the following structure:**

### 1. Root Structure

- Create `package.json` with Turborepo configuration
- Create `turbo.json` with pipeline configuration
- Create `.gitignore`
- Create `README.md` with project overview

### 2. Backend Setup

Create `apps/backend/` with:

- `package.json` with dependencies for chosen framework (Express or Hono)
- `tsconfig.json` extending `@repo/ts-config`
- `src/index.ts` with basic server setup
- `src/routes/` directory structure
- If Express: Express app setup with TypeScript
- If Hono: Hono app setup with TypeScript

### 3. Frontend Setup

Create `apps/frontend/` with:

- Next.js 14+ setup with TypeScript
- `package.json` with Next.js dependencies
- `tsconfig.json` extending `@repo/ts-config`
- Basic app structure (`app/` directory)
- If Authentication selected: NextAuth.js setup

### 4. Packages

Create shared packages:

**packages/lib/**

- `package.json` with name `@repo/lib`
- `src/index.ts` with example exports
- `tsconfig.json`

**packages/ts-config/**

- `package.json` with name `@repo/ts-config`
- `base.json` - base TypeScript config
- `nextjs.json` - Next.js specific config
- `react-library.json` - React library config

**packages/eslint-config/**

- `package.json` with name `@repo/eslint-config`
- `index.js` - ESLint configuration
- Extends standard configs (TypeScript, React, Next.js)

**packages/ui/**

- `package.json` with name `@repo/ui`
- React component library setup
- `src/components/` directory
- If Storybook selected: Storybook configuration

### 5. Documentation

Create `docs/` folder with:

- `PROJECT.md` - Project setup and architecture documentation
- Include setup instructions, tech stack, and project structure

### 6. Project Context

Create `CLAUDE.md` in root with:

- Project name and client name
- Tech stack (backend framework, frontend, packages)
- Selected features
- Project structure overview
- Development guidelines

### 7. Additional Files (if features selected)

- If Database: Prisma schema and setup in backend
- If Docker: `Dockerfile` and `docker-compose.yml`
- If CI/CD: `.github/workflows/ci.yml`
- If Testing: Vitest config files
- If Storybook: Storybook config in packages/ui

Use kebab-case for project names and follow TypeScript best practices throughout.
