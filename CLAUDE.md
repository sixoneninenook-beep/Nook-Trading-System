# CLAUDE.md — Nook Trading System

This file is the primary reference for AI assistants (Claude Code and others) working in this repository. Keep it current as the project evolves.

---

## Project Overview

**Nook-Trading-System** is a cloud-based trading platform project owned by `sixoneninenook-beep`. The repository is in early initialization and does not yet contain application source code.

### Intended scope (inferred from repo name and initial commits)
- Cloud-hosted trading system ("nook-cloud")
- Deployed via GitHub Actions

---

## Repository State

As of the most recent snapshot the repository contains only:

| File | Purpose |
|------|---------|
| `README.md` | Git initialization setup steps (placeholder) |
| `.github/workflows/main.yml` | GitHub Actions workflow stub (no jobs defined yet) |

There is **no application source code** committed yet. When code is added, update this file with accurate descriptions of each new module, directory, and workflow.

---

## Branch Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Stable, production-ready state |
| `claude/<topic>-<id>` | AI-assisted feature/task branches — always created fresh per session |

All Claude Code changes must be developed on the designated `claude/…` branch and pushed there. Never push directly to `main` without an explicit pull request and human review.

---

## GitHub Actions

File: `.github/workflows/main.yml`

Currently contains only the nook-cloud git setup shell script (copy-pasted into the workflow file by mistake — no actual CI jobs are defined). Before adding real jobs, replace the file contents with a proper workflow structure, for example:

```yaml
name: CI
on:
  push:
    branches: [main]
  pull_request:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      # add build/test steps here
```

---

## Development Conventions (to be enforced once code exists)

### General
- Default branch for humans: `main`
- Default branch for Claude sessions: `claude/<task>-<shortid>`
- Commit messages: imperative mood, short subject line (`Add order matching engine`, not `added` or `Adding`)
- No force-push to `main`

### Code style
- Agree on a language/stack before writing code and document it here
- All source files must include a module-level docstring or header comment only if the purpose isn't obvious from the filename
- No inline comments explaining *what* code does — only *why* if it's non-obvious

### Testing
- Every new feature or bug fix should include a corresponding test
- Test files live alongside source (e.g., `src/foo.py` → `src/foo_test.py`) or in a top-level `tests/` directory — pick one and document it here
- CI must pass before any merge to `main`

---

## Key Things for AI Assistants

1. **This repo is early-stage** — before adding code, confirm the intended tech stack with the user.
2. **The `main.yml` workflow is a stub** — do not add CI steps assuming a particular language/runtime.
3. **Do not guess at business logic** — trading systems involve financial correctness; always ask before implementing order matching, pricing, or settlement logic.
4. **Prefer small, reviewable commits** — keep each commit focused on one concern.
5. **Never commit secrets** — API keys, broker credentials, or exchange tokens must go in environment variables or a secrets manager, never in source files.
6. **Update this file** whenever the project structure changes significantly (new top-level directories, new CI jobs, new dependencies, new environment variables required).

---

## Environment Variables

None defined yet. When environment variables are introduced, document them here:

| Variable | Required | Description |
|----------|----------|-------------|
| _(none yet)_ | — | — |

---

## Getting Started (placeholder)

Once the tech stack is decided, replace this section with real setup instructions:

```bash
# clone
git clone https://github.com/sixoneninenook-beep/nook-trading-system.git
cd nook-trading-system

# install deps (example for Node)
npm install

# run tests
npm test

# start dev server
npm run dev
```

---

*Last updated: 2026-06-25. Update this file whenever the project structure or conventions change.*
