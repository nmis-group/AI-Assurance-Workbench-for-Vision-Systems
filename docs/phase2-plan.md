# Phase 2 Plan

Phase 1 proved, on one real production model, that testing against trustworthiness pillars produces genuinely useful evidence rather than an untested claim. 
Phase 2 takes that proof of concept and turns it into a reusable schema: a manifest format, an adapter layer, and a canonical detection format, designed so the same governance-to-assurance evidence trail can be generated for any model submitted to it, regardless of architecture, and mapped directly to the standards that actually carry legal or certification weight (the EU AI Act, NIST AI RMF, and ISO/IEC SC42), rather than a simplified pillar set. This document covers the standards landscape behind that decision, the resulting dimension structure, and the technical build plan.

## 1. The Standards Landscape

Multiple trustworthy AI frameworks exist because different bodies converged on the same concerns from different directions: ethics research, US risk management practice, and international standards work. None specify which tool to run, they stay abstract because the underlying concerns (opacity, brittleness, bias, drift) predate any specific testing tool. The pillars in each framework are the translation layer between that abstract language and concrete tests.

### 1.1 Four Trustworthy AI Frameworks
These four are frameworks for defining what trustworthy AI means, not governance frameworks (an organisation's own policies) and not assurance methods (test evidence). They're the vocabulary layer both of those draw from.

| Framework | Pillars | Used By |
|---|---|---|
| Australia's AI Ethics Principles| 7 | condensed to 5 and used in Phase 1 of this project |
| EU Ethics Guidelines for Trustworthy AI | 7 | Informs EU AI Act compliance work |
| NIST AI RMF | 7 (sometimes cited as 8, see note below) | US-aligned organisations |
| ISO/IEC TR 24028 | commonly summarised as 7 technical/operational properties, though the report covers more | Standards-led assessments |

### 1.2 The Four Frameworks, Pillar by Pillar

![The Four Frameworks, Pillar by Pillar](assets/pillars-by-framework.svg)

The report behind ISO/IEC TR 24028 also discusses accountability, transparency, explainability, and fairness elsewhere, these overlap with what the other frameworks already cover, which is why they're not repeated in this subset.

Phase 1 worked from a 5-pillar version of Australia's AI Ethics Principles. Phase 2 goes back to the EU, NIST, and ISO structures directly, rather than building on that condensed version, for the reasons below.

### 1.3 How the Pillars Line Up

| Theme | EU Ethics Guidelines | NIST AI RMF | ISO/IEC TR 24028 (subset) | Australia's AI Ethics Principles |
|---|---|---|---|---|
| Accountability | Accountability | Accountable and transparent | not in this subset | Accountability |
| Transparency & Explainability | Transparency | Accountable and transparent; Explainable and interpretable | not in this subset | Transparency and explainability |
| Fairness | Diversity, non-discrimination and fairness | Fair, with harmful bias managed | not in this subset | Fairness |
| Privacy | Privacy and data governance | Privacy-enhanced | Privacy | Privacy protection and security |
| Robustness / Reliability / Resilience | Technical robustness and safety | Valid and reliable | Reliability; Resilience | Reliability and safety |
| Safety | folded into technical robustness and safety | Safe | Safety | folded into reliability and safety |
| Security | folded into technical robustness and safety | Secure and resilient | Security | folded into privacy protection and security |
| Human agency / human-centred values | Human agency and oversight | not listed | not in this subset | Human-centred values |
| Societal & environmental wellbeing | Societal and environmental wellbeing | not listed | not in this subset | Human, societal and environmental wellbeing |
| Contestability | not listed | not listed | not in this subset | Contestability |
| Availability / Accuracy | not listed | not listed | Availability; Accuracy | not listed |

### 1.4 Where These Come From

| Body / Regulation | What it is | Why it matters here |
|---|---|---|
| ISO/IEC SC42 | Main international AI standards body, 45+ published standards | Source of ISO 24028, 24027, 24029, 5259, 42001, 5469, and TS 8200 |
| NIST AI RMF | US framework, voluntary, four functions: Govern, Map, Measure, Manage | Widely adopted structure for organising assurance evidence |
| EU AI Act | Legal regulation, not guidance | Bolt detection is plausibly high-risk, either an Annex III use case or a product-embedded safety component |
| IEC 61508 | Traditional functional safety standard for industrial systems | Predates AI but still applies to the manufacturing context |
| IEEE 7000 | Process standard | Embeds ethical concerns into system design |

### 1.5 The Eight Standards to Know Deeply

| # | Standard | One line |
|---|---|---|
| 1 | ISO 24028 | What trustworthiness means, the basis of the five pillars |
| 2 | ISO 24027 | What bias is and how to detect it, the Fairness pillar |
| 3 | ISO 24029 | How to test robustness, the Security/Robustness pillar |
| 4 | ISO 5259 series | Data quality requirements for AI, feeds the data assurance track |
| 5 | ISO 42001 | AI management system, the governance layer around everything |
| 6 | ISO 5469 | Functional safety plus AI, critical for manufacturing context |
| 7 | ISO/TS 8200 | Human oversight of AI, the gap in the current framework |
| 8 | NIST AI RMF | The US risk management framework, four functions: Govern, Map, Measure, Manage |
