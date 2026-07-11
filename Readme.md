# RegMind.ai

**Agentic Compliance: From Regulatory Text to Operational Action**

RegMind.ai is an autonomous, multi-agent compliance automation platform that bridges the gap between regulatory text and operational code. We transform how financial institutions understand, implement, and continuously verify compliance with SEBI and RBI regulations.

---

## The Problem

Financial institutions face two critical compliance challenges:

1. **Regulatory Translation Gap**: SEBI circulars are written in legal language, but implementation is executed by engineering teams. This creates manual overhead, inconsistent understanding, and higher risk of compliance errors.

2. **Continuous Compliance Burden**: Organizations must continuously track obligations, maintain audit evidence, and identify compliance gaps. Today, this is largely manual—especially challenging for smaller firms with limited compliance resources.

---

## The Solution

RegMind.ai deploys a **closed-loop compliance system** that functions as a continuous state machine:

- Ingests regulatory documents (master circulars & amendments)
- Classifies and extracts obligations automatically
- Translates legal text into precise developer specifications
- Generates actionable engineering tasks with evidence checklists
- Verifies code compliance in real-time
- Maintains a secure audit trail

Instead of manual compliance sign-offs, our **Verification Agent** acts as an automated auditor, cross-checking engineering work against regulatory mandates instantly.

---

## Architecture

RegMind.ai operates as a **three-layer agentic pipeline**:

### 1. **The Sorting Layer**
- **Step 1**: Automated document ingestion & filtering (Applicability Gate)
- **Step 2**: Master Circular ingestion with clause-by-clause parsing & obligation creation
- **Step 3**: Semantic filtering and operational routing (separates actionable from non-actionable items)

**Key Components**:
- Applicability Gate Agent: Determines document relevance to organization profile
- Document Classification Agent: Routes Master vs. Amendment circulars
- Domain-Trained LLM: Specialized in SEBI regulatory patterns
- Base Obligation Object: Standardized JSON container for each clause

### 2. **The Action Generation Layer**
- **Step 4**: Scheduling triage & action generation
- Converts obligations into engineering tasks with clear technical specifications
- Assigns urgency tiers: Urgent / Recurring / Conditional Tasks
- Creates evidence checklists for task verification

**Key Components**:
- Scheduling Controller Gate: Maps legal timelines to urgency levels
- Action Generation Engine: Acts as automated IT Project Manager
- Task Object: Provides `technical_spec_summary` + `evidence_checklist`

### 3. **The Continuous State Machine & Verification Layer**
- **Step 5**: Amendment ingestion & intent analysis
- **Step 6**: Dynamic modification routing (handles 4 task states: Open / Ongoing / Completed / Deprecated)
- **Step 7**: Automated evidence verification loop

**Key Components**:
- Structural Variation Gate: Detects if amendment adds or modifies existing rules
- Dynamic Modification State Machine: Routes updates based on live task status
- Verification Agent (AI Auditor): Validates engineering artifacts against regulatory mandates
- Interactive Chatbot Debugger: Guides engineers to fix compliance gaps instantly

---

## Tech Stack

**Frontend**:
- React with responsive UI for compliance dashboards

**Backend**:
- FastAPI (Python) for high-performance API endpoints

**AI & Agents Framework**:
- **Orchestration**: LangChain for multi-agent coordination
- **Models**: Llama 3 / Mistral (open-source, privacy-first)
- **Runtime**: Ollama / vLLM for private, local execution
- **Infrastructure**: Private AWS GPU servers (fully isolated corporate cloud)

**Data & Search**:
- MongoDB for obligation and task storage
- Pinecone for vector-based semantic search

**Document Processing**:
- PyMuPDF for PDF parsing & text extraction
- Tesseract OCR for scanned document processing

---

## Security & Privacy

**Zero-Retention Processing**
- Regulatory documents, source code, configs, and logs are analyzed only during compliance checks
- Never permanently stored or used to train AI models

**Automatic Data Masking**
- Passwords, API keys, customer details, and internal IPs masked before AI processing
- Only compliance-related content analyzed

**Secure Audit Trail**
- Every compliance activity logged with timestamps
- Complete traceability for regulatory audits

---

## Business Model (Revenue Streams)

1. **B2B SaaS Subscription**: Monthly/annual recurring fees (scales with users, firm size, document volume)
2. **On-Premise / Private Cloud Deployment**: One-time implementation fee for bank-hosted installations
3. **Usage-Based Pricing**: Pay per regulatory document processed, AI request, or compliance task
4. **Enterprise Support & Maintenance**: 24/7 support, security patches, regulatory updates
5. **Custom Integrations**: Paid integration with Jira, ServiceNow, ERP systems

---

## Key Differentiators

- **Agentic Autonomy**: No manual compliance sign-offs—agents verify work automatically
- **State Machine Intelligence**: Understands live task status and routes amendments intelligently
- **Privacy-First**: All processing happens in customer's private cloud; zero data retention
- **Domain-Specialized**: LLM trained specifically on SEBI/RBI regulatory patterns
- **Real-Time Audit Trail**: Immutable record for regulatory demonstrations
- **Developer-Friendly**: Converts legal text to clear technical specifications with evidence checklists

---

## Team

**Team Square** — SEBI Securities Market TechSprint 2026

- **Anshu Roy** (Team Leader) — Engineering Physics, NIT Hamirpur | Full-Stack SDE
- **Aayush Dubey** — Co-Founder | Domain Expertise

---

## Current Status

**Idea Submission Round** — Conceptual architecture and business model validated.

**Roadmap**:
- [ ] Phase 1: Proof-of-concept with real SEBI circulars (Q3 2026)
- [ ] Phase 2: Beta deployment with pilot financial institution (Q4 2026)
- [ ] Phase 3: Enterprise SaaS launch (Q1 2027)
- [ ] Phase 4: RBI regulation support & multi-regulator expansion (2027)

---

## Getting Started (Conceptual)

This is an **idea-stage submission**. Once development begins, the repository structure will include:

```
regmind-ai/
├── frontend/              # React compliance dashboard
├── backend/               # FastAPI compliance engine
├── agents/                # LangChain agent orchestration
│   ├── sorting_layer/
│   ├── action_generation/
│   └── verification_layer/
├── models/                # Domain-trained LLMs
├── database/              # MongoDB schemas & Pinecone setup
├── docs/                  # Architecture & API docs
└── README.md
```

---

## How It Works (End-to-End Flow)

```
SEBI Circular Uploaded
         ↓
  Applicability Gate (Agent 1)
    ├─→ YES: Extract PDF → Text
    └─→ NO: Skip
         ↓
  Classification Agent (Agent 2)
    ├─→ Master Circular: Parse clause-by-clause
    └─→ Amendment: Compare against baseline
         ↓
  Obligation Creation (Domain LLM)
    └─→ Create standardized JSON objects
         ↓
  Semantic Routing Agent
    ├─→ Actionable Items → Action Generation Layer
    └─→ Non-Actionable → Reference Library
         ↓
  Action Generation Engine
    └─→ Create engineering tasks with evidence checklists
         ↓
  Developer Executes Task
    └─→ Uploads technical evidence
         ↓
  Verification Agent (AI Auditor)
    ├─→ PASS: Auto-mark task complete
    └─→ FAIL: Trigger Interactive Debugger
         ↓
  Secure Audit Trail Updated
    └─→ Real-time compliance dashboard
```

---

## Contact & Contributions

**Team Lead**: Anshu Roy  
**Email**: 24bph025@nith.ac.in  
**Phone**: +91 77383 85936  

**Collaborator**: Aayush Dubey  
**Email**: dubeyaayushop@gmail.com

For inquiries, partnership opportunities, or to discuss regulatory use cases, reach out to the team above.

---

## License

This project is submitted to the SEBI Securities Market TechSprint 2026 competition. Licensing details to be finalized upon advancement.

---

## Acknowledgments

- SEBI TechSprint 2026 for the opportunity to innovate in regulatory technology
- NIT Hamirpur Engineering Physics Department for foundational knowledge
- Open-source community (LangChain, Ollama, Llama, Mistral, FastAPI)

---

**RegMind.ai: Making Compliance Code, Not Paperwork.**