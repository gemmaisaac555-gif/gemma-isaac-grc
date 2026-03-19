# Internal AI Use Policy
## Arken Systems Ltd

*This is a thinking exercise, not a real organisation.*

---

**Document type:** Internal Policy — Artificial Intelligence Use  
**Document owner:** Head of GRC, Arken Systems Ltd  
**Approved by:** Managing Director  
**Version:** 1.0  
**Date:** March 2025  
**Classification:** Internal — All Staff  
**Review cycle:** Annual, or upon material change to AI landscape, regulatory context, or Arken's service delivery model

---

## 1. Purpose and Scope

### 1.1 Purpose

This policy governs the use of artificial intelligence tools and systems by Arken Systems Ltd staff in the conduct of their professional duties. It establishes the framework within which AI tools may be adopted, the conditions under which they may be used, the oversight requirements that apply to AI-assisted work, and the responsibilities of staff and management when AI tools produce harmful, incorrect, or unexpected outputs.

Arken Systems provides governance, risk, and compliance services to regulated clients. The professional and ethical standards that apply to our client work apply equally to the tools we use to conduct that work. This policy exists because ungoverned AI use in a GRC consultancy is not a minor operational risk — it is a direct contradiction of the governance principles we advise clients to apply to their own systems.

### 1.2 Scope

This policy applies to:
- All Arken Systems employees, contractors, and consultants
- All AI tools used in connection with Arken Systems work, whether accessed via company-provided accounts or personal accounts
- All client-facing and internal work products where AI tools have been used in their preparation

This policy does not govern AI systems deployed by Arken Systems' clients. Client AI governance is addressed through client engagements, not this document.

### 1.3 What This Policy Covers

- Approved and restricted AI tools (Section 3)
- Model approval process for new AI tools (Section 4)
- Permitted and prohibited uses (Section 5)
- Data handling requirements (Section 6)
- Human oversight requirements (Section 7)
- Disclosure obligations (Section 8)
- Incident response (Section 9)
- Staff responsibilities and training (Section 10)

---

## 2. Principles

The following principles underpin this policy and should guide staff judgement in situations not explicitly addressed by the rules below.

**AI tools augment professional judgement — they do not replace it.**
Arken Systems' value to clients derives from the quality of human analysis, contextual understanding, and professional judgement applied to complex governance problems. AI tools may improve the efficiency or breadth of that analysis. They do not substitute for it. Any work product delivered to a client reflects Arken Systems' professional judgement, regardless of what tools were used in its preparation.

**Transparency is not optional.**
Staff must be able to account for how any work product was produced. Where AI tools have contributed materially to a deliverable, that contribution must be disclosed in accordance with Section 8. Concealing AI use from clients or from Arken Systems management is a disciplinary matter.

**Client data is not training data.**
Information shared by clients in the course of an engagement — including strategic plans, risk registers, incident details, personal data, and commercially sensitive material — must not be entered into AI systems that use submitted content for model training. This obligation is absolute and applies regardless of the perceived sensitivity of the specific information.

**Governance applies to us first.**
Arken Systems cannot credibly advise clients on AI governance without applying equivalent governance to our own AI use. The standards in this policy are the standards we hold ourselves to, not a lower threshold maintained for internal convenience.

---

## 3. Approved and Restricted Tools

### 3.1 Approved Tools

The following AI tools are approved for use by Arken Systems staff subject to the conditions and restrictions set out in this policy. Approval means the tool has been assessed against the criteria in Section 4 and found acceptable for the specified use cases.

| Tool | Approved Use Cases | Data Classification Permitted | Conditions |
|---|---|---|---|
| Claude (Anthropic) — Business tier | Research assistance, drafting, analysis, document review | Internal only — no client data | Must use Business tier account; consumer tier prohibited for work use |
| Microsoft Copilot for M365 | Document drafting, summarisation, email assistance | Internal and anonymised client data | Must be accessed via Arken M365 tenant only; data processed within M365 boundary |
| GitHub Copilot | Code assistance for internal tooling development | Internal only | Not for use on client systems or client codebases |

### 3.2 Restricted Tools

The following categories of AI tool are restricted pending assessment or are prohibited entirely.

**Requires approval before use (see Section 4):**
- Any AI tool not listed in Section 3.1
- Any AI tool proposed for use with client data
- Any AI tool used to generate content that will be delivered to a client without human review and revision
- Any AI tool used for automated decision-making in connection with Arken Systems' own operations (e.g. automated screening of job applications, automated risk scoring of suppliers)

**Prohibited:**
- Consumer-tier AI tools (free accounts, personal subscriptions) for any work-related purpose
- AI tools whose terms of service permit use of submitted content for model training, when used with any business information
- AI tools hosted outside the UK or EEA without adequate data transfer safeguards, when used with personal data
- AI image or voice generation tools for the creation of content representing real individuals without their consent
- Any AI tool used to generate content intended to deceive, mislead, or manipulate

---

## 4. Model Approval Process

Any AI tool not listed in Section 3.1 that a staff member wishes to use for work purposes must be assessed before use. This section sets out that process.

### 4.1 Submission

The staff member proposing the tool submits an AI Tool Assessment Request to the Head of GRC. The request must include:

- Tool name, provider, and version
- Proposed use case and business justification
- Data classification of information that would be entered into the tool
- Link to the tool's terms of service and privacy policy
- The staff member's assessment of whether the tool uses submitted content for training

### 4.2 Assessment Criteria

The Head of GRC assesses the tool against the following criteria:

| Criterion | Assessment question |
|---|---|
| Data handling | Does the provider use submitted content for model training? Where is data processed and stored? |
| Terms of service | Are the terms compatible with Arken's confidentiality obligations to clients? |
| Security posture | Does the provider have relevant security certifications (ISO 27001, SOC 2)? |
| Regulatory alignment | Does use of the tool create obligations or risks under UK GDPR, the EU AI Act, or sector-specific regulation? |
| Business necessity | Is there a legitimate business reason for this tool that cannot be met by an already-approved tool? |
| Transparency | Can Arken Systems adequately account for outputs produced using this tool? |

### 4.3 Outcome

The Head of GRC issues one of three outcomes within 10 working days:

- **Approved** — tool added to the approved list in Section 3.1 with specified conditions
- **Approved with conditions** — tool may be used for the specific proposed use case only, subject to named conditions
- **Not approved** — tool may not be used; reasons provided to the requesting staff member

Approvals are reviewed annually as part of the policy review cycle. A tool's approval may be withdrawn if its terms of service, data handling practices, or security posture materially change.

---

## 5. Permitted and Prohibited Uses

### 5.1 Permitted Uses

AI tools on the approved list may be used for the following purposes, subject to the data handling requirements in Section 6:

- Research and horizon scanning — identifying relevant regulatory developments, case law, guidance, and frameworks
- Drafting assistance — producing initial drafts of documents, policies, reports, and correspondence that are subsequently reviewed, revised, and approved by a qualified staff member
- Document review and summarisation — processing large volumes of text to identify relevant passages, themes, or gaps
- Quality assurance — reviewing work products for consistency, completeness, and clarity
- Internal tooling — developing internal GRC tools, templates, and automation where outputs are validated before use
- Training and professional development — using AI tools to explore concepts, test understanding, and prepare for professional examinations

### 5.2 Prohibited Uses

The following uses are prohibited regardless of which tool is used:

- **Unreviewed client deliverables:** Delivering to a client any document, analysis, or recommendation that has been generated by an AI tool without material human review, revision, and professional sign-off
- **Automated risk decisions:** Using AI tools to make or recommend risk acceptance, risk treatment, or compliance decisions without human review and documented rationale
- **Client data input:** Entering client confidential information, personal data, or commercially sensitive material into any AI tool not explicitly approved for that data classification
- **Fabrication:** Using AI tools to generate citations, references, regulatory quotations, or case details that are presented as factual without independent verification
- **Identity misrepresentation:** Using AI tools to impersonate a client organisation, regulator, or individual in any context
- **Circumventing controls:** Using personal AI accounts or unapproved tools to conduct work that would not be permitted under this policy if conducted using approved tools

---

## 6. Data Handling Requirements

### 6.1 Data Classification

For the purposes of this policy, the following classification applies:

| Classification | Definition | Permitted AI tools |
|---|---|---|
| Internal | Arken Systems operational information with no client content | All approved tools |
| Anonymised client | Client information from which all identifying details have been removed or replaced with fictional equivalents | Microsoft Copilot for M365 only |
| Client confidential | Client information as received, including personal data, strategic information, and commercially sensitive material | No AI tools without specific approval |
| Personal data | Any information relating to an identified or identifiable natural person | No AI tools without Data Protection Officer review |

### 6.2 Anonymisation Standard

Where staff wish to use AI tools with client-related content, they must first anonymise the content to the standard below:

- All organisation names replaced with fictional equivalents
- All individual names replaced with generic roles or fictional names
- All specific financial figures replaced with approximate ranges or fictional figures
- All identifying details (regulatory reference numbers, contract values, incident dates) removed or generalised
- All personal data removed entirely — anonymisation does not apply to personal data; personal data must not be entered into AI tools

Staff are responsible for the adequacy of anonymisation. If uncertain whether content has been adequately anonymised, the default position is not to use AI tools with that content.

### 6.3 Retention and Deletion

AI-generated content that forms part of a client deliverable or internal work product is subject to Arken Systems' standard document retention policy. Prompts and conversation histories in AI tools do not constitute business records and should be cleared regularly in accordance with tool-specific guidance.

---

## 7. Human Oversight Requirements

### 7.1 General Requirement

All AI-assisted work products must be reviewed by a qualified staff member before use, delivery, or reliance. The reviewing staff member is professionally responsible for the content of the work product regardless of how it was produced.

### 7.2 Decisions That Cannot Be Delegated to AI

The following decisions must be made by a qualified human professional and may not be made or recommended solely on the basis of AI output:

- Risk acceptance decisions on behalf of Arken Systems or on behalf of a client
- Compliance sign-off — confirmation that a client's processes, controls, or documentation meet a regulatory standard
- Legal interpretation — any statement about the legal meaning or effect of a regulatory provision
- Incident escalation decisions — whether a security or compliance incident meets a reporting threshold
- Hiring, performance, and disciplinary decisions affecting Arken Systems staff

### 7.3 Verification of AI-Generated Factual Claims

AI tools produce plausible-sounding content that may be factually incorrect. Staff must independently verify:

- Regulatory citations — article numbers, section references, and quoted text must be checked against primary sources
- Case references — enforcement actions, ICO decisions, and court judgments cited in work products must be verified
- Statistical claims — figures, percentages, and data points generated by AI tools must be sourced independently
- Tool and product descriptions — specifications, pricing, and feature descriptions for third-party tools must be verified with the provider

Failure to verify AI-generated factual claims before including them in client deliverables is a quality failure and may constitute professional misconduct depending on the nature and impact of the error.

---

## 8. Disclosure Obligations

### 8.1 Client Disclosure

Arken Systems will disclose to clients, on request, whether AI tools were used in the preparation of a specific deliverable and in what capacity. Arken Systems will not misrepresent the nature of its work product preparation to clients.

Where a client's engagement terms or instructions explicitly prohibit AI use, those instructions take precedence over this policy. Staff must check engagement terms before using AI tools on any client matter.

### 8.2 Internal Disclosure

Staff must record AI tool use in work product metadata where the tool has contributed materially to the content of a deliverable. A material contribution means the AI tool generated text, analysis, or structure that appears in the final deliverable, even if substantially revised. Using an AI tool only for research or background reading that does not appear in the deliverable does not require recording.

### 8.3 What Disclosure Does Not Mean

Disclosure of AI use does not imply reduced professional responsibility for the work product. A deliverable that discloses AI assistance is held to exactly the same professional standard as one produced entirely without AI tools. Disclosure is a transparency obligation, not a disclaimer.

---

## 9. Incident Response

### 9.1 What Constitutes an AI-Related Incident

The following events constitute AI-related incidents for the purposes of this policy:

- **Data incident:** Client confidential information or personal data entered into an AI tool without authorisation
- **Quality incident:** AI-generated factual error included in a client deliverable and delivered without correction
- **Disclosure incident:** AI use concealed from a client in breach of Section 8 or in breach of engagement terms
- **Tool incident:** An approved AI tool behaves unexpectedly, produces harmful output, or its terms of service materially change in a way that affects compliance with this policy
- **Compliance incident:** Use of a prohibited tool or prohibited use case discovered during quality review or audit

### 9.2 Reporting

Any AI-related incident must be reported to the Head of GRC within 24 hours of discovery. Staff who discover an incident — including their own — are expected to report immediately. Self-reporting is treated as a mitigating factor. Concealment is treated as an aggravating factor.

### 9.3 Response Process

Upon receiving an incident report, the Head of GRC will:

1. Assess whether the incident constitutes a personal data breach requiring notification to the ICO under UK GDPR Article 33
2. Assess whether the incident requires disclosure to the affected client
3. Determine whether the affected work product requires correction, recall, or re-delivery
4. Identify the root cause and determine whether policy, training, or technical controls require updating
5. Document the incident and response in Arken Systems' incident register

### 9.4 Client Notification

Where an AI-related incident has affected a client deliverable or involved client data, the client will be notified promptly and provided with a clear account of what occurred, what was affected, and what Arken Systems has done in response. Client notification decisions are made by the Managing Director in consultation with the Head of GRC.

---

## 10. Staff Responsibilities and Training

### 10.1 All Staff

All staff are responsible for:
- Reading and understanding this policy before using any AI tool for work purposes
- Using only approved tools within approved use cases
- Applying the data handling requirements in Section 6 to all AI-assisted work
- Reviewing and taking professional responsibility for all AI-assisted work products
- Reporting AI-related incidents in accordance with Section 9
- Completing AI literacy training within 30 days of joining Arken Systems and annually thereafter

### 10.2 Head of GRC

The Head of GRC is responsible for:
- Maintaining the approved tools list and conducting model approval assessments
- Reviewing this policy annually and updating it to reflect changes in the AI landscape, regulatory environment, and Arken Systems' operational context
- Managing AI-related incidents in accordance with Section 9
- Maintaining the AI incident register
- Reporting AI governance matters to the Managing Director quarterly

### 10.3 Managing Director

The Managing Director is responsible for:
- Approving this policy and any material amendments
- Making client notification decisions in the event of an AI-related incident
- Ensuring adequate resources are allocated to AI governance

### 10.4 Training

All staff must complete AI literacy training covering:
- The capabilities and limitations of approved AI tools
- Data handling requirements under this policy
- Recognition of AI-generated errors, hallucinations, and plausible-but-incorrect outputs
- The professional responsibility framework that applies to AI-assisted work
- How to report an AI-related incident

Training records are maintained by the Head of GRC. Completion of training is a condition of approval to use AI tools for work purposes.

---

## 11. Policy Compliance and Enforcement

Compliance with this policy is mandatory. Breaches will be assessed according to their nature, severity, and whether they were self-reported.

| Breach type | Likely response |
|---|---|
| Minor breach, self-reported, no client impact | Documented conversation; additional training if appropriate |
| Moderate breach or repeated minor breach | Formal written warning; suspension of AI tool access pending review |
| Serious breach (client data incident, concealment, unreviewed client deliverable) | Formal disciplinary process; potential suspension; client notification |
| Gross misconduct (deliberate concealment, fabrication in client deliverables) | Disciplinary process up to and including dismissal; potential professional body referral |

Nothing in this policy limits Arken Systems' rights under employment law or prevents Arken Systems from taking appropriate action in response to conduct that falls outside the specific categories above.

---

## 12. Review and Governance

This policy will be reviewed:
- Annually, in Q1 of each year
- Upon material change to the approved tools list
- Upon any significant change to the UK or EU regulatory framework for AI
- Following any AI-related incident that reveals a gap in the policy

Material amendments require Managing Director approval. Minor amendments — including updates to the approved tools list following a model approval assessment — may be made by the Head of GRC and notified to all staff.

**Version history:**

| Version | Date | Summary of changes |
|---|---|---|
| 1.0 | March 2025 | Initial policy — covers approved tools, model approval, data handling, human oversight, disclosure, and incident response |

---

*This document is a thinking exercise demonstrating internal AI governance policy design. Arken Systems Ltd is a fictional organisation.*
