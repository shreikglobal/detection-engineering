# MITRE ATT&CK Coverage

## Purpose

This document maps the detection engineering work to the MITRE ATT&CK
framework.

The purpose of the mapping is to show which adversary techniques are
covered by the implemented detections and where coverage gaps remain.

## Detection Mapping

| Detection | ATT&CK Technique | Tactic | Coverage |
|---|---|---|---|
| DET-001 | T1555 - Credentials from Password Stores | Credential Access | Covered |
| DET-002 | T1562.008 - Disable or Modify Cloud Firewall | Defense Evasion | Covered |
| DET-003 | T1074 - Data Staged | Collection | Covered |

## Coverage Interpretation

### Credential Access

DET-001 is mapped to T1555 and represents detection coverage for
credential-access activity observed during controlled testing.

### Defense Evasion

DET-002 is mapped to T1562.008 and represents detection coverage for
attempts to interfere with security controls/logging.

### Collection

DET-003 is mapped to T1074 and represents detection coverage for
data-staging activity.

This detection was observed during the Purple Team exercise but
subsequently breached the defined SLA and was moved to Draft for
tuning and re-validation.

## Coverage Gaps

ATT&CK mapping does not mean that every variation of a technique is
detected.

Coverage should therefore be interpreted as:

- Techniques validated by testing
- Techniques with partial coverage
- Techniques not yet tested
- Detection logic requiring additional tuning

## Why ATT&CK Coverage Matters

A technique-based coverage view provides a more meaningful security
assessment than simply counting the number of alerts or detection
rules.

It allows defenders to identify:

- Which adversary behaviours are covered.
- Which behaviours remain untested.
- Where detection quality needs improvement.
- Which areas should receive additional detection engineering effort.

## Validation Process

For each mapped technique:

1. Identify the ATT&CK technique.
2. Associate the technique with a detection rule.
3. Execute a controlled test where applicable.
4. Record the detection result.
5. Classify the coverage.
6. Tune and re-test failed or noisy detections.

## Evidence

Supporting material is maintained under:

- `detections/rules/`
- `detections/tests/`
- `simulation/atomic/`
- `simulation/purple-team/`
- `screenshots/`

## Limitation

This document represents the techniques mapped in this project.
It must not be interpreted as complete enterprise-wide ATT&CK
coverage.
