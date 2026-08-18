# Purple Team After-Action Report

## Exercise Overview

This document records the controlled Purple Team exercise performed
in the personal AWS test environment.

The exercise simulated a multi-stage attack path and evaluated whether
the detection and response controls could identify the activity.

## Attack Scenario

The simulated attack path was:

1. Credential Access
2. Lateral Movement
3. Data Staging
4. Exfiltration

The activity was performed only in the controlled test environment.

## Detection Results

| Technique / Stage | Detection | Time to Detect | Result |
|---|---|---|---|
| Credential Access | Yes | Recorded in exercise evidence | Detected |
| Lateral Movement | Yes | Recorded in exercise evidence | Detected |
| Data Staging | Yes | Recorded in exercise evidence | Detected, SLA breach observed |
| Exfiltration | Yes | Recorded in exercise evidence | Detected |

> Time-to-detect values should be taken from the original exercise
> evidence. No estimated values are inserted here.

## Key Finding

The Data Staging detection (DET-003) generated an actionable detection
but breached the defined detection SLA.

As a result, the detection was demoted to Draft for further tuning
rather than being treated as a production-ready detection.

## Detection Gaps

The exercise demonstrated that detection success alone is not enough.
Detection quality must also be evaluated against performance targets,
false-positive behaviour and response requirements.

The main identified gap was the SLA performance of the Data Staging
detection.

## Remediation Actions

- Review the DET-003 detection logic.
- Tune the detection to improve detection performance.
- Re-test the rule after tuning.
- Keep the rule in Draft until it passes validation.
- Re-measure MTTD and false-positive performance.
- Promote the rule only after successful validation.

## Evidence

Supporting screenshots and evidence are stored in:

- `screenshots/`
- `simulation/purple-team/`
- `detections/rules/`
- `detections/tests/`
- `slo/`

Each evidence item should explain what it proves and must not expose
account IDs, ARNs, credentials or other sensitive information.

## Conclusion

The Purple Team exercise demonstrated that the detection program can
identify activity across the simulated attack path while also exposing
a measurable performance gap in the Data Staging detection.

The exercise therefore provides both successful detection evidence and
an actionable improvement path rather than treating alert generation
alone as proof of detection maturity.
