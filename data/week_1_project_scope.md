# Week 1 Project Scope: CareerFit AI

## 1. Project Name and Domain
* **Project Name:** CareerFit AI (AI Career & Skills Alignment Assistant)
* **Domain:** Human Capital, Workforce Development, and Higher Education

## 2. Problem Statement
Fresh graduates and job seekers often struggle to find employment that aligns with their specific skills and academic qualifications. Concurrently, employers face an oversupply of generic applications while experiencing shortages in candidates with required domain-specific competencies. This structural skills mismatch leads to underemployment, extended job search periods, and labor market inefficiencies. An AI-engineered document-grounded solution can analyze job market frameworks alongside candidate profiles to provide objective, data-driven career alignment and actionable upskilling recommendations.

## 3. Evidence of the Problem
* **Evidence 1:** According to the Department of Statistics Malaysia (DOSM) Graduates Statistics, a significant portion of employed graduates remain in skill-related underemployment, working in semi-skilled or low-skilled occupations despite holding tertiary qualifications.
  * **Source / Citation:** Department of Statistics Malaysia (DOSM), *Graduates Statistics Report*, https://www.dosm.gov.my
* **Evidence 2:** The World Economic Forum Future of Jobs Report highlights that over 40% of core skills required in the workforce will change due to rapid technological transformation, creating an urgent gap between academic curricula and evolving industry needs.
  * **Source / Citation:** World Economic Forum, *The Future of Jobs Report*, https://www.weforum.org/reports/the-future-of-jobs-report-2023/

## 4. Initial Related Work / Existing Approaches
1. **General Job Search Engines (e.g., JobStreet, LinkedIn Jobs)**
   * **Source / Citation:** Industry standard employment platforms (https://www.linkedin.com / https://www.jobstreet.com)
   * **Key Limitation:** Primarily rely on keyword search matching and recruiter paywalls; they do not perform deep contextual skills gap analysis or offer structured learning path recommendations grounded in public qualification standards.
2. **General-Purpose Conversational AI (e.g., ChatGPT, Claude)**
   * **Source / Citation:** OpenAI ChatGPT / Anthropic Claude (https://chat.openai.com)
   * **Key Limitation:** While capable of reviewing resumes, general AI models suffer from hallucination risks, lack deterministic grounding in national occupational standards, and may provide generic or outdated career advice.
3. **University Career Advisory Services**
   * **Source / Citation:** Higher education institutional career guidance centers.
   * **Key Limitation:** Highly effective and contextual, but limited by staff availability, constrained operational hours, and manual processing capacity when dealing with large student cohorts.

## 5. Engineering Gap / Limitation
Existing digital recruitment tools either rely on superficial keyword matching or unstructured LLM output without deterministic grounding in official occupational frameworks. There is a lack of an open, document-grounded AI system that ingests standardized job classification frameworks and skill taxonomies to accurately evaluate candidate qualifications against job descriptions and highlight precise skill gaps.

## 6. Initial Project Objectives
* **O1:** To design a document-grounded AI assistant capable of parsing candidate profiles and matching them against official occupational frameworks and competency standards.
* **O2:** To develop a retrieval-augmented system with appropriate safety and domain guardrails to provide verified skill gap assessments and upskilling pathways.
* **O3:** To evaluate the system’s performance in terms of retrieval accuracy, answer groundedness, response latency, and fairness across different academic domains.

## 7. Target Users
* **Fresh Graduates:** Seeking entry-level roles aligned with their field of study and actionable insights on missing skill sets.
* **Job Seekers & Career Switchers:** Looking to transition into new technical or professional domains based on transferable skills.

## 8. Data Sources
* **Source 1:** *Critical Occupations List (COL) & Skills Taxonomy* — Published by TalentCorp Malaysia / Ministry of Human Resources.
  * **URL:** https://www.talentcorp.com.my/en/key-initiatives/critical-occupations-list
* **Source 2:** *Malaysia Standard Classification of Occupations (MASCO)* — Published by Department of Statistics Malaysia (DOSM).
  * **URL:** https://www.dosm.gov.my

## 9. Comparison with EduAdvisor
* **Similar to EduAdvisor:** Like EduAdvisor, CareerFit AI is a document-grounded Retrieval-Augmented Generation (RAG) system that uses official PDF documents as its primary knowledge source to deliver accurate, non-hallucinated guidance to users via a conversational or query interface.
* **Different from EduAdvisor:** While EduAdvisor focuses on internal university administration (course codes, prerequisites, and graduation requirements for enrolled students), CareerFit AI operates on workforce and employment data, bridging academic backgrounds with national labor market demands and industry skill taxonomies.

## 10. Responsible AI Risks
* **Risk 1 — Algorithmic & Historical Bias:** The retrieval or embedding model may penalize graduates from non-traditional or lesser-known academic backgrounds if training or source data favors specific institutions or keyword patterns.
* **Risk 2 — Data Privacy & PII Exposure:** Processing user resumes and career histories involves handling Personally Identifiable Information (PII), posing privacy risks if sensitive user data is retained, logged, or exposed during query processing.