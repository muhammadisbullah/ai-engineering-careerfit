# Architecture Decisions & Requirements Traceability — CareerFit AI

## 1. Requirement-to-Architecture Mapping

| Requirement ID | What does the requirement need? | Architecture Component Response |
|---|---|---|
| **FR3 / RAI4** | Answers must include verifiable source references to national frameworks. | Knowledge Access & Retrieval Component (RAG Pipeline) |
| **RAI2 / RAI3** | Out-of-scope queries must be refused and PII must be scrubbed before external execution. | Input/Output Scope & Safety Control (Guardrail Module) |
| **NFR2 / FR1** | Profile skill extraction must accurately map to standardized job frameworks. | Model API / Embedding & Matching Engine |
| **NFR1** | System must deliver responses under latency targets (< 3,000 ms). | Optimized Processing Pipeline & Caching Interface |

---

## 2. Architecture Decision Records (ADR)

### ADR 1: Integration of Retrieval-Augmented Generation (RAG) for Grounded Career Advice
* **Decision:** Include an explicit Knowledge Access component (RAG pipeline) containing MASCO and COL framework documents.
* **Requirement / Constraint:** FR1, FR3, RAI4 (System must provide grounded answers supported by official sources).
* **Alternatives Considered:** 
  1. Relying solely on fine-tuning or zero-shot prompts with base LLMs.
  2. Static keyword lookup database without semantic search capabilities.
* **Selected Option:** RAG pipeline accessing vector-indexed official workforce documents.
* **Trade-off Accepted:** Increases system architecture complexity and retrieval latency, but ensures factual accuracy, eliminates hallucinations, and provides source citations.

### ADR 2: Implementation of Dedicated Input/Output Scope & Safety Guardrails
* **Decision:** Implement a distinct pre-processing and post-processing Scope/Safety Guardrail module.
* **Requirement / Constraint:** RAI2, RAI3 (Refuse out-of-scope queries and prevent PII leakage).
* **Alternatives Considered:** 
  1. Relying exclusively on system prompt instructions to handle safety and privacy.
  2. Complete manual human-in-the-loop review.
* **Selected Option:** Dedicated Scope/Safety Control module executing regex PII scrubbing and intent-filtering checks.
* **Trade-off Accepted:** Adds minimal latency overhead (~100-200 ms), but guarantees compliance with privacy standards and prevents system misuse.

---

## 3. Initial Requirements Traceability Matrix

| Objective | Requirement | Evaluation Criterion | Architecture Element | Later Evidence |
|---|---|---|---|---|
| **O1** | **FR3 / RAI4** | Source Citation & Grounding Fidelity | Knowledge Base & RAG Pipeline | Retrieval precision test results & citation validation log. |
| **O2** | **RAI2 / RAI3** | Out-of-Scope & Privacy Protection | Scope & Safety Guardrail | Safety test suite refusal metrics & payload PII audit. |
| **O3** | **NFR1 / NFR2** | Latency & Matching Accuracy | Model API / Engine & Interface | Latency benchmark report & expert evaluation score sheet. |

---

### Reflection
* **Which architecture decision involved the most important trade-off? Which requirement drove the decision, and what trade-off did you accept?**
  * *Reflection:* The decision to implement **Retrieval-Augmented Generation (ADR 1)** involved the most significant trade-off. Driven by requirements **FR3** and **RAI4**, we accepted additional architectural complexity and retrieval latency processing overhead in exchange for guaranteeing document grounding and source citation integrity.