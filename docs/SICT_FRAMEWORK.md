# SIC/T Protocol Framework — Overview

## What is SIC/T?

**SIC/T** (Semantic Integrity Control / Transfer) is an open protocol standard for governing semantic integrity in AI systems. It defines how meaning is preserved, monitored, and transferred as information flows through AI pipelines — including across model boundaries.

SIC/T is not a product. It is a **protocol standard**, analogous to TCP/IP for the network layer — but for the semantic layer of AI communication.

## Two Components

**SIC (Semantic Integrity Control)**
Governs semantic boundaries and monitors entropy within a single AI interaction or pipeline stage. Core functions: governance boundary determination, semantic entropy monitoring, halt mechanisms.

**SIT (Semantic Isolation Transfer)**
Ensures semantic state is safely transmitted across conversation boundaries, model handoffs, and agent transitions. Core mechanism: three-way handshake (SYN -> SYN-ACK -> ACK).

## The Threshold System

| Constant | Value | Zone | Meaning |
|---|---|---|---|
| S* | 2.76 | ASSET boundary | Semantic phase transition point |
| CRITICAL | 4.14 | CRITICAL | S* x 1.5 |
| COLLAPSE | 5.0 | COLLAPSE | S* x 1.81 |
| LETHAL | 5.52 | LETHAL | S* x 2.0 |

## Three-Layer Entropy Architecture

**Layer 1 - Statistical Entropy (S_stat)**
zlib compression ratio. Encoding Gate use only. Not a semantic measure (SP-003).

**Layer 2 - Structural Entropy (S_struct)**
Shannon entropy over TF-IDF token distribution. Core semantic measurement layer.

**Layer 3 - Process Entropy (S_evasion)**
Evasion intent detector. Captures stealth, privileged-access, and bypass language.

## ASDR's Position

ASDR implements a **black-box** approximation of SIC/T semantic measurement using only model output text.

## Further Reading

- Protocol site: https://cloud-lx.onrender.com
- GitHub: https://github.com/Endwar116/SIC-SIT-Protocol
