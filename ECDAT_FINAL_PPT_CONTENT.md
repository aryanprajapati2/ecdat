# ECDAT — Final SIH PPT Content

**Smart India Hackathon 2026**  
**Problem Statement ID:** SIH26164  
**Project:** Enterprise Cryptographic Discovery & Analysis Tool (ECDAT)  
**Theme:** Blockchain & Cybersecurity  
**PS Category:** Software  
**Team ID:** 122809  
**Team Name:** Twinks  

---

## Slide 1 — Title Page

### SMART INDIA HACKATHON 2026

**Problem Statement ID – SIH26164**

**Problem Statement Title:**  
Enterprise Cryptographic Discovery & Analysis Tool (ECDAT)

**Theme:** Blockchain & Cybersecurity

**PS Category:** Software

**Team ID:** 122809

**Team Name:** Twinks

---

## Slide 2 — Enterprise Cryptographic Discovery & Analysis Tool (ECDAT)

### Problem Stat → Skill AI Solution

| Problem | ECDAT Solution |
|---|---|
| **Hidden Cryptography** | **Crypto Discovery** |
| **Unclear Risk** | **Context + Quantum Risk** |
| **Uncertain migration order** | **P1–P4 Prioritization** |
| **No proof after migration** | **Re-scan & Verification** |

### Real-world issue

Cryptographic assets are difficult to discover, assess, and prioritize for quantum-safe migration.

### Why important

Organizations need evidence-backed answers to:

- What cryptography exists?
- What is at risk?
- What should migrate first?

### Solution

**ECDAT turns cryptographic discovery into an actionable migration roadmap — with verification.**

---

# Slide 3 — Technical Approach

## System Architecture

### Technologies to be used

- **Python + FastAPI** — Backend & Orchestration
- **CryptoScan + Syft** — Cryptographic Discovery
- **React + TypeScript** — Web UI & Dashboard
- **Docker Compose** — Local / SIH Deployment
- **Tailwind CSS** — Interface Styling
- **PostgreSQL** — Canonical Data & Provenance

---

## ECDAT Architecture

### User / Analyst

The user or security analyst can:

- Upload source code / documents
- View analysis results
- Review the risk map
- Plan migration

### React + TypeScript

**Web UI & Dashboard**

Provides the user interface for:

- Uploading sources
- Viewing analysis results
- Viewing the risk map
- Viewing migration plans

### FastAPI API

**Backend & Orchestration**

Handles:

- API requests
- Business logic
- Scan orchestration
- Analysis orchestration
- Recommendations

### Scan Workers

**CryptoScan + Syft**

Used to scan:

- Git repositories
- ZIP archives
- Local sources

and discover cryptographic assets and software/dependency information.

### ECDAT Core

The core analysis layer handles:

- **Evidence**
  - Repository
  - File
  - Commit
- **Crypto Assets**
- **Context**
- **Usage & Dependencies**
- **Quantum Risk Assessment**
- **Migration**
- **Verification**
  - Re-scan
  - Compare
- **PQC / Hybrid Recommendations**

### PostgreSQL

**Canonical Data & Provenance**

Stores:

- Scanned assets
- Analysis results
- User profiles
- Reports
- Provenance information

### Outputs

ECDAT produces:

- **CBOM** — Cryptographic Bill of Materials
- **Risk Map / Dashboards**
- **Reports**
  - Audit
  - Export

---

## ECDAT Workflow

```text
INGEST
Git / ZIP / Local sources
        ↓
SCAN
CryptoScan + Syft
        ↓
ANALYZE
Evidence + Context + Quantum Risk
        ↓
RECOMMEND
PQC / Hybrid Migration
        ↓
VERIFY
Re-scan + Compare
```

### Core workflow

**Ingest → Scan → Analyze → Recommend → Verify**

---

## Slide 4 — Feasibility and Viability

### Feasibility Challenges & Risks

ECDAT must address:

- Handle malicious archives or repositories.
- Avoid false conclusions from dependencies.
- Account for quantum-risk uncertainty.
- Protect sensitive source code.

### Mitigation

- Process sensitive source code locally.
- Use modular and extensible components.
- Use open technologies for implementation.
- Support local, scalable deployment.
- Secure inputs through validation and quarantine.
- Keep analysis traceable to evidence.
- Use configurable risk scenarios.
- Minimize source-code exposure.

### Security / Engineering Principle

ECDAT is designed to make cryptographic analysis:

**Controlled → Traceable → Explainable → Locally Processed**

---

## Slide 5 — Impact and Benefits

# IMPACT & BENEFITS

ECDAT follows four major stages of organizational value:

### 01 — DISCOVERY

#### Complete Crypto Visibility

Identify and inventory cryptographic assets with evidence.

Example input sources:

- Git repository
- ZIP archive
- Local folder

---

### 02 — CONTEXT

#### Understand Future Risk

Connect cryptography with:

- Quantum exposure
- Data lifetime
- System criticality
- Usage context

---

### 03 — MIGRATION

#### Actionable PQC Roadmaps

Prioritize assets and recommend suitable:

- PQC migration directions
- Hybrid migration directions

---

### 04 — VERIFICATION

#### Prove the Change

Re-scan and compare before/after states to verify migration.

---

## Who Benefits?

### Security Teams

- Identify crypto risk
- Prioritize cryptographic assets
- Understand quantum exposure

### Developers

- Get migration direction
- Understand which cryptographic components require attention

### Organizations

- Track migration
- Maintain compliance evidence
- Build future-ready systems

---

## Expected Outcomes

### Complete Crypto Visibility

A reliable view of discovered cryptographic assets.

### Better Risk Understanding

Context-aware understanding of quantum and operational exposure.

### Actionable Migration Plans

Prioritized PQC / hybrid migration directions.

### Verified and Future-Ready Systems

Evidence-based verification after migration.

---

# Slide 6 — Research and References

## Existing Platforms / Related Work

### CryptoScan

Source-level cryptographic discovery.

### Syft / Anchore

SBOM and dependency evidence.

### NIST / NCCoE

Cryptographic inventory and migration guidance.

### IBM Guardium Cryptography Manager

Cryptography management.

### Sectigo Quantum Ready / QSPM

Quantum readiness.

---

## Research Areas

The ECDAT research and design work focuses on:

- Post-Quantum Cryptography (PQC) standards
- Cryptographic discovery and inventory
- SBOM & CBOM — Software Bill of Materials and Cryptography Bill of Materials
- Quantum-risk assessment & migration planning

---

## Identified Research Gaps

### 1. Connecting cryptographic evidence to actionable decisions

ECDAT aims to move beyond simply reporting that cryptography exists by connecting evidence to risk and migration decisions.

### 2. Linking component dependencies with actual cryptographic usage

Dependency presence alone does not necessarily prove that cryptography is being used. ECDAT separates dependency evidence from actual cryptographic usage evidence.

### 3. Making risk assessments explainable and evidence-based

ECDAT keeps risk decisions connected to discovered evidence and contextual information rather than treating the scanner output itself as the final risk decision.

---

# ECDAT Core Value Proposition

ECDAT connects:

```text
CRYPTOGRAPHIC DISCOVERY
          ↓
       EVIDENCE
          ↓
       CONTEXT
          ↓
    QUANTUM + RISK
          ↓
   PRIORITIZATION
          ↓
  PQC / HYBRID PLAN
          ↓
       RE-SCAN
          ↓
     VERIFICATION
```

### Product lifecycle

**DISCOVER → UNDERSTAND → PRIORITIZE → MIGRATE → VERIFY**

---

# Technology Stack Summary

| Layer | Technology |
|---|---|
| Web UI | React + TypeScript |
| Styling | Tailwind CSS |
| Backend | Python + FastAPI |
| Discovery | CryptoScan + Syft |
| Database | PostgreSQL |
| Deployment | Docker Compose |
| Analysis | ECDAT Core |
| Output | CBOM, Risk Map, Reports |
| Migration | PQC / Hybrid recommendations |
| Verification | Re-scan + Compare |

---

# One-Line Project Description

> **ECDAT is an evidence-driven cryptographic discovery and analysis platform that identifies cryptographic assets, connects them with context and quantum risk, prioritizes migration, recommends PQC/hybrid migration directions, and verifies the change through re-scanning.**

---

# Presentation Narrative

The complete six-slide presentation follows this narrative:

**1. Identify the project and SIH problem**  
↓  
**2. Explain the real-world gap and ECDAT's solution**  
↓  
**3. Show the technical architecture and implementation workflow**  
↓  
**4. Demonstrate feasibility, security controls and mitigation strategy**  
↓  
**5. Explain organizational impact and expected outcomes**  
↓  
**6. Establish the research foundation, related work and research gaps**

This creates the overall story:

> **Problem → Solution → Architecture → Feasibility → Impact → Research Validation**
