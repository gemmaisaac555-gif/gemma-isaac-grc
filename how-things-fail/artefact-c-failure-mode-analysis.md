# Artefact C — Failure Mode Analysis: The 2am Test
## Third-Party Incident Response: Databridge Analytics Notification Failure

*This is a thinking exercise, not a real organisation.*

---

**Document type:** Post-Incident Failure Mode Analysis  
**Prepared by:** Arken Systems GRC Function  
**Addressed to:** CISO and Risk Committee, Veriflow Payments Ltd  
**Date:** April 2025  
**Classification:** Confidential — Internal Distribution Only  
**Incident reference:** INC-2025-003  
**Related documents:** Artefact B — Third-Party Control Gap Analysis, Databridge Analytics Ltd (February 2025); AI Risk Register — Credit Scoring Model Deployment (March 2025)

---

## Preliminary Note

This analysis documents a failure that was predicted.

Artefact B, completed six weeks before this incident, identified Databridge Analytics' incident response capability as a High-rated risk. It noted specifically that Databridge's documented breach notification timeline did not meet the 72-hour requirement under UK GDPR Article 33, and recommended that Veriflow require a revised notification procedure within 21 days.

That recommendation was not actioned before this incident occurred.

This analysis does not exist to assign blame for that gap. It exists to understand why a known risk was not remediated in time, what happened when it materialised, and what the failure modes were at every layer — not just the technical layer, but the human, process, and governance layers that determined how the incident unfolded.

---

## Part One: The Incident Narrative

### 02:17 — The Call

Marcus Webb, Veriflow's on-call security engineer, receives a call from an unknown mobile number. The caller identifies himself as Sanjay Patel, Head of Engineering at Databridge Analytics. He says there has been "a possible security event" affecting Databridge's systems and that it may involve client data.

Marcus has never spoken to Sanjay before. The named escalation contact in Veriflow's third-party records for Databridge is a general security inbox — not a named individual, not a mobile number. Marcus has no way to verify that the person calling him is who he says he is.

Sanjay explains that Databridge detected unusual access patterns on one of their data processing servers at approximately 23:45 the previous evening. Their internal investigation is ongoing. They believe the access may have been limited to internal metadata but cannot confirm this yet. He is calling Veriflow because Veriflow data is processed on the affected server.

The call lasts eleven minutes. Marcus takes notes. He asks three questions: when did it start, what data was affected, and has Databridge informed anyone else. Sanjay says the investigation started around midnight, they don't know yet what data was affected, and Veriflow is the first client they have called.

Marcus says he will escalate internally and someone will be in touch. He ends the call.

---

### 02:31 — The Escalation Problem

Marcus opens Veriflow's incident response runbook. The runbook lists four escalation contacts for a potential data breach: the CISO, the DPO, the Head of Legal, and the on-call manager. He calls the CISO first. No answer. He leaves a voicemail.

He calls the on-call manager. The number rings out. He tries again. No answer.

He sends an email to the DPO and Head of Legal marked urgent. He does not know whether either of them will see it before morning.

It is now 02:41. Twenty-four minutes have passed since Databridge's call. Marcus does not know whether the 72-hour ICO notification clock has started. He does not know when Databridge first became aware of the incident — Sanjay said "around midnight" but Marcus recorded this as "23:45" based on the earlier part of the conversation. He is not sure which figure is correct.

He is alone, it is nearly 3am, and he is making decisions that may have regulatory consequences he cannot fully assess.

---

### 02:47 — The First Decision Point

Marcus faces his first significant decision: does he treat this as a confirmed personal data breach requiring immediate escalation, or a suspected incident requiring investigation before escalation?

The runbook does not help him here. It describes what to do after a breach has been confirmed. It does not describe what to do when a third-party supplier calls at 2am to report a possible event that may or may not involve personal data and may or may not have started before or after midnight.

Marcus makes a judgement call. He decides this is a suspected incident — not yet confirmed — and that his job right now is to document what he knows, keep trying to reach the CISO, and wait for Databridge to provide more information before treating it as a notifiable breach.

He is not wrong to make this call. But he is making it alone, without guidance, under time pressure, with incomplete information, and with no documented criteria to help him distinguish a suspected from a confirmed incident. The runbook has left him exposed at exactly the moment it should have supported him.

---

### 03:15 — Databridge Calls Again

Sanjay calls back. Their investigation has progressed. The unusual access was to a database partition that contains, among other things, anonymised transaction metadata for several clients including Veriflow. Databridge's position is that the data is anonymised and therefore not personal data, and therefore not subject to the 72-hour notification requirement.

Marcus asks whether Veriflow's data was specifically accessed. Sanjay says they cannot confirm which client partitions were accessed — the access logs show the partition was reached but not which records within it were read.

Marcus asks when Databridge first became aware of the incident. Sanjay says their automated monitoring flagged unusual activity at 23:45. He confirms that 23:45 is the correct time.

Marcus asks whether Databridge has a documented incident response procedure. There is a pause. Sanjay says yes. Marcus asks whether the procedure specifies a notification timeline. Another pause. Sanjay says he would need to check.

Marcus ends the call at 03:28. It is now three hours and forty-three minutes since Databridge first detected the incident. The 72-hour window, if it applies, has been running since 23:45.

---

### 03:45 — The Anonymisation Question

Marcus now has a new problem. Databridge's position is that the affected data is anonymised and therefore outside the scope of UK GDPR Article 33. Veriflow's position — as documented in Artefact B — is that Databridge has never provided documentation of its anonymisation methodology, and that the DPIA request made in February 2025 has not been fulfilled.

Marcus does not know whether Databridge's anonymisation is adequate. He does not have the technical documentation to assess it. He is not in a position to confirm or contradict Databridge's claim that the data is not personal data.

If the anonymisation is adequate, this may not be a notifiable breach. If it is not — if the "anonymised" data can be re-identified, or if the anonymisation technique does not meet the standard required by UK GDPR — then this is personal data, and the 72-hour clock has been running for nearly four hours.

This is precisely the gap that Artefact B identified. The risk was known. The DPIA was requested. The request was not fulfilled. Veriflow is now making incident response decisions without information it should have had before this incident occurred.

---

### 06:30 — The CISO Responds

Veriflow's CISO, Rachel Okonkwo, sees Marcus's voicemail and email and calls at 06:30. Marcus briefs her on the incident. The call lasts twenty-two minutes.

Rachel makes three immediate decisions:

1. Treat this as a suspected personal data breach until Databridge can demonstrate adequate anonymisation — Veriflow cannot rely on Databridge's self-assessment
2. Engage Veriflow's external legal counsel to advise on ICO notification obligations given the uncertainty about anonymisation and notification timing
3. Send a formal written request to Databridge requiring a full written incident report, evidence of anonymisation methodology, and confirmation of when their investigation began

She also notes, without elaboration, that the recommendation in Artefact B to require a revised notification procedure from Databridge within 21 days was not implemented. She asks the Head of GRC to identify why.

---

### 09:00 — Legal Counsel's Assessment

External legal counsel reviews the facts and provides initial advice at 09:00. Their assessment:

- The 72-hour notification clock under UK GDPR Article 33 starts when the controller — Veriflow — becomes aware of a breach, not when the processor notifies them
- Veriflow became aware at 02:17 when Databridge called
- Whether the data is personal data depends on the adequacy of Databridge's anonymisation — which Veriflow cannot currently assess because the DPIA has not been provided
- In the absence of evidence of adequate anonymisation, the precautionary position is to treat the data as personal data
- On that basis, the 72-hour window started at 02:17 and expires at 02:17 on the following day
- Veriflow has approximately seventeen hours to notify the ICO or establish that notification is not required

Legal counsel recommends notifying the ICO within the window on a precautionary basis, with a clear statement that the investigation is ongoing and that the notification may be updated or withdrawn if Databridge can demonstrate adequate anonymisation.

---

### 11:30 — ICO Notification

Veriflow submits a precautionary breach notification to the ICO at 11:30, approximately nine hours after first becoming aware of the incident. The notification describes the incident as a suspected breach involving a third-party processor, notes the uncertainty about data classification, and commits to a follow-up report within 72 hours of the investigation concluding.

The notification is submitted within the 72-hour window. Veriflow is compliant — but only because Rachel Okonkwo responded quickly once she was reached, legal counsel was available on short notice, and Marcus documented the timeline accurately despite operating alone in the middle of the night.

None of those things were guaranteed.

---

## Part Two: Failure Mode Analysis

The incident was contained. The notification was made within the required window. By the metrics that regulators measure, Veriflow responded adequately.

This section examines why the response was harder than it needed to be, and what failure modes were present throughout.

---

### Failure Mode 1: Known Risk, Unactioned Recommendation

**What happened:** Artefact B identified Databridge's notification timeline gap as a High-rated risk and recommended requiring a revised procedure within 21 days. Six weeks later, the recommendation had not been actioned and the risk materialised.

**Why it happened:** The recommendation existed in a report. It was not assigned to a named owner with a tracked deadline. There was no mechanism to escalate an unactioned recommendation to the Risk Committee. The gap between identifying a risk and remediating it was filled with nothing — no chase, no escalation, no visibility.

**The failure mode:** Risk registers and gap analyses are only governance documents if someone is responsible for acting on them. A recommendation without an owner, a deadline, and a follow-up mechanism is a documented risk, not a managed one.

**What this looks like at 2am:** Marcus is making decisions without the anonymisation documentation that Veriflow requested two months ago and never received. Every difficulty in this incident traces back to that single unactioned recommendation.

---

### Failure Mode 2: The Runbook Stopped at the Wrong Place

**What happened:** Veriflow's incident response runbook described post-confirmation procedures clearly. It did not describe how to handle an unconfirmed third-party notification received out of hours by a single on-call engineer.

**Why it happened:** Runbooks are typically written for confirmed incidents. The pre-confirmation phase — the period of uncertainty between first notification and established facts — is harder to document because the scenarios are more variable. It is also the most consequential phase, because decisions made in that window determine whether the 72-hour clock is correctly identified and whether the right people are involved early enough.

**The failure mode:** An incident response capability that only activates after confirmation is not a full incident response capability. The pre-confirmation phase needs documented criteria: what constitutes a reportable event, what actions are required before confirmation, and critically — who has authority to make decisions when the primary escalation chain is unavailable.

**What this looks like at 2am:** Marcus spends fourteen minutes trying to reach two people who don't answer, then makes regulatory judgement calls alone because there is no documented guidance for his situation and no alternative escalation path.

---

### Failure Mode 3: The Escalation Chain Was a Single Point of Failure

**What happened:** Marcus tried two escalation contacts. Neither answered. He fell back to email. For nearly four hours, Veriflow's incident response was being managed by one engineer who had never handled a breach notification before.

**Why it happened:** The escalation chain listed four contacts. In practice, it functioned as two contacts — the CISO and the on-call manager — because the others were not expected to respond immediately. There was no documented backup for a scenario where neither primary contact was reachable.

**The failure mode:** An escalation chain with no redundancy is not an escalation chain — it is an optimistic list. Incident response planning must account for the realistic probability that primary contacts will be unavailable, especially out of hours.

**What this looks like at 2am:** The right person — Rachel Okonkwo — is not in the room for four hours. The decisions made in that window are made without her.

---

### Failure Mode 4: Third-Party Contact Records Were Inadequate

**What happened:** Marcus received a call from a mobile number that did not match any contact in Veriflow's third-party records. He could not verify the caller's identity. He could not call Databridge back on a number he trusted. He had no named individual to reach.

**Why it happened:** Veriflow's third-party records for Databridge listed a general security inbox. Named individual contacts, direct lines, and out-of-hours numbers were not recorded. This is common — third-party records are typically populated from contract documents and not kept current as personnel change.

**The failure mode:** In an incident, you need to reach a specific person at a third party quickly and be confident you are speaking to who you think you are. A general inbox does not achieve this. Named contacts with verified direct numbers, reviewed at least annually, are a basic requirement for any supplier where an incident would trigger time-sensitive regulatory obligations.

**What this looks like at 2am:** Marcus cannot call Databridge back. He cannot verify the caller. He is responding to an incident reported by someone whose identity he cannot confirm, on a contact channel that Veriflow never established.

---

### Failure Mode 5: The Anonymisation Gap Created Cascading Uncertainty

**What happened:** Databridge's claim that the affected data was anonymised — and therefore not personal data — could not be verified because Veriflow had never received Databridge's DPIA or anonymisation documentation. This created uncertainty about whether the incident was notifiable, which cascaded through every subsequent decision.

**Why it happened:** See Failure Mode 1. The DPIA request was made. It was not fulfilled. It was not escalated. It was not treated as a material gap in Veriflow's ability to manage a breach involving Databridge's systems.

**The failure mode:** Incident response decisions about personal data require knowledge of what personal data a processor actually holds and how it is protected. That knowledge cannot be obtained in the middle of an incident. It must be established in advance and kept current. The absence of the DPIA was not just a compliance gap — it was a practical impediment to incident management.

**What this looks like at 2am:** Marcus and later Rachel are making notification decisions under time pressure without the basic information — is this personal data? — that those decisions require.

---

## Part Three: What the 2am Test Reveals

The 2am Test is not a test of technical controls. Firewalls, encryption, and access management did not fail here. What failed was the governance infrastructure that surrounds those controls — the processes, the documentation, the human systems that determine whether a known risk gets managed before it becomes an incident, and whether an incident gets handled competently when it occurs.

The test is simple: take your incident response capability, remove the CISO, remove the on-call manager, set the time to 2am on a Tuesday, and ask what happens. If the answer is "one engineer makes regulatory judgement calls alone for four hours with an inadequate runbook and no verified contact at the third party," the test has identified your failure modes before an incident did.

Veriflow passed this incident — narrowly, and with more luck than governance. The ICO notification was made in time. The legal advice was obtained quickly. Rachel Okonkwo acted decisively once she was reached.

But the margin was thin. A slower legal response, a less thorough engineer, a CISO who didn't see the voicemail until 9am rather than 6:30am — any of these would have changed the outcome.

---

## Recommendations

| Recommendation | Owner | Deadline |
|---|---|---|
| Assign named owners with tracked deadlines to all open recommendations from Artefact B | Head of GRC | Immediate |
| Revise incident response runbook to cover pre-confirmation phase and out-of-hours third-party notifications | CISO | 30 days |
| Establish documented backup escalation path for scenarios where primary contacts are unreachable | CISO | 30 days |
| Update Databridge third-party records with named individual contacts and verified out-of-hours numbers | Procurement | 14 days |
| Require Databridge to provide DPIA and anonymisation documentation as a condition of continued processing | Legal / Procurement | 21 days |
| Conduct tabletop exercise simulating out-of-hours third-party incident notification | CISO | 60 days |
| Review all third-party records for suppliers where an incident would trigger regulatory notification obligations | Head of GRC | 60 days |

---

## Closing Note

This analysis was commissioned because an incident occurred. It should have been commissioned because a risk was identified.

Artefact B identified the conditions that made this incident harder to manage than it needed to be. The gap analysis was completed. The recommendations were written. The risk was known. What was missing was the governance mechanism to turn a recommendation into an action, track that action to completion, and escalate it when it was not completed on time.

That is the failure mode this incident most clearly exposes — not a technical gap, not a process gap, but a gap in the discipline of following through on governance decisions. Risk management is not complete when the risk is identified. It is complete when the risk is treated, accepted, or transferred — and when the chosen response has been implemented and verified.

A risk register entry that has been read and filed is not a control. An unactioned recommendation is not a mitigation. Governance documents that exist without generating action are an organisational comfort, not an organisational protection.

---

*Prepared by the Arken Systems GRC Function. This document is a thinking exercise demonstrating failure mode analysis methodology. Veriflow Payments Ltd and Databridge Analytics Ltd are fictional organisations.*
