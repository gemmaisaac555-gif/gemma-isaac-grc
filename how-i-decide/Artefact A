# Artefact A — Risk Acceptance With Teeth

> *This is a thinking exercise, not a real organisation.*

---

## Scenario Context

**Organisation:** Veriflow Payments Ltd — a Series B UK fintech, 38 staff, processing card payments for SME merchants. Regulated by the FCA under the Payment Services Regulations 2017. Currently preparing for SOC 2 Type II audit in Q3.

**Supplier:** Databridge Analytics Ltd — a third-party data enrichment provider with read access to anonymised transaction metadata. Contract value: £84k/year. No viable replacement identified within a 6-month window.

**Risk:** Databridge has formally notified Veriflow that it will not achieve ISO 27001 certification by the contractually agreed deadline of 31 March. Their revised estimate is Q3 — a five-month slip. During this window, Databridge operates without independently verified security controls, while retaining access to Veriflow customer transaction data.

---

## What Could Go Wrong

Databridge holds read access to anonymised transaction metadata covering approximately 40,000 Veriflow merchant customers. Without ISO 27001 certification, there is no independent assurance that their access controls, encryption standards, incident response procedures, or staff security training meet a recognised baseline.

Specific failure modes during the gap period:

- A misconfigured access control at Databridge exposes transaction metadata to an unauthorised internal user or external attacker — triggering a Veriflow obligation to notify the ICO within 72 hours under UK GDPR Article 33.
- A Databridge employee with legitimate access exfiltrates data — Veriflow cannot demonstrate it applied adequate supplier due diligence, weakening its position in any regulatory investigation.
- Databridge experiences a ransomware incident — Veriflow's data pipeline is disrupted during a period when the SOC 2 auditors are actively reviewing third-party risk management.
- An FCA supervisory review asks Veriflow to evidence its supplier assurance framework — the certification gap is visible and unexplained.

The harm is not hypothetical. It is a concrete set of outcomes with regulatory, reputational, and contractual consequences.

---

## Why Full Remediation Is Not Proportionate Right Now

Terminating or suspending Databridge immediately would remove a core data enrichment capability used in Veriflow's fraud detection model. Internal engineering estimates a minimum six-month rebuild timeline to replace this with an alternative supplier or in-house solution. Forcing termination now would degrade fraud detection accuracy at a moment when Veriflow is under active SOC 2 scrutiny — trading one risk for a larger operational and compliance one.

Requiring Databridge to achieve certification on the original timeline is not achievable. Their external auditor has confirmed the revised Q3 estimate is realistic. Contractual pressure cannot accelerate an accreditation process.

This risk acceptance is therefore conditional and time-boxed. It is not an endorsement of Databridge's security posture. It is a documented decision that the business cost of immediate action exceeds the risk cost of a managed gap — *provided* the compensating controls below are in place and active.

---

## Who Is Exposed If This Fails

**Veriflow customers (40,000 SME merchants):** Transaction metadata exposure — though anonymised, re-identification risk exists depending on data richness.

**Veriflow (regulatory):** ICO enforcement action under UK GDPR; FCA supervisory censure for inadequate third-party risk management under PSR 2017 Regulation 23.

**Veriflow (commercial):** SOC 2 audit findings referencing an unmitigated supplier gap; potential customer churn if a breach becomes public during the audit window.

**Veriflow CISO / DPO:** Personal accountability if it can be shown this risk was known, undocumented, or accepted without appropriate escalation.

---

## Compensating Controls

The following controls are required as a condition of this acceptance. They are not optional mitigations — they are the basis on which this acceptance is made:

1. **Databridge access scoped to minimum necessary.** Conduct an immediate access review. Remove any permissions beyond what is required for current active use cases. Completed by: 14 April.

2. **Contractual security obligations formalised.** Issue a formal notice to Databridge requiring written confirmation of: current encryption standards for data at rest and in transit, access control policy, and incident notification obligations to Veriflow within 24 hours of any suspected breach. Completed by: 7 April.

3. **Enhanced monitoring of Databridge data flows.** DLP alerts configured to flag anomalous data volumes or access patterns on the Databridge integration. Reviewed weekly by the security team. In place by: 14 April.

4. **Quarterly interim assurance check.** A structured questionnaire (SIG Lite or equivalent) issued to Databridge in lieu of certification, with responses reviewed by the DPO. First response due: 30 April.

5. **Internal escalation trigger documented.** If Databridge reports any security incident — however minor — this acceptance is suspended immediately and an emergency supplier review is triggered within 48 hours.

---

## Review Triggers

This acceptance expires on **30 September** or earlier if any of the following occur:

- Databridge achieves ISO 27001 certification (acceptance closes, controls reviewed)
- Databridge reports any security incident to Veriflow
- Databridge fails to respond to the interim assurance questionnaire by 30 April
- An alternative supplier is identified and a transition plan is approved
- Veriflow's threat landscape changes materially (e.g. a sector-wide attack targeting payment data enrichment providers)
- The SOC 2 auditors raise a finding related to third-party assurance

---

## Ownership

| Role | Responsibility |
|---|---|
| DPO | Owns this risk acceptance; reviews compensating controls monthly |
| Head of Engineering | Implements access scoping and monitoring by stated dates |
| Legal / Commercial | Issues formal notice to Databridge; monitors contract compliance |
| CISO | Signs off this document; escalates to board if review triggers are met |

---

## Formal Acceptance Statement

> *"If this risk materialises — specifically, if a data incident at Databridge results in unauthorised access to Veriflow customer transaction data during this acceptance window — leadership has consciously accepted that Veriflow proceeded with an uncertified supplier, with documented compensating controls in place, and that this decision will be scrutinised by the ICO, FCA, and SOC 2 auditors. This document is the evidence that the decision was made deliberately, not by default."*

---

**Document owner:** Chief Information Security Officer  
**Approved by:** CEO, DPO  
**Date:** April 2025  
**Next review:** 30 June 2025 (or earlier per triggers above)  
**Classification:** Internal — Restricted
