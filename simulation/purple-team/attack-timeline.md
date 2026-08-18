# Purple Team Attack Timeline

## Scenario

Controlled Purple Team exercise performed in the personal AWS test
environment.

## Attack Sequence

| Order | Attack Stage | Detection Status | Evidence |
|---|---|---|---|
| 1 | Credential Access | Detected | Exercise evidence |
| 2 | Lateral Movement | Detected | Exercise evidence |
| 3 | Data Staging | Detected / SLA Breach | DET-003 |
| 4 | Exfiltration | Detected | Exercise evidence |

## Investigation Flow

Credential Access
→ Lateral Movement
→ Data Staging
→ Exfiltration

## Detection Pivot

The investigation correlated the individual detection events into a
single attack sequence rather than treating each alert independently.

## Key Investigation Finding

DET-003 (Data Staging) was detected but did not meet the defined SLA.
The rule was therefore moved to Draft for tuning and re-validation.

## Evidence

Detailed screenshots and supporting evidence are maintained under:

- `screenshots/`
- `detections/rules/`
- `detections/tests/`
- `slo/`

## Notes

Exact timestamps and benchmark values should be taken from the original
exercise evidence and should not be estimated.
