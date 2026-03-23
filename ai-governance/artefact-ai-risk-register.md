# AI Risk Register — Credit Scoring Model Deployment  
**Veriflow Payments Ltd**

*This is a thinking exercise, not a real organisation.*

---

**Document type:** AI Risk Register  
**Prepared by:** Arken Systems GRC Function  
**Addressed to:** Chief Risk Officer and AI Governance Committee  
**Date:** March 2025  
**Classification:** Confidential — Internal Distribution Only  
**Review cycle:** Quarterly, or upon material change to model, vendor, or regulatory context  

**Related documents:**  
- Artefact A — Risk Acceptance With Teeth  
- Artefact B — Third-Party Control Gap Analysis (Databridge Analytics Ltd)

---

## Context

Veriflow Payments Ltd is a Series B UK fintech regulated by the FCA under the Payment Services Regulations 2017, processing card payments for approximately 40,000 SME merchants.

In Q1 2025, Veriflow deployed an AI-powered credit scoring model from ClearScore AI Ltd to support merchant onboarding and credit limit decisions.

The model assesses applications using transaction history, business profile data, and behavioural signals. Veriflow is the **deployer**; ClearScore AI Ltd is the **provider**.

Under the EU AI Act, this system is classified as **high-risk AI (Annex III, 5(b))**, meaning Veriflow carries direct obligations regardless of who built the model.

This register identifies material risks, evaluates current controls, and records residual exposure.

> This is a live governance document — not a one-time compliance exercise.

---

## Scoring Methodology

| Metric | Scale |
|------|------|
| Likelihood | 1 (Rare) → 5 (Almost certain) |
| Impact | 1 (Negligible) → 5 (Severe) |
| Inherent risk | Likelihood × Impact |
| Residual risk | Likelihood × Impact (after controls) |

**Risk appetite threshold:** Residual score ≥ 9 requires Risk Committee escalation.

---

## Key Management View

- One risk exceeds escalation threshold: **RISK-AI-001 (Discriminatory Output)**  
- Most material control gap: lack of independent fairness validation  
- Most urgent compliance gap: incomplete EU AI Act deployer readiness  
- Most significant operational vulnerability: untested manual fallback for vendor failure  

---

## Risk Register

---

### RISK-AI-001 — Discriminatory Output (Protected Characteristic Bias)

**Category:** Fairness / Discrimination  

**Description:**  
The model may generate systematically lower scores for applicants sharing protected characteristics, not because of genuine credit risk differences but due to bias in training data, feature selection, or proxy variables.

Veriflow remains legally accountable for outcomes regardless of vendor responsibility.

---

#### Risk Scoring

| Stage | Likelihood | Impact | Score | Level |
|------|-----------|--------|------|------|
| Inherent | 3 | 5 | 15 | Critical |
| Residual | 2 | 5 | 10 | High |

---

#### Current Controls

- Vendor contractual requirement for bias testing  
- Internal fairness audit using disaggregated outcome data  
- Quarterly monitoring by demographic segment (where available)  
- Human review for declines above £10,000  

---

#### Control Gaps

- Fairness audit not independently validated  
- Incomplete demographic data limits monitoring accuracy  
- Human review lacks structured decision criteria  

---

#### Residual Risk Narrative

Controls reduce likelihood but cannot eliminate impact. Discriminatory outcomes carry regulatory and reputational consequences that do not reduce because controls exist. Residual exposure remains material and requires ongoing oversight.

---

**Owner:** Chief Risk Officer  

**Review triggers:**
- Regulatory enforcement against peer firms  
- ICO or FCA guidance updates  
- Evidence of skewed outcomes in monitoring  

---

#### Regulatory Hook

| Framework | Relevance |
|----------|----------|
| EU AI Act — Art. 9, 10, 15 | Risk management, data governance, robustness |
| EU AI Act — Art. 13 | Transparency and explanation |
| Equality Act 2010 — s.19 | Indirect discrimination |
| FCA Consumer Duty — PRIN 12 | Fair outcomes requirement |
| UK GDPR — Art. 22 | Automated decision safeguards |

---

### RISK-AI-002 — Model Drift (Degraded Accuracy)

**Category:** Model Risk / Performance  

**Description:**  
Model accuracy may degrade as economic conditions or applicant profiles diverge from training data. This may result in systematically incorrect approvals or declines without visible system failure.

---

#### Risk Scoring

| Stage | Likelihood | Impact | Score | Level |
|------|-----------|--------|------|------|
| Inherent | 4 | 4 | 16 | Critical |
| Residual | 2 | 3 | 6 | Medium |

---

#### Current Controls

- Monthly performance monitoring (accuracy, precision, recall)  
- Feature drift reporting from vendor  
- Contractual retraining obligation  
- Annual model validation  

---

#### Control Gaps

- Drift thresholds not reviewed since procurement  
- Weak enforcement of retraining obligations  
- Annual validation cycle may be too infrequent  

---

#### Residual Risk Narrative

Controls are relatively mature. Residual risk reflects effective monitoring but weak enforcement of vendor obligations.

---

**Owner:** Head of Data Science  

**Review triggers:**
- Drift threshold breach  
- Economic changes affecting SME sector  
- Changes in onboarding profile  

---

#### Regulatory Hook

| Framework | Relevance |
|----------|----------|
| EU AI Act — Art. 9, 15 | Monitoring obligations |
| EU AI Act — Art. 72 | Post-market monitoring |
| FCA SS1/23 | Model risk expectations |
| FCA Consumer Duty | Outcome quality |

---

### RISK-AI-003 — Explainability Failure

**Category:** Transparency / Compliance  

**Description:**  
Veriflow may be unable to provide meaningful explanations for declined decisions due to reliance on vendor-generated outputs and limited visibility into model logic.

---

#### Risk Scoring

| Stage | Likelihood | Impact | Score | Level |
|------|-----------|--------|------|------|
| Inherent | 3 | 4 | 12 | High |
| Residual | 2 | 3 | 6 | Medium |

---

#### Current Controls

- Vendor explanation outputs (top contributing factors)  
- Customer-facing explanation summaries  
- SAR process in place  
- Legal validation against current ICO guidance  

---

#### Control Gaps

- Explanations describe correlation, not causation  
- No independent validation of explanation accuracy  
- No escalation process for disputed explanations  

---

#### Residual Risk Narrative

Risk is currently manageable but dependent on regulatory stability. Future ICO expectations may raise the standard for explanation.

---

**Owner:** Data Protection Officer  

---

### RISK-AI-004 — Vendor Dependency

**Category:** Operational / Third-Party Risk  

**Description:**  
Veriflow is operationally dependent on ClearScore AI. Vendor failure would disrupt onboarding and credit operations.

---

#### Risk Scoring

| Stage | Likelihood | Impact | Score | Level |
|------|-----------|--------|------|------|
| Inherent | 2 | 5 | 10 | High |
| Residual | 2 | 3 | 6 | Medium |

---

#### Current Controls

- Contractual exit provisions  
- Annual financial review of vendor  
- Manual fallback underwriting  
- Model documentation escrow  

---

#### Control Gaps

- Fallback not tested under real conditions  
- No access to model weights  
- No alternative vendor identified  

---

#### Residual Risk Narrative

Impact reduced but not eliminated. Operational resilience depends on controls that are not fully validated.

---

**Owner:** Chief Operating Officer  

---

### RISK-AI-005 — Regulatory Non-Compliance (EU AI Act)

**Category:** Regulatory / Compliance  

**Description:**  
Veriflow has direct obligations under the EU AI Act as a deployer. Current compliance posture is incomplete.

---

#### Risk Scoring

| Stage | Likelihood | Impact | Score | Level |
|------|-----------|--------|------|------|
| Inherent | 4 | 4 | 16 | Critical |
| Residual | 2 | 3 | 6 | Medium |

---

#### Current Controls

- Legal mapping of obligations  
- Partial human oversight  
- Compliance gap assessment underway  

---

#### Control Gaps

- FRIA not completed  
- System not registered  
- No formal post-market monitoring plan  
- No staff AI training  

---

#### Residual Risk Narrative

Residual risk reflects incomplete compliance rather than control failure. Exposure must be reduced on a defined timeline.

---

**Owner:** Chief Risk Officer / General Counsel  

---

### RISK-AI-006 — Data Quality (Unrepresentative Training Data)

**Category:** Data Governance  

**Description:**  
Training data may not reflect Veriflow’s current merchant base, limiting model accuracy for key segments.

---

#### Risk Scoring

| Stage | Likelihood | Impact | Score | Level |
|------|-----------|--------|------|------|
| Inherent | 3 | 3 | 9 | High |
| Residual | 2 | 2 | 4 | Low |

---

#### Current Controls

- Vendor training data description  
- Segment-level validation  
- Quarterly performance monitoring  

---

#### Control Gaps

- No verification of dataset representativeness  
- No feedback loop from monitoring to retraining  

---

#### Residual Risk Narrative

Risk is well controlled. Remaining exposure relates to process maturity rather than immediate impact.

---

**Owner:** Head of Data Science  

---

## Risk Summary

| Risk ID | Description | Inherent | Residual | Level | Owner |
|--------|------------|---------|----------|------|------|
| RISK-AI-001 | Discriminatory output | 15 | 10 | High | CRO |
| RISK-AI-002 | Model drift | 16 | 6 | Medium | Head of Data Science |
| RISK-AI-003 | Explainability failure | 12 | 6 | Medium | DPO |
| RISK-AI-004 | Vendor dependency | 10 | 6 | Medium | COO |
| RISK-AI-005 | Regulatory non-compliance | 16 | 6 | Medium | CRO / GC |
| RISK-AI-006 | Data quality | 9 | 4 | Low | Head of Data Science |

---

## Priority Actions

| Action | Owner | Deadline |
|------|------|---------|
| Independent fairness audit | CRO | Q2 2025 |
| EU AI Act gap assessment | CRO / GC | Q2 2025 |
| Conduct FRIA | DPO | Q2 2025 |
| AI literacy training | HR / GRC | Q2 2025 |
| Test fallback underwriting | COO | Q3 2025 |
| Review drift thresholds | Head of Data Science | Q2 2025 |
| Document monitoring plan | GRC Function | Q2 2025 |

---

## What This Register Is Not

This is not a FRIA, model validation report, or vendor due diligence record.

It is a governance tool — a live record of risks, controls, and decisions.

> A risk register completed once and filed is not a control.

---

*Prepared by the Arken Systems GRC Function. This is a thinking exercise demonstrating AI risk register methodology.*
