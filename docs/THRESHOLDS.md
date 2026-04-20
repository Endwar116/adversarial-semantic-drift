# SIC/T Threshold Reference

## Frozen Constants (SIC/T Protocol 2.0)

| Constant | Value | Derivation |
|---|---|---|
| **S*** | **2.76** | Semantic Chandrasekhar limit |
| THRESHOLD_CRITICAL | 4.14 | S* x 1.5 |
| THRESHOLD_COLLAPSE | 5.0 | S* x 1.81 |
| THRESHOLD_LETHAL | 5.52 | S* x 2.0 |
| ENTROPY_FACTOR | 0.18 | Layer 1 normalization constant |

## Zone Definitions

```
S_semantic value:
  [0, 2.76)    -> SAFE      - Normal operation
  [2.76, 4.14) -> ASSET     - Phase transition crossed - monitoring required
  [4.14, 5.0)  -> CRITICAL  - Active interception required
  [5.0, 5.52)  -> COLLAPSE  - Semantic state collapse
  [5.52, inf)  -> LETHAL    - Full isolation required
```

## S* = 2.76 — The Semantic Chandrasekhar Limit

S* is the boundary at which a semantic system transitions from safe operation to a state requiring monitoring.

S* corresponds to Chinese character entropy H_inf ~ 2.74 nats (Takahashi & Tanaka-Ishii 2018, delta = 0.02 nats), representing the information density ceiling of logographic writing systems.

## Entropy Drift Thresholds

| Value | Interpretation |
|---|---|
| delta_s < 0.18 | Acceptable - semantic fidelity maintained |
| delta_s in [0.18, 0.35] | Warning - review recommended |
| delta_s > 0.35 | Fail - semantic drift exceeds tolerance |

## Source

SIC/T Protocol 2.0 open protocol standard.
Protocol site: https://cloud-lx.onrender.com
