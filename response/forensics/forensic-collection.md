# Automated Forensic Collection

## Objective

The forensic workflow collects volatile and system evidence after a
security event so that investigators can reconstruct what happened
without relying only on the alert itself.

## Collection Workflow

Security Finding
        |
        v
Forensic Collection Trigger
        |
        v
Collect Evidence
        |
        +----------------------+
        |                      |
        v                      v
System Evidence          Network Evidence
        |                      |
        +----------+-----------+
                   |
                   v
Evidence Integrity
                   |
                   v
Secure Evidence Storage
                   |
                   v
Investigation / Analysis

## Evidence Collected

The forensic package should capture:

- Running processes
- Network connections
- System information
- Relevant security/log information
- Recent API activity where available
- Memory snapshot where supported and required

## Evidence Integrity

Each collected evidence artifact should be hashed using SHA-256.

Example:

`SHA256(evidence_file) -> integrity_hash`

The hash provides a mechanism for detecting modification of the
evidence after collection.

## Storage

Collected evidence should be stored separately from the affected
workload with controlled access.

Evidence storage should provide:

- Restricted access
- Clear timestamps
- File integrity information
- Separation from normal operational data
- Retention appropriate for the investigation

## Chain of Custody

For each evidence artifact record:

| Field | Description |
|---|---|
| Evidence ID | Unique identifier |
| Collection Time | Time evidence was collected |
| Source | System/resource from which evidence came |
| Collector | Collection process or analyst |
| SHA-256 | Integrity hash |
| Storage Location | Evidence storage location |
| Access History | Who accessed the evidence |

## Legal Considerations

Automated collection can support an investigation, but admissibility
depends on factors such as reliable collection procedures, integrity
protection, accurate timestamps, access controls and documented
chain of custody.

The collection process should therefore preserve the original
evidence and maintain an auditable record of handling.

## Scope

All collection is performed only within the controlled personal
test environment.

No production or client systems are targeted.

## Evidence Location

Supporting forensic artifacts are maintained under:

- `response/forensics/`
- `screenshots/`

Final evidence should be reviewed for sensitive information before
being included in the repository.
