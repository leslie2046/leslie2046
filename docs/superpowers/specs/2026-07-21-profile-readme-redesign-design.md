# Profile README Redesign

## Goal

Rebuild the profile README in the concise, engineering-first style of `samzong/samzong` while keeping Leslie's own focus and work prominent. The result will be entirely in English, use plain Markdown, and favor concrete projects and contributions over decorative profile elements.

## Design Principles

- Lead with what Leslie builds and contributes.
- Keep the page easy to scan: short sections, compact bullets, and one-sentence descriptions.
- Use project links and precise descriptions as evidence; do not use stars, activity cards, or other popularity metrics.
- Treat the Dify plugin portfolio as a coherent collection rather than mixing it into a generic project table.
- Make the README easy to maintain without generated assets or complex HTML.

## Page Structure

### 1. Introduction

Open with `# Hi, I'm Leslie 👋` followed by one short paragraph positioning Leslie as an engineer working on practical AI infrastructure, Dify plugins, retrieval integrations, model providers, and dependable workflow tooling.

The introduction will not include a banner, centered HTML, navigation links, a slogan, or a quote.

### 2. What I Build

Use four compact bullets:

- Dify plugins and workflow tools.
- Retrieval and knowledge-base integrations.
- Model-provider and inference integrations.
- Storage and data connectors for production AI workflows.

Each bullet will describe the outcome and engineering area rather than list technologies without context.

### 3. Contributions

Highlight representative upstream work in these ecosystems:

- `langgenius/dify`
- `langgenius/dify-official-plugins`
- `langgenius/dify-plugin-sdks` and `langgenius/dify-plugin-daemon`
- `xorbitsai/inference`
- `infiniflow/ragflow`

Each entry will link to the upstream repository and summarize Leslie's contribution themes in one sentence. The copy must avoid unsupported role labels such as "maintainer" or "committer."

### 4. Dify Plugin Collection

This is the main project section. It will list:

- `dify-plugin-lingua` — language detection and ISO language-code output for workflows.
- `dify-ragflow-plugin` — RAGFlow datasets, documents, chunks, retrieval, and memory operations in Dify.
- `dify-plugin-minio` — MinIO object-storage operations for AI workflows.
- `dify-plugin-juhe` — Juhe data APIs for weather, markets, exchange rates, and related lookups.
- `dify-knowledge-plugin` — access to existing Dify knowledge-base operations from plugin workflows.

Every item will include its GitHub repository link and a single purpose-focused sentence. The Lingua entry will also link to its existing Dify Marketplace listing; the other entries will use repository links only. No stars or release badges will be shown.

### 5. Selected Project

Include `leslie2046/skills` as a compact non-plugin project entry, describing it as Leslie's collection of reusable agent skills. This section remains singular and intentionally small so it does not compete with the Dify plugin collection.

### 6. Current Focus

Close with one short paragraph about practical AI infrastructure: plugin ecosystems, retrieval systems, model integrations, and the engineering work required to turn demos into dependable tools.

## Content and Tone

- All visible README copy will be in English.
- Tone: direct, technical, and understated.
- Use active voice and concrete nouns.
- Avoid marketing superlatives, decorative slogans, personal-stat cards, and unverified claims.
- Keep every project or contribution description to one sentence.

## Repository Changes

- Replace the current `README.md` contents.
- Delete `header.svg`, because the redesigned README will have no banner or generated visual dependency.
- Add no scripts, workflows, or external generated assets.

## Validation

Before completion:

- Confirm every repository and Marketplace URL resolves.
- Confirm all listed projects are owned by Leslie or clearly identified as upstream contribution targets.
- Check Markdown headings, bullets, and link syntax.
- Confirm the README contains no HTML layout, image cards, stars badges, or references to `header.svg`.
- Run `git diff --check` to catch whitespace errors.

## Out of Scope

- Automatically generated GitHub statistics.
- A complete catalog of every repository or contribution.
- New artwork, badges, social links, or automation.
- Changes to the linked plugin repositories or their Marketplace listings.
