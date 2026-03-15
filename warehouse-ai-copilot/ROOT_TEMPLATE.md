# AI Smart Warehouse Intelligence — Project Documentation Template

## 1. Project Title
Write the official project name.

**Example:**  
Warehouse AI Copilot

---

## 2. Project Classification
Select the project type.

- [ ] Single-Domain Project
- [x] Hybrid Project

**Why this classification?**  
This project is considered a **Hybrid Project** because it combines multiple domains into one working system, such as:

- warehouse inventory analytics
- anomaly detection
- stock risk monitoring
- dashboard visibility
- AI assistant / agent interaction
- lightweight RAG support
- API and runtime engineering

---

## 3. Overview
Provide a short explanation of the system.

**Template text:**  
This project is an AI-powered warehouse intelligence system designed to analyze inventory activity, detect operational anomalies, identify products at risk of stockout, and provide clear visibility through a dashboard and AI assistant.

The platform transforms raw warehouse data into operational insights that support faster decision-making and better inventory awareness.

---

## 4. Task Definition
Explain what the system is supposed to do.

**Template prompts:**
- What is the main goal of the project?
- What warehouse problem does it solve?
- What operational outcome is expected from the system?

**Example direction:**  
The goal of the system is to reduce manual effort in monitoring warehouse activity by automatically identifying unusual inventory movements, highlighting stock risks, analyzing category activity, and allowing users to ask questions about the warehouse state through an AI assistant.

---

## 5. System Scope
Define what is included and what is excluded.

### Included
- products dataset
- inventory dataset
- inventory movements dataset
- stock risk analysis
- anomaly detection
- category activity analysis
- warehouse activity visibility
- dashboard presentation
- AI assistant queries
- lightweight RAG on warehouse documents
- API endpoints
- local Docker runtime

### Excluded
- live ERP/WMS integration in V1
- production cloud deployment
- real-time IoT sensor streaming
- automatic procurement ordering
- advanced forecasting models
- multi-client tenant architecture

---

## 6. Design Rationale
Explain **why** the system was built this way.

**Template prompts:**
- Why was a modular architecture chosen?
- Why separate analytics, models, agent, and dashboard?
- Why use synthetic data in V1?
- Why prepare RAG in a lightweight way instead of building a heavy knowledge system?

**Example direction:**  
The system was designed modularly to allow safe development, easy testing, and clean demonstration in V1.  
Synthetic data was used to create a controlled, repeatable environment for analytics and AI experimentation before introducing real customer data.

---

## 7. Why Each Component Was Chosen
Document the reason behind each major component.

### Products Dataset
Explain why product metadata is necessary for stock thresholds, category analysis, and reporting.

### Inventory Dataset
Explain why current stock visibility is required for stock risk detection.

### Inventory Movements Dataset
Explain why movement history is necessary for anomaly detection and warehouse activity analysis.

### Analytics Layer
Explain why raw warehouse data must be transformed into operational indicators.

### Anomaly Detection Engine
Explain why unusual movement detection adds value beyond standard inventory reports.

### Stock Risk Engine
Explain why stockout prevention is one of the most important warehouse intelligence functions.

### Dashboard
Explain why visibility matters for warehouse operations.

### AI Assistant
Explain why natural language access improves usability and decision support.

### Lightweight RAG Layer
Explain why warehouse documents, policies, and notes can enrich answers beyond pure tabular analytics.

---

## 8. End-to-End Pipeline Stages
Describe the full system flow.

### Stage 1 — Data Preparation
Products, inventory, and movement data are loaded and validated.

### Stage 2 — Cleaning and Validation
Missing values, invalid timestamps, and inconsistent movement types are checked and corrected.

### Stage 3 — Feature Engineering
Operational features such as stock level, category activity, and movement frequency are generated.

### Stage 4 — AI Analysis
Models detect unusual movement behavior and stock risks.

### Stage 5 — Analytics Services
Processed results are exposed for dashboard and agent use.

### Stage 6 — API Layer
FastAPI endpoints provide structured access to warehouse insights.

### Stage 7 — AI Assistant / RAG
User questions are routed to analytics functions and, when relevant, supported by warehouse documents.

### Stage 8 — Dashboard Presentation
The Streamlit dashboard presents stock status, anomalies, activity, and AI query results.

---

## 9. Data Strategy
Document which data sources are active and how they are handled.

### Active Data in V1
- synthetic products dataset
- synthetic inventory dataset
- synthetic inventory movements dataset

### Planned / Future Data
- real customer warehouse exports
- ERP / WMS integration
- supplier master data
- real policy documents
- operational event streams

**Template prompts:**
- Which datasets are active by default?
- Which are synthetic only?
- Which require future real-world integration?

---

## 10. Runtime Modes
Explain how the system can be run.

### Example modes
- local script mode
- API mode
- dashboard mode
- docker compose mode

**Template prompts:**
- What does each mode do?
- Which mode is recommended for demo?
- Which mode is simplest for development?

---

## 11. Stock Risk Logic
Explain how stock risk is calculated.

**Template prompts:**
- How is minimum stock used?
- How are risky products identified?
- Is there projected stock depletion logic?
- How are critical / high / medium levels defined?

**Suggested direction:**  
The stock risk layer compares current stock against minimum stock thresholds and, where supported, estimates remaining coverage based on recent movement behavior.

---

## 12. Anomaly Detection Strategy
Explain the anomaly logic clearly.

**Recommended sections:**
- movement quantity anomalies
- spike detection
- statistical deviation
- Isolation Forest detection
- anomaly score interpretation

**Why it matters:**  
Warehouse operators need to identify unusual movement behavior early, especially when large or unexpected movements may indicate operational issues, shortages, or process errors.

---

## 13. Analytics Architecture
Describe how warehouse activity is analyzed.

### Stock Level Analysis
Explain how current inventory status is evaluated.

### Movement Frequency
Explain how product or warehouse activity frequency is calculated.

### Category Activity
Explain how categories are ranked by movement volume.

### Daily Activity Patterns
Explain how daily warehouse behavior is summarized.

**Template prompts:**
- Which analytics are exposed in the dashboard?
- Which analytics support the AI assistant?
- Which metrics are most relevant for operations?

---

## 14. AI Assistant
Document how the assistant answers warehouse questions.

### Example supported questions
- Which products are close to stockout?
- Which category moved the most this week?
- Were there unusual inventory movements?
- What is the reorder policy?

### Logic
Explain whether the assistant:
- routes to analytics services
- uses RAG for documentation
- uses an LLM provider abstraction
- combines structured results with generated explanation

---

## 15. Dashboard / UI
Describe the dashboard as part of the system.

**Template prompts:**
- What does the UI display?
- Is it read-only or interactive?
- What dashboard sections exist?
- How does the user navigate between views?

**Example direction:**  
The dashboard acts as the operational visibility layer of the project.  
It allows the user to inspect stock risks, anomalies, category activity, warehouse behavior, and AI answers without working directly with backend scripts or raw data files.

---

## 16. RAG / Documentation Layer
Explain what knowledge sources are available for retrieval.

### Active in V1
- local markdown docs
- warehouse notes
- policy text
- internal documentation

### Future-Ready
- supplier policy documents
- warehouse operating procedures
- customer documentation
- external connected knowledge sources

**Template prompts:**
- Why is RAG useful in this project?
- What questions should go to analytics and what questions should go to documents?

---

## 17. Testing & Validation
Document how the system was validated.

### Suggested subsections
- dataset validation
- anomaly detection tests
- stock risk tests
- API endpoint tests
- dashboard sanity checks
- docker runtime validation

**Template prompts:**
- What areas are covered by tests?
- What logic was verified manually?
- What runtime checks were performed after Docker build?

---

## 18. CI/CD
Describe the automation pipeline.

### Example workflow areas
- lint / style checks
- test execution
- API validation
- Docker build
- smoke tests

**Template prompts:**
- What runs on push?
- What ensures runtime consistency?
- What validates that the demo still works?

---

## 19. Repository Structure
Provide a short explanation of the repo layout.

**Example template:**
data/
docs/
scripts/
src/
tests/
configs/
Dockerfile
docker-compose.yml
requirements.txt

Describe the purpose of each major folder.

---

## 20. Results & Artifacts
Describe the concrete outputs of the project.

Examples

- generated synthetic warehouse dataset
- anomaly detection results
- stock risk tables
- category activity analytics
- API responses
- dashboard screenshots
- AI assistant answers
- Docker runtime proof

---

## 21. Known Limitations
Be explicit about current boundaries.

**Example prompts:**
- Is the dataset synthetic only?
- Is the AI assistant partly rule-based?
- Is the RAG layer lightweight only?
- Is the system local-first in V1?
- Which parts still need real customer data?

---

## 22. Notebook Usage Policy
Document whether notebooks are used and what role they play.

**Recommended default text:**
- This project is primarily application-oriented and runtime-based.
- If notebooks are used, they serve as lightweight demo or analysis artifacts only.
- The notebook does not replace the main reproducible execution flow of the system.

---

## 23. Design Philosophy
Document the core engineering mindset.

**Example topics:**
- clarity over unnecessary complexity
- modular architecture
- demo-safe design for V1
- local-first execution
- synthetic-first before real customer data
- explicit separation between current functionality and future expansion

---

## 24. Future Improvements
List future evolution paths.

Examples

- real warehouse customer data integration
- advanced forecasting
- supplier lead-time modeling
- procurement recommendations
- richer anomaly explanations
- better RAG knowledge base
- cloud deployment
- multi-warehouse benchmarking
- alerting / notification workflows

---

## 25. Final Notes
Close the document clearly.

**Template direction:**  
This project represents an end-to-end AI-assisted warehouse intelligence platform built with a modular and extensible mindset.  
The current version focuses on safe development, clear analytics, operational visibility, and future readiness for real-world warehouse data integration.

# Optional Appendix A — Demo Flow
python scripts/generate_synthetic_data.py
python scripts/run_api.py
python scripts/run_dashboard.py

# Optional Appendix B — Docker Flow
docker compose up --build

# Optional Appendix C — Example Questions
- Which products are close to stockout?
- Which category moved the most this week?
- Were there unusual inventory movements?
- What is the warehouse reorder policy?