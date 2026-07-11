# RegMind.ai

**Agentic Compliance: From Regulatory Text to Operational Action**

RegMind.ai is an autonomous, multi-agent compliance automation platform that bridges the gap between regulatory text and operational code. We transform how financial institutions understand, implement, and continuously verify compliance with SEBI and RBI regulations.

---

## The Problem

Financial institutions face two critical compliance challenges:

**The Challenge of Regulatory Translation**

Every time SEBI releases a new circular, amendment, or master circular, financial institutions must quickly understand what has changed and implement those changes in their internal systems. However, these regulations are written in legal language, while the implementation is carried out by software and engineering teams. This creates a communication gap that relies heavily on manual interpretation by compliance and legal teams, resulting in slower implementation, inconsistent understanding, and a higher risk of compliance errors.

**The Challenge of Continuous Compliance**

Implementing a regulation is only the first step. Organizations must continuously ensure that their systems, processes, and operational evidence remain compliant as regulations evolve. Today, this process is largely manual, making it difficult to track obligations, maintain audit evidence, and identify compliance gaps before they become regulatory issues. Smaller firms face an even greater challenge due to limited compliance resources, making continuous monitoring and audit readiness both time-consuming and inefficient.

---

## The Solution

Our solution bridges the gap between raw legal text and operational code by deploying an autonomous, multi-agent pipeline. Instead of relying on manual oversight, the system functions as a continuous state machine that ingests regulatory text, classifies it, translates it into precise developer specifications, and automatically verifies engineering work against the law.

### The Agentic Architecture

RegMind.ai operates through **three primary agentic layers**:

1. **The Sorting Layer** — Document ingestion, applicability filtering, and classification
2. **The Action Generation Layer** — Task creation with scheduling and urgency triage
3. **The Continuous State Machine & Verification Layer** — Amendment handling and automated evidence validation

```
                    Closed-Loop Compliance System
                              ↓
                    Primary Agentic Layers
                              ↓
                    ┌─────────────────────┐
                    │ Upload SEBI Circular │
                    └──────────────┬──────┘
                                   ↓
                    ┌──────────────────────────┐
                    │  The Sorting Layer       │
                    │  (Steps 1-3)             │
                    │  • Applicability Gate    │
                    │  • Classification       │
                    │  • Semantic Filtering   │
                    └──────────────┬───────────┘
                                   ↓
                    ┌──────────────────────────┐
                    │ Action Generation Layer  │
                    │  (Step 4)                │
                    │  • Scheduling Triage     │
                    │  • Task Creation         │
                    │  • Evidence Checklists   │
                    └──────────────┬───────────┘
                                   ↓
                    ┌──────────────────────────────────┐
                    │ Continuous State Machine &       │
                    │ Verification Layer (Steps 5-7)   │
                    │  • Amendment Handling            │
                    │  • Dynamic Routing               │
                    │  • Automated Verification        │
                    └──────────────┬───────────────────┘
                                   ↓
                    ┌──────────────────────────┐
                    │ Compliance Dashboard     │
                    │ Real-Time Updates        │
                    └──────────────────────────┘
```

---

## Detailed 7-Step Flow Diagram

```
STEP 1: UPLOAD & INGESTION
┌────────────────────────┐
│  Upload SEBI Circular  │
└───────────┬────────────┘
            ↓
      ┌─────────────┐
      │  Agent 1    │  → Applicability Gate: Does it apply to you?
      └─────┬───────┘
            ├─→ YES: Extract PDF text
            └─→ NO: Skip
            ↓
      ┌─────────────┐
      │  Agent 2    │  → Document Classification: Master or Amendment?
      └─────┬───────┘
            ├─→ Master Circular Flow
            └─→ Amendment Circular Flow

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 2: MASTER CIRCULAR INGESTION & STRUCTURAL TRIAGE
┌──────────────────────────┐
│ Master Circular Track    │
└───────────┬──────────────┘
            ↓
   Parse Entire Document
   Clause-by-Clause
            ↓
   ┌─────────────┐
   │ Domain LLM  │  → Specialized SEBI Pattern Recognition
   └──────┬──────┘
          ↓
  Create Base Obligation
  Object (JSON)
  • obligation_id
  • section_reference
  • raw_clause_text
  • metadata
          ↓
   ┌─────────────┐
   │  Agent 3    │  → Binary Classification: Actionable or Not?
   └─────┬───────┘
         ├─→ Actionable Item (Technical/Non-Technical)
         └─→ Non-Actionable (Prohibitive/Governance/Informational)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 3: SEMANTIC FILTERING & OPERATIONAL ROUTING
            ↓
      ACTIONABLE ITEMS         NON-ACTIONABLE ITEMS
            ↓                           ↓
   ┌────────────────┐         ┌────────────────────┐
   │ Technical      │         │ Reference Library  │
   │ Actions        │         │ (Immutable)        │
   │ (IT/Systems)   │         ├─ Prohibitive      │
   │ OR             │         ├─ Governance       │
   │ Non-Technical  │         └─ Informational    │
   │ (Business)     │
   └────────┬───────┘
            ↓
   Routes to Developer
   Pipeline (Step 4)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 4: SCHEDULING TRIAGE & ACTION GENERATION
┌──────────────────────────────┐
│ Technical IT Action          │
│ (From Step 3)                │
└───────────┬──────────────────┘
            ↓
   ┌──────────────────┐
   │ Scheduling Agent │  → Assign Urgency Tier
   └─────────┬────────┘
             ├─→ URGENT (Immediate deadline)
             ├─→ RECURRING (Weekly/Monthly/Quarterly)
             └─→ CONDITIONAL (Triggered by events)
             ↓
   ┌──────────────────────────┐
   │ Action Generation Engine │  → Code-Friendly Translation
   │ (LLM as IT Project Mgr)  │
   └─────────┬────────────────┘
             ↓
    Create Engineering Task
    • technical_spec_summary
    • evidence_checklist
    • measurable criteria
             ↓
   ┌─────────────────┐
   │ Task Ready for  │  → Ready for Developer Assignment
   │ Developer       │
   └─────────────────┘

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 5: AMENDMENT INGESTION & INTENT ANALYSIS
┌──────────────────────────┐
│ Amendment Circular Track │
│ (From Step 1)            │
└───────────┬──────────────┘
            ↓
   ┌─────────────┐
   │ Domain LLM  │  → Parse Amendment Clauses
   └──────┬──────┘
          ↓
   ┌──────────────────────┐
   │ Structural Variation │  → Evaluate Impact on Baseline
   │ Gate (Agent)         │
   └──────────┬───────────┘
              ├─→ ADDING A NEW CLAUSE
              │   (Simple additive path)
              └─→ MODIFYING AN EXISTING CLAUSE
                  (Complex state-altering path)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 6: AMENDMENT STATE MACHINE & DYNAMIC ROUTING
┌───────────────────────────────────────────┐
│ For EACH Modified or New Clause:          │
│ Check Live Status of Original Task        │
└─────────────────┬───────────────────────┘
                  ↓
        ┌─────────────────────┐
        │ Action vs Non-Action │
        │ Check (Agent)        │
        └────────┬─────────────┘
                 ↓
      ACTIVE TECHNICAL TASK
                 ↓
    ┌────────────────────────────────┐
    │ Dynamic Modification State      │
    │ Machine: Where is the task NOW? │
    └────────────┬───────────────────┘
                 │
    ┌────────────┼────────────┬──────────────┬─────────────┐
    ↓            ↓            ↓              ↓             ↓
  OPEN       ONGOING       COMPLETED    REMOVE PREV
  (Unassigned) (In Progress) (Deployed)   REQUIREMENT
    │            │            │              │
    ↓            ↓            ↓              ↓
OVERWRITE    HALT & ALERT  CREATE DELTA  DEPRECATE
SPEC        ENGINEER      TASK          TICKET
    │            │            │              │
    └────────────┴────────────┴──────────────┘
                 ↓
      Task Updated/Routed
      to Developer

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

STEP 7: AUTOMATED EVIDENCE VERIFICATION LOOP
┌────────────────────────────────┐
│ IT Department Executes Task    │
│ & Uploads Evidence             │
│ (config, code, logs, payloads) │
└───────────────┬────────────────┘
                ↓
        ┌───────────────────┐
        │ Verification      │
        │ Agent (AI Auditor)│  → Cross-check Evidence vs Law
        └────────┬──────────┘
                 │
        ┌────────┴────────┐
        ↓                 ↓
    CORRECT          INCORRECT
    (100% match)      (Incomplete/Errors)
        │                 │
        ↓                 ↓
   AUTO-MARK         TRIGGER
   COMPLETED      INTERACTIVE
        │         CHATBOT DEBUGGER
        │              │
        ↓              ↓
   DASHBOARD      Engineer Gets
   UPDATE          Exact Feedback
   (Real-time)      on What's Missing
        │              │
        ↓              ↓
   ┌──────────────┐  ┌──────────┐
   │ COMPLIANCE   │  │ Developer│
   │ VERIFIED     │  │ Fixes    │
   │ AUDIT TRAIL  │  │ Re-submits
   │ LOGGED       │  └──────┬───┘
   └──────────────┘         │
                            └─→ Back to Verification Agent
                                (Loop continues)
```

---

## End-to-End Workflow: 7-Step Pipeline

### **Step 1: Upload & Automated Document Ingestion**

When a SEBI circular is uploaded, the platform immediately begins processing:

- **The Applicability Gate (Agent 1)**: Analyzes the circular against your firm's profile. If the document doesn't apply to your specific market entity, it's skipped entirely to prevent processing overhead.
- **Text Extraction**: The pipeline extracts raw text from the PDF container for downstream analysis.
- **The Document Classification Gate (Agent 2)**: Routes the circular into one of two tracks—Master Circular (to build baseline rulebook) or Amendment Circular (to update existing obligations).

---

### **Step 2: Master Circular Ingestion & Structural Triage**

Once routed to the Master Circular track, the pipeline initializes deep clause-by-clause breakdown:

- **Clause-by-Clause Parsing**: The system extracts unstructured text and systematically tokenizes the entire document into individual atomic clauses based on numerical and legal paragraph structures.
- **The Domain-Trained Core**: Each clause is passed through an LLM highly specialized in SEBI regulatory patterns. The model acts as an analytical engine that maps the contextual intent of each regulation.
- **The Base Obligation Object**: For every clause, the system dynamically constructs a standardized JSON data container. This object securely locks down permanent metadata including unique obligation ID, section references, timestamps, and original raw legal text.
- **The Ingestion Agent Routing**: This structured baseline object is handed to the next downstream agent for binary classification—is this clause actionable or purely informational?

---

### **Step 3: Semantic Filtering and Operational Routing**

At this stage, the pipeline splits into two distinct routing streams:

**The Actionable Tracking Track:**
When a clause is flagged as an active obligation, a specialized categorization agent separates:
- **Technical Actions (IT/Systems)** — Engineering requirements that route directly to the developer pipeline
- **Non-Technical Actions** — Business workflows or compliance paperwork handled separately

**The Non-Actionable Reference Track:**
Clauses that don't require explicit operational task execution are organized into an immutable legal lookup library:
- **Prohibitive**: Strict restrictions and boundary definitions (what the system must avoid)
- **Governance**: Structural and procedural guidelines (long-term planning framework)
- **Informational**: Pure reference material and definitions (audit defense documentation)

---

### **Step 4: Scheduling Triage and Action Generation**

Once a clause is isolated as a Technical IT Action, the pipeline shifts from compliance routing to engineering execution:

- **The Scheduling Controller Gate**: An agent assesses legal timelines and trigger conditions, assigning each obligation a specific urgency tier:
  - **Urgent**: Core requirements with mandatory deadlines demanding immediate development
  - **Recurring**: Periodic operations (e.g., log rotations, quarterly validations) configured into recurring schedules
  - **Conditional Tasks**: Latent requirements hidden until an active platform event triggers them

- **The Action Generation Engine**: Acts as an automated IT Project Manager and System Architect. It translates legal intent into a deterministic, code-friendly framework.

- **The Engineering Task Creation**: The pipeline constructs an operational Task Object with a clear `technical_spec_summary` alongside a pre-defined, measurable `evidence_checklist` (e.g., configuration file updates, simulation logs) required for compliance verification.

---

### **Step 5: Amendment Ingestion & Intent Analysis**

When a document takes the Amendment Circular path, the system switches from baseline construction to dynamic update:

- **Targeted Clause Analysis**: Amendment text is fed into the domain-trained LLM layer, which breaks down specific update provisions into individual clauses.

- **The Structural Variation Gate**: A specialized routing agent evaluates each clause's impact on the existing baseline, executing a structural split:
  - **Adding a New Clause**: Simple additive path where the amendment introduces a brand-new requirement with no interference to old rules
  - **Modifying an Existing Clause**: Complex state-altering path where the amendment overrides, replaces, or alters a baseline rule already stored in the engine

---

### **Step 6: Amendment State Machine & Dynamic Modification Routing**

This is where our system operates as a true state machine. Instead of simply dumping an amendment onto a developer's dashboard, the amendment agents evaluate the **live status** of the original baseline task and dynamically route the update based on its operational state:

- **The Action vs. Non-Action Check**: Agents first run a triage scan to split simple non-actionable administrative edits from active technical engineering actions.

- **The Dynamic Modification State Machine**: When an active engineering requirement is modified, the agent maps it against the live task in your developer environment, resolving across four distinct scenarios:

  - **Previous Task is Open**: If the original task sits unassigned in the backlog, the agent cleanly intercepts and overwrites the technical specification payload
  - **Previous Task is Ongoing**: If a developer is actively coding, the system halts the task, alerts the engineer via dashboard, and delivers newly modified requirements to their active workspace
  - **Previous Task is Completed**: If code is already in production, the agent treats this as a new change request, spawning an isolated "delta" task to update production without breaking the baseline
  - **Remove Previous Technical Requirement**: If the amendment cancels a prior rule, the agent automatically deprecates the ticket and archives it to prevent redundant development work

---

### **Step 7: Automated Evidence Verification Loop**

Once a technical task is assigned, the IT Department executes development work. Instead of manual compliance sign-off, our Verification Agent acts as an automated auditor:

**The Execution & Validation Pipeline:**

- **IT Execution & Submission**: The IT Department completes the task based on generated specifications and uploads required technical evidence (config files, code snippets, logs, API payloads) to the platform.

- **The Verification Agent (AI Auditor)**: A specialized LLM agent trained to evaluate engineering artifacts against original regulatory mandates. It instantly processes uploaded evidence to verify compliance.

**Branch A: The Success Path (Correct)**
If evidence meets 100% of criteria, the Verification Agent automatically marks the task as completed and updates the organization's compliance dashboard in real time.

**Branch B: The Correction Path (Incorrect/Incomplete)**
If evidence falls short or contains errors, the system doesn't just reject it. It triggers an **Interactive Chatbot Debugger** that acts as an AI pair-programmer, telling the engineer exactly what is missing or wrong so they can fix it instantly.

---

## Tech Stack

**Frontend:**
- React with responsive UI for compliance dashboards

**Backend:**
- FastAPI (Python) for high-performance API endpoints

**AI & Agents Framework:**
- **Orchestration**: LangChain for multi-agent coordination
- **Models**: Llama 3 / Mistral (open-source, privacy-first)
- **Runtime**: Ollama / vLLM for private, local execution
- **Infrastructure**: Private AWS GPU servers (fully isolated corporate cloud)

**Data & Search:**
- MongoDB for obligation and task storage
- Pinecone for vector-based semantic search

**Document Processing:**
- PyMuPDF for PDF parsing & text extraction
- Tesseract OCR for scanned document processing

---

## Security & Privacy

**Zero-Retention Processing**
Regulatory documents, source code, configs, and logs are analyzed only during compliance checks. They're never permanently stored or used to train AI models.

**Automatic Data Masking**
Passwords, API keys, customer details, and internal IPs are masked before AI processing. Only compliance-related content is analyzed.

**Secure Audit Trail**
Every compliance activity is securely logged with timestamps—from document ingestion through task generation, evidence verification, and final approval. This creates a complete audit trail that helps organizations demonstrate compliance while protecting their internal systems and technical assets.

---

## Business Model (Revenue Streams)

1. **B2B SaaS Subscription**: Monthly/annual recurring fees based on users, firm size, and document volume
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
- **Aayush Dubey** (Co-Founder) — Domain Expertise

---

## Current Status

**Idea Submission Round** — Conceptual architecture and business model validated.

**Roadmap**:
- [ ] Phase 1: Proof-of-concept with real SEBI circulars (Q3 2026)
- [ ] Phase 2: Beta deployment with pilot financial institution (Q4 2026)
- [ ] Phase 3: Enterprise SaaS launch (Q1 2027)
- [ ] Phase 4: RBI regulation support & multi-regulator expansion (2027)

---

## Repository Structure (Planned)

Once development begins:

```
regmind-ai/
├── frontend/              # React compliance dashboard
├── backend/               # FastAPI compliance engine
├── agents/                # LangChain agent orchestration
│   ├── sorting_layer/     # Applicability & classification agents
│   ├── action_generation/ # Scheduling & task creation
│   └── verification_layer/# Evidence validation & audit
├── models/                # Domain-trained LLMs (Llama/Mistral)
├── database/              # MongoDB schemas & Pinecone vector configs
├── docs/                  # Architecture & API documentation
└── README.md
```

---

## Contact & Contributions

**Team Lead**: Anshu Roy  
**Email**: 24bph025@nith.ac.in  
**Phone**: +91 7738385936  

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
