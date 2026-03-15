# Predictive Log Anomaly Engine — Project Documentation

## 1. Overview

**Predictive Log Anomaly Engine** is an AI-powered observability and anomaly detection system for software logs.

The project was designed to detect risky behavioral patterns in log streams before full service failure occurs.  
Instead of reacting only after incidents happen, the system analyzes event sequences in real time, scores anomalous behavior, generates alerts, and exposes a complete observability and investigation layer.

This repository represents a full Applied AI Engineering prototype that combines runtime inference, alerting, monitoring, and lightweight investigation capabilities.

---

## 2. Task Definition

The goal of this project is to identify abnormal operational behavior from incoming logs and surface meaningful alerts before system instability becomes a full incident.

The system is responsible for:

- ingesting raw or synthetic log events
- transforming logs into structured behavioral representations
- building event sequences over time
- applying anomaly scoring logic
- generating severity-based alerts
- exposing runtime health and monitoring visibility
- supporting investigation through API, dashboards, and UI

This is not a passive log viewer.  
It is a proactive AI-assisted observability system.

---

## 3. System Scope

The project includes an end-to-end runtime pipeline with the following scope:

### Included in scope

- log ingestion
- parsing and template extraction
- sequence construction
- ML-based anomaly scoring
- alert lifecycle handling
- FastAPI runtime service
- Prometheus metrics exposure
- Grafana dashboard support
- lightweight read-only investigation UI
- Docker-based local deployment
- CI/CD validation and automated tests

### Out of scope

- production cloud deployment
- Kubernetes orchestration
- active system remediation
- complex analyst workflow management
- full autonomous incident response
- advanced LLM-based investigation agents in production mode

The system is intentionally scoped as a strong engineering prototype focused on runtime behavior, alerting, and observability.

---

## 4. Design Rationale

This project is documented as a complete hybrid system because it combines multiple engineering domains:

- AI / anomaly detection
- backend API engineering
- observability tooling
- operational alerting
- investigation-oriented UI
- containerized deployment and validation

A simpler system would not be enough because raw log viewing alone does not provide early anomaly detection.  
A more complex system would add unnecessary architectural weight at this stage.

The design intentionally focuses on a practical middle ground:

- intelligent enough to detect behavioral anomalies
- observable enough to investigate them
- simple enough to run locally and demonstrate clearly

The purpose was to build a system that feels realistic, explainable, and operationally meaningful.

---

## 5. Why Each Component Was Chosen

### Log Parsing & Template Mining
Chosen to reduce raw log noise and convert unstructured input into repeatable behavioral units.

### Sequence Builder
Chosen because anomalies in operations often emerge across event order and context, not in isolated log lines.

### ML Scoring Engine
Chosen to identify suspicious or unusual behavior patterns beyond static rule-based matching.

### Alert Manager
Chosen to transform model output into operationally useful alerts with severity logic and lifecycle handling.

### FastAPI Service
Chosen as a lightweight and clear backend layer for ingestion, health, alerts, metrics, and UI access.

### Prometheus
Chosen to expose runtime metrics in a standard monitoring-friendly format.

### Grafana
Chosen to provide visual investigation support and live runtime observability.

### Investigation UI
Chosen to give a direct and simple read-only interface for alert review and system visibility.

### Docker
Chosen to keep execution reproducible and easy to run locally.

### GitHub Actions + Pytest
Chosen to validate the repository through repeatable automated testing and CI checks.

---

## 6. End-to-End Pipeline Stages

The system follows this runtime flow:

```text
Logs
  ↓
Parsing & Template Mining
  ↓
Sequence Builder
  ↓
ML Scoring Engine
  ↓
Alert Manager
  ↓
FastAPI Service
  ↓
Prometheus + Grafana
  ↓
Investigation UI
```

---

## Stage 1 — Log Ingestion

Synthetic or runtime events enter the system.

## Stage 2 — Parsing & Structuring

Raw logs are normalized and transformed into structured representations.

## Stage 3 — Behavioral Pattern Extraction

Templates and event patterns are identified to preserve behavior while reducing noise.

## Stage 4 — Sequence Construction

Operational events are grouped into windows or sequences that represent temporal behavior.

## Stage 5 — Anomaly Scoring

The scoring engine evaluates whether observed behavior is normal or suspicious.

## Stage 6 — Alert Generation

Severity-aware alerts are created based on anomaly score and system rules.

## Stage 7 — Runtime Exposure

The backend exposes alerts, health signals, and metrics through FastAPI endpoints.

## Stage 8 — Observability & Investigation

Prometheus, Grafana, and the lightweight UI provide investigation support and runtime visibility.

---

## 7. Main Components
### 7.1 Parsing & Template Mining

Transforms raw logs into structured templates that reduce noise while preserving behavioral meaning.

### 7.2 Sequence Builder

Builds event windows and temporal sequences that represent runtime behavior over time.

### 7.3 ML Scoring Engine

Applies anomaly detection logic to identify unusual system activity.

### 7.4 Alert Manager

Generates alerts with severity scoring, cooldown handling, and lifecycle logic.

### 7.5 API Service

Provides ingestion, alerts, metrics, health, and UI-related endpoints through FastAPI.

### 7.6 Observability Layer

Integrates Prometheus and Grafana for runtime monitoring and operational visibility.

### 7.7 Investigation UI

Provides a lightweight read-only layer for alert review and future investigation workflows.

---

## 8. Results & Artifacts

The project currently includes the following delivered artifacts:

- working runtime inference pipeline

- implemented alert generation pipeline

- integrated observability stack

- Prometheus metrics support

- Grafana dashboard support

- Docker-based local runtime

- production-style compose override

- lightweight investigation UI

- automated CI/CD validation

- passing test suite

This makes the repository not just a research demo, but a structured engineering prototype.

---

## 9. Runtime Capabilities

The current system supports:

- sequence-based anomaly detection

- real-time style event ingestion

- severity-oriented alert handling

- system health visibility

- operational metrics exposure

- dashboard-based investigation

- lightweight API-driven UI access

The emphasis is on practical observability and explainable runtime behavior.

---

## 10. Deployment & Execution

### Local Run
```bash
docker compose build
docker compose up
```

### Services

API / UI: http://localhost:8000

Prometheus: http://localhost:9090

Grafana: http://localhost:3000

### Testing

Fast tests:

```bash
pytest -m "not slow"
```

Integration tests:

```bash
pytest -m integration
```

---

## 11. Documentation Structure

Project documentation is organized under:

- docs/current_system/ — current architecture, roadmap, UI direction

- docs/api/ — API reference

- docs/operations/ — alerts, deployment, metrics, security

- docs/system_validation/ — audit and validation reports

This structure separates engineering explanation, runtime operation, and validation evidence.

---

## 12. Notebook Usage Policy

Notebooks, when present, should be treated as demonstration or presentation assets only.

They are not the primary execution path of the system.

The official system flow should remain:

- reproducible

- script-based

- API-based

- containerized

- test-validated

This follows the project documentation philosophy of prioritizing engineering reproducibility over ad-hoc notebook execution.

---

## 13. Design Philosophy

This project follows several core documentation and engineering principles:

- clarity over unnecessary complexity

- system behavior over isolated code fragments

- operational visibility over black-box AI

- reproducibility over one-off execution

- investigation support over cosmetic UI

- practical engineering value over inflated architecture

The project was intentionally designed to be strong enough to demonstrate real engineering thinking without becoming over-engineered.

---

## 14. Project Status

Current repository status:

- runtime inference pipeline implemented

- alert pipeline implemented

- observability stack integrated

- Grafana and Prometheus configured

- production-style deployment override added

- validation and tests passing

- UI implemented for alert review and investigation workflows

The repository currently represents a complete AI engineering prototype with strong emphasis on runtime behavior, observability, and investigation workflows.

---

## 15. Career / Portfolio Value

This project demonstrates practical work across:

- AI runtime systems

- anomaly detection workflows

- FastAPI backend engineering

- observability architecture

- Docker-based deployment

- CI/CD validation

- investigation-oriented system design

It is suitable as a portfolio project because it reflects both AI reasoning and engineering execution.

---

## 16. Project Team

Developed as part of an Applied AI Engineering project.

- Oren Salami — DevOps, QA, Core Architecture Design, Technical Specification

- Dan Kalfon — Backend Engineering, Core Architecture Design, Technical Specification

- Nahshon Raizman — Frontend Development and UI, Core Architecture Design, Technical Specification

- Jonathan Finkelstein — Frontend Development and UI, Core Architecture Design, Technical Specification

---

## 17. Final Notes

This project should be understood as a hybrid AI engineering system, not as a single isolated model or a simple monitoring dashboard.

Its value comes from the integration between:

- anomaly detection

- runtime processing

- alert generation

- API exposure

- observability tooling

- investigation support

That combination is what makes the system meaningful from an engineering and portfolio perspective.

---