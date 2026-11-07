# Repository Guidelines

## Project Structure & Module Organization

This repository is a public, read-only JML image and prompt gallery. `index.html` contains the page markup, inline CSS, embedded JSON in `#archive-data`, and vanilla JavaScript for rendering, filtering, hash routing, and exports. `assets/` holds image previews and references, primarily WebP and PNG files. `README.md` describes scope and attribution; `.nojekyll` supports static GitHub Pages hosting. There are no separate source, test, or build directories.

## Build, Test, and Development Commands

- `python -m http.server 8000 --bind 127.0.0.1`: serve the repository locally when Python is installed; open `http://localhost:8000`.
- `git diff --stat`: review the scope of changes, especially large embedded-data or asset updates.
- `git diff --check`: check tracked changes for whitespace errors before committing.

No dependency installation, compilation, or package-manager scripts are required. GitHub Pages serves the root of `main` directly.

## Coding Style & Naming Conventions

Preserve the existing compact formatting in `index.html`; avoid whole-file reformatting. No formatter, linter, or fixed indentation rule is configured. Keep JavaScript functions and local variables in camelCase, constants such as `DATA` and `ARTICLE_STYLES` uppercase, and CSS classes and HTML IDs hyphenated. Embedded data uses snake_case fields such as `article_id` and `image_ids`.

Use the existing `esc()` helper when inserting text into HTML strings. Preserve record IDs, cross-references, and relative `assets/` paths. Follow existing asset patterns such as `archive-<hash>.webp` and `source-<hash>.webp`.

## Testing Guidelines

There is no automated test framework, test naming convention, or coverage threshold. Validate changes through the local server: check archive search and filters, blog style selection, detail navigation, prompt copying, image enlargement, and JSON downloads. Reload affected hash routes directly. Check desktop and narrow mobile layouts, browser console errors, and missing images. For data changes, verify that referenced IDs and asset files exist.

## Commit & Pull Request Guidelines

History uses short, imperative, sentence-case subjects, such as `Add cultural examples and prompt variants`. Follow that convention. Keep changes focused. PRs should describe the change, identify affected gallery sections, link relevant issues, and record manual checks. Include screenshots for visible layout changes.

## Content & Privacy

Retain source credits, license notices, provenance, and prompt-status distinctions. Keep AI-generated examples clearly labeled. Never add private conversation links, local filesystem paths, attachment identifiers, or credentials to this public export.
