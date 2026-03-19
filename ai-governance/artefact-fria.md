# Fundamental Rights Impact Assessment
## AI Credit Scoring System — Veriflow Payments Ltd

*This is a thinking exercise, not a real organisation.*

---

**Document type:** Fundamental Rights Impact Assessment (FRIA)  
**Prepared by:** Arken Systems GRC Function  
**Addressed to:** Data Protection Officer and Chief Risk Officer, Veriflow Payments Ltd  
**Date:** March 2025  
**Classification:** Confidential — Internal Distribution Only  
**Legal basis:** EU AI Act Article 27 — mandatory for deployers of high-risk AI systems in financial services  
**Related documents:** AI Risk Register — Credit Scoring Model Deployment (March 2025); Artefact A — Risk Acceptance With Teeth (January 2025)

---

## Preliminary Note

This FRIA is retrospective. Veriflow deployed the ClearScore AI credit scoring system in Q1 2025. EU AI Act Article 27 requires deployers in financial services to conduct a FRIA before deployment. This assessment was not completed prior to go-live.

That gap is acknowledged directly here rather than obscured. The purpose of this document is not to manufacture retroactive compliance — it is to conduct the assessment that should have been conducted earlier, identify what that omission means for current risk posture, and establish a baseline for ongoing fundamental rights governance of this system.

A FRIA completed after deployment is better than no FRIA. It is not equivalent to a FRIA completed before deployment. The difference matters and is noted in the findings.

---

## 1. System Description

**System name:** ClearScore AI Credit Scoring Model (deployed instance: Veriflow Payments Ltd)  
**System type:** Automated credit scoring — EU AI Act Annex III, point 5(b) — High Risk  
**Provider:** ClearScore AI Ltd  
**Deployer:** Veriflow Payments Ltd  
**Deployment context:** Automated creditworthiness assessment for merchant onboarding and credit limit decisions. The system processes applications from SME merchants seeking payment processing services and credit facilities through Veriflow's platform.  
**Decision type:** The system produces a credit score and a recommendation (approve / decline / refer for human review). Decisions below £10,000 are fully automated. Decisions above £10,000 trigger a human review process.  
**Scale:** Approximately 400–600 merchant credit assessments per month at current volume.  
**Data inputs:** Transaction history, business profile data, Companies House records, behavioural signals from Veriflow platform usage.

---

## 2. Purpose of This Assessment

This assessment examines the impact of Veriflow's credit scoring system on the fundamental rights of individuals and groups affected by its decisions. It is required under EU AI Act Article 27, which mandates that deployers of high-risk AI systems in financial services conduct a FRIA before putting the system into use.

The assessment addresses four questions:

1. Which fundamental rights are engaged by this system?
2. Which populations are most exposed to rights impacts?
3. What is the likelihood and severity of those impacts?
4. Are current safeguards adequate, and what gaps remain?

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
Merchants with limited trading history have thin data profiles. The model was trained on historical credit data that may underrepresent early-stage businesses. Applicants with fewer data points receive less reliable scores, and the system may default to conservative (declining) recommendations in the absence of signal. This disproportionately affects new market entrants, including those from communities where business formation has historically been lower.

**Rights engaged:** Equal treatment, right to contest  
**Current safeguard:** Human review for applications above £10,000. No specific safeguard for lower-value applications.  
**Gap:** No mechanism to flag thin-data profiles for additional scrutiny regardless of decision value.

### 4.2 Merchants in Sectors Underrepresented in Training Data

**Exposure:** Medium-High  
Merchants in sectors that grew significantly post-2020 — gig economy platforms, creator economy businesses, certain care sector providers — may be systematically underscored if their sector is underrepresented in the model's training data. This is not deliberate discrimination but produces discriminatory-equivalent outcomes.

**Rights engaged:** Equal treatment, data protection (accuracy)  
**Current safeguard:** Quarterly monitoring disaggregated by merchant sector.  
**Gap:** Monitoring detects underperformance but does not trigger automatic remediation or additional human review.

### 4.3 Sole Traders and Micro-Businesses

**Exposure:** Medium-High  
For sole traders, the boundary between personal and business financial data is blurred. The model may incorporate signals that reflect personal financial circumstances rather than business creditworthiness. This raises proportionality concerns under UK GDPR and creates potential for indirect discrimination given the demographic profile of sole trader applicants.

**Rights engaged:** Data protection (proportionality), equal treatment  
**Current safeguard:** Data Protection Impact Assessment requested from ClearScore AI (pending — see AI Risk Register RISK-AI-001).  
**Gap:** DPIA has not been completed. Proportionality of personal data use has not been independently assessed.

### 4.4 Applicants with Limited Digital Footprint

**Exposure:** Medium  
The model incorporates behavioural signals from Veriflow platform usage. Applicants who are new to the platform or who use it differently from the training population — including those who are less digitally active — may be systematically disadvantaged by the absence of behavioural signal, independent of their actual creditworthiness.

**Rights engaged:** Equal treatment, right to contest  
**Current safeguard:** None specifically addressing this population.  
**Gap:** No documented assessment of how the model handles low-signal applicant profiles.

---

## 5. Impact Assessment

For each identified rights impact, the following scale applies:

**Severity:** 1 (Negligible) — 2 (Minor) — 3 (Moderate) — 4 (Significant) — 5 (Severe)  
**Likelihood:** 1 (Rare) — 2 (Unlikely) — 3 (Possible) — 4 (Likely) — 5 (Almost certain)

| Rights Impact | Affected Population | Severity | Likelihood | Overall | Current Safeguard Adequacy |
|---|---|---|---|---|---|
| Discriminatory outcome via proxy variable | Protected characteristic groups | 5 | 3 | High | Partial — fairness audit not independent |
| Wrongful decline due to thin data profile | New businesses | 4 | 3 | High | Partial — human review threshold too high |
| Inaccurate scoring due to sector bias | Underrepresented sectors | 3 | 3 | Medium | Partial — monitoring without remediation trigger |
| Disproportionate personal data use | Sole traders | 3 | 3 | Medium | Inadequate — DPIA not completed |
| Inadequate explanation of decline | All declined applicants | 3 | 2 | Medium | Partial — factor-based explanation may not be meaningful |
| No effective remedy for contested decisions | All applicants | 4 | 2 | Medium | Inadequate — escalation process not documented |

---

## 6. Consultation

EU AI Act Article 27 and supporting guidance indicate that FRIAs should, where appropriate, involve consultation with representatives of affected groups or civil society organisations with relevant expertise.

**Consultation conducted prior to deployment:** None.

This is a significant gap. Veriflow did not consult with any of the following before deploying the system:

- Organisations representing small business owners from minority ethnic communities
- Consumer or SME advocacy groups with expertise in algorithmic credit decisions
- The ICO or FCA, despite both having published relevant guidance on automated decision-making in financial services

The absence of consultation does not mean rights impacts were not considered — Veriflow conducted internal fairness testing and legal review. It means that the perspectives of people most likely to be adversely affected were not sought before the system went live. That is a meaningful omission, both as a matter of regulatory good practice and as a matter of governance integrity.

**Recommended remediation:**
Veriflow should establish a standing advisory relationship with at least one organisation representing SME owners from communities with protected characteristics. This does not require formal consultation on every model change — it requires that affected community perspectives are available to inform governance decisions about the system on an ongoing basis.

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
Reviewing decisions above £10,000 means that the majority of credit decisions — lower-value merchant applications — are fully automated with no human review option. Rights impacts do not scale with decision value. A £2,000 credit decline can have as significant an effect on a sole trader's ability to operate as a £15,000 decline. The threshold should be reviewed against the actual distribution of affected applicants, not against operational convenience.

**2. There is no documented appeals process.**
An applicant who believes their credit decision was wrong, discriminatory, or based on inaccurate data has no documented route to appeal within Veriflow's systems. The SAR process allows them to access their data. The explanation process tells them why they were declined. Neither provides a mechanism for contesting the decision itself. This is a gap in the right to an effective remedy and a potential Consumer Duty failure.

**3. The retrospective nature of this assessment has a specific consequence.**
Any merchants who were declined during the period between deployment and this FRIA were assessed by a system whose fundamental rights impacts had not been formally evaluated. If discriminatory patterns exist in that period's decisions, they cannot now be remediated prospectively — only identified and learned from. Veriflow should conduct a retrospective outcome analysis covering the deployment period to date, specifically looking for evidence of the impacts identified in Section 5.

---

## 9. Recommendations

**Immediate (within 30 days):**
- Document and publish an internal appeals process for contested credit decisions
- Commission retrospective outcome analysis covering decisions from deployment to date
- Begin AI literacy training for all staff who operate, monitor, or make decisions based on the credit scoring system

**Short-term (within 90 days):**
- Review human review threshold against actual applicant distribution — consider lowering to £5,000 or introducing risk-based triggers independent of decision value
- Complete DPIA for ClearScore AI processing activities (see AI Risk Register RISK-AI-001)
- Identify and establish an advisory relationship with at least one organisation representing affected SME communities

**Ongoing:**
- Incorporate fundamental rights lens into quarterly outcome monitoring — not just performance metrics but distributional fairness analysis
- Review this FRIA annually and upon any material change to the model, its inputs, or its deployment context
- Include FRIA findings in annual AI governance report to Risk Committee

---

## 10. Sign-Off and Review

This assessment was prepared by the Arken Systems GRC Function and should be reviewed and approved by Veriflow's Data Protection Officer and Chief Risk Officer before being filed as part of the EU AI Act compliance record.

**This document does not constitute legal advice.** Veriflow should seek independent legal counsel on the implications of the retrospective deployment gap and on the adequacy of the appeals process against FCA Consumer Duty requirements.

| Role | Name | Sign-off date |
|---|---|---|
| Data Protection Officer | | |
| Chief Risk Officer | | |
| General Counsel | | |

**Next review date:** March 2026, or upon material change to the system  
**Document version:** 1.0 — initial retrospective assessment

---

*Prepared by the Arken Systems GRC Function. This document is a thinking exercise demonstrating fundamental rights impact assessment methodology under the EU AI Act. Veriflow Payments Ltd and ClearScore AI Ltd are fictional organisations.*
