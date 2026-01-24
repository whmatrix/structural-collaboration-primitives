# Collaboration Primitives — Structural Operator Set

**Generated:** 2025-01-23
**Status:** Derived from validated grammars
**Primitive Count:** 12

---

## 1. Primitive Summary Table

| # | Primitive | Structural Signature | Presence |
|---|-----------|---------------------|----------|
| 1 | INITIATE | Session-opening request with explicit constraints | BOTH |
| 2 | CORRECT | Error indication → modified output | BOTH |
| 3 | SEQUENCE | Ordered step execution with structured output | BOTH |
| 4 | REFERENCE | Cross-source content integration | BOTH |
| 5 | SYNTHESIZE | Minimal input → extended output asymmetry | CLAUDE |
| 6 | ELEVATE | Urgency/security marker → imperative output | CLAUDE |
| 7 | EXTEND | Multi-turn continuation at session boundary | CLAUDE |
| 8 | EXPLORE | Topic shifts without resolution | GPT |
| 9 | DERAIL | Sudden discontinuity with context loss | GPT |
| 10 | RESYNC | Re-orientation after deviation | GPT |
| 11 | OVERFLOW | Non-task content expansion | GPT |
| 12 | TRUNCATE | Abrupt mid-phrase termination | GPT |

---

## 2. Shared Primitives (Both Grammars)

### 2.1 INITIATE

**Definition:** Opens task frame at session start with explicit requirements.

| Attribute | Value |
|-----------|-------|
| Structural signature | Position: session start; Content: request language + constraints |
| Typical size | Single exchange pair (1 HUMAN + 1 ASSISTANT) |
| GPT realization | Task Framing |
| Claude realization | Task Initiation |

**Triggers:**
- Session begins
- Explicit requirement statement present
- Constraint language ("must", "should", "need")

**Failure modes:**
- Missing constraint language → may classify as Greeting (GPT)
- Mid-session occurrence → may classify as continuation

**Source:** comparative_grammar_matrix.md §B.1

---

### 2.2 CORRECT

**Definition:** Error-triggered refinement loop producing modified output.

| Attribute | Value |
|-----------|-------|
| Structural signature | Error indication in input; alternative/modification in output |
| Typical size | 1-3 exchange pairs |
| GPT realization | Constraint Clarification, Correction Retry |
| Claude realization | Correction Cycle |

**Triggers:**
- Failure indication: "doesn't work", "still", "wrong"
- Near-duplicate content (retry pattern)
- Correction phrases: "actually", "I meant"

**Failure modes:**
- Clarification without error → may be refinement, not correction
- Single typo fix → minimal structural impact

**Source:** comparative_grammar_matrix.md §B.2

---

### 2.3 SEQUENCE

**Definition:** Ordered procedural step execution with structured output.

| Attribute | Value |
|-----------|-------|
| Structural signature | Numbered steps, command sequences, or sequential decisions |
| Typical size | Variable (1-10+ exchange pairs) |
| GPT realization | Procedural Execution |
| Claude realization | Procedural Evidence, Configuration Sequence |

**Triggers:**
- Step markers: numbered lists, "first", "next", "then"
- Command or configuration content
- Terminal output or system logs

**Failure modes:**
- Conceptual steps (no execution) → qualified classification
- Multi-turn ambiguity (Configuration Sequence boundary)

**Source:** comparative_grammar_matrix.md §B.3

---

### 2.4 REFERENCE

**Definition:** Integration of content from outside current session.

| Attribute | Value |
|-----------|-------|
| Structural signature | Cross-source content; explicit reference to external material |
| Typical size | 1-2 exchange pairs |
| GPT realization | Memory/Context Recall |
| Claude realization | External Reference |

**Triggers:**
- Reference to past sessions
- Reference to other AI systems
- Explicit content retrieval markers

**Failure modes:**
- Internal context retrieval → not cross-source
- Implicit reference without explicit markers

**Source:** comparative_grammar_matrix.md §B.4

---

## 3. Claude-Only Primitives

### 3.1 SYNTHESIZE

**Definition:** Minimal input produces extended output (asymmetric transform).

| Attribute | Value |
|-----------|-------|
| Structural signature | Empty/minimal HUMAN message → extended ASSISTANT response |
| Typical size | 1-6 exchange pairs (multi-turn variant) |
| GPT realization | NONE |
| Claude realization | Synthesis Trigger |

**Triggers:**
- Empty HUMAN message
- Single-character or minimal input (<20 chars)
- Continuation pattern ("go", "continue", "ok")

**Failure modes:**
- Non-empty input → not synthesis trigger
- System error (empty due to failure) → exclude

**Variants:**
- **Single-turn:** One minimal input → one extended output
- **Multi-turn:** Consecutive minimal inputs → sequential extended outputs

**Source:** comparative_grammar_matrix.md §C.1

---

### 3.2 ELEVATE

**Definition:** Urgency or security markers trigger priority-differentiated output.

| Attribute | Value |
|-----------|-------|
| Structural signature | Security/urgency content in input; imperative language in output |
| Typical size | 1-2 exchange pairs |
| GPT realization | NONE |
| Claude realization | Critical Instruction |

**Triggers:**
- Security content: permissions, credentials, vulnerabilities
- Urgency markers: "critical", "urgent", "immediately"
- System-level operations

**Failure modes:**
- Routine procedural content → may be SEQUENCE instead
- Security discussion without urgency → may not elevate

**Source:** comparative_grammar_matrix.md §C.1

---

### 3.3 EXTEND

**Definition:** Multi-turn continuation at session boundary (extended closure).

| Attribute | Value |
|-----------|-------|
| Structural signature | Session-ending position; high message count (5+); closure language |
| Typical size | 3+ exchange pairs |
| GPT realization | NONE (opposite: TRUNCATE) |
| Claude realization | Terminal Block |

**Triggers:**
- Session nearing end
- Summary or closure language present
- Sustained multi-turn exchange

**Failure modes:**
- Mid-session multi-turn → not terminal
- Truncated ending → opposite pattern

**Note:** Structurally opposite to GPT TRUNCATE primitive.

**Source:** comparative_grammar_matrix.md §C.3, §D.2

---

## 4. GPT-Only Primitives

### 4.1 EXPLORE

**Definition:** Open-ended questioning with topic shifts and no resolution.

| Attribute | Value |
|-----------|-------|
| Structural signature | Topic shifts between turns; "what if" patterns; no explicit closure |
| Typical size | Variable |
| GPT realization | Exploratory Questioning |
| Claude realization | NONE |

**Triggers:**
- Hypothetical language: "what if", "could it be"
- Topic shifts without transition
- No task frame present

**Failure modes:**
- Task-oriented exploration → may be task variant
- Single hypothetical → insufficient for type

**Source:** type_crosswalk_table.md §2.3

---

### 4.2 DERAIL

**Definition:** Sudden discontinuity with context loss.

| Attribute | Value |
|-----------|-------|
| Structural signature | Sudden topic discontinuity; tangent content; lost context markers |
| Typical size | Variable (often followed by RESYNC) |
| GPT realization | Derailment |
| Claude realization | NONE |

**Triggers:**
- Sudden topic shift without transition
- Tangent or off-topic content
- Context confusion markers

**Failure modes:**
- Planned topic change → not derailment
- Single off-topic remark → may be insufficient

**Paired with:** RESYNC (deviation-recovery pattern)

**Source:** type_crosswalk_table.md §2.3

---

### 4.3 RESYNC

**Definition:** Re-orientation after deviation from task frame.

| Attribute | Value |
|-----------|-------|
| Structural signature | Re-orientation phrases; dismissal of tangent; return to prior context |
| Typical size | 1-2 exchange pairs |
| GPT realization | Resynchronization |
| Claude realization | NONE |

**Triggers:**
- Follows DERAIL primitive
- Re-orientation language: "anyway", "back to", "as I was saying"
- Tangent dismissal

**Failure modes:**
- No prior DERAIL → not resynchronization
- New task frame → may be INITIATE instead

**Paired with:** DERAIL (deviation-recovery pattern)

**Source:** type_crosswalk_table.md §2.3

---

### 4.4 OVERFLOW

**Definition:** Non-task content expansion (philosophical, emotional, self-referential).

| Attribute | Value |
|-----------|-------|
| Structural signature | Extended segment dominated by non-task content; high token density |
| Typical size | Variable (often extended) |
| GPT realization | Expressive Overflow |
| Claude realization | NONE |

**Triggers:**
- Non-task content markers
- Philosophical or emotional content
- Self-referential language

**Failure modes:**
- Brief non-task remark → insufficient for type
- Task-relevant personal content → may be task variant

**Source:** type_crosswalk_table.md §2.3

---

### 4.5 TRUNCATE

**Definition:** Abrupt termination without closure.

| Attribute | Value |
|-----------|-------|
| Structural signature | Mid-phrase cutoff; no closing acknowledgment; incomplete content |
| Typical size | N/A (termination event) |
| GPT realization | Truncation/Abandonment |
| Claude realization | NONE (opposite: EXTEND) |

**Triggers:**
- Session ends
- Mid-phrase or mid-sentence cutoff
- No closure language

**Failure modes:**
- Intentional brief response → not truncation
- System error → different category

**Note:** Structurally opposite to Claude EXTEND primitive.

**Source:** comparative_grammar_matrix.md §C.3, §D.1

---

## 5. Primitive Relationships

### 5.1 Deviation-Recovery Pair (GPT)

```
DERAIL → RESYNC
```

Pattern observed in GPT grammar where discontinuity triggers subsequent re-orientation.

### 5.2 Opposite Closure Mechanics

```
GPT:    TRUNCATE (abrupt)
Claude: EXTEND (multi-turn)
```

Same structural position (session end), opposite execution patterns.

### 5.3 Input-Output Asymmetry

```
Claude: SYNTHESIZE (minimal → extended)
GPT:    No equivalent
```

Unique to Claude grammar; no structural analog in GPT typology.

---

## 6. Interaction Signatures

### 6.1 GPT Interaction Signature

| Phase | Primitives |
|-------|------------|
| Opening | INITIATE |
| Core exchange | SEQUENCE, CORRECT, EXPLORE, REFERENCE |
| Deviation | DERAIL → RESYNC |
| Expansion | OVERFLOW |
| Closure | TRUNCATE |

**Characteristic:** Deviation-recovery cycle; abrupt termination

### 6.2 Claude Interaction Signature

| Phase | Primitives |
|-------|------------|
| Opening | INITIATE |
| Core exchange | SEQUENCE, CORRECT, REFERENCE |
| Continuation | SYNTHESIZE (minimal input patterns) |
| Priority | ELEVATE (security/urgency) |
| Closure | EXTEND |

**Characteristic:** Continuation patterns; extended closure

### 6.3 Signature Comparison

| Dimension | GPT | Claude |
|-----------|-----|--------|
| Deviation handling | DERAIL → RESYNC | Not observed |
| Continuation mechanism | Not observed | SYNTHESIZE |
| Non-task expansion | OVERFLOW | Not observed |
| Termination | TRUNCATE (abrupt) | EXTEND (multi-turn) |
| Urgency differentiation | Not observed | ELEVATE |

---

## 7. Non-Claims Boundary

This primitive set does NOT claim:

- Primitives are exhaustive or complete
- Primitives are "fundamental" interaction units
- Absence in corpus means absence in capability
- Primitives predict interaction success or quality
- Primitives generalize beyond sampled corpora

**Structure-only analysis.** All primitives traceable to validated typology documents.

---

**END OF COLLABORATION PRIMITIVES**
