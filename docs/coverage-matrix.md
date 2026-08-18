# Atomic Red Team Coverage Matrix

## Purpose

This document records the detection coverage validated through
controlled Atomic Red Team testing.

The objective is to classify tested techniques as:

- Reliable
- Noisy
- Missed

Only results supported by the recorded exercise evidence are treated
as validated results.

## Coverage Matrix

| Test | Technique | Detection Result | Classification | Notes |
|---|---|---|---|---|
| Atomic Test 1 | T1057 - Process Discovery | Detection observed during testing | Reliable | Validated during controlled test |
| Atomic Test 2 | T1057 - Process Discovery | Detection observed during testing | Reliable | Additional validation |
| Atomic Test 3 | T1057 - Process Discovery | Detection observed during testing | Reliable | Additional validation |
| Atomic Test 4 | T1057 - Process Discovery | Detection observed during testing | Reliable | Additional validation |
| Atomic Test 5 | T1057 - Process Discovery | Detection observed during testing | Reliable | Additional validation |
| Atomic Test 6 | T1057 - Process Discovery | Detection observed during testing | Reliable | Additional validation |
| Atomic Test 7 | T1057 - Process Discovery | Test execution did not produce the expected result | Missed | Requires detection improvement |
| Additional tests | Not recorded | Not recorded | Not classified | Exact test record not available |

## Classification Definitions

### Reliable

The test produced the expected security detection and the result
was usable for investigation.

### Noisy

The detection fired but produced excessive or non-actionable activity
that requires tuning.

### Missed

The controlled test was executed but the expected detection did not
fire.

## Key Finding

The testing demonstrated that detection validation must be based on
actual adversary simulation rather than only on the existence of a
detection rule.

A missed test represents a detection coverage gap and should result
in further detection engineering and re-testing.

## Detection Engineering Follow-up

For any missed or noisy detection:

1. Review the detection logic.
2. Identify the telemetry required for the technique.
3. Tune the detection.
4. Re-run the Atomic test.
5. Record the new result.
6. Promote the rule only after successful validation.

## Evidence

Supporting evidence is maintained in:

- `simulation/atomic/`
- `detections/rules/`
- `detections/tests/`
- `screenshots/`

## Important Limitation

The repository should not claim complete Atomic Red Team coverage
where an individual test's exact technique ID, execution result or
classification was not captured in the original evidence.

Additional tests should be added to this matrix only after their
execution evidence has been verified.
