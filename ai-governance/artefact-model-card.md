# Model Card — ClearScore AI Credit Scoring Model
## Veriflow Payments Ltd — Deployed Instance

*This is a thinking exercise. There is no such company.*

---

**Document type:** Model Card (Deployer-Issued)
**Prepared by:** Arken Systems GRC Function
**Addressed to:** AI Governance Committee, Veriflow Payments Ltd
**Date:** March 2025
**Classification:** Confidential — Internal Distribution Only
**Review cycle:** Annually, or upon material change to model, inputs, or deployment context

**Related documents:**
- AI Risk Register — Credit Scoring Model Deployment (March 2025)
- Fundamental Rights Impact Assessment — ClearScore AI Credit Scoring System (March 2025)
- Artefact A — Risk Acceptance With Teeth (January 2025)
- Artefact B — Third-Party Control Gap Analysis, Databridge Analytics Ltd

---

## About This Document

A model card is a structured transparency document that describes what an AI system does, how it performs, and what its known limitations are. The term was introduced in the machine learning literature to support accountability in AI deployment. It has since been taken up as a governance standard and is referenced in the EU AI Act's technical documentation requirements under Article 11 and Annex IV.

This model card is issued by Veriflow Payments Ltd as the deployer of the ClearScore AI credit scoring system. It is not issued by ClearScore AI Ltd as the provider. The two documents are different in scope: the provider's technical documentation covers model architecture and training methodology. This card covers what the model does in Veriflow's specific deployment context, how it performs against Veriflow's population of merchant applicants, and what Veriflow has identified as its material limitations and governance requirements.

Veriflow is responsible for this document and for the governance it describes. ClearScore AI Ltd's responsibility for technical documentation under EU AI Act Article 11 is separate and does not discharge Veriflow's obligations as a deployer.

> This document should be read alongside the AI Risk Register and FRIA, not instead of them.

It is also worth stating plainly: this document reflects what we currently understand about the system. Some of that understanding is incomplete.

---

## 1. Model Identity

| Field | Detail |
|---|---|
| Model name | ClearScore AI Credit Scoring Model |
| Provider | ClearScore AI Ltd |
| Deployer | Veriflow Payments Ltd |
| Deployed instance identifier | VF-CS-001 |
| Deployment date | Q1 2025 |
| Current version | v2.3 (as supplied by ClearScore AI Ltd, March 2025) |
| Model type | Supervised classification — creditworthiness assessment |
| EU AI Act classification | High-risk AI system, Annex III point 5(b) — AI systems used to evaluate creditworthiness |
| Primary use | Merchant onboarding and credit limit decisions |

---

## 2. Intended Use

### 2.1 What This Model Is For

The model is used to generate a creditworthiness score and recommendation for SME merchants applying to use Veriflow's payment processing platform. It supports two decision contexts:

- **Merchant onboarding:** whether to approve a new merchant for access to Veriflow payment services
- **Credit limit decisions:** whether to approve or adjust a merchant's credit limit on the Veriflow platform

The model outputs a score and one of three recommendations: **Approve**, **Decline**, or **Refer for human review**.

In practice, most decisions follow the model's recommendation without challenge. That is the operational reality, even where formal human oversight exists.

### 2.2 Decision Thresholds

| Decision value | Process |
|---|---|
| Below £10,000 | Automated decision based on model output |
| £10,000 and above | Referred to human underwriter for review |

Decisions at or above the £10,000 threshold are not automated. A human underwriter reviews the model output alongside supporting documentation and makes the final decision.

Below that threshold, the model effectively acts as the decision-maker.

### 2.3 Who Is Affected

Affected parties are SME merchant applicants — primarily sole traders, partnerships, and limited companies with annual turnover under £1m. Veriflow processes approximately 400 to 600 merchant creditworthiness assessments per month at current volumes.

Decisions have a material effect on affected parties: a credit decline affects a merchant's ability to access payment processing services, which in practice affects their ability to trade. This is the primary reason the system is classified as high-risk.

For smaller merchants, even relatively low credit limits can determine whether the business can operate at all. The impact is not proportional to the value of the decision.

---

## 3. Out-of-Scope Uses

The following uses are outside the intended deployment scope of this model. Using the model for these purposes is not permitted without a formal change control process and updated governance documentation.

- Consumer credit decisions (the model is calibrated for business applicants)
- Decisions where the applicant is not a UK-registered or UK-trading business
- Fraud detection or identity verification (separate systems are used for this purpose)
- Ongoing credit monitoring of existing merchants outside of the scheduled review cycle
- Any decision context not described in section 2 above

---

## 4. Model Inputs

The model takes the following categories of data as inputs. This reflects Veriflow's understanding of the model's input requirements as documented by ClearScore AI Ltd. Full technical detail of feature engineering and weighting is held in ClearScore AI's technical documentation under Article 11.

| Input category | Description | Source |
|---|---|---|
| Transaction history | Volume, value, and pattern of transactions processed through the Veriflow platform | Veriflow internal |
| Business profile | Company age, sector, size, and structure | Companies House; applicant-supplied |
| Behavioural signals | Patterns of platform usage derived from Veriflow account data | Veriflow internal |
| Credit reference data | External credit file data supplied via ClearScore AI's data providers | Third-party (details in ClearScore AI technical documentation) |

### 4.1 What the Model Does Not Use

The model does not take protected characteristics (age, sex, race, religion, disability, sexual orientation) as direct inputs. However, this does not mean discriminatory outcomes are not possible — proxy variables may produce correlated effects on protected groups. This is addressed in section 6 and in RISK-AI-001 of the AI Risk Register.

Put more simply: not using protected characteristics directly does not make the system fair.

---

## 5. Training Data

Veriflow is the deployer, not the provider, and does not have direct access to the training dataset. The following is based on ClearScore AI Ltd's data disclosure to Veriflow during procurement and on representations made in the vendor contract.

| Field | Detail |
|---|---|
| Dataset description | Historical creditworthiness records from UK SME credit applications |
| Geographic scope | United Kingdom |
| Temporal coverage | ClearScore AI has represented that training data covers applications from 2018 to 2023 |
| Approximate size | Not disclosed to Veriflow |
| Data exclusions | Not fully disclosed; ClearScore AI has confirmed exclusion of applications where regulatory issues prevented use |

### 5.1 Known Data Limitations

**Representativeness of Veriflow's merchant base.**
Veriflow's merchant base includes a higher proportion of early-stage and platform-dependent businesses than the broader SME credit market from which training data was drawn. The model may underperform for applicants whose profile diverges significantly from the training distribution. This is likely to affect exactly the kinds of businesses Veriflow is trying to grow.

**Underrepresentation of post-2020 business formations.**
Businesses formed after 2020 — including those that emerged in response to pandemic-era market shifts — may be underrepresented in the training data. The economic conditions under which these businesses have traded differ materially from pre-2020 norms. This is a recognised source of potential model drift (see RISK-AI-002).

This is not just a technical issue — it means the model is making decisions about newer business models using older economic assumptions.

**Demographic representativeness not verified.**
Veriflow has requested but not yet received verification from ClearScore AI that the training dataset is demographically representative of the UK SME population. This is an open gap in governance. It is also one of the more uncomfortable ones.

---

## 6. Performance

### 6.1 Summary Metrics

| Metric | Value | Period |
|---|---|---|
| Overall approval rate | 71% | Q1 2025 (deployment period) |
| Refer rate | 12% | Q1 2025 |
| Decline rate | 17% | Q1 2025 |
| Model drift status | Within threshold | As of March 2025 |

These figures reflect early deployment performance. The monitoring programme established under RISK-AI-002 will produce quarterly updates.

At this stage, the model appears stable. That should not be confused with being well-understood.

### 6.2 Disaggregated Performance

This is the most significant gap in Veriflow's current model documentation.

Veriflow does not yet have validated disaggregated performance data broken down by protected characteristic group.

What this means in practice is straightforward: we do not currently know whether the model is fair.

**What Veriflow does have:**

- Sector-level outcome data showing no material variance across major sectors represented in the applicant population to date
- No evidence of systematic outcome disparity by business age at current monitoring levels

**What Veriflow does not have:**

- Validated outcome data disaggregated by protected characteristic
- Independent verification of the vendor's own fairness testing
- Specific performance data for the populations identified as elevated-risk in the FRIA (new businesses, underrepresented sectors, sole traders, applicants with limited digital footprint)

The absence of this data does not mean no disparity exists. It means we cannot yet confirm that it does not.

The independent fairness audit commissioned for Q2 2025 is intended to close this gap. It should have been in place before deployment.

### 6.3 Known Performance Limitations

**Thin file applicants.**
Applicants with limited transaction history or a short trading record produce less reliable scores. The model's uncertainty is not currently surfaced in the output — it produces a score and recommendation regardless of data volume.

This means the system presents low-confidence decisions with the same level of apparent certainty as high-confidence ones.

**Sector underrepresentation.**
Merchants in sectors not well-represented in the training data — particularly newer platform-economy and care sector businesses — may receive scores that reflect limited signal rather than genuine credit risk assessment.

In some cases, the model is effectively guessing based on limited precedent.

**Behavioural signal dependency.**
Applicants who are infrequent users of the Veriflow platform prior to application produce limited behavioural signal. The model's treatment of low-signal applicants has not been independently validated.

This has not been independently validated. We are relying on the vendor's position here.

---

## 7. Human Oversight

### 7.1 Current Oversight Structure

| Stage | Oversight mechanism |
|---|---|
| Decisions above £10,000 | Human underwriter review before final decision |
| Monitoring | Monthly performance review by Head of Data Science |
| Governance | Quarterly review by AI Governance Committee |
| Escalation | Residual risk score ≥ 9 triggers Risk Committee escalation (per AI Risk Register) |

### 7.2 Oversight Gaps

**Human review threshold.**
The current £10,000 threshold means the majority of credit decisions are fully automated. As noted in the FRIA, rights impacts do not scale with decision value. A sole trader declined for a £2,000 credit limit is as materially affected as one declined for £15,000.

The threshold is under review as part of the Q2 2025 action plan.

At present, most affected individuals do not meaningfully interact with a human decision-maker.

**No override logging.**
Where human underwriters review and override model recommendations, there is currently no structured logging of override reasoning.

This limits Veriflow's ability to identify patterns in human judgement. It also weakens any claim that human review is acting as an effective control.

**No fallback testing.**
The manual fallback underwriting process identified in RISK-AI-004 has not been tested under real operational conditions.

At the moment, this is an assumption rather than a tested capability.

---

## 8. Explainability

### 8.1 What Applicants Are Told

Declined applicants receive a summary explanation identifying the top factors that contributed to the decision. These are derived from the model's output and are supplied by ClearScore AI as part of the standard output format.

Example factor categories: transaction volume below threshold; business age below threshold; credit reference score below threshold.

### 8.2 Limitations of Current Explanations

The factor-based explanations describe correlation rather than causation. They tell an applicant which variables were associated with their outcome; they do not explain the model's reasoning in a way that would allow an applicant to understand what they would need to change to receive a different outcome.

These explanations are useful for transparency, but of limited practical value to applicants trying to change an outcome.

They tell an applicant what correlated with the decision. They do not tell them what to do next.

This is a known limitation of the explanation methodology used by most commercial credit scoring systems. It is not unique to ClearScore AI. It does, however, create a gap against the standard implied by UK GDPR Article 22 and EU AI Act Article 86, both of which require meaningful explanation.

Veriflow has not independently validated the accuracy of the factor-based explanations against the model's actual decision logic.

This is an open governance gap, and one that is likely to attract regulatory attention.

### 8.3 Appeals

There is currently no documented internal appeals process by which an applicant can contest a credit decision. This gap was identified in the FRIA and is subject to a 30-day remediation action.

Until an appeals process is in place, Veriflow's compliance with the right to an effective remedy under EU AI Act Article 86 and UK GDPR Article 22 is incomplete.

At present, an affected applicant has no structured way to challenge a decision that may be wrong.

---

## 9. Regulatory Compliance Status

As of March 2025. This table reflects Veriflow's deployer obligations, not ClearScore AI's provider obligations.

| Obligation | Basis | Status |
|---|---|---|
| Pre-deployment FRIA | EU AI Act Art. 27 | Not completed before deployment — retrospective FRIA completed March 2025 |
| Technical documentation | EU AI Act Art. 11, Annex IV | Partially met via vendor documentation; deployer-side documentation gaps remain |
| Human oversight measures | EU AI Act Art. 26 | Partial — human review threshold under review |
| Transparency to affected persons | EU AI Act Art. 86 | Partial — explanation provided but adequacy not validated |
| System registration | EU AI Act Art. 49 | Not completed |
| AI literacy training | EU AI Act Art. 26(6) | Not completed |
| Post-market monitoring plan | EU AI Act Art. 72 | Monitoring in place; formal plan not documented |
| Fairness testing | FCA Consumer Duty; Equality Act | Vendor testing in place; independent validation pending |
| Automated decision safeguards | UK GDPR Art. 22 | Partial — human review above threshold only |

---

## 10. Version and Change History

| Version | Date | Change |
|---|---|---|
| v1.0 | March 2025 | Initial model card — retrospective, covering deployment from Q1 2025 |

This document will be updated upon:
- Any material change to the model version deployed
- Any material change to model inputs or decision thresholds
- Completion of the independent fairness audit
- Regulatory guidance updates affecting deployer obligations
- Annual review (next due: March 2026)

---

## 11. Contact and Governance

| Role | Responsibility |
|---|---|
| Chief Risk Officer | Document owner; escalation point for residual risk |
| Data Protection Officer | GDPR and explanation obligations |
| Head of Data Science | Performance monitoring; drift management |
| General Counsel | Regulatory compliance; vendor contract |
| Arken Systems GRC Function | Document preparation; governance support |

---

## What This Document Is Not

This model card is not a risk register, a FRIA, or a vendor due diligence record. Those documents exist separately and should be read alongside this one.

It is also not a static compliance artefact. A model card that is completed once and filed is not a governance control.

If this document is not kept current, it becomes a record of what we believed at one point in time — not what is actually happening.

> Transparency about what we do not know is as important as documenting what we do.

In practice, it is often more important.

---

*Prepared by the Arken Systems GRC Function. This is a thinking exercise demonstrating model card methodology for a deployed high-risk AI system under the EU AI Act. Veriflow Payments Ltd and ClearScore AI Ltd are fictional organisations.*
