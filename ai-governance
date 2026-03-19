# AI Risk Register — Credit Scoring Model Deployment
## Veriflow Payments Ltd

*This is a thinking exercise, not a real organisation.*

---

**Document type:** AI Risk Register  
**Prepared by:** Arken Systems GRC Function  
**Addressed to:** Chief Risk Officer and AI Governance Committee, Veriflow Payments Ltd  
**Date:** March 2025  
**Classification:** Confidential — Internal Distribution Only  
**Review cycle:** Quarterly, or upon material change to model, vendor, or regulatory context  
**Related documents:** Artefact A — Risk Acceptance With Teeth; Artefact B — Third-Party Control Gap Analysis (Databridge Analytics Ltd)

---

## Context

Veriflow Payments Ltd is a Series B UK fintech regulated by the FCA under the Payment Services Regulations 2017, processing card payments for approximately 40,000 SME merchants. In Q1 2025, Veriflow procured an AI-powered credit scoring model from ClearScore AI Ltd — a third-party AI vendor — to automate creditworthiness assessments for merchant onboarding and credit limit decisions.

The model uses machine learning to assess applications based on transaction history, business profile data, and behavioural signals. Veriflow is the deployer; ClearScore AI Ltd is the provider. Under the EU AI Act, credit scoring systems of this type are classified as **high-risk AI systems** (Annex III, point 5(b)). Veriflow, as deployer, carries direct obligations regardless of who built the model.

This register identifies the material risks associated with deploying this system, assesses current controls, and maps each risk to its regulatory hook. It is a live governance document, not a one-time compliance exercise.

---

## Scoring Methodology

**Likelihood:** 1 (Rare) — 2 (Unlikely) — 3 (Possible) — 4 (Likely) — 5 (Almost certain)  
**Impact:** 1 (Negligible) — 2 (Minor) — 3 (Moderate) — 4 (Significant) — 5 (Severe)  
**Inherent risk score:** Likelihood × Impact  
**Residual risk score:** Likelihood × Impact after controls applied  
**Risk appetite threshold:** Residual score of 9 or above requires Risk Committee escalation

---

## Risk Register

---

### RISK-AI-001 — Discriminatory Output: Protected Characteristic Bias

**Category:** Fairness / Discrimination  
**Description:** The credit scoring model produces systematically lower scores for applicants sharing a protected characteristic — such as age, race, sex, or disability — not because of genuine creditworthiness differences but because of bias encoded in training data, feature selection, or proxy variables. Veriflow, as the decision-making entity, is legally accountable for discriminatory outcomes regardless of whether the model or the vendor introduced the bias.

| | Pre-controls | Post-controls |
|---|---|---|
| **Likelihood** | 3 | 2 |
| **Impact** | 5 | 5 |
| **Risk score** | 15 | 10 |
| **Risk level** | Critical | High |

**Current controls:**
- Contractual requirement for ClearScore AI to provide bias testing results across protected characteristic proxies prior to deployment
- Pre-deployment fairness audit conducted by Veriflow's data science function using disaggregated outcome data
- Quarterly outcome monitoring: score distributions reviewed by merchant demographic segment where data is available
- Human review required for all declined applications above £10,000 credit limit

**Control gaps:**
- Fairness audit methodology has not been independently validated — conducted internally by the same team that manages the vendor relationship
- Demographic data for merchant applicants is incomplete, limiting the granularity of quarterly monitoring
- Human review process for declined applications lacks documented criteria — reviewers exercise discretion without a structured framework

**Residual risk narrative:**
Controls reduce likelihood but cannot eliminate impact. A discriminatory outcome in credit decisions carries regulatory, reputational, and legal consequences that do not scale down because controls were in place. The residual score of 10 reflects that meaningful exposure remains and warrants ongoing scrutiny.

**Owner:** Chief Risk Officer  
**Review trigger:** Any regulatory guidance update; ICO or FCA enforcement action against a peer; evidence of skewed outcome distributions in quarterly monitoring

**Regulatory hook:**
| Framework | Relevance |
|---|---|
| EU AI Act — Art. 9, 10, 15 | High-risk AI system: mandatory risk management, data governance, and accuracy/robustness requirements |
| EU AI Act — Art. 13 | Transparency obligations: affected persons must be able to obtain explanation of decision |
| Equality Act 2010 — s.19 | Indirect discrimination: proxy variables that disadvantage protected groups constitute unlawful discrimination regardless of intent |
| FCA Consumer Duty — PRIN 12 | Firms must deliver good outcomes for all customers; discriminatory credit decisions are a direct Consumer Duty failure |
| UK GDPR — Art. 22 | Right not to be subject to solely automated decisions with significant effect; human review obligations |

---

### RISK-AI-002 — Model Drift: Degraded Predictive Accuracy Over Time

**Category:** Model Risk / Performance  
**Description:** The model's predictive accuracy degrades over time as the economic environment, merchant behaviour patterns, or applicant profiles diverge from the training data distribution. Drift may be gradual and difficult to detect without active monitoring. Decisions made on a drifted model may be systematically miscalibrated — approving higher-risk applicants or declining lower-risk ones — without any visible system failure.

| | Pre-controls | Post-controls |
|---|---|---|
| **Likelihood** | 4 | 2 |
| **Impact** | 4 | 3 |
| **Risk score** | 16 | 6 |
| **Risk level** | Critical | Medium |

**Current controls:**
- Monthly model performance review: accuracy, precision, recall, and F1 score tracked against baseline
- Data drift monitoring: ClearScore AI provides a monthly feature drift report flagging input distribution changes above a defined threshold
- Contractual retraining obligation: ClearScore AI is required to retrain the model if drift metrics exceed agreed thresholds
- Annual full model validation conducted by Veriflow's data science function

**Control gaps:**
- Drift thresholds were set at procurement and have not been reviewed since — they may not reflect current business risk appetite
- Retraining obligation is contractual but enforcement mechanism is weak: no defined remediation timeline, no financial penalty for non-compliance
- Annual validation cycle may be too infrequent given the pace of change in SME merchant behaviour post-2023

**Residual risk narrative:**
Controls are relatively mature for this risk. Monthly monitoring and contractual retraining obligations represent genuine mitigations. Residual score of 6 reflects well-managed but not fully closed risk. The control gap around enforcement mechanism is the most material remaining exposure.

**Owner:** Head of Data Science  
**Review trigger:** Monthly drift report flagging threshold breach; material change in UK economic conditions; significant change in merchant onboarding volume or profile

**Regulatory hook:**
| Framework | Relevance |
|---|---|
| EU AI Act — Art. 9, 15 | Ongoing risk management and post-market monitoring obligations for high-risk AI systems |
| EU AI Act — Art. 72 | Deployers must monitor system performance and report serious incidents to provider |
| FCA Model Risk Management — SS1/23 | PRA/FCA expectations on model monitoring, validation, and governance — directly applicable to credit models |
| FCA Consumer Duty — PRIN 12 | Miscalibrated credit decisions represent poor customer outcomes under Consumer Duty |

---

### RISK-AI-003 — Explainability Failure: Inability to Justify Declined Decisions

**Category:** Transparency / Regulatory Compliance  
**Description:** Veriflow is unable to provide a meaningful explanation of why the model declined a specific credit application when requested by the applicant or a regulator. ClearScore AI's model uses a proprietary algorithm; Veriflow has limited visibility into feature weights and decision logic. This creates a direct conflict with UK GDPR Article 22 obligations and FCA expectations under Consumer Duty.

| | Pre-controls | Post-controls |
|---|---|---|
| **Likelihood** | 3 | 2 |
| **Impact** | 4 | 3 |
| **Risk score** | 12 | 6 |
| **Risk level** | High | Medium |

**Current controls:**
- ClearScore AI provides a per-decision explanation output: top three factors contributing to the score, expressed in plain English
- Veriflow's customer-facing decline notification includes a summary of contributing factors drawn from this output
- Subject Access Request process documented: applicants can request full decision record within 30 days
- Legal review confirmed that factor-based explanation meets current ICO guidance on automated decision explanations

**Control gaps:**
- Factor-based explanations describe correlation, not causation — they satisfy current guidance but may not withstand regulatory scrutiny if ICO updates its position on meaningful explanation
- ClearScore AI's explanation output is contractually guaranteed but Veriflow has not independently validated that the explanations accurately reflect the model's actual decision logic
- No process exists for handling explanation requests that escalate to formal complaints or FOS referrals

**Residual risk narrative:**
Current controls are adequate for the present regulatory environment. Residual score of 6 reflects that explainability risk is managed but contingent on regulatory stability. The ICO's evolving position on automated decision-making is the primary watch item.

**Owner:** Data Protection Officer  
**Review trigger:** ICO guidance update on automated decision explanations; FOS ruling on AI credit decision complaint; Subject Access Request that cannot be adequately addressed with current explanation output

**Regulatory hook:**
| Framework | Relevance |
|---|---|
| UK GDPR — Art. 13, 14, 22 | Right to explanation for automated decisions; right to human review; right to contest |
| EU AI Act — Art. 13, 86 | Transparency requirements; right of affected persons to obtain explanation from deployer |
| FCA Consumer Duty — PRIN 12 | Customers must be able to understand decisions that affect them |
| FCA CONC 7 | Consumer credit rules: declined applicants must receive adequate reasons |

---

### RISK-AI-004 — Vendor Dependency: Loss of Model Access or Vendor Failure

**Category:** Operational / Third-Party Risk  
**Description:** Veriflow's credit decisioning process becomes operationally dependent on ClearScore AI's continued service availability, financial viability, and contractual compliance. If ClearScore AI experiences a service outage, enters insolvency, or terminates the contract, Veriflow has no alternative credit scoring capability and cannot onboard new merchants or process credit limit reviews.

| | Pre-controls | Post-controls |
|---|---|---|
| **Likelihood** | 2 | 2 |
| **Impact** | 5 | 3 |
| **Risk score** | 10 | 6 |
| **Risk level** | High | Medium |

**Current controls:**
- Contract includes 90-day termination notice requirement and data portability clause
- ClearScore AI's financial position reviewed annually as part of third-party risk programme
- Business continuity plan includes manual underwriting fallback for applications under £5,000
- Model documentation (feature list, training data description, validation reports) held by Veriflow under escrow arrangement

**Control gaps:**
- Manual underwriting fallback has not been tested under realistic volume conditions — it is documented but not operationally validated
- Escrow arrangement covers model documentation but not model weights — Veriflow cannot independently run the model without ClearScore AI
- 90-day notice period may be insufficient to procure and validate an alternative solution given FCA model validation requirements
- No alternative vendor has been identified or assessed — switching costs are unknown

**Residual risk narrative:**
Impact has been reduced from Severe to Moderate by the fallback and escrow controls, but the residual score of 6 masks a meaningful operational gap: the manual fallback is untested and the switching timeline is probably longer than the contractual notice period allows.

**Owner:** Chief Operating Officer  
**Review trigger:** ClearScore AI financial difficulty signals; service reliability below contractually agreed SLA; material contract dispute; annual third-party risk review

**Regulatory hook:**
| Framework | Relevance |
|---|---|
| EU AI Act — Art. 25, 26 | Deployer obligations when provider ceases to operate or withdraws system from market |
| FCA SYSC 8 | Outsourcing requirements: operational resilience and exit planning for critical third-party services |
| DORA — Art. 28 | Digital operational resilience: ICT third-party risk management and contractual requirements |
| FCA Operational Resilience Policy | Important business services must remain within impact tolerances during disruption |

---

### RISK-AI-005 — Regulatory Non-Compliance: EU AI Act Deployer Obligations

**Category:** Regulatory / Compliance  
**Description:** As a deployer of a high-risk AI system under EU AI Act Annex III, Veriflow has direct legal obligations that apply independently of ClearScore AI's obligations as provider. These include maintaining a human oversight function, conducting fundamental rights impact assessments, registering the system in the EU database, and implementing post-market monitoring. Veriflow has not yet completed a formal assessment of its compliance posture against these obligations.

| | Pre-controls | Post-controls |
|---|---|---|
| **Likelihood** | 4 | 2 |
| **Impact** | 4 | 3 |
| **Risk score** | 16 | 6 |
| **Risk level** | Critical | Medium |

**Current controls:**
- Legal counsel has confirmed EU AI Act applicability and provided initial obligations mapping
- Human review process exists for declined applications above £10,000 (partially addresses Art. 26 human oversight requirement)
- GRC function has initiated a compliance gap assessment — expected to complete Q2 2025

**Control gaps:**
- Fundamental Rights Impact Assessment (FRIA) has not been conducted — required under Art. 27 for deployers in financial services
- System has not been registered in the EU AI Act database — registration obligation applies from August 2026 but preparation should begin now
- Human oversight function is partial: covers declined applications above £10,000 only; lower-value decisions are fully automated with no human review option
- Staff operating the system have not received AI literacy training as required under Art. 26(6)
- No documented post-market monitoring plan exists that meets Art. 72 requirements

**Residual risk narrative:**
The inherent score of 16 reflects that this is a new regulatory framework with direct financial penalties (up to €15 million or 3% of global annual turnover for deployer violations) and that Veriflow's compliance posture is currently incomplete. Controls reduce likelihood of enforcement given good-faith compliance efforts, but the gap between current state and full compliance is material and must be closed on a defined timeline.

**Owner:** Chief Risk Officer / General Counsel  
**Review trigger:** EU AI Act compliance deadline milestones; FCA AI guidance updates; completion of Q2 2025 gap assessment; any regulatory inquiry

**Regulatory hook:**
| Framework | Relevance |
|---|---|
| EU AI Act — Art. 26 | Deployer obligations: human oversight, monitoring, staff training, use in accordance with instructions |
| EU AI Act — Art. 27 | Fundamental Rights Impact Assessment: mandatory for deployers in financial services |
| EU AI Act — Art. 49 | Registration obligations for high-risk AI systems |
| EU AI Act — Art. 99 | Penalties: up to €15m or 3% global turnover for deployer violations |
| UK AI Regulatory Framework | Pro-innovation principles; sector regulator expectations (FCA) apply in parallel |

---

### RISK-AI-006 — Data Quality: Training Data Unrepresentative of Current Merchant Base

**Category:** Data Governance / Model Risk  
**Description:** The model was trained on historical credit data that may not reflect Veriflow's current merchant base — which skews towards younger businesses, gig economy operators, and sectors that grew significantly post-2020. If the training data underrepresents these segments, the model's predictive accuracy for Veriflow's actual applicant population is structurally limited regardless of overall performance metrics.

| | Pre-controls | Post-controls |
|---|---|---|
| **Likelihood** | 3 | 2 |
| **Impact** | 3 | 2 |
| **Risk score** | 9 | 4 |
| **Risk level** | High | Low |

**Current controls:**
- ClearScore AI provided a training data description at procurement: data covers UK SME credit applications 2018–2024 across multiple lenders
- Pre-deployment validation included segment-level performance testing against Veriflow's own historical merchant data
- Quarterly performance monitoring disaggregated by merchant sector and business age

**Control gaps:**
- Training data description is summary-level — Veriflow has not verified the sector and age distribution of training data against its own applicant profile
- Segment-level monitoring tracks performance but does not feed back into retraining requests — there is no mechanism to flag persistent underperformance in a specific segment as a data quality issue

**Residual risk narrative:**
Controls are adequate. Residual score of 4 reflects well-managed risk. The absence of a formal feedback loop from monitoring to retraining is a process gap worth closing but does not represent material current exposure.

**Owner:** Head of Data Science  
**Review trigger:** Quarterly monitoring showing persistent underperformance in a specific merchant segment; significant change in Veriflow's merchant acquisition strategy

**Regulatory hook:**
| Framework | Relevance |
|---|---|
| EU AI Act — Art. 10 | Data governance requirements for high-risk AI: training data must be relevant, representative, and free of errors |
| FCA SS1/23 | Model risk: data quality as a component of model validation |
| UK GDPR — Art. 5(1)(d) | Accuracy principle: personal data used in automated decisions must be accurate and kept up to date |

---

## Risk Summary

| Risk ID | Description | Inherent Score | Residual Score | Level | Owner |
|---|---|---|---|---|---|
| RISK-AI-001 | Discriminatory output: protected characteristic bias | 15 | 10 | High | CRO |
| RISK-AI-002 | Model drift: degraded predictive accuracy | 16 | 6 | Medium | Head of Data Science |
| RISK-AI-003 | Explainability failure: inability to justify decisions | 12 | 6 | Medium | DPO |
| RISK-AI-004 | Vendor dependency: loss of model access | 10 | 6 | Medium | COO |
| RISK-AI-005 | Regulatory non-compliance: EU AI Act deployer obligations | 16 | 6 | Medium | CRO / General Counsel |
| RISK-AI-006 | Data quality: unrepresentative training data | 9 | 4 | Low | Head of Data Science |

**Risks requiring Risk Committee escalation (residual score ≥ 9):**
- RISK-AI-001 — Discriminatory output remains at residual score 10. This is the only risk that cannot be adequately mitigated by operational controls alone. It requires ongoing governance attention at committee level.

---

## Priority Actions

| Action | Owner | Deadline |
|---|---|---|
| Commission independent fairness audit — RISK-AI-001 | CRO | Q2 2025 |
| Complete EU AI Act compliance gap assessment — RISK-AI-005 | CRO / General Counsel | Q2 2025 |
| Conduct Fundamental Rights Impact Assessment — RISK-AI-005 | DPO | Q2 2025 |
| Deliver AI literacy training to staff operating the system — RISK-AI-005 | HR / GRC | Q2 2025 |
| Test manual underwriting fallback under volume conditions — RISK-AI-004 | COO | Q3 2025 |
| Review and update drift thresholds — RISK-AI-002 | Head of Data Science | Q2 2025 |
| Document post-market monitoring plan — RISK-AI-005 | GRC Function | Q2 2025 |

---

## What This Register Is Not

This register does not constitute a Fundamental Rights Impact Assessment (FRIA), which is a separate obligation under EU AI Act Article 27 and warrants its own document. It does not substitute for the model validation report, the vendor due diligence record, or the Article 28 processor agreement with ClearScore AI. It is a governance document — a live record of known risks, current controls, and open actions — intended to support informed decision-making by the Risk Committee, not to demonstrate compliance by its existence.

A risk register that is completed once and filed is not a control. This document should be reviewed quarterly, updated when material changes occur, and treated as evidence of ongoing risk management rather than a one-time exercise.

---

*Prepared by the Arken Systems GRC Function. This document is a thinking exercise demonstrating AI risk register methodology. Veriflow Payments Ltd and ClearScore AI Ltd are fictional organisations.*
