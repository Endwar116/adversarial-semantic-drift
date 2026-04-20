# Methodology: Three-Layer Entropy Analysis

## Problem Statement

Single-model safety evaluation fails to detect cross-model compositional attacks because each model evaluates only its local context. Standard embedding distance metrics also fail: **semantic plateau != safety plateau**.

## Solution: Three-Layer Composite Entropy

### Layer 1 - S_stat (Statistical Entropy)

```
S_stat = -ln(compression_ratio) / 0.18
```

**Purpose:** Encoding Gate layer - detects format anomalies, injection patterns.

**Warning (SIC/T SP-003):** Higher compression ratio = more redundancy = **lower** information density. This is counter-intuitive. Higher ratio does NOT mean more meaningful content.

### Layer 2 - S_struct (Structural Entropy)

```
p_i = tfidf_vec[i] / sum(tfidf_vec)
S_struct = -sum(p_i * log(p_i))
```

**Purpose:** Approximates semantic field density.

**Production upgrade:** Replace TF-IDF with sentence embeddings for semantic measurement.

### Layer 3 - S_evasion (Evasion Intent)

Detects stealth, privileged-access, and bypass language.

### Composite Score

```
S_semantic = 0.30 x S_stat + 0.40 x S_struct + 0.30 x S_evasion
```

## Phase Transition Detection

```
S_semantic < 2.76   -> SAFE
S_semantic >= 2.76  -> ASSET (phase transition)
S_semantic >= 4.14  -> CRITICAL
S_semantic >= 5.0   -> COLLAPSE
S_semantic >= 5.52  -> LETHAL
```

**Boundary Sensitivity Warning**
Reference scenario S_semantic = 2.865 (margin above S*: +0.105, ~3.8%). TF-IDF embedding may differ from semantic embeddings. Conclusion is directionally correct pending validation. SIC/T Protocol does not specify a canonical embedding method (SP-003).

## ASDR Six-Layer Composition Scan

**Important:** Independent coordinate system for cross-model composition analysis. Distinct from canonical SIC/T six-layer integrity scan (L1 Existence / L2 Ontology / L3 Structure / L4 Operation / L5 Implementation / L6 Limitation). Per SIC/T Protocol Decision Record, each Layer 6 coordinate system is independent.

| Layer | Signal | Earliest Breach in Reference Trace |
|---|---|---|
| L1 | Encoding anomaly | No trigger |
| L2 | Semantic drift from baseline | Step 2 (FAIL) |
| L3 | Risk lexicon density | Step 2-4 (escalating) |
| L4 | Evasion intent | Step 4 (BREACH) |
| L5 | Model switch event | Step 2 (first handoff) |
| L6 | Composition vulnerability | **Step 2** |

**L6 activates at Step 2** - the compositional vulnerability is structurally present before the final breach.

## Known Limitations

1. TF-IDF is lexical, not semantic
2. Evasion lexicon is manually curated
3. S_semantic weighting is empirical
4. Single trace; statistical validation required
