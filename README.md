> **Author:** John Mitchell (@whmatrix)

# Structural Collaboration Primitives

**Generated:** 2025-01-23
**Status:** Derived from validated grammars; meta-layer only

---

## Purpose

Define a compact set of "collaboration primitives" as structural interaction operators, grounded in two validated grammars:

- **Research Corpus v1 (GPT):** 12-segment typology
- **Research Corpus v2 (Claude):** 8-segment typology

Primitives are structural transforms observable in dialogue exchange patterns—not topics, behaviors, or capabilities.

---

## Input Sources

### Comparative Grammar Layer

See [comparative-grammar-gpt-vs-claude](https://github.com/whmatrix/comparative-grammar-gpt-vs-claude):
- `comparative_grammar_matrix.md`
- `type_crosswalk_table.md`

### Source Typologies

- GPT: `segment_typology_map.md` from the GPT corpus (v1)
- Claude: `segment_typology_map.md` from the Claude corpus (v2)

---

## Output Files

| File | Content |
|------|---------|
| README.md | This document |
| collaboration_primitives.md | 12 structural primitives with signatures |
| primitive_to_type_mapping.md | Primitive → type mapping with strengths |

---

## Methodology

1. **Invariant extraction:** Operators present in both grammars
2. **Divergence extraction:** Operators unique to one grammar
3. **Operator definition:** Structural signature, triggers, failure modes
4. **Mapping construction:** Primitive ↔ type relationships

---

## Non-Claims Statement

This primitive layer does NOT claim:

### Equivalence Claims
- Primitives are NOT "atomic" or "fundamental"
- Primitives are NOT exhaustive of possible operators
- Presence in one grammar does NOT indicate absence in underlying system

### Behavioral Claims
- Primitives describe structural patterns, NOT model capabilities
- GPT-only primitives do NOT mean Claude cannot exhibit those patterns
- Claude-only primitives do NOT mean GPT cannot exhibit those patterns

### Quality Claims
- Neither primitive set is "better" or "more complete"
- Primitive count does NOT indicate sophistication

### Cognitive Claims
- No claims about reasoning, understanding, or intelligence
- No claims about alignment or safety properties
- No claims about interaction quality

### Scope Claims
- Derived from validated corpus material only
- No extrapolation to unsampled sessions
- No extrapolation to other operators or timeframes

**Structure-only analysis.** All statements traceable to typology documents.

---

## Limitations

| Limitation | Description |
|------------|-------------|
| Corpus dependency | Primitives reflect observed corpora only |
| Single operator | Same user for both corpora |
| Era constraint | GPT: May 2025; Claude: Jul-Oct 2025 |
| Domain skew | GPT: mixed tasks; Claude: technical only |

---

## Related

- [comparative-grammar-gpt-vs-claude](https://github.com/whmatrix/comparative-grammar-gpt-vs-claude) — Source grammar comparison from which these primitives are derived
- [interaction-mechanics-index](https://github.com/whmatrix/interaction-mechanics-index) — Queryable FAISS index using these primitives for structural retrieval
