# Artefact A — Risk Acceptance With Teeth

*This is a thinking exercise, not a real organisation.*

> This document records a time-bound acceptance of third-party security risk, with defined compensating controls and review triggers.

---

## Scenario Context

**Organisation:** Veriflow Payments Ltd — Series B UK fintech (38 staff), FCA-regulated under the Payment Services Regulations 2017, preparing for SOC 2 Type II audit (Q3)

**Supplier:** Databridge Analytics Ltd — third-party data enrichment provider  
**Contract value:** £84k/year  
**Constraint:** No viable replacement within 6 months  

**Risk:**  
Databridge will not achieve ISO 27001 certification by the contractual deadline (31 March). Revised timeline: Q3 (five-month delay). During this period, Databridge operates without independently verified security controls while retaining access to Veriflow transaction metadata.

---

## What Could Go Wrong

Databridge has access to anonymised transaction metadata for ~40,000 merchants.

Failure modes include:

- Misconfigured access exposes data → ICO notification under UK GDPR Art. 33  
- Insider exfiltration → weakened regulatory defence due to inadequate due diligence  
- Ransomware incident → disruption during SOC 2 audit window  
- FCA review → visible supplier assurance gap  

> The harm is not hypothetical — it is a defined set of failure modes with regulatory, reputational, and commercial consequences.

---

## Why Full Remediation Is Not Proportionate

Immediate termination would remove a core fraud detection capability.

- Replacement timeline: ~6 months  
- Impact: degraded fraud detection during SOC 2 audit  

Contractual pressure cannot accelerate certification.

This acceptance is:
- **conditional**
- **time-bound**
- **not an endorsement of supplier controls**

It reflects a deliberate decision:

> The business cost of immediate action exceeds the risk cost of a controlled, temporary gap.

---

## Who Is Exposed

- **Customers:** potential exposure of transaction metadata  
- **Veriflow (regulatory):** ICO enforcement; FCA scrutiny  
- **Veriflow (commercial):** SOC 2 findings; reputational damage  
- **CISO / DPO:** accountability for known but unmanaged risk  

---

## Compensating Controls

These controls are conditions of acceptance — not optional mitigations.

- **Access scoping** — remove all non-essential permissions (by 14 April)  
- **Contractual confirmation** — obtain written security controls and 24h incident notification (by 7 April)  
- **Enhanced monitoring** — DLP alerts on Databridge data flows, reviewed weekly  
- **Interim assurance** — quarterly questionnaire (first due: 30 April)  
- **Escalation trigger** — any supplier incident triggers immediate review within 48 hours  

> If these controls are not in place, this risk is not accepted.

---

## Review Triggers

This acceptance expires on **30 September**, or earlier if:

- ISO 27001 certification achieved  
- Any Databridge security incident occurs  
- Supplier fails to respond to assurance request  
- Alternative supplier becomes viable  
- Threat landscape changes materially  
- SOC 2 auditors raise third-party concerns  

---

## Ownership

| Role | Responsibility |
|------|--------------|
| DPO | Owns acceptance; monthly control review |
| Head of Engineering | Implements access and monitoring |
| Legal / Commercial | Manages contractual enforcement |
| CISO | Signs off and escalates if triggered |

---

## Formal Acceptance Statement

> If this risk materialises — specifically, if a data incident at Databridge results in unauthorised access to Veriflow customer data — leadership has consciously accepted that Veriflow operated with an uncertified supplier, with compensating controls in place.
>
> This decision is expected to be scrutinised by the ICO, FCA, and SOC 2 auditors.
>
> This document exists as evidence that the decision was made deliberately, not by default.

---

**Document owner:** Chief Information Security Officer  
**Approved by:** CEO, DPO  
**Date:** April 2025  
**Next review:** 30 June 2025  
**Classification:** Internal — Restricted
