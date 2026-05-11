# OLM Context Bundle

**Version:** 1.1 — May 2026
**Public URL:** https://openlearningmap.org/ai/olm_context_bundle_latest.md
**Repo:** https://github.com/Meta-Humans/olm

This is the single-file context bundle for OLM. Drop it into any LLM, agent, or pipeline that needs to generate, validate, or reason about OLM-aligned content. It contains:

1. Constitution summary
2. Canonical registry (full)
3. Layer contracts (full)
4. Generation rules
5. Validation rules
6. A worked example (Homemade Pizza)

This bundle is self-contained. Nothing needs to be fetched separately. If you want only the system prompt or only the registry, use the narrower files at `/ai/olm_system_prompt_latest.md` or `/ai/canonical_registry_latest.yaml`.

---

## 1. Constitution Summary

OLM (Open Learning Map) is a **structural framework**, not a curriculum. It defines how learning experiences are described, decomposed, and verified — not what is taught.

### Core constructs

- **Program** — a named learning structure composed of routines, artifacts, evidence, constraints, and optional patterns. Every program declares an embedding mode: `standalone`, `embeddable`, or `contextual`.
- **Pattern** — a reusable structural macro composed of routines and artifacts. Optional accelerator; not pedagogy.
- **Routine** — a repeatable learner action or practice.
- **Artifact** — a tangible or digital output produced by learners.
- **Evidence** — observable trace used to justify learning claims.
- **Constraint** — a structural limitation (time, team size, materials, rules).
- **HDD (Human Development Dimension)** — non-measurable human capacity referenced as design intent only. HDDs are non-claimable, non-derivable, non-scorable.

### What OLM is not

OLM does not define delivery scripts, schedules, staffing models, pedagogy, or assessments. Those concerns belong in **Playbooks** (typical delivery), **Runbooks** (specific execution), and **Rituals** (delivery-layer practices that support culture and flow without making learning claims).

### Skills

Skills are **derived outcomes**, not direct claims. They emerge from the accumulation of routines, artifacts, and evidence. Program completion does not equal skill mastery. The OLM registry does not enumerate skill IDs for direct attribution — skill derivation is a separate downstream concern handled by the platform, not by individual program packets.

### Activities (non-OLM)

An Activity is a delivery-level task or exercise. Activities live in Playbooks, Runbooks, and internal briefs. They do not generate evidence and must not appear in OLM Core mappings. An activity may be promoted to a program only if its learning structure can be explicitly defined using routines, artifacts, evidence, and constraints.

---

## 2. Canonical Registry

Use only these IDs. Any other ID is invalid.

### Patterns (12)

| ID | Use |
|---|---|
| `pattern.opening` | Section header for opening routines |
| `pattern.middle` | Section header for main content routines |
| `pattern.closing` | Section header for closing routines |
| `pattern.question_board` | Collective sensemaking and question generation |
| `pattern.project_planning` | Collaborative planning and workflow setup |
| `pattern.design_review` | Structured critique and refinement |
| `pattern.prototype_cycle` | Iterative build-test-revise loop |
| `pattern.capstone_pitch` | Synthesis and public communication |
| `pattern.retrospective` | Team reflection on process |
| `pattern.phenomenon_anchor` | Anchoring instruction in a phenomenon to be explained |
| `pattern.investigation_cycle` | Iterative empirical investigation |
| `pattern.consensus_model` | Collective construction of a shared model |

### Routines (21)

`routine.noticing_wondering`, `routine.question_generation`, `routine.problem_interpretation`, `routine.design_planning`, `routine.new_material`, `routine.discuss`, `routine.hands_on_activity`, `routine.model_construction`, `routine.apply_cad_feature`, `routine.explore_tool`, `routine.apply_feature_with_parameters`, `routine.iterate_for_precision`, `routine.prototype_iteration`, `routine.verify_with_measurement`, `routine.compare_to_spec`, `routine.kanban_workflow`, `routine.peer_feedback`, `routine.presentation_pitch`, `routine.reflect`, `routine.retrospective`, `routine.evidence_synthesis`

### Artifacts (19)

`artifact.prototype`, `artifact.physical_product`, `artifact.cad_part_file`, `artifact.measurement_log`, `artifact.design_brief`, `artifact.feedback_log`, `artifact.verification_record`, `artifact.retrospective_notes`, `artifact.question_set`, `artifact.team_canvas`, `artifact.kanban_board`, `artifact.reflection_log`, `artifact.pitch_deck`, `artifact.photo`, `artifact.video_clip`, `artifact.portfolio_entry`, `artifact.poster`, `artifact.presentation_recording`, `artifact.scientific_model`

### Evidence (5)

| ID | Role |
|---|---|
| `evidence.artifact_presence` | Primary — required when any artifact is declared |
| `evidence.short_answer_reflection` | Primary — reflective writing |
| `evidence.rubric_observation` | Primary — observed against a rubric |
| `evidence.numeric_match` | Primary — measured against a numeric spec |
| `evidence.routine_completion` | Supporting only — never primary |

### Constraints (9)

`constraint.time_limit`, `constraint.team_size`, `constraint.material_limit`, `constraint.safety_requirement`, `constraint.budget_cap`, `constraint.design_specification`, `constraint.tool_limit`, `constraint.self_direction`, `constraint.ruleset`

### HDDs (11)

`hdd.curiosity`, `hdd.belonging`, `hdd.agency`, `hdd.collaboration`, `hdd.sensemaking`, `hdd.persistence`, `hdd.self_trust`, `hdd.precision_orientation`, `hdd.collective_efficacy`, `hdd.intrinsic_motivation`, `hdd.psychological_safety`

**Deprecated:** `hdd.self_direction` → use `hdd.self_trust`.

**Pending:** none currently.

---

## 3. Layer Contracts

Every program packet is a stack of layered documents. Each layer reads from the layer above it and writes its own output. Layers do not skip dependencies, and downstream layers must not regenerate content that can be derived from upstream.

```
Brief
 → Core Mapping            (learning architecture)
   → Playbook              (delivery model)
     → Runbook             (internal — executable session flow)
       → Prep Pack         (internal — pre-session prep)
         → Educator Brief  (compiled from Runbook + Prep Pack)
         → Parent Brief    (compiled from Brief + Educator Brief)
```

### Core Mapping

Defines learning architecture. Required fields:

- `program_id` — slug, lowercase, underscored
- `title`
- `embedding_mode` — `standalone` | `embeddable` | `contextual`
- `duration`
- `age_range`
- `program_intent` — 1–3 plain-language sentences, non-claiming
- `patterns` — registry IDs
- `routines` — registry IDs
- `artifacts` — registry IDs, each with durability classification
- `evidence` — registry IDs
- `constraints` — registry IDs with values
- `hdd_alignment` — registry IDs (optional)

Must **not** contain: tools, videos, lesson scripts, materials lists, timing.

### Artifact durability

Every artifact carries one of:

- `durable` — persists physically or digitally
- `perishable` — exists briefly then is consumed or destroyed
- `requires_documentation` — must be photographed or recorded to persist

### Playbook

Defines delivery model — pedagogy, educator guidance, group configuration, safety assumptions, adaptation rules. One playbook may support multiple programs in the same domain (e.g., a culinary workshop playbook supports pizza, sushi, and cookie decorating). Must not redefine routines, artifacts, or evidence.

`rituals_referenced` may contain only **named OLM Ritual Library entries** (Morning Circle, Daily Stand-Up, Closing Circle, Demo Day, etc.) or be empty `[]`. Free-text descriptions of techniques are not valid entries.

### Runbook (internal)

Executable session flow. Step sequence, timing, facilitator and participant actions, artifact production, instructional asset usage. Constrained by Core Mapping + Playbook. Routines must originate from Core Mapping. Runbook duration must equal program duration exactly. Pattern markers may have 0 duration and act as section headers.

**Notes fields are educator-facing.** They must use plain language and must not contain any canonical OLM ID tokens.

### Prep Pack (internal)

Pre-session preparation: materials checklist, setup, safety reminders, common pitfalls, non-negotiables, key prompts, cleanup guidance. Must not include chronological steps in model-generated fields. The `session_flow` field is the exception — it is written by a post-processor from the Runbook and is not model-generated.

### Educator Brief (the educator-facing deliverable)

Compiled from Runbook + Prep Pack. Educators never see Runbook and Prep Pack as separate documents. Required sections in order:

1. Header (program name, session length, age range)
2. Program Intent
3. What to Expect (non-chronological)
4. Before the Session (preparation checklist)
5. Materials
6. Resources
7. Non-Negotiables
8. Key Prompts (unordered)
9. Common Pitfalls
10. Session Flow (the only chronological section)
11. Closing Checklist

**No canonical OLM IDs may appear anywhere in the Educator Brief.** This is the most common leak point — guard it.

### Parent Brief

Family-facing. Plain language. No internal terminology, no pedagogy explanation, no skill claims, no canonical IDs.

---

## 4. Generation Rules

### Pattern markers as section headers

```
pattern.opening        ← header
routine.xxx            ← opening section content
routine.xxx
pattern.middle         ← header
routine.xxx            ← middle section content
pattern.closing        ← header
routine.xxx            ← closing section content  ← correct
```

All three pattern markers appear exactly once, in order: `opening → middle → closing`. Each section must contain at least one timed routine following its marker. `pattern.closing` is **not** a terminator — closing routines (`routine.reflect`, `routine.retrospective`) go **after** it.

### Routine selection — common errors

- **`routine.discuss` vs `routine.reflect`** — `discuss` is group verbal exchange (learners talking to each other). `reflect` is individual written or silent reflection on the learning experience. A closing written reflection is always `reflect`, even if brief verbal sharing follows.
- **`routine.explore_tool`** — low-stakes, goal-free familiarization with a tool. Once a specific output or goal is added, it becomes `routine.hands_on_activity` or `routine.apply_cad_feature`.

### Artifact selection — written outputs

- **`artifact.portfolio_entry`** — the primary written creative or intellectual output. Writing IS the task (a short story in response to a prompt, a written argument, a research summary).
- **`artifact.reflection_log`** — metacognitive reflection. Writing is ABOUT the task (closing reflections, journal entries on what was learned).

Decision rule: if the writing IS the task → `portfolio_entry`. If it is ABOUT the task → `reflection_log`. The physical medium (book, paper, digital) is irrelevant.

### Evidence rules

- If any artifact is declared, `evidence.artifact_presence` must be included.
- `evidence.routine_completion` is supporting evidence only — never primary.

### HDDs

HDDs are non-claimable. They never appear as reported competency outcomes on dashboards or parent reports. They go in `hdd_alignment` as design intent only.

---

## 5. Validation Rules

A packet must pass these checks before being treated as valid.

### Core Mapping
- All required fields present
- All IDs exist in the registry
- All artifacts carry durability classification
- If any artifact present, `evidence.artifact_presence` present
- Deprecated IDs not used

### Runbook (internal)
- All routines exist in Core Mapping
- Timed routine durations sum exactly to program duration
- Participant actions explicit at every step
- Artifacts do not appear as steps
- No new canonical IDs introduced
- Notes fields contain no canonical ID tokens

### Playbook
- Does not redefine routines, artifacts, or evidence
- `rituals_referenced` contains only named library rituals, or is empty
- If matched from library, `playbook_id` exists; if provisional, status declared

### Prep Pack (internal)
- No chronological session steps in model-generated fields
- `session_flow` field, if present, is post-processor output (not flagged as a boundary violation)
- Key Prompts appear as unordered reference list

### Educator Brief
- All 11 sections present, in order
- Session length in header matches Core Mapping duration exactly
- Session Flow durations sum to total program duration
- Session Flow routines all exist in Core Mapping
- No canonical OLM IDs anywhere in the document
- No skill claims, assessment language, or scoring guidance

### Parent Brief
- No internal terminology
- No pedagogy explanation
- No canonical IDs
- Describes the experience in family-friendly language

---

## 6. Worked Example — Homemade Pizza

This is a complete Core Mapping for a 60-minute culinary program where learners explore the origins of pizza, then make one. It demonstrates the most common Core Mapping shape and is a good template for any single-session activity-based program.

**Source brief (paraphrased):**
> Ages: All. Time: 60 min. Objectives: Learn about the history of pizza, then make a pizza. Guiding question: What is the origin of pizza? Opening uses a hook (Does pineapple belong on pizza?), a discussion of what learners already know, and a video on pizza history. Middle is hands-on pizza making. Closing connects the activity back to the guiding question and a book prompt: "What is your favorite pizza topping?"

**Core Mapping output:**

```yaml
program_id: program.homemade_pizza
title: Homemade Pizza
embedding_mode: standalone
duration: 60 min
age_range: All ages
program_intent: >
  Learners explore the origins of pizza and then make a pizza of their own.
  The session connects a brief historical and cultural inquiry with a
  hands-on culinary outcome, anchored by a book prompt at close.

patterns:
  - pattern.opening
  - pattern.middle
  - pattern.closing

routines:
  - routine.noticing_wondering      # opening hook ("Does pineapple belong on pizza?")
  - routine.question_generation     # framing the guiding question
  - routine.new_material            # short video on the history of pizza
  - routine.discuss                 # what have we learned about pizza's origin?
  - routine.hands_on_activity       # assembling and baking pizza
  - routine.reflect                 # book prompt response at close

artifacts:
  - id: artifact.physical_product
    durability: perishable
    note: The pizza itself
  - id: artifact.photo
    durability: durable
    note: Documentation of the finished pizza
  - id: artifact.reflection_log
    durability: durable
    note: Book prompt response — "What is your favorite pizza topping?"

evidence:
  - evidence.artifact_presence
  - evidence.short_answer_reflection
  - evidence.routine_completion       # supporting only

constraints:
  - id: constraint.time_limit
    value: 60 min
  - id: constraint.safety_requirement
    value: Food handling, oven use, allergen awareness
  - id: constraint.material_limit
    value: Pre-purchased crust, sauce, cheese, and toppings

hdd_alignment:
  - hdd.curiosity
  - hdd.sensemaking
  - hdd.belonging
```

### What this example illustrates

- **Three pattern markers, in order.** Routines that follow each marker belong to that section. The closing reflection (`routine.reflect`) comes after `pattern.closing` — never before it.
- **The pizza is a perishable artifact.** `artifact.physical_product` with durability `perishable`. The photo is the durable record of it. This is the standard treatment for food and other consumable outputs.
- **`evidence.artifact_presence` is required** because artifacts are declared. `evidence.routine_completion` appears as supporting evidence only.
- **The video is not in the Core Mapping.** Tools, videos, and instructional materials live in the Runbook's Instructional Assets list — never in Core Mapping.
- **HDDs are design intent.** `hdd.curiosity` reflects that the origin-of-pizza framing is a curiosity hook. `hdd.sensemaking` reflects connecting historical context to current practice. `hdd.belonging` reflects shared cooking as a social experience. None of these will appear on a parent dashboard.

A Playbook for this program would describe the typical culinary delivery model (small groups, station-based, allergen protocol, parent communication about ingredients) and could be shared across other single-session culinary programs.

---

*OLM is a project of Meta Humans. Submit programs, propose canonical elements, or report inconsistencies via openlearningmap.org/contribute or the OLM repo.*

*Bundle version 1.1 — May 2026. Check `/ai/changelog.md` for revision history.*
