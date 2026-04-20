# Adversarial Semantic Drift Replayer (ASDR)

**Cross-model attack trace analysis powered by SIC/T Protocol 2.0**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Protocol: SIC/T 2.0](https://img.shields.io/badge/Protocol-SIC%2FT%202.0-blue)](docs/SICT_FRAMEWORK.md)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue)](https://python.org)

---

## What This Is

ASDR is an open-source tool for analyzing **cross-model adversarial drift attacks** — a class of AI safety failures where a harmful workflow is decomposed across multiple AI models, with each individual model producing only benign outputs. The vulnerability emerges at the **composition layer**.

This tool quantifies semantic drift across a multi-step, multi-model attack trace using the **SIC/T Protocol 2.0** three-layer entropy framework, producing reproducible, verifiable evidence of semantic integrity failure.

**Key result:** A four-step, two-model attack trace that stays SAFE in per-model evaluation registers a confirmed **semantic phase transition** (S > S* = 2.76) when analyzed as a composition.

---

## The Core Finding

```
Single-model evaluation:   Step 1 OK  Step 2 OK  Step 3 OK  Step 4 OK
Composition-layer analysis: SAFE      SAFE       SAFE     BREACH (S=2.865 > S*=2.76)
```

No single model produced a complete sensitive workflow. The threat materialized only through **recomposition of outputs across the chain**.

---

## SIC/T Threshold System

```
0 ------- 2.76 ------- 4.14 ------- 5.0 ------- 5.52 ------- inf
   SAFE       ASSET      CRITICAL    COLLAPSE    LETHAL
               ^
           S* = 2.76  (Semantic Phase Transition Point)
```

| Constant | Value | Definition |
|---|---|---|
| **S*** | **2.76** | Semantic Chandrasekhar limit — phase transition boundary |
| CRITICAL | 4.14 | S* x 1.5 — active interception required |
| COLLAPSE | 5.0 | S* x 1.81 — semantic state collapse |
| LETHAL | 5.52 | S* x 2.0 — full isolation required |

---

## Quick Start

```bash
git clone https://github.com/Endwar116/adversarial-semantic-drift
cd adversarial-semantic-drift
pip install -r requirements.txt

# Run the included example trace
python sict_replay.py scenarios/s01_access_inconsistency.json

# Run simplified version (no SIC/T framework)
python replay.py
```

---

## Three-Layer Entropy Architecture

| Layer | Metric | Method | Role |
|---|---|---|---|
| **L1** `S_stat` | Statistical entropy | zlib compression ratio | Encoding Gate / format anomaly |
| **L2** `S_struct` | Structural entropy | TF-IDF Shannon entropy | Semantic field density |
| **L3** `S_evasion` | Evasion intent | Lexicon-based detection | Process entropy proxy |

```
S_semantic = 0.30 x S_stat + 0.40 x S_struct + 0.30 x S_evasion
```

> **Note:** L1 is a statistical proxy for encoding anomaly detection, not a semantic measure (SIC/T SP-003). For production, replace TF-IDF with semantic embeddings (e.g. `all-MiniLM-L6-v2`).

---

## ASDR Six-Layer Composition Scan

**Important:** This is an independent coordinate system for cross-model composition analysis — distinct from the canonical SIC/T six-layer integrity scan (L1 Existence / L2 Ontology / L3 Structure / L4 Operation / L5 Implementation / L6 Limitation). Per SIC/T Protocol Decision Record, each "Layer 6" coordinate system is independent and does not cross-reference.

| Layer | Function | What It Detects |
|---|---|---|
| L1 Encoding Gate | Format + injection anomaly | Injection patterns, format violations |
| L2 Semantic Drift | Distance from baseline | Semantic movement from safe initial state |
| L3 Risk Density | System/debug/tool lexicon | Escalating operational specificity |
| L4 Evasion Intent | Stealth/privileged/bypass language | Alert avoidance, privileged routing |
| L5 Model Switch | Cross-model handoff events | Compositional boundaries |
| L6 Composition Vulnerability | Switch + escalation | The core compositional failure mode |

**L6 activates at Step 2** — two steps before the final breach. Earliest detectable signal.

---

## Repository Structure

```
adversarial-semantic-drift/
├── sict_replay.py          — SIC/T Protocol 2.0 enhanced analyzer (main)
├── replay.py               — Standalone simplified analyzer
├── scenarios/
│   ├── s01_access_inconsistency.json  — Example attack trace
│   └── template.json                  — Scenario template
├── docs/
│   ├── SICT_FRAMEWORK.md   — SIC/T Protocol overview
│   ├── METHODOLOGY.md      — Three-layer entropy methodology
│   └── THRESHOLDS.md       — Threshold system reference
├── tests/
│   └── test_sict_replay.py — 22 tests (all passing)
└── requirements.txt
```

---

## Limitations

- Default embedding is TF-IDF (lexical); semantic embeddings improve L2 significantly
- Evasion lexicon is manually curated; a trained intent classifier generalizes better
- S_semantic weighting (0.30/0.40/0.30) is empirically set — calibration against labeled datasets pending
- **Boundary sensitivity:** Reference scenario S_semantic = 2.865, margin above S* = +0.105 (~3.8%). Different embedding backends may produce different values. Conclusion is directionally correct pending semantic embedding validation.

---

## Background: SIC/T Protocol

SIC/T (Semantic Integrity Control / Transfer) is an open protocol standard for cross-model semantic integrity in AI systems.

- **Protocol site:** [cloud-lx.onrender.com](https://cloud-lx.onrender.com)
- **GitHub:** [Endwar116/SIC-SIT-Protocol](https://github.com/Endwar116/SIC-SIT-Protocol)

Developed by **Andwar (Cheng, An-Hua)**, independent protocol researcher, Kaohsiung, Taiwan.

---

## Roadmap

- [ ] SIC-JS v2.0 output format (S_semantic -> `state`, Encoding Gate -> `event`, breach -> `intent`)
- [ ] Sentence embedding backend for L2 S_struct
- [ ] Multi-scenario batch runner
- [ ] Intent classifier to replace manual evasion lexicon
- [ ] S_semantic weight calibration against labeled dataset

---

## Responsible Use

This repository contains synthetic adversarial scenarios for defensive research only. See [SECURITY.md](SECURITY.md).

---

## License

MIT License — see [LICENSE](LICENSE).

The **SIC/T Protocol specification** is the intellectual property of Cheng, An-Hua (Andwar) / SIC/T Protocol Project. See [NOTICE](NOTICE).

---

## Citation

```
Andwar / Cheng, An-Hua (2026). Adversarial Semantic Drift Replayer: Cross-model attack analysis
via SIC/T Protocol 2.0 three-layer entropy framework.
https://github.com/Endwar116/adversarial-semantic-drift
```

---

[中文版 README](README.zh.md)
