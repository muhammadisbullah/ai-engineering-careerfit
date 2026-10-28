# CareerFit AI — AI-Powered Career and Skills Alignment Assistant
> An AI-powered, document-grounded assistant that matches fresh graduates and job seekers with relevant career opportunities and identifies skill gaps using official occupational frameworks.

## Problem Statement
The palm oil industry generates massive volumes of solid biomass and waste, such as Empty Fruit Bunches (EFB) and Palm Oil Mill Effluent (POME) (Norrahim et al., 2022; Kan et al., 2024). However, conventional mill operations face inefficiencies in raw material utilization and lack an automated system to convert low-value waste into high-value downstream products (Dominic & Baidurah, 2025; Norrahim et al., 2022). Furthermore, there is a critical technological gap: the absence of an integrated predictive decision support system that processes real-time operational data alongside historical records to optimize waste mixture ratios and evaluate their economic potential (Kan et al., 2024; Dominic & Baidurah, 2025).

## Proposed Solution:
This project proposes a hybrid data pipeline and AI-driven decision support system integrating real-time IoT sensor data (moisture, weight, temperature) with historical batch logs. Using machine learning and optimization algorithms, the system dynamically predicts optimal downstream products from palm waste, determines ideal mixture formulations, and evaluates net economic returns to reduce waste and maximize resource efficiency (Kan et al., 2024; Dominic & Baidurah,
2025).

REFERENCES:
Dominic, D., & Baidurah, S. (2025). A review of biological processing technologies for palm oil
mill waste treatment and simultaneous bioenergy production with technoeconomic analysis.
Energy Conversion and Management: X, 100914
Kan, K. W., Chan, Y. J., Tiong, T. J., & Lim, J. W. (2024). Maximizing biogas yield from palm oil
mill effluent (POME) through advanced simulation and optimization techniques on an industrial
scale. Chemical Engineering Science, 285, 119644.
Norrahim, M. N. F., et al. (2022). Emerging technologies for value-added use of oil palm biomass.
Environmental Science and Pollution Research, 29, 62112–62130.

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
