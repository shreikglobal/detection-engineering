# Research and Written Analysis

## 1. MITRE ATT&CK vs D3FEND vs Cyber Kill Chain

### MITRE ATT&CK

MITRE ATT&CK is a knowledge base of adversary tactics and techniques
based on real-world observations. It provides a common language for
describing adversary behaviour and can be used to develop detection
analytics and assess defensive capabilities.

Source:
https://attack.mitre.org/resources/

### MITRE D3FEND

MITRE D3FEND is a knowledge graph of cybersecurity countermeasure
techniques. It focuses on defensive capabilities and provides a
standardised vocabulary for describing how defensive technologies
counter malicious activity.

D3FEND complements ATT&CK by focusing on the defensive side of the
problem.

Source:
https://d3fend.mitre.org/

### Cyber Kill Chain

The Cyber Kill Chain was developed by Lockheed Martin as part of its
Intelligence Driven Defense model. It describes seven stages of a
cyber intrusion:

1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command and Control
7. Actions on Objectives

The model helps analysts understand an intrusion as a sequence rather
than as isolated events.

Source:
https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html

---

## 2. Framework Comparison

| Framework | Primary Focus | Main Value | Project Use |
|---|---|---|---|
| MITRE ATT&CK | Adversary behaviour | Technique-based detection and coverage | Map detections to adversary techniques |
| MITRE D3FEND | Defensive countermeasures | Describe defensive capabilities | Identify defensive controls and countermeasures |
| Cyber Kill Chain | Attack progression | Understand intrusion sequence | Structure the Purple Team attack scenario |

### Coverage

ATT&CK is strongest when the objective is to describe and measure
specific adversary behaviours and detection coverage.

D3FEND is strongest when the objective is to describe defensive
countermeasures and relate defensive capabilities to adversary
behaviour.

Cyber Kill Chain is useful for communicating the overall progression
of an intrusion and identifying opportunities to interrupt an attack.

These frameworks are complementary rather than interchangeable.

---

## 3. Detection Engineering Maturity

Detection engineering maturity should not be measured only by the
number of alerts or rules.

A mature detection program should measure:

- Detection coverage
- Detection accuracy
- False-positive rate
- Mean Time to Detect (MTTD)
- Test repeatability
- Rule lifecycle
- ATT&CK technique coverage
- Detection gaps
- Tuning frequency
- Response effectiveness

### Detection Lifecycle

A practical lifecycle used in this project is:

Draft
→ Tested
→ Production

A detection that fails validation or breaches its defined SLA should
return to Draft for tuning and re-testing.

This creates a feedback loop in which detections are continuously
validated instead of being treated as permanent console configurations.

MITRE provides resources specifically describing the use of ATT&CK for
detection analytics, assessment and engineering.

Source:
https://attack.mitre.org/resources/get-started/detections-and-analytics/

Source:
https://attack.mitre.org/resources/get-started/assessment-and-engineering/

---

## 4. Purple Team After-Action Methodology

A Purple Team exercise should produce an evidence-based after-action
report rather than simply recording whether an alert appeared.

The report should document:

1. Exercise objective
2. Attack scenario
3. Techniques attempted
4. Detection result
5. Time to detect
6. Evidence generated
7. Detection gaps
8. False positives or noisy behaviour
9. Response actions
10. Remediation recommendations
11. Re-testing requirements

### Project Application

The project used the following simulated attack sequence:

Credential Access
→ Lateral Movement
→ Data Staging
→ Exfiltration

The exercise demonstrated both successful detection and a measurable
performance gap.

DET-003 (Data Staging) generated a detection but breached the defined
SLA. The rule was therefore moved to Draft for tuning and
re-validation.

This demonstrates why a Purple Team exercise should measure detection
quality and performance rather than only the presence of an alert.

---

## 5. Client-Facing Assessment

### What the Detection Program Reliably Catches

The project demonstrates detection coverage for the tested techniques
and provides version-controlled detection rules, repeatable test
definitions and an ATT&CK-based coverage view.

The Purple Team exercise also demonstrated that the detection
pipeline can identify activity across multiple stages of a controlled
attack scenario.

### What a Skilled Adversary Could Still Evade

No detection program should be treated as complete coverage.

An adversary may evade detection through:

- Untested techniques
- Variations of known techniques
- Missing telemetry
- Detection logic gaps
- Timing and behavioural changes
- Excessive alert noise that hides actionable events

The Atomic coverage matrix therefore records missed and unclassified
coverage rather than claiming complete protection.

### Highest-Priority Improvement

The most immediate improvement identified by this project is continued
detection tuning and re-validation of SLA-breaching detections,
particularly the Data Staging detection.

The rule should remain in Draft until it passes the defined validation
and performance requirements.

---

## 6. Conclusion

MITRE ATT&CK provides the adversary-behaviour language needed to map
and measure detection coverage.

MITRE D3FEND provides a complementary defensive vocabulary for
describing countermeasures.

Cyber Kill Chain provides a high-level model for understanding the
progression of an intrusion.

Together, these perspectives provide a stronger detection engineering
program than relying on alert counts alone.

The project therefore treats detection as an engineering lifecycle:
build, test, measure, tune, re-test and only then promote to
production.

---

## References

1. MITRE ATT&CK - Get Started
   https://attack.mitre.org/resources/

2. MITRE ATT&CK - Detections and Analytics
   https://attack.mitre.org/resources/get-started/detections-and-analytics/

3. MITRE ATT&CK - Assessment and Engineering
   https://attack.mitre.org/resources/get-started/assessment-and-engineering/

4. MITRE D3FEND
   https://d3fend.mitre.org/

5. MITRE D3FEND FAQ
   https://d3fend.mitre.org/faq/

6. Lockheed Martin Cyber Kill Chain
   https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html
