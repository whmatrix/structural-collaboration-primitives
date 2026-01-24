# Primitive → Type Mapping Table

**Generated:** 2025-01-23
**Purpose:** Structural alignment between collaboration primitives and source typology segment types

---

## 1. Master Mapping Matrix

### 1.1 Primitive → GPT Type Mapping

| Primitive | GPT Type | Mapping Strength | Justification |
|-----------|----------|------------------|---------------|
| INITIATE | Task Framing | **STRONG** | Direct realization; same position, markers |
| CORRECT | Constraint Clarification | **STRONG** | Direct realization; clarification function |
| CORRECT | Correction Retry | **STRONG** | Direct realization; retry function |
| SEQUENCE | Procedural Execution | **STRONG** | Direct realization; step-based exchange |
| REFERENCE | Memory/Context Recall | **STRONG** | Direct realization; cross-session reference |
| SYNTHESIZE | — | **NONE** | No GPT type captures asymmetric output |
| ELEVATE | — | **NONE** | No GPT type with urgency markers |
| EXTEND | — | **NONE** | Opposite of Truncation/Abandonment |
| EXPLORE | Exploratory Questioning | **STRONG** | Direct realization; open-ended pattern |
| DERAIL | Derailment | **STRONG** | Direct realization; discontinuity pattern |
| RESYNC | Resynchronization | **STRONG** | Direct realization; re-orientation |
| OVERFLOW | Expressive Overflow | **STRONG** | Direct realization; non-task expansion |
| TRUNCATE | Truncation/Abandonment | **STRONG** | Direct realization; abrupt termination |

### 1.2 Primitive → Claude Type Mapping

| Primitive | Claude Type | Mapping Strength | Justification |
|-----------|-------------|------------------|---------------|
| INITIATE | Task Initiation | **STRONG** | Direct realization; same position, markers |
| CORRECT | Correction Cycle | **STRONG** | Direct realization; failure-retry loop |
| SEQUENCE | Procedural Evidence | **PARTIAL** | Shared procedural content; different focus |
| SEQUENCE | Configuration Sequence | **PARTIAL** | Shared sequential structure; multi-turn variant |
| REFERENCE | External Reference | **STRONG** | Direct realization; cross-source content |
| SYNTHESIZE | Synthesis Trigger | **STRONG** | Direct realization; asymmetric pattern |
| ELEVATE | Critical Instruction | **STRONG** | Direct realization; urgency/security |
| EXTEND | Terminal Block | **STRONG** | Direct realization; multi-turn closure |
| EXPLORE | — | **NONE** | No Claude type for open-ended exploration |
| DERAIL | — | **NONE** | No Claude type for discontinuity |
| RESYNC | — | **NONE** | No Claude type for re-orientation |
| OVERFLOW | — | **NONE** | No Claude type for non-task expansion |
| TRUNCATE | — | **NONE** | Opposite of Terminal Block |

---

## 2. Strength Definitions

| Strength | Criteria |
|----------|----------|
| **STRONG** | Direct realization; type is primary instantiation of primitive |
| **PARTIAL** | Overlapping function; shared markers but different scope/boundary |
| **WEAK** | Minimal overlap; structural similarity without functional equivalence |
| **NONE** | No corresponding type; primitive not represented in grammar |

---

## 3. Coverage Analysis

### 3.1 Primitive Coverage by Grammar

| Primitive | GPT Coverage | Claude Coverage |
|-----------|--------------|-----------------|
| INITIATE | STRONG | STRONG |
| CORRECT | STRONG | STRONG |
| SEQUENCE | STRONG | PARTIAL × 2 |
| REFERENCE | STRONG | STRONG |
| SYNTHESIZE | NONE | STRONG |
| ELEVATE | NONE | STRONG |
| EXTEND | NONE | STRONG |
| EXPLORE | STRONG | NONE |
| DERAIL | STRONG | NONE |
| RESYNC | STRONG | NONE |
| OVERFLOW | STRONG | NONE |
| TRUNCATE | STRONG | NONE |

### 3.2 Coverage Summary

| Grammar | STRONG | PARTIAL | NONE | Total Primitives |
|---------|--------|---------|------|------------------|
| GPT | 9 | 0 | 3 | 12 |
| Claude | 6 | 2 | 4 | 12 |

### 3.3 Shared vs Unique Primitives

| Category | Count | Primitives |
|----------|-------|------------|
| Shared (Both STRONG) | 4 | INITIATE, CORRECT, SEQUENCE, REFERENCE |
| Claude-only | 3 | SYNTHESIZE, ELEVATE, EXTEND |
| GPT-only | 5 | EXPLORE, DERAIL, RESYNC, OVERFLOW, TRUNCATE |

---

## 4. Type → Primitive Reverse Mapping

### 4.1 GPT Types → Primitives

| GPT Type | Primary Primitive | Secondary Primitive |
|----------|-------------------|---------------------|
| Task Framing | INITIATE | — |
| Constraint Clarification | CORRECT | — |
| Procedural Execution | SEQUENCE | — |
| Exploratory Questioning | EXPLORE | — |
| Derailment | DERAIL | — |
| Resynchronization | RESYNC | — |
| Expressive Overflow | OVERFLOW | — |
| Correction Retry | CORRECT | — |
| Memory/Context Recall | REFERENCE | — |
| Precision Drilling | CORRECT | (absorbed) |
| Truncation/Abandonment | TRUNCATE | — |
| Greeting/Pleasantry | — | (no primitive) |

**Note:** Precision Drilling absorbed into CORRECT primitive. Greeting/Pleasantry has no primitive equivalent (structurally thin).

### 4.2 Claude Types → Primitives

| Claude Type | Primary Primitive | Secondary Primitive |
|-------------|-------------------|---------------------|
| Task Initiation | INITIATE | — |
| Correction Cycle | CORRECT | — |
| Procedural Evidence | SEQUENCE | — |
| External Reference | REFERENCE | — |
| Configuration Sequence | SEQUENCE | — |
| Critical Instruction | ELEVATE | — |
| Synthesis Trigger | SYNTHESIZE | — |
| Terminal Block | EXTEND | — |

---

## 5. Mapping Visualization

```
PRIMITIVES (12)                     GPT TYPES (12)              CLAUDE TYPES (8)
───────────────                     ──────────────              ────────────────

INITIATE ─────────────────STRONG──→ Task Framing
         ╲────────────────STRONG───────────────────────────────→ Task Initiation

CORRECT ──────────────────STRONG──→ Constraint Clarification
         │                STRONG──→ Correction Retry
         │                          (absorbs: Precision Drilling)
         ╲────────────────STRONG───────────────────────────────→ Correction Cycle

SEQUENCE ─────────────────STRONG──→ Procedural Execution
         ╲────────────────PARTIAL──────────────────────────────→ Procedural Evidence
          ╲───────────────PARTIAL──────────────────────────────→ Configuration Sequence

REFERENCE ────────────────STRONG──→ Memory/Context Recall
          ╲───────────────STRONG───────────────────────────────→ External Reference

SYNTHESIZE ───────────────NONE────→ (no equivalent)
           ╲──────────────STRONG───────────────────────────────→ Synthesis Trigger

ELEVATE ──────────────────NONE────→ (no equivalent)
        ╲─────────────────STRONG───────────────────────────────→ Critical Instruction

EXTEND ───────────────────NONE────→ (opposite: Truncation)
       ╲──────────────────STRONG───────────────────────────────→ Terminal Block

EXPLORE ──────────────────STRONG──→ Exploratory Questioning
        ╲─────────────────NONE─────────────────────────────────→ (no equivalent)

DERAIL ───────────────────STRONG──→ Derailment
       ╲──────────────────NONE─────────────────────────────────→ (no equivalent)

RESYNC ───────────────────STRONG──→ Resynchronization
       ╲──────────────────NONE─────────────────────────────────→ (no equivalent)

OVERFLOW ─────────────────STRONG──→ Expressive Overflow
         ╲────────────────NONE─────────────────────────────────→ (no equivalent)

TRUNCATE ─────────────────STRONG──→ Truncation/Abandonment
         ╲────────────────NONE─────────────────────────────────→ (opposite: Terminal Block)

                                    Greeting/Pleasantry ←──────── (no primitive)
```

---

## 6. Absorption Notes

### 6.1 Precision Drilling → CORRECT

GPT's Precision Drilling type (narrow question, exact specification, rejection of approximation) absorbed into CORRECT primitive:
- Both involve refinement toward specification
- Drilling is a specialized correction pattern
- Insufficient structural distinction for separate primitive

### 6.2 Greeting/Pleasantry → No Primitive

GPT's Greeting/Pleasantry type not elevated to primitive status:
- Structurally thin (salutation only)
- Does not represent structural transform
- Insufficient impact on exchange sequence

---

## 7. Opposite Mapping Pairs

| Primitive | GPT Type | Claude Type | Relationship |
|-----------|----------|-------------|--------------|
| TRUNCATE | Truncation/Abandonment | — | GPT has type |
| EXTEND | — | Terminal Block | Claude has type |

TRUNCATE and EXTEND represent opposite termination mechanics:
- TRUNCATE: Abrupt, mid-phrase cutoff
- EXTEND: Multi-turn continuation with closure

These primitives map to types in their respective grammars but have no cross-grammar equivalent—they represent structural opposites.

---

## 8. Non-Claims Statement

This mapping table does NOT claim:

- Mapping completeness or correctness
- Equivalence between mapped types
- Primitives capture all type behavior
- Absorption decisions are definitive
- Mapping generalizes beyond sampled corpora

**Structure-only analysis.** All mappings traceable to source typology documents.

---

**END OF MAPPING TABLE**
