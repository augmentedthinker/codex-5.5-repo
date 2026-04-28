# Codex 5.5 Repo

This repository is the dedicated workspace for experiments, artifacts, and continuity work using **OpenAI Codex 5.5** inside OpenClaw.

## Purpose

The Codex 5.5 Repo is a fresh workspace for exploring what `openai-codex/gpt-5.5` brings to our collaboration: deeper repository awareness, stronger implementation discipline, careful tool use, and a more architectural understanding of project state.

Unlike the Google repo, this space is not meant to imitate an existing structure. It starts from the same spirit of careful documentation and live publishing, but it is designed around Codex's strengths: building, inspecting, refactoring, verifying, and shaping durable software artifacts.

## Active Model

- `openai-codex/gpt-5.5`

## Live Site

This repository is published with GitHub Pages so the work can be viewed directly in the browser:

https://augmentedthinker.github.io/codex-5.5-repo/

## Current Site Architecture

The site is currently a small static GitHub Pages project built from plain HTML, CSS, and browser JavaScript. Each major surface is intentionally browser-facing and easy to inspect directly from GitHub.

### Top-Level Pages

- `index.html` — the homepage and primary menu surface. It introduces the repo and links into the main sections.
- `readme.html` — a browser-friendly mirror of this README.
- `agents.html` — a browser-facing mirror of `AGENTS.md`, showing Ash's startup and memory protocols.
- `artifacts.html` — the archive surface for Codex-generated artifacts.
- `memories.html` — the browser-facing memory archive for Codex memory pushes.

### Content Directories

- `artifacts/` — individual artifact pages, including visual experiments and interactive browser-native outputs.
- `memories/` — memory push mirrors. Each memory should include both a raw markdown file and a browser-readable HTML page when appropriate.

### Core Markdown

- `README.md` — canonical repository overview and architecture notes.
- `AGENTS.md` — mirrored assistant operating protocol for this repo.

## Navigation Pattern

The site uses a universal top navigation bar across browser-facing pages:

- Home
- README
- Agents
- Artifacts
- Memories

External links are intentionally not part of the primary navigation, so clicking through the site does not unexpectedly throw the user out of the GitHub Pages experience.

## Memory Push Protocol

When Christopher asks for a memory push while we are working in this repository:

1. Create a detailed local memory file under the shared workspace `memory/` directory.
2. Mirror the same memory into this repo under `memories/`.
3. Include date, time, active model ID, repository context, decisions, file changes, and continuity notes.
4. Add a newest-first entry to `memories.html` linking to the browser-facing memory page.
5. Keep the repository mirror aligned in substance with the local internal memory.

## Artifact Protocol

When creating a new artifact:

1. Add the artifact page under `artifacts/`.
2. Add a newest-first card to `artifacts.html`.
3. Include a clear title and signature on the archive card with date, time, and model ID.
4. Keep the site navigation consistent unless a specific artifact intentionally needs a different presentation.

## Maintenance Direction

The site has reached the point where repeated inline CSS is becoming a maintenance cost. The recommended next refactor is to extract shared layout, navigation, card, typography, and theme styles into a universal stylesheet, likely:

- `assets/css/site.css`

After that, individual pages should only keep page-specific styles locally when necessary, such as canvas animation styling for visual artifacts. This will make the site easier to maintain, reduce duplicated code, and keep visual consistency across new pages.

A later improvement could add small shared JavaScript for reusable navigation or markdown loading, but CSS extraction should come first because it provides the highest maintenance benefit with the least complexity.
