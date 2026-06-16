# CLAUDE.md

Guidance for AI assistants (Claude Code and others) working in this repository.

## Project overview

- **Name:** `opnesimai`
- **Tagline:** AI Bot simulation Lab (per `README.md`)
- **License:** MIT (see `LICENSE`, © 2026 Victory)

This repository is in a **pre-development / scaffolding** state. As of this
writing it contains only project metadata — there is no application source
code, build configuration, tests, or CI yet.

> **Keep this file honest.** The sections below describe what *currently*
> exists and the intended direction inferred from configuration. When real
> source code, build tooling, or workflows are added, update this file to match
> reality rather than leaving aspirational descriptions in place.

## Current repository structure

```
.
├── .gitignore     # Ignore rules — templated for AL / Dynamics 365 Business Central
├── LICENSE        # MIT License
├── README.md      # One-line project description
└── CLAUDE.md      # This file
```

Documentation lives under `docs/`:

- `docs/agent-skills-simulation.md` — Top 50 automatic-simulation agent skills
  (domain blueprint for the "AI Bot simulation Lab"), written in Traditional
  Chinese.

There are no source files or dependency manifests yet.

## Intended technology direction

Two signals point at the likely stack — confirm with the maintainer before
committing to either:

1. **AL / Microsoft Dynamics 365 Business Central.** The `.gitignore` is the
   standard Microsoft template for AL projects. It ignores AL-specific
   artifacts: `.alcache/`, `.alpackages/`, `.snapshots/`, `.output/`, compiled
   `*.app` extension files, `rad.json`, generated translations (`*.g.xlf`),
   license files (`*.flf`), and `TestResults.xml`. AL projects are normally
   developed in **VS Code** with the **AL Language extension** and use an
   `app.json` manifest plus a `.alpackages/` symbol folder.

2. **AI / bot simulation.** The README ("AI Bot simulation Lab") suggests the
   functional goal is simulating AI agents/bots.

These two signals are not obviously the same stack. When code lands, determine
the actual setup and rewrite the relevant sections here.

## Development workflow

### Branching

- The default integration branch is `main`.
- Active development for the current task happens on a dedicated feature branch
  (e.g. `claude/...`). **Do not push directly to `main`** — open a pull request.
- Create a PR as a **draft** after pushing a feature branch.

### Commits

- Write clear, descriptive commit messages in the imperative mood
  (e.g. "Add bot scheduler module").
- Keep commits focused; group related changes together.
- Only commit or push when the change is complete and the working tree reflects
  the intended state.

### Pull requests

- After pushing a feature branch, open a draft PR against `main` if one does not
  already exist.
- Keep PRs scoped and reviewable.

## Build, test, and run

No build system, test suite, or run scripts exist yet. There are **no commands
to document at this time.**

When tooling is introduced, record the canonical commands here. Likely
candidates depending on the chosen stack:

- **If AL / Business Central:** build/publish via the AL extension in VS Code
  (Ctrl+Shift+B / `AL: Publish`), `app.json` for configuration, and tests run
  through the AL Test Runner (results in `TestResults.xml`, which is gitignored).
- **If another stack is chosen:** document its install, build, test, lint, and
  run commands.

## Conventions

- **Honesty first:** never describe files, commands, or structure that do not
  exist. Verify by reading the repository before documenting.
- **Match local style:** once source code exists, mirror the surrounding code's
  naming, formatting, and idioms rather than imposing a new style.
- **Respect `.gitignore`:** do not commit ignored build artifacts (`*.app`,
  `.alpackages/`, caches, generated translations, test result files, etc.).
- **License headers:** the project is MIT-licensed; keep the `LICENSE` intact.

## For AI assistants: getting started

1. Read `README.md`, `LICENSE`, and `.gitignore` to confirm current state.
2. Run `git ls-files` to see exactly what is tracked before assuming structure.
3. If asked to add code, first clarify the intended stack (AL/Business Central
   vs. another runtime) if it is still ambiguous.
4. Update this `CLAUDE.md` whenever the repository's structure, tooling, or
   workflows meaningfully change.
