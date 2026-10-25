# CareerFit AI — AI-Powered Career and Skills Alignment Assistant
> An AI-powered, document-grounded assistant that matches fresh graduates and job seekers with relevant career opportunities and identifies skill gaps using official occupational frameworks.

## Problem Statement
Fresh graduates and job seekers frequently face skill-related underemployment due to a lack of visibility into real-world job requirements and skill expectations. Conversely, employers receive vast volumes of misaligned applications. CareerFit AI provides a data-grounded, 24/7 intelligent assistant that evaluates user qualifications against national occupational standards and identifies exact upskilling needs.

## Evidence of the Problem
- **Underemployment:** Official statistics indicate persistent skill-related underemployment among tertiary graduates due to structural mismatches between education outputs and industry needs (DOSM Graduates Statistics Report).
- **Rapidly Evolving Skill Demands:** Core job skills are changing rapidly across industries, creating a widening gap between academic preparation and market expectations (World Economic Forum Future of Jobs Report).

## Initial Related Work / Existing Approaches
- **Job Portals (LinkedIn / JobStreet):** Dependent on keyword searches and lack structured skills gap analysis grounded in national occupational standards.
- **General LLMs (ChatGPT):** Flexible for drafting resumes, but prone to hallucinations and ungrounded career advice.
- **University Advisory Centers:** High quality guidance, but constrained by human bandwidth and operational hours.

## Engineering Gap / Limitation
Current solutions lack a transparent, document-grounded mechanism that maps individual academic profiles directly to standardized national occupational frameworks (e.g., MASCO / COL) to provide hallucination-free career alignment and upskilling guidance.

## Project Objectives
- **O1:** Design a document-grounded AI alignment assistant based on official workforce and occupational frameworks.
- **O2:** Develop the retrieval pipeline with domain-specific guardrails to ensure grounded recommendations.
- **O3:** Evaluate the system on retrieval precision, groundedness, latency, and fairness.

## Target Users
- Fresh university graduates seeking entry-level positions matched to their skills.
- Early-career professionals and career switchers looking for targeted upskilling pathways.

## Data Sources
- **TalentCorp Critical Occupations List (COL):** [https://www.talentcorp.com.my](https://www.talentcorp.com.my)
- **Malaysia Standard Classification of Occupations (MASCO):** [https://www.dosm.gov.my](https://www.dosm.gov.my)

## Weekly Progress
| Week | Focus | Deliverable | Status |
|------|-------|-------------|--------|
| W1 | System map + project scope | README.md + /docs/ files | ✅ |
| W2 | Requirements & Evaluation Criteria | docs/week2_requirements.md | ⏳ |
