# AGENTS.md - dcyfr-plugins

## Project Overview

Official curated plugin marketplace for the `@dcyfr/ai` framework. This repo is registry-centric and security-sensitive.

## Architecture

- Marketplace index: `marketplace.json`
- Curated plugins live in `plugins/`
- Policy docs: `README.md`, `CONTRIBUTING.md`, `SECURITY.md`
- Enforcement automation: `.github/workflows/`

## Working Rules

- Changes should preserve curation, trust, and security guarantees.
- If plugin metadata changes, keep `marketplace.json`, plugin manifests, and docs aligned.
- Prefer editing the smallest possible surface area in curated plugin entries.
