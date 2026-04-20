# Security Policy

## Responsible Use

This repository contains synthetic adversarial scenarios designed to study compositional vulnerabilities in LLM systems.

The examples may resemble operational procedures but are not intended for real-world use. They are provided solely for defensive research and evaluation.

ASDR is a research and evaluation tool for AI safety professionals. It is designed to demonstrate and measure compositional vulnerabilities in multi-model AI pipelines.

**Intended uses:**
- AI red-team evaluation and security research
- Developing and testing semantic integrity monitoring systems
- Academic research on cross-model adversarial behavior
- Building safer multi-agent AI pipelines

**Not intended for:**
- Operational exploitation of production AI systems without authorization
- Generating or amplifying harmful content
- Bypassing safety measures in deployed systems outside of authorized testing

## Reporting Vulnerabilities

If you discover a security issue in this tool itself, please open a GitHub issue or contact the maintainer directly.

## Example Trace Notice

The `scenarios/s01_access_inconsistency.json` file contains a synthetic attack trace constructed for research demonstration purposes. The model outputs shown are representative examples of how a cross-model decomposition attack can escalate through a conversation chain. They are not verbatim outputs from any specific production deployment.
