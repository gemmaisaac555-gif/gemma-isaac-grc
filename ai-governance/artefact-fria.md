Fundamental Rights Impact Assessment AI Credit Scoring System is Veriflow Payments Ltd This is a hypothetical scenario and not a real company.

Type: Fundamental Rights Impact Assessment (FRIA) Author: Arken Systems GRC Function Recipient: Data Protection Officer and Chief Risk Officer, Veriflow Payments Ltd Completed: March 2025 Handling Instructions: Confidential, Internal Use Only Legal Basis: EU AI Act Article 27, mandatory for users of high-risk AI systems in financial services Cross-references: AI Risk Register, Credit Scoring Model Deployment (March 2025); Document A, Risk Acceptance with Teeth (January 2025)

Important: This FRIA is retrospective. Veriflow has already deployed the ClearScore AI credit scoring system (in Q1 2025). EU AI Act Article 27 says that users in financial services must do a FRIA before deploying a high-risk AI system. Veriflow did not complete this FRIA before deploying the system.

Rather than disguising that fact, it is being made explicit. This document is not an attempt to pretend that the requirement has been fulfilled, it is an attempt to retrospectively undertake the impact assessment that should have been done in the first place, and to use that as a basis to understand the current risk position, and to set a baseline for the ongoing management of fundamental rights issues associated with this application.

Doing a FRIA after deploying the system is better than not doing one at all. It is not the same as doing a FRIA before deploying the system. That distinction is relevant to the findings.

1. System Description

Name: ClearScore AI Credit Scoring Model (instance deployed: Veriflow Payments Ltd) Type: Automated credit scoring, EU AI Act Annex III, point 5(b), High Risk Supplier: ClearScore AI Ltd User: Veriflow Payments Ltd Context: The system is used for automated creditworthiness assessment for merchant onboarding and credit limit decisions. The system evaluates applications from merchants (small and medium-sized enterprises) applying for payment processing and credit through the Veriflow platform. Outcome: The system generates a credit score, and makes a decision (approve/decline/refer for human evaluation). Decisions with a value of less than £10,000 are automated. Decisions with a value of more than £10,000 are referred for human evaluation. Volume: The system evaluates approximately 400-600 merchant credit applications per month (current volumes). Inputs: Data inputs to the system include: (i) transaction history; (ii) business profile data; (iii) Companies House data; (iv) behavioural data/signals from the use of the Veriflow platform.

2. Purpose of This Assessment

This impact assessment considers the impact of Veriflow’s credit scoring system on the fundamental rights of natural persons who are affected by the system. This document is required by EU AI Act Article 27, which says that users of high risk AI systems in financial services must complete a FRIA before the AI system is put into service.

This assessment addresses four questions:

What are the fundamental rights at stake in this system?

Which groups are most likely to experience rights impacts from this system?

What is the likelihood and potential severity of the rights impacts?



Are existing mitigations adequate, and if not, what more is needed?

3. Fundamental Rights at Stake

The following fundamental rights are engaged by an automated credit scoring application in this context. This does not mean that they are all equally at risk, this assessment distinguishes between those rights that are directly engaged, and those that provide the background conditions against which the system operates.

Directly engaged:

Right to equal treatment (Equality Act 2010; EU Charter Article 21) Automated credit scoring applications that incorporate proxy variables (such as geographic location, business sector, transaction history) may result in different outcomes for applicants that share particular protected characteristics, even if those protected characteristics are not directly used as inputs to the system. This is the right that is most directly engaged by the system.

Right to explanation and contest automated decisions (UK GDPR Article 22; EU AI Act Article 86) Individuals have the right to an explanation of automated decisions that have a substantial effect on them, and the right to contest those decisions. An automated credit decision has a substantial effect on a merchant, it determines whether or not they are able to access payment services (which in practice means whether or not they can trade).

Right to the protection of personal data (UK GDPR; EU Charter Article 8) The system processes the personal data of individual owners and directors of merchants as part of the creditworthiness assessment. This includes the right to accuracy, proportionality, and the right not to be subject to automated decisions made on the basis of inaccurate or out-of-date data.

Background conditions:

Right to work and engage in work (EU Charter Article 15) For some individuals (sole traders, and the owners of the smallest businesses), access to payment services is a practical prerequisite for trading. An automated credit decision that is wrong (i.e. one that inappropriately declines a credit application) does not directly infringe the right to work, but may in practice make it much harder to exercise.

Right to an effective remedy (EU Charter Article 47) Individuals who believe that an automated credit decision was wrong or discriminatory must have access to effective complaints and appeals processes. This right is engaged by the design of Veriflow’s review and escalation processes.

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
