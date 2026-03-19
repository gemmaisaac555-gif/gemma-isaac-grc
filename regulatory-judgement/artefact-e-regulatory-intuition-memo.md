# Artefact E — Regulatory Intuition Memo
## EU AI Act: What Financial Services Deployers Should Be Doing Now

*This is a thinking exercise, not a real organisation.*

---

**Document type:** Regulatory Intuition Memo  
**Prepared by:** Arken Systems GRC Function  
**Intended audience:** Compliance and Risk functions at UK and EU financial services firms deploying or considering AI systems  
**Date:** March 2025  
**Classification:** Internal Guidance — Not Legal Advice  
**Related documents:** AI Risk Register — Credit Scoring Model Deployment (March 2025); Fundamental Rights Impact Assessment — AI Credit Scoring System (March 2025)

---

## What This Document Is

A regulatory intuition memo is not a compliance checklist. It is an attempt to read a regulatory situation honestly — to say what the framework actually requires, where it is ambiguous, where the direction of travel is clear even if the destination is not yet fixed, and what a prudent organisation should be doing now rather than waiting for certainty that may never fully arrive.

The EU AI Act is a framework in early implementation. The text is final. Much of the guidance is not. Organisations that wait for complete clarity before acting will find themselves behind organisations that read the direction of travel and moved early. This memo is written for the second kind of organisation.

It is not legal advice. It is professional judgement about regulatory risk and governance priorities, offered in the context of financial services firms that are deploying or considering deploying AI systems.

---

## The Timeline, Honestly Read

The EU AI Act entered into force on 1 August 2024. Its obligations apply in phases. The headline dates are well-documented. What is less often discussed is what those dates actually mean in practice for a financial services firm that is deploying AI systems today.

**February 2025 — Prohibited practices.**
Obligations relating to prohibited AI practices applied from 2 February 2025. These include AI systems that manipulate individuals through subliminal techniques, exploit vulnerabilities of specific groups, and certain uses of biometric categorisation and emotion recognition. For most financial services firms, these prohibitions do not directly affect current operations. But they set the tone: the Act draws hard lines, and firms should know where those lines are before their product development teams find them by accident.

**August 2025 — GPAI model obligations.**
Obligations for providers of general-purpose AI models apply from 2 August 2025. This is primarily relevant to AI developers, not deployers. However, financial services firms that are fine-tuning foundation models or integrating GPAI capabilities into their own systems should understand what their providers are now required to do — and whether those requirements are reflected in their contractual arrangements.

**August 2026 — High-risk AI system obligations.**
The obligations that matter most to financial services deployers — the full suite of requirements for high-risk AI systems under Annex III — apply from 2 August 2026. Credit scoring, insurance risk assessment, employment screening, and certain customer-facing decision systems all fall within the high-risk classification for financial services.

Seventeen months. That sounds like a long time. It is not a long time if you are starting from zero.

**August 2027 — Legacy systems.**
High-risk AI systems that were already in use before August 2026 have an additional twelve months to comply — until August 2027. This transition period applies only to systems that are not substantially modified after August 2026. Firms that modify existing systems after that date lose the transition period and must comply immediately.

The legacy system transition period is a trap for the unprepared. It looks like breathing room. In practice, it creates a governance question that must be answered before August 2026: which of your AI systems are in scope, what counts as a substantial modification, and do you want to run legacy systems under the transition period or bring them into compliance proactively?

---

## What Financial Services Firms Are Getting Wrong

### 1. Treating August 2026 as the start date rather than the deadline

The most common mistake is reading the compliance date as the date to begin preparing. It is not. The compliance date is the date by which preparation must be complete.

For a high-risk AI system, full compliance requires: a risk management system, data governance procedures, technical documentation, a fundamental rights impact assessment, human oversight measures, accuracy and robustness testing, a post-market monitoring plan, and — for systems deployed in the EU — registration in the EU AI Act database.

None of these can be completed in a week. Several require ongoing processes that need to be designed, documented, tested, and embedded in operational practice before the compliance date. A firm that begins this work in June 2026 will not be compliant by August 2026.

The practical implication: if you are deploying a high-risk AI system and you have not started your compliance programme, you are already late.

### 2. Assuming the FCA will interpret the Act for them

UK firms face a specific complexity: the EU AI Act does not directly apply in the UK following Brexit. The UK government has taken a pro-innovation, sector-regulator approach — meaning that the FCA, PRA, and other regulators are responsible for implementing AI governance expectations within their sectors, rather than a single cross-sector Act.

The practical effect is that UK financial services firms face FCA expectations that are evolving in parallel with, and influenced by, the EU AI Act — without the clarity of a single legislative framework to comply with.

The FCA has published its AI update and confirmed it is monitoring EU AI Act implementation. The direction of travel is clear: the FCA will expect governance standards for high-risk AI systems that are broadly consistent with EU AI Act principles, even if the specific obligations differ. Firms that comply with EU AI Act requirements for their UK operations are unlikely to find themselves behind FCA expectations. Firms that ignore both are taking a regulatory risk on two fronts.

For UK firms with EU operations or EU customers, the EU AI Act applies directly. The question of whether a UK firm is in scope is not always straightforward and warrants legal advice specific to the firm's operating model.

### 3. Treating compliance as a legal function rather than a governance function

EU AI Act compliance for high-risk AI systems is not a legal sign-off exercise. It requires substantive input from data science, risk, operations, HR, and the business functions that own the AI systems. A legal team cannot conduct a fundamental rights impact assessment alone. A compliance team cannot design a human oversight function alone. A risk team cannot validate model accuracy alone.

Firms that assign EU AI Act compliance to their legal or compliance function without cross-functional ownership will produce documentation that satisfies form but not substance. The Act is designed to produce genuine governance of AI systems — not paper compliance. Regulators are developing audit and enforcement capabilities that will test substance, not just documentation.

### 4. Underestimating the deployer obligations

The EU AI Act distinguishes between providers — organisations that develop or place AI systems on the market — and deployers — organisations that use AI systems in a professional context. Many financial services firms assume that because they did not build the AI system they are using, the compliance burden sits with the provider.

This is incorrect. Deployers of high-risk AI systems have direct obligations under the Act that cannot be contracted away to the provider. These include:

- Implementing appropriate human oversight measures (Article 26)
- Ensuring the system is used in accordance with the provider's instructions
- Monitoring system performance and reporting serious incidents to the provider
- Conducting a fundamental rights impact assessment where required (Article 27)
- Registering the system in the EU AI Act database (Article 49, from August 2026)
- Ensuring staff who operate the system receive adequate AI literacy training (Article 26(6))

A financial services firm that procures an AI credit scoring system from a third-party provider is a deployer. The obligations above apply to it. The fact that the provider carries separate obligations does not reduce the deployer's obligations — it means both parties carry obligations, not that the obligations are shared between them.

### 5. Confusing the transition period with compliance discretion

The transition period for legacy systems — August 2027 for systems in use before August 2026 — is a phased implementation measure, not a signal that pre-existing systems are lower priority. Firms that rely on the transition period should understand what it actually provides: additional time to achieve compliance with the same standards. It does not reduce the standards that apply or create a permanently lighter regime for legacy systems.

More importantly, the transition period creates a governance question that must be answered now: which systems will be managed under the transition period, and which will be brought into compliance before August 2026? This is a strategic decision that requires an inventory of AI systems in use, an assessment of which are high-risk, and a resourcing plan for compliance. Firms that have not made this decision are implicitly choosing to manage all systems under the transition period — which means running out-of-compliance systems for an additional year and then scrambling to comply by August 2027.

---

## What Prudent Organisations Are Doing Now

The following represents Arken Systems' assessment of what a well-governed financial services firm deploying high-risk AI systems should be doing in March 2025, seventeen months before the August 2026 compliance deadline.

### Now — Foundation work

**AI system inventory.**
Every AI system in use or in development should be identified, documented, and assessed against the EU AI Act's risk classification framework. This is not a one-time exercise — it needs to be an ongoing process, because new systems are deployed and existing systems are modified continuously. The inventory is the foundation for everything else: you cannot govern what you cannot see.

**Deployer obligation mapping.**
For each high-risk AI system identified, the deployer obligations under Articles 26, 27, and 49 should be mapped against current practice. Gaps should be documented and prioritised. This mapping should be done by people who understand both the regulatory text and the operational reality of how the systems are used — not by legal counsel alone.

**Provider contract review.**
Existing contracts with AI system providers should be reviewed against EU AI Act requirements. Key questions: does the provider's documentation meet Article 13 transparency requirements? Are incident reporting obligations consistent with Article 72? Does the contract address what happens if the provider needs to make changes to the system to achieve compliance? Contracts that were signed before the Act entered into force will frequently not address these requirements.

### By Q3 2025 — Governance infrastructure

**Human oversight framework.**
Article 26 requires deployers to implement appropriate human oversight measures. What this means in practice depends on the system, its use case, and the decisions it informs. A credit scoring system used for fully automated lending decisions requires more robust oversight than one used to support a human underwriter. The oversight framework should be designed, documented, and operationalised — not described in a policy that bears no relationship to how the system is actually used.

**FRIA process.**
Article 27 requires deployers in financial services to conduct a fundamental rights impact assessment before deploying a high-risk AI system. For systems already in use, this assessment should be conducted retrospectively — acknowledging the gap, assessing current impacts, and establishing a baseline for ongoing monitoring. A retrospective FRIA completed in good faith is materially better than no FRIA and demonstrates regulatory good faith.

**AI literacy training.**
Article 26(6) requires deployers to ensure staff operating high-risk AI systems have sufficient AI literacy. This is frequently overlooked because it sounds like a training administration task rather than a governance requirement. It is both. Firms should identify which staff interact with high-risk AI systems, what AI literacy means for each role, and how training will be delivered and evidenced.

### By Q1 2026 — Compliance readiness

**Post-market monitoring plan.**
Article 72 requires deployers to monitor the performance of high-risk AI systems and report serious incidents to providers. A post-market monitoring plan should specify: what metrics are monitored, at what frequency, by whom, what constitutes a reportable incident, and how findings feed back into system governance. This plan should be operational — not a document that describes monitoring that does not actually happen.

**Registration preparation.**
High-risk AI systems must be registered in the EU AI Act database from August 2026. The registration process requires detailed technical and governance information about the system. Firms should begin assembling this information now rather than treating registration as an August 2026 task.

**Compliance testing.**
Before the August 2026 deadline, firms should conduct internal compliance testing against the full suite of deployer obligations. This is not a legal review — it is an operational assessment of whether the governance measures in place are substantive and functional. Testing should include scenarios: what actually happens when a serious incident is detected? Does the human oversight process work as documented? Can the firm produce the documentation required by Article 13 within a reasonable timeframe?

---

## The Regulatory Intuition

Beneath the implementation timeline and the compliance checklist, there is a regulatory philosophy in the EU AI Act that is worth understanding directly.

The Act is designed to make the governance of AI systems legible — to regulators, to affected individuals, and to the organisations deploying them. The documentation requirements, the FRIA obligations, the transparency provisions, the human oversight requirements — these are not bureaucratic friction. They are mechanisms for making the behaviour of AI systems visible and accountable in a way that allows informed oversight.

Financial services regulators have been thinking about algorithmic accountability for longer than most. The FCA's work on algorithmic trading, the PRA's model risk management expectations, the ICO's guidance on automated decision-making — all of these predate the EU AI Act and reflect a consistent regulatory direction: decisions that significantly affect people should be explainable, contestable, and subject to human accountability.

The EU AI Act formalises and extends this direction. Firms that have been governing their AI systems well — with genuine human oversight, meaningful impact assessment, honest monitoring — will find that compliance is largely a documentation exercise. Firms that have been treating AI governance as a compliance formality will find that the Act requires something more substantive than they have built.

The intuition, plainly stated: the EU AI Act is not primarily about the documentation. It is about whether the governance is real. Regulators will, over time, develop the capability to tell the difference. Firms that build genuine governance now will be in a better position than firms that produce compliant documentation for systems that are not genuinely governed.

The firms most at risk are not those that are unaware of the Act. They are those that are aware of it, are producing documentation to demonstrate compliance, and have not asked themselves whether the documentation reflects reality.

---

## Implications for Veriflow Payments

The Arken Systems GRC team has been engaged with Veriflow's AI governance programme since January 2025. The following reflects our current assessment of Veriflow's position against the framework above.

**Inventory:** Veriflow has identified its primary high-risk AI system — the ClearScore AI credit scoring model. It is not known whether a complete AI system inventory has been conducted across all business functions. This should be confirmed before Q3 2025.

**Deployer obligation mapping:** Partially complete. The AI risk register (March 2025) maps key risks against regulatory obligations. A full deployer obligation gap assessment has been initiated but not completed.

**FRIA:** Completed retrospectively (March 2025). Gaps identified include absent pre-deployment consultation and incomplete human oversight coverage for lower-value decisions. Remediation actions are documented.

**Human oversight:** Partial. Review threshold of £10,000 covers a minority of decisions. Requires revision before August 2026.

**AI literacy training:** Not yet conducted. Required under Article 26(6). Should be scheduled for Q2 2025.

**Post-market monitoring:** Monitoring exists for model performance metrics. A formal post-market monitoring plan meeting Article 72 requirements has not been documented.

**Registration preparation:** Not yet started. Should begin Q3 2025.

**Overall assessment:** Veriflow is ahead of many firms of comparable size in having identified its high-risk AI systems and initiated governance work. The gap between current state and August 2026 compliance is closeable on the current trajectory if open actions are completed on schedule. The primary risk is not regulatory complexity — it is the same risk identified throughout this portfolio: the gap between identifying what needs to be done and ensuring it gets done.

---

*Prepared by the Arken Systems GRC Function. This document is a thinking exercise demonstrating regulatory analysis and professional judgement under uncertainty. All organisations named are fictional. This document does not constitute legal advice.*
