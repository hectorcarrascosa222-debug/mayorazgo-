# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**mayorazgo-** is a repository with minimal initial content. The git history shows it previously contained a single HTML file (`el-mayorazgo.html`) which has been removed. This repository is in an early stage and requires architecture decisions and implementation.

## Repository Structure

The repository is currently minimal:
- `README.md` - Project title only
- `.git/` - Git history

### Expected Future Structure

As the project grows, follow these conventions:

- **Documentation files** should be in the root (README.md, CLAUDE.md, etc.)
- **Source code** should be in a `src/` directory if a web application, or organized by feature/module
- **Tests** should mirror the source structure with `.test.` or `.spec.` in filenames
- **Build artifacts** should be in `dist/` or `build/`
- **Configuration files** (.env, config files) should be in root, excluded from git via .gitignore

## Development Workflow

### Initial Setup

1. **Clone and explore**: The repository is currently empty except for this documentation. Begin by:
   - Clarifying the project purpose with stakeholders
   - Defining the tech stack (frontend framework, backend, etc.)
   - Creating initial project structure

2. **Create .gitignore**: Before adding source code, establish a proper `.gitignore` file to exclude:
   - Build artifacts (`dist/`, `build/`, `*.min.js`)
   - Dependencies (`node_modules/`, `__pycache__/`, `venv/`)
   - Environment files (`.env`, `.env.local`)
   - IDE files (`.vscode/`, `.idea/`)
   - OS files (`.DS_Store`, `Thumbs.db`)

### Git Conventions

- **Branch naming**: Use descriptive names like `feature/user-auth`, `fix/login-bug`, `docs/readme-update`
- **Commit messages**: Write clear, imperative-mood messages ("Add feature X" not "Added feature X")
- **Commit frequency**: Commit logically grouped changes, not after every keystroke
- **Pull requests**: Create PRs for code review before merging to main
- **Main branch**: Treat `main` or `master` as stable; develop on feature branches

## Code Style and Quality

### Before Adding Code

1. **Define linting rules**: Set up ESLint (JavaScript), Prettier (formatting), or equivalent for your language
2. **Testing strategy**: Decide on testing framework and coverage requirements
3. **Type checking**: If using TypeScript or Python type hints, establish mypy/tsc configuration

### Code Standards (Language-Agnostic)

- **Naming**: Use clear, descriptive names for variables, functions, and modules
- **Structure**: Keep functions/methods small and focused on a single responsibility
- **Comments**: Only add comments explaining WHY, not WHAT (code should be self-documenting)
- **Modularity**: Separate concerns; avoid tightly coupled code
- **Error handling**: Handle errors explicitly at system boundaries (user input, external APIs)

## Future Development Guidance

### When Starting a New Component/Feature

1. Create a directory for the feature
2. Add a local README or comments explaining:
   - What the component does
   - Key dependencies
   - Configuration options if applicable
3. Ensure tests are co-located or in a `tests/` directory
4. Update main README.md with new feature documentation

### Code Review Focus Areas

When reviewing code or implementing features:
- **Correctness**: Does it work and handle edge cases?
- **Performance**: Are there obvious inefficiencies?
- **Maintainability**: Can future developers understand it?
- **Security**: Are inputs validated? Are dependencies secure?
- **Testing**: Is behavior covered by tests?

## Deployment and CI/CD

Once the project has substantial code:
- Create a `.github/workflows/` directory (if using GitHub Actions) for CI/CD pipelines
- Define build, lint, and test steps
- Add deployment automation if applicable
- Document environment requirements and setup steps

## Key Decisions to Make

Before substantial development begins:

1. **Language/Framework**: Will this be JavaScript/React, Python/Flask, or something else?
2. **Database**: Will a database be needed? Which type (SQL, NoSQL)?
3. **Hosting**: Where will this be deployed?
4. **Authentication**: What authentication method (JWT, OAuth, sessions)?
5. **API Design**: If building an API, what format (REST, GraphQL)?

## Common Commands Template

Once tooling is set up, document them here:

```bash
# Build
npm run build          # or equivalent for your stack

# Development
npm run dev            # Start dev server
npm run lint           # Run linter
npm run format         # Auto-format code

# Testing
npm test               # Run all tests
npm run test:watch     # Run tests in watch mode
npm run test:coverage  # Generate coverage report

# Deployment
npm run deploy         # Deploy to production
```

## Resources

- **README.md**: Main project documentation
- **Git history**: Review commits to understand evolution of the codebase
- **.gitignore**: Prevent accidentally committing sensitive or build files

## Notes for Future Maintainers

- This repository started minimal; refer to git history for context on why files were removed
- Establish code standards early rather than retrofitting them later
- Keep CLAUDE.md updated as project structure and conventions evolve
- Consider creating additional documentation files as the project grows (ARCHITECTURE.md, CONTRIBUTING.md, etc.)
