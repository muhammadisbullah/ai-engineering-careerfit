# Section 0 — Project Framing & Application Scope Checkpoint

* **Problem Evidence:** Official statistics indicate persistent skill-related underemployment among tertiary graduates due to structural mismatches between educational outputs and industry requirements (DOSM Graduates Statistics Report). Furthermore, core job skills are evolving rapidly across sectors, creating a widening gap between academic preparation and market expectations (World Economic Forum Future of Jobs Report).
* **Existing Approaches:** 
  1. *Commercial Job Portals (LinkedIn, JobStreet):* Offer keyword-based job matching but lack structured skills gap analysis grounded in national occupational standards.
  2. *General LLM Chatbots (ChatGPT, Claude):* Provide flexible resume assistance but are highly prone to domain hallucinations and ungrounded career advice.
  3. *University Career Advisory Centers:* Offer high-quality guidance but are constrained by human bandwidth, staff availability, and operational hours.
* **Project / Engineering Gap:** Current AI solutions lack a transparent, document-grounded mechanism that maps individual academic profiles directly to standardized national workforce frameworks (e.g., MASCO / TalentCorp COL) to provide verifiable, hallucination-free career alignment and upskilling guidance.
* **Objective O1:** To design a document-grounded AI alignment assistant based on official workforce and occupational frameworks.
* **Objective O2:** To develop a retrieval pipeline with domain-specific guardrails to ensure grounded recommendations.
* **Objective O3:** To evaluate the system on retrieval precision, groundedness, latency, and fairness.
* **Intended Users:** Fresh university graduates seeking entry-level role matching and early-career job seekers/career switchers looking for targeted upskilling pathways.
* **Supported Tasks:** Resume and skill profile extraction, job role matching against official standards, explicit skill gap identification, and verified upskilling recommendations.
* **Information / Knowledge Domain:** Official Malaysian national workforce frameworks, specifically the Malaysia Standard Classification of Occupations (MASCO) and the TalentCorp Critical Occupations List (COL).
* **Operating Context:** Web-based interactive assistant deployed as a supportive advisory tool for individual job seekers.
* **Important Constraints:** Reliance on open-access national framework documents, limited computational budget for real-time inference, and strict data privacy requirements regarding user resume data.
* **Explicit Out-of-Scope Tasks:** The system shall NOT perform automated hiring decisions, issue binding professional certifications, or offer psychological, legal, or financial counseling.
* **Evaluation Focus:** Determining whether document grounding (RAG) significantly reduces hallucinated job recommendations and improves skill gap precision compared to ungrounded LLM baselines while maintaining acceptable latency.

---

# Section 1 — Functional Requirements
**Version:** 1.0

| # | Requirement — The system SHALL | Scope Boundary — SHALL NOT (where relevant) |
|---|---|---|
| **FR1** | Match user skill profiles and academic backgrounds against official occupational descriptions in MASCO and TalentCorp COL frameworks. | Invent occupational codes or job qualifications not supported by the underlying source documents. |
| **FR2** | Identify explicit technical and soft skill gaps required for a targeted job role based on standard framework benchmarks. | Guarantee employment outcome or make automated hiring/rejection decisions on behalf of employers. |
| **FR3** | Provide direct source citations (document title, code, section) for every career requirement or skill gap assertion. | Present unsupported career advice or unverified skill requirements as factual standard data. |
| **FR4** | Decline out-of-scope queries (e.g., mental health, legal, academic assignment cheating) and provide standard administrative redirects. | Provide advice on non-career, medical, financial, or legal matters. |
| **FR5** | Present career match summaries and recommended upskilling pathways in clear, structured Markdown format appropriate for early-career users. | — |

---

# Section 2 — Non-Functional Requirements

| # | Quality Attribute | Requirement | Measurement Method | Metric | Threshold |
|---|---|---|---|---|---|
| **NFR1** | Performance | The system shall keep interactive query responses within acceptable user waiting limits. | Measure end-to-end latency across a standardized test workload of 50 queries. | p90 latency | < 3,000 ms |
| **NFR2** | Correctness | System recommendations and skill mappings shall accurately align with official framework definitions. | Score a curated test dataset of 30 candidate profiles using an expert-validated rubric. | Correct response rate (%) | ≥ 85% |
| **NFR3** | Cost | Inference and embedding retrieval operations shall remain within project budget boundaries. | Track model API token consumption over the full evaluation benchmark. | Cost per 100 queries | < US$0.40 |
| **NFR4** | Maintainability | Updates to source framework documents (e.g., annual COL updates) shall be indexed without altering core pipeline code. | Run a controlled document re-indexing procedure on updated source files. | Index update duration | < 15 minutes |

---

# Section 3 — Responsible AI Requirements

| # | Responsible AI Risk | Requirement | Measurement Method | Metric | Threshold |
|---|---|---|---|---|---|
| **RAI1** | Fairness | System recommendation accuracy shall remain consistent regardless of candidate institutional background markers. | Evaluate a stratified test set across varied academic background profiles. | Accuracy gap between candidate groups | ≤ 8 percentage points |
| **RAI2** | Safety / Scope | The system shall refuse out-of-scope or harmful queries and provide safe redirection. | Run a safety evaluation benchmark containing at least 25 out-of-scope prompts. | Refusal-and-redirect success rate | ≥ 95% |
| **RAI3** | Privacy | The system shall filter and redact Personally Identifiable Information (PII) before sending payloads to external LLM APIs. | Inspect outgoing API payloads for PII leaks (names, phone numbers, identity numbers). | Number of detected PII transmissions | 0 |
| **RAI4** | Transparency / Grounding | The system shall provide verifiable source references for grounded statements and explicitly state when evidence is insufficient. | Evaluate responses for citation presence and verify citation-to-source fidelity. | Citation presence rate; source-match rate | 100% citation presence; ≥90% source match |

---

### Reflection
* **Which Responsible AI requirement in your project will be the most difficult to measure or enforce technically? Why?**
  * *Reflection:* **RAI1 (Fairness)** will be the most technically challenging to enforce and measure. Academic and skill descriptions vary widely across universities, TVET institutions, and non-traditional learning paths. Standard embedding models may implicitly bias similarity scores toward standard university terminology. Ensuring equal retrieval precision across non-standardized resume phrasing without extensive fine-tuning requires continuous schema alignment and rigorous benchmark stratification.