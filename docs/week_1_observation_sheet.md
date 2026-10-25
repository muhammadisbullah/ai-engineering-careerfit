# Week 1 Observation Sheet: AI System Observation Report

## System Name
CareerFit AI (Observed Baseline: Conversational Job & Career AI Assistant)

## Group Members
* [Insert Your Name / Group Members' Names]

## 1. What problem does this system solve? Who benefits?
* **Problem:** Fresh graduates and job seekers face significant structural challenges in finding employment aligned with their qualifications, leading to skill-related underemployment. Concurrently, recruiters and employers spend excessive time screening generic or misaligned applications.
* **Beneficiaries:** Fresh university graduates, early-career job seekers, career switchers, and HR/recruitment teams seeking targeted candidate-job alignment.

## 2. Which AI stack layer is most visible to users?
* **Layer:** Application Layer
* **Explanation:** End users interact directly with the front-end chat interface or web application to upload resumes, input skills, or query career paths. The underlying retrieval pipelines, embedding models, and foundation LLMs operate invisibly in the background.

## 3. Quality dimensions — at least 3, with measurement method
* **Dimension 1: Groundedness / Factuality**
  * **Measure:** Percentage of generated job qualification statements and skill gap assessments that directly cite and match official occupational frameworks (e.g., MASCO or TalentCorp COL) without unverified claims.
* **Dimension 2: Latency**
  * **Measure:** Total time (in seconds) measured from the moment a user submits a query or resume profile to the point the complete response is generated and rendered.
* **Dimension 3: Fairness & Bias**
  * **Measure:** Evaluation of recommendation consistency when analyzing identical skill sets originating from candidates with different academic institutions or demographic background markers.

## 4. What did the system do WELL? Give a specific example.
* **Example & Observation:** When provided with a targeted list of technical skills (e.g., "Python, SQL, Data Visualization, Git"), the system rapidly generated relevant job role suggestions (e.g., Junior Data Analyst, Business Intelligence Assistant) with clear duty descriptions. Response delivery was prompt (under 3 seconds) and neatly structured into bullet points.

## 5. What did it do POORLY? Give a specific example.
* **Example & Observation:** When prompted to evaluate a candidate's course syllabus against real-world industry demand, the system provided generic career advice rather than cross-referencing official occupational standards. It failed to identify specific technical skill gaps and exhibited hallucination by assuming qualifications not mentioned in the query.

## 6. Responsible AI risks — at least 2. Who is harmed and how?
* **Risk 1 — Algorithmic Bias in Qualification Ranking:**
  * *Harmed Party:* Graduates from non-traditional, TVET, or regional higher education institutions.
  * *Harm:* The embedding model or LLM ranking algorithm may penalize candidates based on institution naming conventions or non-standard resume phrasing, leading to systematic filtering bias.
* **Risk 2 — Exposure of Personally Identifiable Information (PII):**
  * *Harmed Party:* Individual job seekers uploading resumes.
  * *Harm:* Resumes contain sensitive PII (full name, email, phone number, address). If logs are unencrypted or user data is improperly retained for training, candidate privacy is severely compromised.

## 7. If you could fix ONE thing, what and why?
* **Fix:** Implement a strict Document Grounding & Retrieval-Augmented Generation (RAG) Guardrail that restricts career recommendations exclusively to verified, official occupational classification frameworks (e.g., MASCO / TalentCorp COL).
* **Why:** This eliminates hallucinated career advice and ensures that fresh graduates receive accurate, industry-validated skill gap insights and actionable upskilling pathways.