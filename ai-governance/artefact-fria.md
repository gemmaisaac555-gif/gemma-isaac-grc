# Fundamental Rights Impact Assessment
## AI Credit Scoring System — Veriflow Payments Ltd

*This is a thought exercise. There is no such company.*

---

**Document Type:** Fundamental Rights Impact Assessment (FRIA)  
**Prepared By:** Arken Systems GRC Function  
**Addressee:** Data Protection Officer and Chief Risk Officer, Veriflow Payments Ltd  
**Date:** March 2025  
**Classification:** Confidential — Internal Use Only  
**Basis in Law:** EU AI Act Article 27 (mandated for deployers of high-risk AI systems in financial services)  
**Associated Documents:** AI Risk Register, Credit Scoring Model Deployment (March 2025); Artefact A, Risk Acceptance With Teeth (January 2025)

---

## Introduction

This FRIA is retrospective. Veriflow went live with the ClearScore AI credit scoring system in Q1 2025. EU AI Act Article 27 says deployers in financial services must conduct a FRIA before deployment. This assessment wasn't completed before go-live.

I'm stating that fact clearly, rather than trying to hide it. The objective of this document isn't to create retroactive compliance; it is to carry out the assessment we should have carried out, to determine what not carrying out that assessment means to our current risk position, and to establish a baseline for ongoing fundamental rights governance of this system.

A FRIA done after deployment is better than no FRIA. It is not the same as a FRIA done before deployment. That difference is significant, and I will note it in the findings.

---

## 1. System Description

- **System Name:** ClearScore AI Credit Scoring Model (deployed instance: Veriflow Payments Ltd)
- **System Type:** Automated credit scoring, EU AI Act Annex III, point 5(b), High Risk
- **Supplier:** ClearScore AI Ltd
- **Deployer:** Veriflow Payments Ltd
- **Deployment Context:** Automated creditworthiness assessment for merchant onboarding and credit limit decisions. The system considers applications from SME merchants for payment processing and credit services offered by Veriflow's platform.
- **Decision Type:** The system generates a credit score and recommendation (accept / decline / refer for human review). Decisions for amounts below £10,000 are automated. Decisions for amounts above £10,000 are referred for human review.
- **Scale:** c.400 to 600 merchant creditworthiness assessments per month (current volumes).
- **Data Inputs:** Transaction history; business profile data; Companies House records; behavioural data (derived from use of the Veriflow platform).

---

## 2. Purpose of This Assessment

This assessment considers the implications of Veriflow's credit scoring system for the fundamental rights of individuals and groups affected by its decisions. It is mandated by EU AI Act Article 27, which requires deployers of high-risk AI systems in financial services to conduct a FRIA before the system is put into service.

This assessment addresses four questions:

1. Which fundamental rights are implicated by this system?
2. Which groups are most likely to experience an impact on those rights?
3. What is the nature of those impacts and how significant are they likely to be?
4. Are there steps we should take to mitigate the negative impacts or otherwise ensure the system operates compatibly with the fundamental rights of affected parties?

---

## 3. Fundamental Rights Engaged

The following rights are engaged by an automated credit scoring system in this context. Not all are equally at risk — the assessment below distinguishes between rights that are directly implicated and those that are engaged as background conditions.

**Directly implicated:**

**Right to equal treatment and non-discrimination (Equality Act 2010; EU Charter Art. 21)**
Credit scoring systems that use proxy variables — postcode, business sector, transaction patterns — may produce systematically different outcomes for applicants sharing protected characteristics, even where those characteristics are not explicit inputs. The right to equal treatment is the most directly implicated right in this system.

**Right to an explanation and to contest automated decisions (UK GDPR Art. 22; EU AI Act Art. 86)**
Applicants have a right to meaningful explanation of decisions that significantly affect them and a right to contest those decisions. An automated credit decline affects a merchant's ability to access payment services, which in practice affects their ability to trade. This is a significant effect.

**Right to data protection and privacy (UK GDPR; EU Charter Art. 8)**
The system processes personal data about merchant owners and directors as part of the credit assessment. The right to data protection encompasses accuracy, proportionality, and the right not to be subject to decisions based on inaccurate or outdated information.

**Engaged as background conditions:**

**Right to work and to engage in work (EU Charter Art. 15)**
For sole traders and small business owners, access to payment processing is a practical precondition for trading. A wrongful credit decline does not directly violate the right to work but can materially constrain its exercise.

**Right to an effective remedy (EU Charter Art. 47)**
Applicants who believe a credit decision was wrong or discriminatory must have access to a meaningful complaints and appeals process. This right is engaged by the design of Veriflow's review and escalation procedures.

---

## 4. Affected Populations

The following populations face elevated exposure to rights impacts from this system. This analysis is based on known patterns in automated credit decision systems and on Veriflow's merchant base profile.

### 4.1 New and Early-Stage Businesses

**Exposure:** High

Merchants with limited trading history have thin data profiles. The model was trained on historical credit data that may underrepresent early-stage businesses. Applicants with fewer data points receive less reliable scores, and the system may default to conservative (declining) recommendations in the absence of signal. New businesses, particularly those in groups that have had lower rates of entrepreneurship, are more likely to have thin credit files. This could lead to higher declines among these groups, even if, when approved, they prove to be similarly creditworthy to longer-established businesses.

**Rights engaged:** Equal treatment, right to contest  
**Current safeguard:** Human review of all applications over £10,000. No specific provision for applications below £10,000.  
**Gap:** The current human review threshold does not catch all potentially impacted applicants (those with thin files but loan values under £10,000), and there is no specific provision flagging thin file applicants for review irrespective of loan value.

### 4.2 Merchants in Underrepresented Sectors

**Exposure:** Medium-High

Merchants whose sectors have seen the most growth since 2020 — such as gig economy platforms, creator economy enterprises, and certain types of care sector businesses — may be disproportionately underscored if their sector is not well-represented in the training data. While not directly discriminatory in intent, this could have a discriminatory effect in outcome.

**Rights engaged:** Equal treatment, data protection (accuracy)  
**Current safeguard:** Quarterly performance monitoring, disaggregated by merchant sector.  
**Gap:** While monitoring would detect if underperformance was occurring on a sectoral basis, it does not automatically trigger remedial action or human review.

### 4.3 Sole Traders

**Exposure:** Medium-High

For sole traders, the distinction between personal and business finances is not clearly defined. There is a risk that the model is using signals relating to the individual's personal circumstances rather than the business creditworthiness. This raises issues of proportionality under the UK GDPR, and potentially indirect discrimination given the likely demographic characteristics of sole trader applicants.

**Rights engaged:** Data protection (proportionality), equal treatment  
**Current safeguard:** A Data Protection Impact Assessment has been requested from ClearScore AI (currently pending — see AI Risk Register RISK-AI-001).  
**Gap:** The DPIA has not been completed, so the proportionality of the use of personal data has not been independently verified.

### 4.4 Applicants with Limited Digital Footprint

**Exposure:** Medium

The model uses behavioural data from interactions with the Veriflow platform. Applicants who are infrequent users of the platform, or who interact with it in a way that differs from the training data — potentially including those with generally lower levels of digital engagement — may be disproportionately impacted by the lack of a behavioural signal, regardless of their true creditworthiness.

**Rights engaged:** Equal treatment, right to contest  
**Current safeguard:** None specifically for this group.  
**Gap:** There is no record of any assessment of how applicants with low behavioural signal are treated by the model.

---

## 5. Impact Assessment

**Severity:** 1 (Negligible) — 2 (Minor) — 3 (Moderate) — 4 (Significant) — 5 (Severe)  
**Likelihood:** 1 (Rare) — 2 (Unlikely) — 3 (Possible) — 4 (Likely) — 5 (Almost certain)

| Rights Impact | Affected Population | Severity | Likelihood | Overall | Current Safeguard Adequacy |
|---|---|---|---|---|---|
| Discriminatory effect resulting from the use of a proxy variable | Protected characteristic groups | 5 | 3 | High | Partial — fairness audit not conducted independently |
| Unfair refusal as a result of thin data profile | New businesses | 4 | 3 | High | Partial — human review threshold set too high |
| Inaccurate scoring due to sector bias | Underrepresented sectors | 3 | 3 | Medium | Partial — monitoring but no trigger for remedial action |
| Disproportionate use of personal data | Sole traders | 3 | 3 | Medium | Inadequate — DPIA not yet conducted |
| Inadequate explanations provided for refusals | All refused applicants | 3 | 2 | Medium | Partial — factor-based explanation may not be meaningful |
| Insufficient remedy for contested decisions | All applicants | 4 | 2 | Medium | Inadequate — remedy escalation process not documented |

---

## 6. Consultation

EU AI Act Article 27 and associated guidance specify that FRIAs should consult with representatives of affected groups or civil society organisations with relevant expertise where appropriate.

**Consultation conducted prior to deployment:** None.

This is a significant gap. Veriflow did not consult with any of the following before deploying the system:

- Organisations representing small business owners from minority ethnic communities
- Consumer or SME advocacy groups with expertise in algorithmic credit decisions
- The ICO or FCA, despite both having published relevant guidance on automated decision-making in financial services

The absence of consultation does not mean rights impacts were not considered — Veriflow conducted internal fairness testing and legal review. It means that the perspectives of people most likely to be adversely affected were not sought before the system went live. That is a meaningful omission, both as a matter of regulatory good practice and as a matter of governance integrity.

**Recommended remediation:** Veriflow should establish a standing advisory relationship with at least one organisation representing SME owners from communities with protected characteristics. This does not require formal consultation on every model change — it requires that affected community perspectives are available to inform governance decisions about the system on an ongoing basis.

---

## 7. Existing Safeguards — Assessment

| Safeguard | Status | Assessment |
|---|---|---|
| Human review for decisions above £10,000 | In place | Partial — threshold excludes majority of applications |
| Factor-based explanation for declined applicants | In place | Partial — adequacy of explanation not independently validated |
| Quarterly outcome monitoring by segment | In place | Adequate for detection, not for remediation |
| Contractual fairness testing by ClearScore AI | In place | Partial — not independently verified by Veriflow |
| Subject Access Request process | In place | Adequate |
| Complaints and appeals process | Not documented | Inadequate |
| Pre-deployment FRIA | Not conducted | Gap — this document is retrospective |
| Consultation with affected communities | Not conducted | Gap |
| AI literacy training for staff | Not conducted | Gap — required under EU AI Act Art. 26(6) |

The overall picture is a system with genuine monitoring controls in place but significant gaps in remediation, escalation, and the governance processes that should surround deployment of a high-risk AI system. The controls that exist were designed to detect problems. The gaps are predominantly in what happens after a problem is detected.

---

## 8. Residual Concerns

After accounting for existing safeguards, the following concerns remain open and are not adequately addressed by current controls:

**1. The human review threshold is set at the wrong level.**
Reviewing decisions above £10,000 means that the majority of credit decisions — specifically lower-value merchant applications — are fully automated with no human review option. Rights impacts do not scale with decision value. A £2,000 credit decline can have as significant an effect on a sole trader's ability to operate as a £15,000 decline. The threshold should be reviewed against the actual distribution of affected applicants, not against operational convenience.

**2. There is no appeals process.**
There is no documented process within Veriflow by which an applicant who considers their credit decision to have been incorrect, discriminatory, or based on inaccurate information may challenge the decision. The SAR process allows them to see their data. The explanation process tells them why they were declined. Neither provides a process to dispute the decision itself. This is a gap in the right to an effective remedy and a potential Consumer Duty failure.

**3. The retrospective nature of this assessment has a direct consequence.**
Any merchants who were declined in the period between deployment and this FRIA were assessed by a system whose fundamental rights implications had not been formally assessed. If discriminatory effects exist in those decisions, they cannot now be addressed prospectively — only retrospectively identified and learned from. Veriflow should undertake retrospective outcomes analysis covering the deployment period to date, specifically looking for evidence of the effects identified in Section 5.

---

## 9. Recommendations

**Immediate (within 30 days):**
- Document and publish an internal appeals process for contested credit decisions
- Commission retrospective outcomes analysis covering decisions from deployment to date
- Begin AI literacy training for all staff who operate, monitor, or make decisions based on the credit scoring system

**Short-term (within 90 days):**
- Review human review threshold against actual applicant distribution, and consider reducing to £5,000 or introducing risk-based triggers independent of decision value
- Complete DPIA for ClearScore AI processing activities (see AI Risk Register RISK-AI-001)
- Identify and establish an advisory relationship with at least one organisation representing affected SME communities

**Ongoing:**
- Incorporate fundamental rights analysis into quarterly outcomes monitoring — not just performance metrics but distributional equity analysis
- Review this FRIA annually and upon any material change to the model, its inputs, or its deployment context
- Include FRIA findings in annual AI governance report to Risk Committee

---

## 10. Sign-Off and Review

This assessment was prepared by the Arken Systems GRC Function and should be reviewed and approved by Veriflow's Data Protection Officer and Chief Risk Officer prior to being filed as part of the EU AI Act compliance record.

**This document does not constitute legal advice.** Veriflow should seek independent legal advice on the implications of the retrospective deployment gap and on the adequacy of the appeals process against FCA Consumer Duty requirements.

| Role | Name | Sign-off date |
|---|---|---|
| Data Protection Officer | | |
| Chief Risk Officer | | |
| General Counsel | | |

**Next review date:** March 2026, or upon material change to the system  
**Document version:** 1.0 — initial retrospective assessment

---

*Prepared by the Arken Systems GRC Function. This document is a thinking exercise demonstrating fundamental rights impact assessment methodology under the EU AI Act. Veriflow Payments Ltd and ClearScore AI Ltd are fictional organisations.*
