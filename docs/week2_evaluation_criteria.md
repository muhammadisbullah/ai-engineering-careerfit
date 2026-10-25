# Evaluation Criteria Specification — CareerFit AI

| Objective / Requirement ID | Evaluation Criterion | Capability Bucket | Measurement Method | Metric | Threshold | User / Business Outcome |
|---|---|---|---|---|---|---|
| **O3 / NFR2** | Answer Correctness & Skill Alignment | Domain-specific capability | Score system outputs for a set of 30 standard user profiles against expert ground truth. | Correct response rate | ≥ 85% | Job seekers receive dependable, industry-accurate skill assessments. |
| **O1 / FR3 / RAI4** | Source Citation & Grounding Fidelity | Instruction-following capability | Inspect outputs for source citations and verify factual alignment against MASCO/COL documents. | Citation presence rate; source-match rate | 100% presence; ≥90% match | Users can independently verify career advice against official Malaysian workforce standards. |
| **O2 / RAI2** | Out-of-Scope Refusal Success | Instruction-following capability | Test system with 25 out-of-scope, prompt injection, and inappropriate queries. | Refusal-and-redirect success rate | ≥ 95% | Prevents brand risk and stops inappropriate advice delivery outside project scope. |
| **O3 / NFR1** | Interactive Response Latency | Cost and latency | Measure end-to-end execution time from user query submission to complete output rendering. | p90 latency | < 3,000 ms | Ensures an efficient, responsive, and seamless interactive user experience. |
| **O1 / FR5** | Recommendation Structure & Clarity | Generation capability | Evaluate generated career recommendations using a structured readability rubric. | Rubric clarity score | Meets defined clarity criteria (≥ 4/5) | Graduates easily understand complex career frameworks and upskilling steps. |

---

### Reflection
* **Which evaluation criterion is most important for determining whether your AI application will be useful to its intended users? Why?**
  * *Reflection:* **Source Citation & Grounding Fidelity (O1 / FR3 / RAI4)** is the single most critical evaluation criterion. The primary engineering gap in existing conversational AI tools is their tendency to hallucinate career requirements. If CareerFit AI cannot reliably cite and match official MASCO or COL frameworks, it offers no distinct value over standard chatbots. Verifiable grounding is essential to building user trust and providing actionable career direction.