# Detection Engineering & Automated Response

## Project Overview

This project builds and validates a security detection engineering program using a controlled AWS test environment.

The project covers six stages:

1. Telemetry and security-data collection
2. Detection as code and validation
3. Purple-team attack simulation
4. Detection performance and SLA evaluation
5. Automated forensic collection
6. SIEM cost modelling and build-vs-buy analysis

## Project Objectives

- Build reviewable and testable security detections.
- Validate detections using controlled security tests.
- Map detection coverage to recognised security frameworks.
- Investigate a realistic multi-step attack scenario.
- Measure detection performance and alert quality.
- Collect forensic evidence automatically.
- Compare AWS-native security capabilities with SIEM alternatives.

## Repository Structure

```text
detections/
├── rules/
└── tests/

simulation/
├── atomic/
└── purple-team/

response/
├── containment/
└── forensics/

slo/

docs/
├── coverage-matrix.md
├── att&ck-coverage.md
├── siem-cost-model.md
└── research.md

screenshots/
