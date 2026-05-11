# OLM AI Files — Changelog

**Public URL:** https://openlearningmap.org/ai/changelog.md
**Repo:** https://github.com/Meta-Humans/olm

This file tracks revisions to the public AI-facing files served at `openlearningmap.org/ai/`:

- `canonical_registry_latest.yaml`
- `olm_system_prompt_latest.md`
- `olm_context_bundle_latest.md`

When the canonical registry changes, all three files are republished together. Use this changelog to determine whether the version of OLM you have in context is current.

---

## v1.1 — May 2026

**Registry revision: three HDDs promoted from pending to canonical.**

### Registry counts after this revision
- Patterns: 12
- Routines: 21
- Artifacts: 19
- Evidence: 5
- Constraints: 9
- HDDs: **11** (was 8)

### HDDs promoted to canonical

- `hdd.collective_efficacy` — Cultural & Collective. The shared belief that a group can succeed together. Particularly relevant for multi-session projects, where collaboration accumulates across sessions and learners begin to act on a shared expectation of group capability. Project programs are the primary evidence base.
- `hdd.intrinsic_motivation` — Dispositional. Engagement driven by internal interest, curiosity, or sense of purpose rather than external reward. Referenced in the HDD canonical document v0.1 and present across many programs as a design intent.
- `hdd.psychological_safety` — Cultural & Collective. A felt sense that participants can speak, question, disagree, or risk an answer without social cost. Particularly relevant for discussion-heavy and question-board programs.

All three were previously held in the `pending` block of the registry pending formal promotion. The `pending` block is now empty.

### What this changes

- These three IDs may now appear in `hdd_alignment` on any new or regenerated Core Mapping.
- They follow the same non-claimable rules as all other HDDs — never scored, validated, or attached as outcomes.
- Existing programs continue to validate as before; this is an additive change.

### Files updated

- `canonical_registry_latest.yaml`
- `olm_system_prompt_latest.md`
- `olm_context_bundle_latest.md`

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
