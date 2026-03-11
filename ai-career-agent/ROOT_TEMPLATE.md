# Job Search Agent — Project Documentation Template

## 1. Project Title
Write the official project name.

**Example:**  
AI Career Agent

---

## 2. Project Classification
Select the project type.

- [ ] Single-Domain Project
- [x] Hybrid Project

**Why this classification?**  
This project is considered a **Hybrid Project** because it combines multiple domains into one working system, such as:

- job source collection
- normalization and deduplication
- scoring and resume matching
- notifications
- dashboard / UI
- automation readiness
- CI/CD and runtime engineering

---

## 3. Overview
Provide a short explanation of the system.

**Template text:**  
This project is an AI-assisted job search system designed to collect, organize, score, and present job opportunities in a structured way.  
The platform helps transform scattered job listings into a more focused pipeline for decision-making, prioritization, and future automation.

The system combines source collection, matching logic, filtering, scoring, and dashboard visibility into one end-to-end workflow.

---

## 4. Task Definition
Explain what the system is supposed to do.

**Template prompts:**
- What is the main goal of the project?
- What problem does it solve for the user?
- What is the operational outcome expected from the system?

**Example direction:**  
The goal of the system is to reduce the manual effort involved in job searching by collecting jobs from multiple sources, removing duplicates, scoring relevance, and presenting the results in one usable dashboard.

---

## 5. System Scope
Define what is included and what is excluded.

### Included
- job source collection
- source normalization
- deduplication
- scoring
- resume-based relevance matching
- dashboard display
- local notifications / summaries
- future-ready integration structure

### Excluded
- automatic job application submission
- live Gmail access in V1
- live n8n orchestration in V1
- production cloud deployment
- advanced recruiter-response automation

---

## 6. Design Rationale
Explain **why** the system was built this way.

**Template prompts:**
- Why was a modular architecture chosen?
- Why separate collectors, scoring, notifications, and UI?
- Why build future-ready integrations without activating them now?
- Why keep part of the system mock-safe in V1?

**Example direction:**  
The system was designed modularly to allow safe development and demonstration in V1 without depending on unstable integrations.  
This approach makes it easier to expand the platform gradually, keep runtime predictable, and separate what is active now from what is planned for future versions.

---

## 7. Why Each Component Was Chosen
Document the reason behind each major component.

### Source Collectors
Explain why collectors exist and why source-specific logic is isolated.

### Dedup Engine
Explain why duplicates are a real problem in job aggregation systems.

### Scoring Layer
Explain why jobs must be ranked rather than only collected.

### Resume Matching
Explain why relevance must reflect candidate profile, not just raw keywords.

### Notifications
Explain why the system needs output channels beyond the database.

### Dashboard
Explain why observability and visibility matter for job search workflows.

### Gmail / n8n Future Layer
Explain why future-ready integrations were prepared without being activated.

---

## 8. End-to-End Pipeline Stages
Describe the full system flow.

### Stage 1 — Source Collection
Jobs are collected from configured sources such as mock collectors, RSS feeds, or Israeli job boards.

### Stage 2 — Normalization
Collected job entries are normalized into a shared structure.

### Stage 3 — Deduplication
Duplicate jobs are removed using layered rules such as URL, source ID, and title/company/location matching.

### Stage 4 — Scoring
Jobs are evaluated using keyword logic, semantic logic, or combined scoring.

### Stage 5 — Resume Matching
Candidate profile and resume-derived signals are used to improve relevance.

### Stage 6 — Persistence
Jobs and scores are stored in the local database.

### Stage 7 — Notification / Summary
Relevant jobs may be surfaced through console output, file summaries, or future channels.

### Stage 8 — Dashboard Presentation
The Streamlit dashboard provides visibility into job totals, match quality, and current source mode.

---

## 9. Source Strategy
Document which sources are active and how they are handled.

### Active Sources in V1
- Mock sources
- RSS sources
- Israeli mock-safe sources (if enabled)

### Planned / Disabled Sources
- Additional Israeli boards
- recruiter channels
- future integrations

**Template prompts:**
- Which sources are enabled by default?
- Which are planned only?
- Which require careful handling due to scraping or access limitations?

---

## 10. Runtime Modes
Explain how the system can be run.

### Example modes
- mock
- rss
- israel
- all

**Template prompts:**
- What does each mode do?
- Which mode is recommended for demo?
- Which mode is safest for local development?

---

## 11. Candidate Profile / Resume Matching
Explain how candidate context is used.

**Template prompts:**
- Is resume parsing supported?
- What artifacts are generated?
- How does candidate profile affect scoring?
- What fallback logic exists if parsing is incomplete?

---

## 12. Deduplication Strategy
Explain the dedup logic clearly.

**Recommended sections:**
- URL-level dedup
- source ID dedup
- title/company/location fingerprint
- fuzzy matching fallback

**Why it matters:**  
Job aggregation systems often ingest the same role from multiple sources, so deduplication is critical for keeping the dashboard useful and reducing noise.

---

## 13. Scoring Architecture
Describe how jobs are ranked.

### Keyword Scoring
Explain the role of direct term matching.

### Semantic / Embedding Scoring
Explain the role of broader contextual matching.

### Combined Score
Explain how the final score is derived.

**Template prompts:**
- What score ranges are used?
- How are high / medium / low matches defined?
- What happens if semantic scoring dependencies are unavailable?

---

## 14. Notifications
Document how the system surfaces results.

### Active in V1
- console output
- file notifier

### Future-Ready
- email
- Gmail-based workflows
- n8n automation
- additional channels

---

## 15. Dashboard / UI
Describe the dashboard as part of the system.

**Template prompts:**
- What does the UI display?
- Is it read-only or interactive?
- What filters exist?
- What quick actions exist?
- How does the user know which source mode is active?

**Example direction:**  
The dashboard acts as the operational visibility layer of the project.  
It allows the user to inspect collected jobs, match levels, source mode, and quick runtime actions without interacting directly with backend scripts.

---

## 16. Automation Readiness
Explain what future automation was prepared but not activated.

### Gmail Layer
- future-ready only
- mock-safe in current version
- no active credentials in V1

### n8n Layer
- future-ready only
- webhook contracts / example payloads
- no live workflow dependency in V1

**Template prompts:**
- Why was this prepared now?
- Why was it intentionally left inactive?

---

## 17. Testing & Validation
Document how the system was validated.

### Suggested subsections
- unit tests
- integration tests
- mock-based tests
- scheduler tests
- dashboard sanity checks
- CI validation

**Template prompts:**
- What areas are covered by tests?
- What failures were fixed during V1?
- What does the CI pipeline validate?

---

## 18. CI/CD
Describe the automation pipeline.

### Example workflow areas
- CI lint and tests
- test matrix
- security scan
- Docker smoke test
- release flow

**Template prompts:**
- What runs on push?
- What ensures runtime consistency?
- What was required to make CI pass fully?

---

## 19. Repository Structure
Provide a short explanation of the repo layout.

**Example template:**
app/
automation/
config/
dashboard/
data/
docs/
logs/
scripts/
tests/
Dockerfile
docker-compose.yml
requirements.txt

Describe the purpose of each major folder.

---

## 20. Results & Artifacts

Describe the concrete outputs of the project.

Examples

- populated jobs database

- scored job records

- candidate profile files

- CI workflow results

- runtime alignment report

- closure report

---

## 21. Known Limitations

Be explicit about current boundaries.

Example prompts:

- Which collectors are mock-safe only?

- Which integrations are not active yet?

- Which parts are intentionally local-only?

- What still needs future implementation?

---

## 22. Notebook Usage Policy

Document whether notebooks are used and what role they play.

Recommended default text:
- This project is designed to be script-first and runtime-oriented.
- If notebooks are used, they are supportive only and do not replace the reproducible execution flow of the system.

---

## 23. Design Philosophy

Document the core engineering mindset.

Example topics:

- clarity over unnecessary complexity

- modular growth over premature automation

- production-style structure even in local-first projects

- future-ready integrations without forced activation

- explicit separation between active, planned, and mock-safe components

---

## 24. Future Improvements

List future evolution paths.

Examples

- real Israeli source scraping

- recruiter response tracking

- Gmail activation

- n8n activation

- application tracking

- better ranking logic

- analytics improvements

- cloud deployment

---

## 25. Final Notes

Close the document clearly.

Template direction:
This project represents an end-to-end AI-assisted job search platform built with a modular and extensible mindset.
The current version focuses on safe runtime behavior, structured visibility, and future expansion readiness rather than premature full automation.

# Optional Appendix A — Demo Flow
pip install -r requirements.txt
python scripts/run_v1_demo.py
streamlit run dashboard/streamlit_app.py

# Optional Appendix B — Reset Flow
python scripts/reset_demo_state.py --mode israel
streamlit run dashboard/streamlit_app.py

# Optional Appendix C — Source Mode Summary
- mock = internal safe demo mode

- rss = RSS-based collection mode

- israel = Israeli source mode

- all = all enabled sources