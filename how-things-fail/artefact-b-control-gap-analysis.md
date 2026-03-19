# Artefact B — Third-Party Control Gap Analysis: Databridge Analytics Ltd

*This is a thinking exercise, not a real organisation.*

---

**Document type:** Third-Party Control Gap Analysis — Formal Memo  
**Prepared by:** Arken Systems GRC Function  
**Addressed to:** CISO and Risk Committee, Veriflow Payments Ltd  
**Date:** 14 February 2025  
**Classification:** Confidential — Internal Distribution Only  
**Related documents:** Artefact A — Risk Acceptance With Teeth (31 January 2025); Tool 01 — Third-Party Risk Auto-Scorer output, Databridge Analytics Ltd (12 February 2025)

---

## Purpose

This memo presents the findings of a structured control gap analysis of Databridge Analytics Ltd, conducted following the formal risk acceptance of their ISO 27001 certification delay (Artefact A, 31 January 2025). The analysis was triggered by the 45-day review clause in that acceptance document.

The risk acceptance acknowledged that Databridge would operate without independently verified security controls until approximately Q3 2025. This gap analysis examines what that means in practice — which specific controls are unverified, what the realistic failure scenarios are for Veriflow, and whether the compensating controls documented in Artefact A remain adequate given what the scoring has surfaced.

This is not a re-opening of the risk acceptance decision. It is the analyst function doing its job: ensuring that acceptance was made with accurate information, and that the conditions under which it was made continue to hold.

---

## Scoring Context

Databridge was assessed using the Arken Systems Third-Party Risk Auto-Scorer on 12 February 2025. The assessment covered eight control domains. Overall score: **54/100 — Elevated Risk**.

| Domain | Score | Flag |
|---|---|---|
| Data Protection & Privacy | 48/100 | High |
| Identity & Access Management | 51/100 | High |
| Incident Response | 42/100 | High |
| Supply Chain & Fourth-Party Risk | 38/100 | Critical |
| Risk Management Maturity | 61/100 | Medium |
| Business Continuity | 57/100 | Medium |
| Asset Management | 63/100 | Medium |
| Compliance Posture | 44/100 | High |

Four domains returned High or Critical flags. The Supply Chain domain is the most significant finding and was not adequately surfaced in the original risk acceptance. Each domain is addressed below.

---

## Domain Analysis

### 1. Data Protection and Privacy — Score: 48 — High

**What the scorer flagged:**
Databridge has not completed a current Data Protection Impact Assessment (DPIA) for its data enrichment processing activities. Their stated data retention schedule has not been reviewed since 2022. Responses to questions about anonymisation methodology were incomplete — they confirmed anonymisation is applied to transaction metadata but could not specify the technique or provide documentation.

**What this means for Veriflow:**
Veriflow is the data controller for the transaction metadata Databridge processes. Under UK GDPR Article 28, Veriflow is accountable for ensuring its processors apply appropriate technical and organisational measures. If Databridge's anonymisation methodology is inadequate — or if their retention schedule means data is held longer than disclosed — Veriflow carries the regulatory exposure, not Databridge.

The ICO's enforcement record shows controller accountability is not a theoretical risk. In practice, processors rarely face primary enforcement action; controllers do.

**Analyst assessment:**
The absence of a current DPIA is not a paperwork gap. A DPIA is the mechanism by which a processor identifies and mitigates privacy risks in its own processing. Without it, Databridge cannot demonstrate it has systematically assessed whether its anonymisation, retention, and access controls are proportionate to the data it holds. This is a meaningful gap, not a compliance formality.

The 2022 retention schedule is particularly concerning given that Databridge has grown significantly since then. Their processing scope almost certainly does not match what was documented three years ago.

**Recommendation:**
Veriflow should formally request an updated DPIA from Databridge within 30 days, along with written confirmation of the anonymisation technique applied to Veriflow transaction data. If Databridge cannot provide this, Veriflow should consider whether the Article 28 processor agreement remains adequate and whether a processor audit right should be exercised.

---

### 2. Identity and Access Management — Score: 51 — High

**What the scorer flagged:**
Databridge does not enforce multi-factor authentication across all systems with access to client data. Privileged access review is conducted annually rather than quarterly. There is no documented joiner-mover-leaver process — access deprovisioning is handled ad hoc. Role-based access control is applied inconsistently across their platform.

**What this means for Veriflow:**
Databridge holds read access to anonymised transaction metadata covering approximately 40,000 Veriflow merchant customers. The access path exists. Without MFA enforcement and a functioning joiner-mover-leaver process, the realistic threat is not a sophisticated external attack — it is an opportunistic insider or a credential compromise that goes undetected because privileged access is not regularly reviewed.

Annual privileged access reviews mean that a compromised or inappropriately retained account could persist for up to twelve months without being identified. In the context of financial transaction data, that is an unacceptable detection window.

**Analyst assessment:**
This is the gap that most directly threatens the compensating controls in Artefact A. The acceptance document listed enhanced contractual audit rights and quarterly check-ins as mitigating factors. Neither of those controls addresses the underlying access management weakness — they are detective controls at best, applied after the fact. The IAM gaps are preventive failures.

MFA gaps in particular are no longer considered acceptable for any system processing financial data. The NCSC, FCA, and PCI DSS are aligned on this point.

**Recommendation:**
Arken Systems recommends adding MFA enforcement and a documented joiner-mover-leaver process as explicit remediation requirements in the Databridge contract review scheduled for Q2 2025. These should be framed as contractual obligations with a compliance deadline, not recommendations. Failure to remediate should be treated as a material contract breach.

---

### 3. Incident Response — Score: 42 — High

**What the scorer flagged:**
Databridge has an incident response policy but has not conducted a tabletop exercise in over eighteen months. Their documented breach notification timeline does not meet the 72-hour requirement under UK GDPR Article 33. Follow-up questions about their incident classification criteria received vague responses — there is no clear threshold at which a security event becomes a notifiable incident.

**What this means for Veriflow:**
If Databridge experiences a breach involving Veriflow data, Veriflow's obligation to notify the ICO within 72 hours is triggered by when Veriflow becomes aware, not when Databridge chooses to tell them. A processor with unclear incident classification criteria and a documented notification timeline that exceeds 72 hours is a direct threat to Veriflow's regulatory compliance, regardless of who caused the incident.

This is not a hypothetical. The ICO's guidance on controller-processor relationships is explicit: controllers cannot rely on processor notification as their primary detection mechanism.

**Analyst assessment:**
An untested incident response plan is not an incident response capability. Tabletop exercises exist to surface the gaps between the policy and the reality — what actually happens when someone gets a call at 2am, who has authority to make decisions, what the escalation path looks like when the usual contacts are unavailable. An eighteen-month gap means Databridge's current team has almost certainly never run through the process together.

The notification timeline gap is the more urgent issue. A processor whose documented process does not meet the 72-hour requirement should not be operating as a processor for regulated data until that is corrected.

**Recommendation:**
Veriflow should require Databridge to provide a revised incident notification procedure within 21 days that explicitly meets the 72-hour requirement. This should include a named escalation contact at Databridge with 24/7 availability and a defined threshold for what constitutes a notifiable event. Veriflow's own IR plan should be updated to reflect that Databridge notification cannot be assumed to be timely and that independent detection mechanisms are needed.

---

### 4. Supply Chain and Fourth-Party Risk — Score: 38 — Critical

**What the scorer flagged:**
This is the most significant finding. Databridge was unable to provide a complete inventory of its own sub-processors. They confirmed using third-party cloud infrastructure and at least two data analytics platforms but could not specify which vendors have access to client data, what contractual obligations those vendors carry, or whether those vendors have been assessed against any security standard.

**What this means for Veriflow:**
Veriflow's visibility into its data supply chain ends at Databridge. Beyond that, the data may be flowing through sub-processors that Veriflow has never assessed, that operate under weaker contractual terms, and that may be subject to different legal jurisdictions. Under UK GDPR, Veriflow's accountability does not end at the first processor in the chain.

The phrase "at least two data analytics platforms" is the part that should concern the Risk Committee most. Databridge does not know with certainty which of its vendors have access to Veriflow data. That is not a minor gap — it is a fundamental failure of data inventory that makes the Article 28 processor agreement essentially unenforceable.

**Analyst assessment:**
This finding was not adequately surfaced in the original risk acceptance. Artefact A addressed the ISO 27001 certification gap as the primary risk. The fourth-party exposure is a separate and in some respects more immediate risk: it is not a future certification gap, it is a current state of unknown data flows.

The critical score here reflects not just the severity of the gap but the inability to assess it properly. You cannot manage a risk you cannot see. Databridge's inability to provide a sub-processor inventory means Veriflow is currently accepting risk it has not been able to quantify.

**Recommendation:**
This finding should be escalated to the Risk Committee as a standalone item, separate from the original ISO 27001 acceptance. Veriflow should formally request a complete sub-processor inventory from Databridge within 14 days. If Databridge cannot provide this, the Risk Committee should consider whether the current processing arrangement can continue under the existing Article 28 agreement. This is not a question of remediation timelines — it is a question of whether the contractual basis for the relationship is currently adequate.

---

### 5. Business Continuity — Score: 57 — Medium

**What the scorer flagged:**
Databridge has a business continuity plan but their documented recovery time objective (RTO) for core data enrichment services is 48 hours. Their last BCP test was conducted ten months ago. There is no documented dependency mapping between their services and Veriflow's operational requirements.

**What this means for Veriflow:**
A 48-hour RTO means that in the event of a Databridge outage, Veriflow could lose access to transaction enrichment services for up to two days. Whether that is acceptable depends on how operationally dependent Veriflow's fraud detection and merchant services are on Databridge's enrichment output — something that does not appear to have been formally assessed.

**Analyst assessment:**
The medium score reflects that the gap is real but not immediately critical. A 48-hour RTO is not inherently unreasonable for a third-party enrichment service, but its acceptability depends entirely on Veriflow's own business impact analysis for this dependency. If no such analysis exists, that is the gap to close — not necessarily Databridge's RTO itself.

**Recommendation:**
Veriflow's business continuity function should conduct a dependency impact assessment for the Databridge integration within the next 60 days. If Veriflow's operations would be materially affected by a 48-hour outage of enrichment services, that should be reflected in the contractual SLA and in Veriflow's own contingency planning.

---

## Overall Assessment

The Artefact A risk acceptance was made on the basis of a specific, bounded risk: Databridge's failure to achieve ISO 27001 certification by the contractually agreed deadline. This gap analysis has surfaced additional risks that were not fully visible at the time of acceptance, most significantly the fourth-party sub-processor gap and the incident response notification timeline.

**The original acceptance conditions are partially still holding.** The compensating controls documented in Artefact A — enhanced audit rights, quarterly check-ins, contractual remediation milestones — remain in place and are appropriate for managing the ISO 27001 gap specifically. They are not adequate for the fourth-party and incident response gaps identified here.

**Three findings require action before the next scheduled review:**

| Finding | Urgency | Owner |
|---|---|---|
| Sub-processor inventory request | 14 days | Legal / Procurement |
| Revised IR notification procedure | 21 days | Veriflow IR Lead |
| DPIA and anonymisation documentation request | 30 days | DPO |

**One finding requires Risk Committee escalation as a standalone item:**

The fourth-party sub-processor gap should not be managed as part of the existing ISO 27001 acceptance. It represents a currently unknown data flow that may not be covered by the existing Article 28 agreement. The Risk Committee should determine whether the current processing arrangement requires a contract amendment before the Q2 review.

---

## What Would Change This Assessment

This analysis is based on Databridge's self-reported responses to the auto-scorer questionnaire. The following would materially affect the conclusions:

- **A completed sub-processor inventory** showing that sub-processors are contractually bound and have been assessed would significantly reduce the fourth-party risk rating.
- **Evidence of MFA enforcement** across Databridge's client data systems would reduce the IAM finding from High to Medium.
- **A revised incident notification SOP** meeting the 72-hour requirement would close the most immediate regulatory exposure.

None of these require Databridge to achieve ISO 27001 certification. They are operational controls that can be verified and implemented independently of the certification timeline. Requesting them is reasonable and proportionate given the data Veriflow has entrusted to Databridge.

---

## Recommended Next Steps

1. Legal and Procurement to issue a formal written request to Databridge for sub-processor inventory — **within 14 days**
2. Veriflow IR Lead to request revised notification SOP from Databridge — **within 21 days**
3. DPO to request current DPIA and anonymisation documentation — **within 30 days**
4. Risk Committee to review fourth-party finding as standalone agenda item at next scheduled meeting
5. GRC function to update Artefact A risk acceptance to reflect these additional findings and revised compensating controls
6. Next full scoring review of Databridge scheduled for **Q3 2025**, aligned with ISO 27001 certification target

---

*Prepared by the Arken Systems GRC Function. This document is a thinking exercise demonstrating control gap analysis methodology. Veriflow Payments Ltd and Databridge Analytics Ltd are fictional organisations.*
