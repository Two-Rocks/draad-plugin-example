# Maatwerk Scaffold Plugin

A Claude Code plugin that scaffolds new maatwerk projects with a complete Turborepo monorepo structure.

## Features

- **Monorepo Setup**: Turborepo configuration for managing multiple packages
- **Backend Options**: Choose between Express or Hono (TypeScript)
- **Frontend**: Next.js 14+ with TypeScript
- **Shared Packages**: Pre-configured packages for lib, ts-config, eslint-config, and ui
- **Documentation**: Auto-generated project documentation
- **Optional Features**: Authentication, Database, API Docs, Testing, Docker, CI/CD, Storybook

## Installation

### As a Marketplace Plugin

1. Add the marketplace:

   ```bash
   /plugin marketplace add <repository-url>
   ```

2. Install the plugin:
   ```bash
   /plugin install maatwerk-scaffold@tworocks-plugins
   ```

### Local Development

1. Add the marketplace locally:

   ```bash
   /plugin marketplace add .
   ```

2. Install the plugin:
   ```bash
   /plugin install maatwerk-scaffold@tworocks-plugins
   ```

## Usage

Run the scaffold command:

```
/scaffold-maatwerk
```

The command will ask you:

1. **Project name** - The name of your project (kebab-case)
2. **Client name** - The name of the client
3. **Backend framework** - Express or Hono
4. **Features** - Select which optional features to include

After answering the questions, the plugin will scaffold:

- Complete Turborepo monorepo structure
- Backend application with your chosen framework
- Next.js frontend application
- Shared packages (lib, ts-config, eslint-config, ui)
- Documentation folder with PROJECT.md
- CLAUDE.md with project context
- Additional configuration files based on selected features

## Project Structure

```
project-name/
├── apps/
│   ├── backend/          # Express or Hono backend
│   └── frontend/          # Next.js frontend
├── packages/
│   ├── lib/              # Shared utilities
│   ├── ts-config/        # TypeScript configurations
│   ├── eslint-config/    # ESLint configurations
│   └── ui/               # Shared UI components
├── docs/                 # Project documentation
├── turbo.json           # Turborepo configuration
├── package.json         # Root package.json
├── CLAUDE.md           # Project context for Claude
└── README.md           # Project README
```

## Plugin Structure

```
.claude-plugin/
├── plugin.json          # Plugin manifest
└── marketplace.json     # Marketplace catalog
commands/
└── scaffold-maatwerk.md # Scaffold command
skills/                  # (Optional) Skills directory
agents/                  # (Optional) Agents directory
```

## Development

This repository IS the plugin. To modify the plugin:

1. Edit the command file: `commands/scaffold-maatwerk.md`
2. Update plugin metadata: `.claude-plugin/plugin.json`
3. Test locally: `/plugin marketplace add .` then `/plugin install maatwerk-scaffold@tworocks-plugins`

## License

MIT
