# Automated Containment Workflow

## Objective

The containment workflow is designed to provide a fast response to a
clear-cut security finding while preventing high-impact actions from
being performed automatically without human approval.

## Workflow

Security Finding
        |
        v
Detection / Alert
        |
        v
Validate Finding
        |
        +-----------------------------+
        |                             |
        v                             v
Reversible Action              High-Impact Action
        |                             |
        v                             v
Automatic Containment          Human Approval Required
        |                             |
        v                             v
Verify Result                 Approved -> Execute
        |                     Rejected -> Do Not Execute
        v
Record Evidence

## Automatic Containment

Automatic containment should be limited to actions that are:

- Clearly associated with a confirmed finding.
- Reversible.
- Low risk to the test environment.
- Logged for later investigation.

Examples include temporarily isolating a test resource or disabling
a test credential when the finding is clear and the action can be
reversed safely.

## Human Approval

Irreversible or high-impact actions must not be executed automatically.

The workflow requires an analyst or authorised human to review the
finding and explicitly approve the action before execution.

Examples include:

- Permanent deletion of resources.
- Destructive changes.
- High-impact access changes.
- Actions that could affect business availability.

## Safety Controls

- All actions are restricted to the personal controlled test
  environment.
- Findings are validated before containment.
- High-impact actions require human approval.
- Every containment action should produce an auditable record.
- Evidence should be preserved before destructive actions.
- Containment results should be verified after execution.

## Measurement

Containment performance should be measured using:

- Detection timestamp
- Containment trigger timestamp
- Action execution timestamp
- Verification timestamp

Measured response time:

`Containment Response Time = Action Execution Time - Detection/Trigger Time`

Exact benchmark values must come from the recorded exercise evidence
and should not be estimated.

## Evidence

Supporting evidence is maintained under:

- `response/containment/`
- `response/forensics/`
- `slo/`
- `screenshots/`

## Project Scope

This workflow describes the controlled test-environment implementation
and should not be interpreted as authorisation to perform destructive
actions against production or client systems.
