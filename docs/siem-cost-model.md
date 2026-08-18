# SIEM Cost Model and Build-vs-Buy Analysis

## Objective

Compare three security monitoring approaches across three daily log
volumes:

- 10 GB/day
- 100 GB/day
- 1 TB/day

The comparison covers:

1. AWS-native security stack
2. Microsoft Sentinel
3. Amazon OpenSearch

The model separates ingestion costs from storage, compute, retention
and other supporting-service costs.

---

## 1. AWS Security Lake Baseline

For this baseline, the modeled logs use the documented "other AWS
security logs" ingestion category.

Reference assumptions:

- Ingestion: $0.25/GB
- Normalization: $0.035/GB
- Monthly period: 30 days

### Monthly Volume

| Daily Volume | Monthly Volume |
|---|---:|
| 10 GB/day | 300 GB |
| 100 GB/day | 3,000 GB |
| 1 TB/day | 30,000 GB |

### Baseline Calculation

Formula:

`Monthly Cost = Monthly GB × (Ingestion Rate + Normalization Rate)`

| Daily Volume | Monthly Volume | Baseline Monthly Cost |
|---|---:|---:|
| 10 GB/day | 300 GB | $85.50 |
| 100 GB/day | 3,000 GB | $855.00 |
| 1 TB/day | 30,000 GB | $8,550.00 |

### Important Cost Exclusions

This baseline does not include:

- Amazon S3 storage
- Query costs
- Data transfer
- Supporting AWS services
- Additional retention costs

Therefore these figures are modelling assumptions and not vendor
quotes.

---

## 2. Microsoft Sentinel

Microsoft Sentinel uses a data-volume-based pricing model.

The effective cost depends on factors including:

- Azure region
- Pricing tier
- Pay-As-You-Go vs Commitment Tier
- Data ingestion
- Retention
- Additional Azure services

Monthly volume:

`Monthly GB = Daily GB × 30`

| Daily Volume | Monthly Volume |
|---|---:|
| 10 GB/day | 300 GB |
| 100 GB/day | 3,000 GB |
| 1 TB/day | 30,000 GB |

Because Sentinel pricing depends on the applicable region and pricing
model, a universal USD/GB rate is not assumed in this document.

---

## 3. Amazon OpenSearch

OpenSearch is infrastructure-based rather than a simple SIEM
per-GB license.

Primary cost drivers include:

- Compute/instance hours
- Storage
- Data transfer
- Cluster sizing
- Retention
- UltraWarm/cold storage
- High-availability requirements

Monthly data volumes:

| Daily Volume | Monthly Volume |
|---|---:|
| 10 GB/day | 300 GB |
| 100 GB/day | 3,000 GB |
| 1 TB/day | 30,000 GB |

Actual OpenSearch cost requires a defined cluster architecture,
instance type, storage configuration and retention period.

---

## 4. Capability Comparison

| Capability | AWS Security Lake | Microsoft Sentinel | OpenSearch |
|---|---|---|---|
| AWS integration | Strong | Good | Good |
| Managed SIEM operations | High | High | Lower |
| Infrastructure control | Medium | Lower | High |
| Customisation | High | High | High |
| Storage control | High | Medium | High |
| Operational overhead | Lower | Lower | Higher |
| Best fit | AWS-centric environments | Microsoft/Azure environments | Custom/self-managed environments |

---

## 5. Crossover Analysis

A precise commercial-SIEM crossover point cannot be calculated from
the available model without a region-specific Sentinel price and a
defined OpenSearch architecture.

Therefore this project does not invent a crossover value.

The correct crossover calculation is:

`Find volume where Commercial SIEM Total Cost <= AWS Native Total Cost`

The comparison must include equivalent:

- Ingestion
- Storage
- Retention
- Querying
- Compute
- Data transfer
- Operational requirements

---

## 6. Recommendation

For an AWS-centric security environment, AWS Security Lake is the
primary recommendation because it provides strong integration with
AWS security telemetry and a security-data-lake architecture.

For a Microsoft/Azure-centric environment, Microsoft Sentinel is the
primary managed-SIEM recommendation.

For an organisation requiring maximum infrastructure and architecture
control, OpenSearch is the primary recommendation, provided the team
can support the additional operational overhead.

---

## 7. Decision Rule

The final platform decision should not be based only on ingestion
price.

The decision should consider:

- Log volume
- Retention
- Detection capability
- AWS/Azure integration
- Query requirements
- Infrastructure management
- Operational overhead
- Scalability
- Security requirements

## Model Status

STAGE-6-COMPARISON-COMPLETE

These figures and assumptions are a project cost model and should be
validated against the applicable vendor pricing calculators before
production procurement.
