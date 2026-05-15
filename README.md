# olm-site

Source for [openlearningmap.org](https://openlearningmap.org), the public-facing site for Open Learning Map (OLM). Deployed via GitHub Pages.

OLM is a governed vocabulary and structural framework for describing educational programs. It is not a curriculum. The framework, canonical registry, reference programs, and authoritative documentation live in the main repository: [Meta-Humans/olm](https://github.com/Meta-Humans/olm).

## What's in this repository

- `index.html`, `styles.css`, `assets/` — the homepage and styling.
- `ai/` — stable, AI-facing resources served at `openlearningmap.org/ai/`. These are the canonical public URLs that LLM tools and agents fetch.
  - `olm_system_prompt_latest.md` — drop-in system prompt for any capable LLM.
  - `olm_context_bundle_latest.md` — full context bundle (constitution, registry, rules, worked example).
  - `canonical_registry_latest.yaml` — machine-readable source of truth for valid canonical IDs.
  - `changelog.md` — revision history for the three files above.
- `llms.txt`, `llms-full.txt` — root-level LLM discovery files following the [llmstxt.org](https://llmstxt.org) convention.
- `robots.txt`, `sitemap.xml` — crawler guidance. AI bots are explicitly allowlisted.
- `CNAME` — GitHub Pages custom domain pointer.

## Versioning

The files in `ai/` are versioned. When the canonical registry changes in [Meta-Humans/olm](https://github.com/Meta-Humans/olm), the three `_latest` files here are republished together. `ai/changelog.md` records each revision. Stable `_latest` URLs let LLM tools pin to the file name without breaking when content updates.

## License

- Code in this repository: MIT.
- Documentation, prompts, and conceptual content: Creative Commons Attribution 4.0 (CC BY 4.0). See `LICENSE-CONTENT.md`.

## Related

- [openlearningmap.org](https://openlearningmap.org) — live site.
- [Meta-Humans/olm](https://github.com/Meta-Humans/olm) — framework, registry, reference programs.
- [Meta Humans community forum](https://community.metahumans.com/c/olm) — practitioner discussion.
