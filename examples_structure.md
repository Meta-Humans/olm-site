# OLM Examples — Repository Structure

## Where examples live

```
olm-main/
├── canonical/          ← registry + element YAML files
├── programs/           ← contributed programs (staging → canonical)
├── examples/           ← reference implementations (this folder)
│   ├── README.md
│   ├── popcorn_factory/
│   ├── homemade_pizza/
│   ├── cad_missions/
│   └── openscied_6_1/
├── rituals/
├── docs/
└── templates/
```

## File structure per example

Each example folder contains:

```
examples/popcorn_factory/
├── README.md                  ← what the program is, why chosen, how to read it
├── core_mapping.yaml          ← the OLM Core Mapping
└── playbook.yaml              ← the OLM Playbook
```

For externally-authored programs (CAD Missions, OpenSciEd):

```
examples/openscied_6_1/
├── README.md
├── core_mapping.yaml
├── playbook.yaml
└── companion.md               ← translation narrative (published on site)
```

## README template per example

Each example README follows this structure:

```markdown
# [Program Name]

**Program ID:** program.xxx
**Domain:** [venture/culinary/technical/science]
**Age Range:** [ages]
**Format:** [workshop/camp/series/unit]
**Type:** [Authored by Meta Humans / Integrated — source: X]

## What this program is
[1-2 sentences]

## Why it was chosen as a reference
[1-2 sentences — what this example demonstrates about OLM]

## How to read the mapping
[1-2 sentences — what's notable about the structural choices]

## Source materials
[Links to original program, if integrated]

## Attribution
[contributor block if applicable]
```

## Core Mapping YAML format

Convert from the JSON pipeline format to YAML for the repo.
Key fields:

```yaml
program_id: program.xxx
title: Program Title
embedding_mode: standalone
typical_duration: 60 min
age_range: all ages
program_intent: >
  Plain language description...

patterns:
  - pattern.opening
  - pattern.middle
  - pattern.closing

routines:
  - routine.discuss
  - routine.hands_on_activity

artifacts:
  - id: artifact.physical_product
    durability: perishable
    capture_note: Pizza is consumed; photo optional

evidence:
  primary:
    - evidence.artifact_presence
  supporting:
    - evidence.routine_completion

constraints:
  - constraint.time_limit
  - constraint.material_limit

hdd_alignment:
  - hdd.curiosity
  - hdd.sensemaking

notes: >
  Optional notes on mapping decisions...
```

## What does NOT go in examples

- Runbooks (execution-specific, not reusable)
- Educator Prep Packs (internal generation stage)
- Parent Briefs (generated output)
- Instructional assets lists (session-specific)

The Core Mapping and Playbook are the reusable structural artifacts.
Everything else is generated from them by the pipeline.

## Relationship to programs/

- `examples/` = reference implementations, maintained by Meta Humans,
  never modified by contributors, always canonical quality
- `programs/` = contributed programs, reviewed and promoted through
  the contribution workflow, staged before canonical promotion

A contributed program that reaches canonical quality could theoretically
be promoted to examples/ as a featured reference, but that's a deliberate
editorial decision, not part of the standard contribution workflow.
