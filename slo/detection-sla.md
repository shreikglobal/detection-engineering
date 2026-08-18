# Detection SLA and Performance

## Objective

Measure detection performance using Mean Time to Detect (MTTD) and
False Positive Rate (FPR).

## Service Level Targets

| Metric | Target |
|---|---|
| Mean Time to Detect (MTTD) | < 5 minutes |
| False Positive Rate | < 5% |

## MTTD

MTTD measures the average time between the beginning/occurrence of
a detectable security event and the generation of an actionable alert.

Formula:

`MTTD = Sum(Time to Detect) / Number of Detected Events`

## False Positive Rate

False Positive Rate measures the proportion of alerts that are
classified as false positives.

Formula:

`FPR = False Positive Alerts / Total Alerts × 100`

## Detection Lifecycle

Detection validation follows this lifecycle:

Draft
→ Tested
→ Production

If a production detection breaches the defined SLA or fails validation:

Production
→ Draft

The detection must then be tuned and re-tested before promotion.

## SLA Breach

DET-003 (Data Staging) was identified as an SLA-breaching detection
during the controlled exercise.

Action:

`Production/Tested state → Draft`

Reason:

The detection did not meet the defined performance target and
requires tuning and re-validation.

## Measurement Requirements

Each test run should record:

- Event timestamp
- Detection timestamp
- Time to detect
- Alert classification
- False-positive/true-positive result
- Rule ID
- Final lifecycle state

## Evidence

Supporting evidence is maintained under:

- `slo/`
- `detections/rules/`
- `detections/tests/`
- `screenshots/`

## Notes

Exact MTTD and FPR values must be calculated from recorded test data.
No benchmark values are estimated or fabricated.
