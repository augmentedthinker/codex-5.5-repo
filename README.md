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
- `style-guide.html` — the house style reference for shared visual patterns and site conventions.
- `openclaw-usage.html` — the OpenClaw/Codex usage dashboard, showing sanitized usage-window gauges, reset times, and the calculation method used to update them.
- `artifacts.html` — the archive surface for Codex-generated artifacts.
- `memories.html` — the browser-facing memory archive for Codex memory pushes.

### Content Directories

- `assets/css/site.css` — universal stylesheet for theme tokens, navigation, layout, cards, typography, and responsive behavior.
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
- Style
- Usage
- Artifacts
- Memories

External links are intentionally not part of the primary navigation, so clicking through the site does not unexpectedly throw the user out of the GitHub Pages experience.

Note: the nav is beginning to get crowded. For now `Usage` belongs in the top bar because it is an active operational surface. A later cleanup should consider grouping secondary pages, adding a compact menu, or moving less-used surfaces into a dashboard/index page.

## Memory Push Protocol

When Christopher asks for a memory push while we are working in this repository:

1. Create a detailed local memory file under the shared workspace `memory/` directory.
2. Mirror the same memory into this repo under `memories/`.
3. Include date, time, active model ID, repository context, decisions, file changes, and continuity notes.
4. Add a newest-first entry to `memories.html` linking to the browser-facing memory page.
5. Keep the repository mirror aligned in substance with the local internal memory.

## Usage Dashboard Protocol

When Christopher asks for a usage dashboard update:

1. Check OpenClaw's private provider-usage source for `openai-codex` when available.
2. Update `openclaw-usage.html` with the sanitized usage percentages, reset/end times, derived start times, elapsed-time percentages, and the last-updated timestamp.
3. Do not publish OAuth tokens, account IDs, raw provider responses, or hidden quota details.
4. Commit, push, and verify the GitHub Pages deployment.

## Artifact Protocol

When creating a new artifact:

1. Add the artifact page under `artifacts/`.
2. Add a newest-first card to `artifacts.html`.
3. Include a clear title and signature on the archive card with date, time, and model ID.
4. Keep the site navigation consistent unless a specific artifact intentionally needs a different presentation.

## Maintenance Direction

Shared layout, navigation, card, typography, theme, and responsive styles now live in `assets/css/site.css`. Individual pages should only keep page-specific styles locally when necessary, such as canvas animation styling for visual artifacts. The `style-guide.html` page acts as the browser-facing house style reference and should be updated whenever we add reusable patterns.

A later improvement could add small shared JavaScript for reusable navigation or markdown loading, but the first CSS extraction pass is complete.
