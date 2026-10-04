# ECDAT — Enterprise Cryptographic Discovery & Analysis Tool

> **ECDAT is an evidence-driven cryptographic discovery and analysis platform that identifies cryptographic assets, connects them with context and quantum risk, prioritizes migration, recommends PQC/hybrid migration directions, and verifies the change through re-scanning.**

---

## 🔍 What is ECDAT?

**ECDAT** (Enterprise Cryptographic Discovery & Analysis Tool) is an open, evidence-first, scanner-agnostic cryptographic intelligence platform built for Smart India Hackathon 2026 (Problem Statement SIH26164) under the **Blockchain & Cybersecurity** theme, organized in response to NTRO's need for enterprise-grade cryptographic inventory.

Modern organizations face a critical gap: cryptographic implementations — from legacy symmetric ciphers and vulnerable PKI to quantum-vulnerable algorithms — are scattered across codebases, configuration files, containers, and third-party dependencies with no comprehensive, verifiable inventory in place.

**ECDAT acts as an organization's "Cryptographic X-Ray"**, navigating the full lifecycle:

```
DISCOVER → PROVE → INVENTORY → UNDERSTAND → ASSESS → PRIORITIZE → MIGRATE → VERIFY
```

### What ECDAT Is

- ✅ A **scanner-agnostic discovery and analysis framework** — external tools are pluggable adapters.
- ✅ An **evidence-first inventory system** — strict separation between raw empirical evidence and derived interpretations.
- ✅ A **CycloneDX 1.7 CBOM (Cryptographic Bill of Materials)** compliant platform.
- ✅ A **deterministic, explainable risk and role-aware PQC migration decision engine**.
- ✅ A **verification system** capable of diffing scans across commits to verify cryptographic retirement.

### What ECDAT Is NOT

- ❌ Not a quantum computer simulator.
- ❌ Not an encryption/decryption product or key manager.
- ❌ Not an opaque AI chatbot making unverified security decisions.
- ❌ Not a generic SAST scanner or dependency CVE checker.
- ❌ Not a one-click PQC code-rewriting tool.

---

## 🧩 Core Problem → Solution Mapping

| Problem | ECDAT Solution |
|---|---|
| **Hidden Cryptography** | **Crypto Discovery** — scans repos, ZIPs, local sources |
| **Unclear Risk** | **Context + Quantum Risk** — role-aware risk dimensions |
| **Uncertain migration order** | **P1–P4 Prioritization** — dependency-ordered planning |
| **No proof after migration** | **Re-scan & Verification** — diff before/after states |

---

## 🏗️ Technology Stack

| Layer | Technology |
|---|---|
| Web UI | React + TypeScript |
| Styling | Tailwind CSS |
| Backend | Python + FastAPI |
| Discovery | CryptoScan + Syft |
| Database | PostgreSQL |
| Deployment | Docker Compose |
| Analysis | ECDAT Core Engine |
| Output | CBOM, Risk Map, Reports |
| Migration | PQC / Hybrid recommendations |
| Verification | Re-scan + Compare |

---

## ⚙️ Working Features (Capability Classification)

### ✅ LIVE Capabilities

| Capability | Location | Description |
|:---|:---|:---|
| **ECDAT Core Engine** | `product/core/workflow/engine.py` | Real implementation, executed dynamically. Orchestrates the full scan → analyze → recommend pipeline. |
| **CryptoScan Adapter** | `product/core/ingestion/adapters/cryptoscan.py` | Real adapter parsing raw CryptoScan tool outputs to extract cryptographic findings. |
| **Syft Adapter** | `product/core/ingestion/adapters/syft.py` | Real adapter cataloging package-level software dependencies and SBOM evidence. |
| **CycloneDX 1.7 CBOM Serializer** | `product/core/cbom/serializer.py` | Generates standard-compliant Cryptographic Bill of Materials output. |
| **Phase 4A — PQC Target Mapper** | `product/core/migration/target_mapper.py` | Deterministic, role-aware mapping to NIST PQC standards (ML-KEM, ML-DSA, SLH-DSA). |
| **Phase 4B — Migration Scheduler** | `product/core/migration/scheduler.py` | Dependency-aware scheduler producing ordered, milestone-based migration plans. |
| **Demo Analyst Control Plane (9 Tabs)** | `demo/` | Complete 9-tab UI for analyst walkthroughs — see section below. |

### 🔬 Test Scenarios (Controlled Demo Fixtures)

| Scenario | Description |
|:---|:---|
| **TC-01: Direct RSA** | Benchmark fixture for a direct RSA key-establishment usage |
| **TC-02: Symmetric AES** | Benchmark fixture for symmetric AES encryption usage |
| **TC-06: Ed25519 Signature** | Benchmark fixture for an Ed25519 digital signature scheme |

### 🕐 ARCHITECTURAL / FUTURE (Not Yet Active)

| Capability | Reason Deferred |
|:---|:---|
| **Sonar Adapter** | Parser deferred; architectural boundary documented |
| **CodeQL Adapter** | Requires proprietary license; SARIF ingestion deferred |
| **sslscan2 Adapter** | Network TLS discovery deferred; GPLv3 isolation required |
| **Rescan Verification Engine** | Planned for Phase 9; not claimed as production capability |

---

## 🖥️ The 9-Tab Analyst Control Plane (Demo UI)

The demo presents a **complete Analyst Control Plane** accessible via 9 workflow tabs:

| Tab | Name | What It Shows |
|:---:|:---|:---|
| **1** | **Overview & Pipeline** | 5-step analyst journey, runtime evidence-to-migration trace, and project intellectual foundation |
| **2** | **Discovery & Adapters** | Execute controlled scenarios (TC-01, TC-02, TC-06); view live Ingestion Adapters registry with capability classifications |
| **3** | **Crypto Inventory** | Discovered cryptographic assets table with operational role, location, confidence, priority tier, PQC mapping, and review gate status |
| **4** | **Evidence Explorer** | 7-stage interactive runtime provenance chain: `Scanner → Raw Evidence → Finding → Crypto Asset → Risk → Migration Target → Schedule` |
| **5** | **Context & Risk** | Risk dimensions: Priority, Risk category, Cause, Classical status, Quantum exposure; authoritative rule citations (e.g., `R-RISK-06`) |
| **6** | **Migration Intelligence** | Role-aware PQC mapping (KEM vs Signatures vs Symmetric), FIPS 203/204/205 parameter sets, agility assessment |
| **7** | **Migration Plan** | Dependency-ordered milestones, agility blockers, advisory status notices |
| **8** | **Review Gates** | Human Review Gate Protocol visualizer, active gates, missing info, required triage actions |
| **9** | **Verification [Future]** | Post-migration verification boundary (Phase 9 projection), cryptographic diff delta schema |

---

## 🚀 How to Run the Demo

### Prerequisites

- Python 3.10+ installed and on your `PATH`
- All dependencies installed — from the project root run:
  ```bash
  pip install -r requirements.txt
  ```

### Step 1 — Launch the Demo Server

From the **project root** (`ECDAT-main/`), run:

```bash
python -m demo.backend.server --port 8080
```

Then open your browser and navigate to:

```
http://127.0.0.1:8080
```

---

### Step 2 — Demo Walkthrough (Tab by Tab)

#### 🟦 Tab 1 — Overview & Pipeline
- Land on the overview page to orient the audience.
- Point out the 5-step analyst journey and the evidence-to-migration trace diagram.

#### 🟩 Tab 2 — Discovery & Adapters
1. Select scenario **TC-01 (Direct RSA)** from the scenario selector.
2. Click **Run Discovery** to trigger the live core engine execution.
3. Observe the Ingestion Adapters registry — note which adapters are **LIVE** vs **ARCHITECTURAL/FUTURE**.

#### 🟨 Tab 3 — Crypto Inventory
- View the discovered cryptographic assets table.
- Point out columns: **Operational Role**, **Location**, **Confidence**, **Priority Tier** (P1–P4), **PQC Mapping**, and **Review Gate Status**.

#### 🟧 Tab 4 — Evidence Explorer
1. Click on any asset in the inventory to open its provenance chain.
2. Walk through the 7 interactive stages:
   `Scanner → Raw Evidence → Finding → Crypto Asset → Risk → Migration Target → Schedule`
3. Click on a node to inspect source code snippets and raw scanner outputs.

#### 🟥 Tab 5 — Context & Risk
- Show the **"What ECDAT Empirically Knows vs. What Is Not Established"** panel.
- Highlight the 5 risk dimensions and the authoritative rule citation (e.g., `R-RISK-06`).
- Emphasize that risk decisions are **deterministic and traceable** — never black-box.

#### 🟪 Tab 6 — Migration Intelligence
- Show the role-aware PQC mapping:
  - Key Exchange → **ML-KEM** (FIPS 203)
  - Digital Signatures → **ML-DSA / SLH-DSA** (FIPS 204/205)
  - Symmetric → Symmetric Review
- Point out the **agility assessment** (`HARDCODED` flag) and candidate hybrid schemes.

#### ⬛ Tab 7 — Migration Plan
- View dependency-ordered milestones.
- Point out agility blockers flagged as `CODE_REFACTOR_REQUIRED`.
- Show how the plan is advisory — no automated code patching is performed.

#### 🔷 Tab 8 — Review Gates
- Show the Human Review Gate Protocol visualizer.
- Point out the active gate (`GATE-REVIEW-26700200`) and the list of required analyst triage actions before migration proceeds.

#### ⚪ Tab 9 — Verification (Future)
- Show the Phase 9 boundary projection.
- Explain that after a migration, ECDAT will re-scan and diff the before/after cryptographic state to **verify** that vulnerable algorithms were actually replaced.

---

### Step 3 — Run the Test Suites (Optional, for Technical Judges)

```bash
# Run the complete demo test suite (34 tests: D1 + D2 + D3)
python -m unittest discover -s demo/tests

# Run the full frozen product test suite (300 tests)
python -m unittest discover -s product/tests
```

---

## 📊 Core Value Chain

```
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

---

## 📐 Development Principles

1. **Evidence Over Claims** — findings are meaningless without unambiguous evidence.
2. **Role-Aware Migration** — ML-KEM for key establishment, ML-DSA/SLH-DSA for signatures; universal replacement is rejected.
3. **Deterministic Risk Logic** — transparent, verifiable rule sets; no black-box models.
4. **Explicit Uncertainty** — clearly distinguishes `CONFIRMED`, `LIKELY`, `POSSIBLE`, `NEEDS_REVIEW`.
5. **Standardization** — aligned with CycloneDX 1.7 CBOM and NIST FIPS 203, 204, 205.
6. **Scanner Agnosticism** — external tools are pluggable adapters; swapping one doesn't touch the core.

---

## 🚧 Known Demo Limitations

- Controlled benchmark fixtures (`TC-01`, `TC-02`, `TC-06`) drive the demo; live arbitrary repository scanning is intentionally out of scope.
- No live code refactoring or automated source patching — remediation is advisory and plan-oriented.
- Enterprise RBAC, multi-tenant databases, and cloud infrastructure are deferred non-goals.

---

## 📁 Project Layout

```
ECDAT-main/
├── demo/                    # Full Analyst Control Plane Demo
│   ├── backend/             # FastAPI backend + server entry point
│   ├── frontend/            # HTML/JS/CSS demo UI (index.html, app.js, style.css)
│   ├── adapters/            # Adapter registry (live + architectural)
│   ├── scenarios/           # TC-01, TC-02, TC-06 benchmark fixtures
│   └── tests/               # 34 demo tests (D1 + D2 + D3)
├── product/                 # Authoritative Engineering Core (300 tests)
│   ├── core/                # ECDAT core engine, adapters, CBOM, risk, migration
│   ├── docs/                # Architecture, security model, threat model, decisions
│   └── benchmark/           # Ground-truth evaluation corpus
├── app.py                   # Root entry point
├── requirements.txt         # Python dependencies
└── README.md                # Root project constitution
```

---

*ECDAT — Team Twinks | SIH 2026 | Problem Statement SIH26164 | NTRO | Blockchain & Cybersecurity*
