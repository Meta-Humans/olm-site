# OLM AI Files — Changelog

**Public URL:** https://openlearningmap.org/ai/changelog.md
**Repo:** https://github.com/Meta-Humans/olm

This file tracks revisions to the public AI-facing files served at `openlearningmap.org/ai/`:

- `canonical_registry_latest.yaml`
- `olm_system_prompt_latest.md`
- `olm_context_bundle_latest.md`

When the canonical registry changes, all three files are republished together. Use this changelog to determine whether the version of OLM you have in context is current.

---

## v1.0 — May 2026

**Initial public release of the AI files.**

### Registry counts at launch
- Patterns: 12
- Routines: 21
- Artifacts: 19
- Evidence: 5
- Constraints: 9
- HDDs: 8

### Notable canonical additions in this release
- `pattern.phenomenon_anchor`, `pattern.investigation_cycle`, `pattern.consensus_model` — added to support phenomenon-anchored science programs (driven by the OpenSciEd Unit 6.1 reference implementation).
- `routine.explore_tool` — recovered from OLM Building Blocks Training v1; canonical low-stakes tool familiarization routine (driven by the CAD Missions reference implementation).
- `routine.evidence_synthesis` — added for programs that require learners to integrate multiple evidence sources into a model or conclusion.
- `artifact.scientific_model` — added for shared model construction in inquiry-driven programs.

### Notable HDD changes
- `hdd.self_direction` → deprecated. Use `hdd.self_trust`. Any existing brief using `hdd.self_direction` should be updated on next regeneration.
- Three HDD concepts are documented but not yet assigned canonical IDs: collective efficacy, intrinsic motivation, psychological safety. These appear in `pending` in the registry. Do not use them in pipeline output until they are promoted to canonical.

### Files in this release
- `canonical_registry_latest.yaml` — full registry, machine-readable
- `olm_system_prompt_latest.md` — self-contained system prompt for any LLM
- `olm_context_bundle_latest.md` — full context bundle with constitution summary, layer contracts, and a worked example (Homemade Pizza)

---

*Future revisions will appear above this entry. Each entry will note registry changes, behavioral rule changes, and any deprecations.*
