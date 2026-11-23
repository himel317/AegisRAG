# AegisRAG
### AegisRAG is an AI-powered security framework for detecting prompt injection and data poisoning attacks in Retrieval-Augmented Generation (RAG) systems, featuring intelligent threat detection, secure retrieval, and explainable security analysis.

<p align="center">
  <strong>Securing AI. Protecting Knowledge. Building Trust.</strong>
</p>

<p align="center">
  An AI-powered cybersecurity framework designed to detect and prevent Prompt Injection and Data Poisoning attacks in Retrieval-Augmented Generation (RAG) systems.
</p>

---

## Overview

**AegisRAG** is an AI-powered cybersecurity framework developed to strengthen the security and reliability of Retrieval-Augmented Generation (RAG) systems.

As Large Language Models increasingly depend on external knowledge sources, RAG architectures become vulnerable to malicious prompts, manipulated documents, indirect instructions, and knowledge-base poisoning.

AegisRAG addresses these challenges through a multi-layered security architecture that analyzes incoming prompts, examines knowledge-base documents, protects retrieval operations, and provides explainable threat assessments.

The framework primarily focuses on two critical security domains:

- **Prompt Injection Detection and Prevention**
- **Knowledge Base Data Poisoning Detection and Prevention**

AegisRAG combines machine learning, semantic analysis, heuristic security rules, transformer-based classification, secure document ingestion, and explainable AI to improve RAG security.

---

## Key Features

### 1. Prompt Injection Detection — 3-Tier Engine

AegisRAG uses a three-tier detection architecture.

| Tier | Detection Method |
|---|---|
| Tier 1 | Heuristics and Regex-Based Security Rules |
| Tier 2 | TF-IDF with Logistic Regression / SVM |
| Tier 3 | DistilBERT Transformer Classifier |

Key capabilities:

- Direct prompt injection detection.
- System instruction override detection.
- Context-aware filtering to reduce false positives.
- Multilingual attack pattern detection.
- Bangla and Banglish security rules.
- Risk scoring and automated security decisions.

### 2. Data Poisoning Detection — 5-Layer Engine

The knowledge-base security engine analyzes documents through five detection layers.

| Layer | Detection Method |
|---|---|
| Layer 1 | SHA-256 and MinHash Provenance Analysis |
| Layer 2 | Semantic Anomaly Detection and Isolation Forest |
| Layer 3 | Factual Contradiction Checking |
| Layer 4 | Backdoor and Trigger Scanner |
| Layer 5 | Indirect Prompt Injection Detection |

Additional capabilities:

- Duplicate and near-duplicate analysis.
- Suspicious document identification.
- Structured document audit records.
- Version-update and malicious-poisoning differentiation.
- Risk assessment and quarantine decisions.

### 3. Secure Document Ingestion

AegisRAG supports document ingestion through:

- PDF files.
- TXT files.
- Markdown files.

The ingestion workflow includes:

1. Document upload and validation.
2. File-type and content verification.
3. Security scanning.
4. Risk assessment.
5. Trusted document indexing or quarantine isolation.

Clean documents are indexed in the trusted ChromaDB collection, while suspicious documents are isolated in the quarantine collection.

### 4. Quarantine Vault & Retrieval Isolation

AegisRAG maintains separate vector collections:

- `trusted_documents`
- `quarantine_documents`

Suspicious or poisoned documents are prevented from entering the trusted retrieval workflow.

The project evaluation reports **0.0% retrieval leakage** in the tested quarantine-isolation scenarios.

### 5. Dual-Core Security Dashboard

The main workspace uses a two-panel security interface.

**Core 01 — Prompt Injection Detection**

- Prompt input interface.
- Benign and malicious test presets.
- One-click security analysis.
- Real-time risk assessment.
- Detection explanations.

**Core 02 — Data Poisoning Detection**

- Document drag-and-drop upload.
- Text-based document scanning.
- Poisoning test presets.
- Document risk assessment.
- Quarantine management.

Each result provides:

- Security status: SAFE, SUSPICIOUS, or MALICIOUS.
- Risk score from 0–100.
- Recommended action.
- Detection explanation.
- Triggered rules and detection layers.
- Processing latency.

### 6. Explainable AI (XAI)

AegisRAG provides explainability capabilities to help users understand security decisions.

The system supports investigation-oriented explanations and detection analysis to improve transparency and security auditing.

### 7. Defense-Grounded RAG Chatbot

A secure RAG chatbot demonstrates retrieval and response generation while incorporating security validation into the pipeline.

### 8. System Telemetry

The dashboard provides security-related operational information, including detection activity, system events, and processing metrics.

### 9. Multilingual Threat Analysis

The detection system includes security rules and testing support for:

- English.
- Bangla.
- Banglish.
- Selected European languages.

---

## System Architecture

```text
                  USER INPUT
                      |
                      v
             PROMPT SECURITY ENGINE
                  (3 TIERS)
                      |
                      v
              SECURITY DECISION
                      |
                      v
              SECURE RAG PIPELINE
                      |
                      v
             DOCUMENT RETRIEVAL
                      |
                      v
             DATA POISONING ENGINE
                  (5 LAYERS)
                      |
              +-------+-------+
              |               |
              v               v
           TRUSTED         QUARANTINE
          DOCUMENTS         VAULT
              |
              v
          LLM GENERATION
              |
              v
         OUTPUT VALIDATION
              |
              v
          EXPLAINABLE AI
              |
              v
       SECURITY EVENTS & TELEMETRY
```

*Conceptual architecture. Refer to the source code for the complete implementation.*

---

## Technology Stack

| Category | Technologies |
|---|---|
| Backend | Python, FastAPI, Uvicorn |
| Frontend | React 18, Vite |
| Styling | Tailwind CSS |
| Database | SQLite, SQLAlchemy, aiosqlite |
| Vector Database | ChromaDB |
| Machine Learning | PyTorch, Scikit-learn |
| NLP | Hugging Face Transformers |
| Embeddings | Sentence Transformers |
| Classification | DistilBERT, TF-IDF, Logistic Regression, SVM |
| Generative AI | Google Gemini API |
| Visualization | Recharts |
| Testing | Pytest |

---

## Research & Experimental Evaluation

AegisRAG has undergone empirical evaluation using dedicated benchmark datasets and adversarial security testing.

### Benchmark Dataset Summary

| Dataset | Samples |
|---|---:|
| Prompt Injection | 1,862 |
| Data Poisoning | 1,600 |
| Adversarial Red-Teaming | 800 |
| **Total** | **4,262** |

Additional external out-of-distribution evaluation data was also used.

### Reported Model Performance

| Metric | Result |
|---|---:|
| Model Accuracy | 92.53% |
| Precision | 96.30% |
| Recall | 91.20% |
| F1-Score | 93.68% |

### Security Evaluation Results

| Evaluation | Result |
|---|---:|
| Overall Defense Rate | 98.75% |
| Attacks Blocked | 633 / 641 |
| Retrieval Leakage | 0.0% |
| Average Ingress Latency | 14.5 ms |

**Research interpretation:**

- Overall Defense Rate represents the reported attack-blocking result for the evaluated 641 attack cases.
- Model classification metrics and overall defense rate represent different evaluation measurements.
- Retrieval leakage refers to the tested quarantine-isolation scenarios.
- Average ingress latency represents the reported measurement under the tested environment.
- These results should be interpreted within their respective experimental datasets, configurations, and evaluation protocols.

Detailed benchmark methodology, dataset provenance, split definitions, and reproducibility instructions should be consulted alongside the research artifacts.

---

## Installation & Setup

### Prerequisites

- Python 3.11+
- Node.js 20+
- npm 10+
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/himel317/AegisRAG.git
cd AegisRAG
```

### 2. Backend Environment

```bash
python -m venv backend/venv
```

Activate on Windows:

```bash
backend\venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r backend/requirements.txt
```

### 3. Environment Configuration

Create a local `.env` file based on `.env.example`.

Configure the required environment variables and AI provider credentials.

Never commit real API keys, passwords, or authentication secrets.

### 4. Start Backend

From the project root:

```bash
python -m uvicorn backend.app.main:app --host 127.0.0.1 --port 8000 --reload
```

Backend:

`http://127.0.0.1:8000`

API Documentation:

`http://127.0.0.1:8000/docs`

### 5. Start Frontend

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

Frontend:

`http://localhost:5173`

*Commands should be adjusted if the actual repository configuration differs.*

---

## Project Structure

```text
AegisRAG/
│
├── backend/
│   ├── app/
│   ├── tests/
│   └── requirements.txt
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── README.md
├── SECURITY.md
├── .gitignore
└── .env.example
```

*Illustrative structure. Actual repository contents may vary.*

---

## Security Considerations

AegisRAG incorporates security-oriented mechanisms such as:

- JWT-based authentication.
- Role-Based Access Control.
- Password hashing.
- API request validation.
- Rate limiting.
- Security response headers.
- File upload validation.
- Document quarantine isolation.
- Security event logging.

The application should undergo independent security testing before production deployment.

---

## Current Development Status

**Status: Active Research & Development**

AegisRAG is being developed as an academic research and engineering project.

Current development focuses on improving:

- Detection accuracy and robustness.
- False-positive reduction.
- Multilingual threat analysis.
- Retrieval security.
- Explainability.
- User experience.
- System performance and reliability.

---

## Future Research Directions

- Improved multilingual semantic detection.
- Advanced out-of-distribution calibration.
- Stronger factual contradiction detection.
- Enhanced adversarial robustness.
- Scalable knowledge-base security.
- Extended independent benchmark evaluation.
- Further optimization of detection latency.

---

## Author

**Md. Abul Hasnat Himel**

Software Engineering & Cybersecurity  
Daffodil International University (DIU)

GitHub: [@himel317](https://github.com/himel317)

---

## Academic Disclaimer

AegisRAG is developed for academic research, experimentation, and educational purposes.

Reported results are based on specific experimental configurations and datasets. They do not guarantee equivalent performance in all real-world environments.

The project is not independently security-certified and should not be considered production-ready without further validation.

---

<p align="center">
  <strong>AegisRAG — Securing the Intelligence Behind RAG.</strong>
</p>
