# Artefact D — Human-Centred Root Cause Analysis
## Access Control Failure: The Account That Should Not Have Existed

*This is a thinking exercise, not a real organisation.*

---

**Document type:** Human-Centred Root Cause Analysis  
**Prepared by:** Arken Systems GRC Function  
**Addressed to:** CISO and People Director, Veriflow Payments Ltd  
**Date:** April 2025  
**Classification:** Confidential — Internal Distribution Only  
**Incident reference:** INC-2025-007  
**Related documents:** Artefact C — Failure Mode Analysis: The 2am Test (April 2025)

---

## The Presenting Problem

On 3 April 2025, Veriflow's security monitoring flagged unusual access to the Tradify job management system outside normal business hours. Investigation revealed that the access originated from credentials belonging to Daniel Osei — a former Veriflow account manager who left the company on 14 February 2025, seven weeks earlier.

Daniel's account had never been deprovisioned. It remained active, with full access permissions, for forty-nine days after his last working day.

The access on 3 April was not malicious. Daniel had logged in to retrieve a personal document he had stored in the wrong location. He did not access customer data. He did not cause a breach. He logged out after four minutes.

This incident is not in the report because of what happened. It is in this report because of what could have happened — and because the conditions that allowed it to happen are still present in Veriflow's systems.

---

## What a Surface Analysis Would Find

A surface analysis of this incident produces a simple finding: the IT team failed to deprovision Daniel's account when he left. The fix is obvious — implement a checklist, make deprovisioning mandatory, close the gap.

That analysis is not wrong. It is incomplete.

If the only lesson from this incident is "remember to deprovision accounts," the conditions that made the failure likely will remain unchanged. A checklist will be added. It will be followed for a while. Pressure will build, a leaver will be processed quickly, the checklist will be skipped, and the same failure will recur — possibly with different consequences.

Human-centred root cause analysis starts where surface analysis stops. It asks not what failed, but why the system made failure likely — and what would need to change for the system to make success the easier path.

---

## The Five Whys

**Why was Daniel's account still active forty-nine days after he left?**
Because the IT team did not deprovision it when he left.

**Why did the IT team not deprovision it?**
Because they were not informed that Daniel had left.

**Why were they not informed?**
Because there is no formal process requiring People to notify IT when an employee leaves. Notification happens informally — a message, an email, a conversation — when someone remembers to do it.

**Why is there no formal process?**
Because when Veriflow was smaller, everyone knew when someone left and IT was always in the building. The informal process worked well enough that no one formalised it. The company grew; the informal process did not scale; no one noticed the gap until now.

**Why did no one notice the gap?**
Because there is no mechanism to detect undiscovered active accounts belonging to leavers. The gap is only visible when something goes wrong. Until 3 April 2025, nothing had gone wrong — or if it had, it had not been detected.

---

## Contributing Factor Map

The Five Whys identifies the immediate causal chain. The contributing factor map identifies the systemic conditions that made each link in that chain likely.

### Factor 1: The process was designed for a smaller organisation

Veriflow had eleven employees when it was founded. At eleven people, informal communication about leavers works. At current headcount — forty-three people across three offices — it does not. The gap between the organisation's size and its processes is not unusual; it is one of the most common failure modes in growing companies. Processes that worked at one scale become invisible risks at another.

**Systemic condition:** No mechanism exists to periodically review whether informal processes remain adequate as the organisation grows.

### Factor 2: Accountability for the leaver process was diffuse

People think IT knows. IT thinks People will tell them. Neither function has explicit ownership of the end-to-end leaver process. When accountability is shared informally between functions, it tends to fall through the gap between them — not because anyone is negligent, but because each function reasonably assumes the other has it covered.

**Systemic condition:** The leaver process has no named owner and no defined handoff point between People and IT.

### Factor 3: The consequence of failure was invisible until it materialised

An active account belonging to a leaver produces no signal until it is used. There is no alert, no monitoring, no periodic review that would have surfaced Daniel's account between 14 February and 3 April. The gap existed for forty-nine days without anyone knowing it existed.

This is the most important factor. Failures that are invisible until they cause harm are structurally different from failures that are visible in advance. A visible failure — a missed deadline, an incomplete form — creates the opportunity for correction. An invisible failure accumulates silently until a detection event occurs. In this case, the detection event was benign. It will not always be.

**Systemic condition:** No periodic review of active accounts against current employee records. No alerting for accounts inactive beyond a defined threshold.

### Factor 4: The informal process had never failed visibly before

The most dangerous property of a process that has worked by luck is that it looks like a process that works. Everyone involved in Daniel's offboarding acted reasonably within the system as they understood it. No one was careless. No one skipped a step they knew existed. The failure was not a deviation from the process — it was the process operating normally in conditions it was not designed to handle.

**Systemic condition:** No near-miss reporting culture. Informal processes are not periodically tested or audited. Success is assumed from absence of failure.

### Factor 5: The offboarding happened quickly and under pressure

Daniel's departure was not planned. He resigned with two weeks' notice during a period when the People team was managing two other leavers and a new starter simultaneously. The informal notification to IT — which should have happened as a matter of course — was not sent because the People team member responsible was managing competing demands and assumed a colleague had handled it.

This is not a finding about that individual's performance. It is a finding about capacity. When informal processes depend on individuals remembering to do things under pressure, the probability of failure scales with workload. The system was designed for normal conditions. It was operating in abnormal conditions. It failed.

**Systemic condition:** No safeguard exists for high-workload periods when informal process steps are most likely to be missed.

---

## What This Is Not About

This section exists because human-centred root cause analysis is sometimes misread as an attempt to identify who is to blame and then absolve them. That is not its purpose.

The People team member who did not notify IT did not cause this incident. They were operating within a system that gave them no formal process to follow, no reminder when a step was missed, and no signal that anything had gone wrong. Telling them to be more careful would not prevent the next occurrence. Changing the system might.

The IT team did not cause this incident. They were not informed of Daniel's departure. They had no mechanism to detect that his account was still active. They had no reason to check.

Daniel did not cause this incident. He left in February. His account remaining active was not his responsibility.

The incident was caused by a system that made this failure likely — and had been making it likely for some time, without anyone knowing, because the failure was invisible until it materialised.

Assigning blame to individuals in a system-level failure does not fix the system. It fixes the individual's behaviour temporarily, under observation, while the system continues to make the same failure likely for everyone else.

---

## The Deeper Pattern

This incident and the incident documented in Artefact C share a structural characteristic that is worth naming directly.

In Artefact C, a risk was identified, a recommendation was written, and the recommendation was not actioned. The failure was not in the analysis — the analysis was correct. The failure was in the mechanism that should have turned the analysis into action.

In this incident, a process worked informally for years, was never formally documented or owned, and failed when conditions exceeded its design parameters. The failure was not in anyone's intentions — everyone intended to do the right thing. The failure was in the assumption that intention is sufficient, and that a process which has not visibly failed is a process that works.

Both failures are invisible until they materialise. Both are predictable in retrospect. Both are preventable — not by asking people to try harder, but by designing systems that make failure visible before it causes harm.

This is the central insight of human-centred root cause analysis: most failures are not caused by bad people. They are caused by systems that make failure the easier path — or that make failure invisible until the path has already been taken.

---

## Recommendations

### Immediate

**1. Full account audit against current employee records**
IT should conduct an immediate audit of all active accounts across all systems — Microsoft 365, Tradify, Xero, and any other platform with access to Veriflow data — against the current employee list. Any active account belonging to a former employee should be disabled immediately and reviewed before any reinstatement.

This audit should be completed within five working days. Its findings should be reported to the CISO.

**2. Disable Daniel's account**
Daniel's account should be disabled immediately if not already done. This is noted separately because the incident report does not confirm this was actioned at the time of detection.

---

### Short-Term (within 30 days)

**3. Define and document the leaver process with named ownership**
People owns the trigger: when an employee's last working day is confirmed, a formal notification must be sent to IT within 24 hours. IT owns the execution: account deprovisioning must be completed within one working day of notification. Both steps must be documented, with named owners and a defined handoff point.

The process should be simple enough to follow under pressure and specific enough that there is no ambiguity about who does what and when.

**4. Add account deprovisioning to the leaver checklist as a mandatory tracked step**
The leaver checklist — if one exists — should include account deprovisioning as a tracked item with a completion confirmation required from IT before the leaver process is closed. If no leaver checklist exists, one should be created. The checklist should be owned by People and completed for every leaver without exception.

**5. Implement inactive account alerting**
IT should configure alerting for accounts that have been inactive beyond a defined threshold — recommended 30 days. Alerts should be reviewed monthly. An account that has been inactive for 30 days and belongs to a current employee may indicate a different problem; an account that has been inactive for 30 days and belongs to a former employee should not exist.

---

### Medium-Term (within 90 days)

**6. Quarterly access review**
A quarterly review of all active accounts against current employee records should be established as a standing process. This review serves as a backstop for any failures in the leaver process and will surface accounts that were missed for any reason. The review should be owned by IT, conducted in the first week of each quarter, and results reported to the CISO.

**7. Extend the access review to third-party and contractor accounts**
The leaver process as currently understood covers employees. Contractors, consultants, and third-party users with system access are subject to the same risks — accounts persist after the relationship ends, access is retained beyond its purpose, detection depends on something going wrong. The access review should cover all account types, not just employees.

**8. Near-miss reporting**
This incident was detected because Daniel logged in and the login was flagged. A different former employee, with the same access, who did not log in would never have been detected. The near-miss reporting culture at Veriflow should be examined: are staff encouraged to report when they notice something that should not exist, even if no harm has occurred? Near-miss reporting is the mechanism that makes invisible failures visible before they cause harm.

---

## What Good Looks Like

A well-governed access control process for leavers has three properties that this incident reveals Veriflow currently lacks:

**It is automatic, not dependent on memory.** The trigger for deprovisioning should not be someone remembering to send an email. It should be a formal step in a documented process with a tracked completion requirement. Memory fails under pressure. Process does not — if the process is designed to be followed under pressure.

**It has a backstop.** Even a good process fails sometimes. A quarterly access review is the backstop: it catches what the leaver process misses. Without a backstop, a single process failure creates an open window that persists until something goes wrong.

**It is visible.** Compliance with the leaver process should be measurable. How many leavers were processed last quarter? How many had accounts deprovisioned within one working day? How many were identified in the quarterly review rather than the leaver process? Visibility turns a governance aspiration into a governance reality.

None of this requires significant investment. It requires process design, clear ownership, and the discipline to treat access control as a governance matter rather than an IT administration task.

---

## Closing Note

Daniel's account existed for forty-nine days after he left because the system made that outcome likely. It was detected because he logged in for four minutes to retrieve a personal document. It caused no harm.

The next one may not be so benign. A disgruntled former employee, a credential harvested in a phishing attack, an external actor who purchased leaked credentials — any of these could have used Daniel's account for purposes very different from retrieving a personal document. The access was there. The opportunity was there. Whether harm resulted was a matter of who happened to find it first.

That is not a comfortable way to describe a near-miss. It is an accurate one.

---

*Prepared by the Arken Systems GRC Function. This document is a thinking exercise demonstrating human-centred root cause analysis methodology. Veriflow Payments Ltd is a fictional organisation.*
