# Detection Engineering

## Threat Detection Engineering — Adversary Simulation, Detection-as-Product and Purple Team

This project implements a detection engineering lifecycle with adversary simulation, purple team validation, detection performance SLAs, automated forensic collection, and SIEM cost analysis.

## Project Objectives

- Build a controlled detection lifecycle from Draft to Production.
- Validate detections using adversary simulation.
- Measure detection reliability, MTTD and false-positive rate.
- Perform a structured purple team exercise.
- Automate high-confidence forensic collection.
- Compare AWS-native detection capabilities with SIEM alternatives.

## Detection Lifecycle

Draft → Tested → Production → Deprecated

A detection rule must have a valid test before it can reach Production.

## Repository Structure

- `detections/` — Detection rules and test cases
- `simulation/` — Adversary simulation and purple team exercises
- `response/` — Containment and forensic collection
- `slo/` — Detection performance SLA configuration
- `docs/` — Coverage, research and cost-model documentation
- `screenshots/` — Evidence from the project

## Safety

All simulations are performed only in an isolated personal test environment. No live or client systems are targeted.

## Author

Vedant Kale
