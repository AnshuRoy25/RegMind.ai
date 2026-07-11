# RegMind.ai

## Agentic Compliance: From Regulatory Text to Operational Action

RegMind.ai is an AI-powered compliance platform built for financial institutions. It helps organizations convert complex SEBI and RBI regulations into clear engineering tasks, making compliance faster, more accurate, and much easier to manage.

Instead of relying on teams to manually interpret lengthy circulars, RegMind.ai reads regulatory documents, identifies what actually applies to your organization, generates implementation tasks, and continuously verifies whether those requirements have been met.

---

# The Problem

Financial institutions deal with two major compliance challenges.

### Understanding Regulations

Whenever SEBI or RBI publishes a new circular, amendment, or master circular, companies have to quickly understand what has changed and update their internal systems. The problem is that regulations are written in legal language, while implementation is handled by software engineers.

This creates a communication gap where compliance teams spend hours interpreting legal documents before developers can even begin their work. The process is slow, heavily manual, and different teams often interpret the same regulation differently, increasing the risk of compliance mistakes.

### Staying Compliant Over Time

Implementing a regulation once isn't enough. Regulations keep changing, which means organizations need to constantly monitor their systems and verify that they're still compliant.

Today, this usually involves spreadsheets, manual audits, and collecting evidence from multiple teams. It's time-consuming, difficult to track, and especially challenging for smaller organizations that don't have dedicated compliance teams.

---

# The Solution

RegMind.ai closes the gap between legal regulations and engineering execution through an AI-driven multi-agent workflow.

Instead of expecting people to manually translate legal documents into technical requirements, the platform automates the entire process. It reads regulatory documents, identifies applicable obligations, converts them into developer-friendly tasks, tracks amendments, and verifies implementation using AI.

The goal isn't to replace compliance teams—it's to remove repetitive manual work so they can focus on higher-value decisions.

---

# Agentic Architecture

The platform is organized into three major layers, each responsible for a different stage of the compliance lifecycle.

### 1. Sorting Layer

The first layer receives regulatory documents, checks whether they actually apply to the organization, extracts their content, and classifies them before any detailed processing begins.

### 2. Action Generation Layer

Once actionable obligations have been identified, this layer converts them into structured engineering tasks. It prioritizes work, assigns urgency, and prepares clear implementation requirements for developers.

### 3. Continuous Verification Layer

The final layer continuously monitors regulatory updates and validates engineering work against the original legal requirements. Whenever regulations change, the system automatically updates existing tasks instead of forcing teams to start from scratch.

---

# End-to-End Workflow

## Step 1 — Upload & Document Ingestion

Everything begins when a regulatory document is uploaded to the platform.

The first AI agent checks whether the circular actually applies to the organization. If it doesn't, the document is ignored, saving both time and processing resources.

For applicable documents, the system extracts the text from the PDF and classifies it as either a **Master Circular** or an **Amendment Circular**. This decision determines which workflow the document will follow.

---

## Step 2 — Master Circular Processing

If the document is identified as a Master Circular, the platform begins building the organization's baseline compliance rulebook.

The document is broken down into individual clauses so that every requirement can be analyzed independently.

Each clause is then passed through a domain-specific language model trained on SEBI regulations. Instead of simply summarizing the text, the model understands the intent behind every clause and extracts meaningful compliance obligations.

For every obligation, RegMind.ai creates a structured JSON object containing details such as the clause ID, section reference, timestamps, and the original legal text.

These structured objects become the foundation for all future compliance tracking.

---

## Step 3 — Identifying Actionable Requirements

Once every clause has been processed, the platform determines whether it requires action or is simply informational.

Actionable clauses are divided into two categories.

The first includes technical requirements that need engineering work, such as system changes, configurations, or software updates.

The second contains business or operational tasks that belong to compliance or management teams rather than developers.

Clauses that don't require direct action are still valuable, so they're stored as searchable reference material. These include governance guidelines, regulatory definitions, and prohibitive rules that help during audits or future regulatory analysis.

---

## Step 4 — Generating Engineering Tasks

Once a clause is identified as a technical requirement, the platform shifts from compliance analysis to execution planning.

An AI scheduling agent first looks at the regulatory timeline and decides how urgent the task is. Based on the requirement, each task is classified as one of the following:

- **Urgent** — Requirements that have strict regulatory deadlines and need immediate implementation.
- **Recurring** — Activities that must be performed on a regular basis, such as quarterly validations or periodic reporting.
- **Conditional** — Tasks that only become active when a specific business event or system trigger occurs.

After prioritization, the Action Generation Engine translates the legal requirement into a clear technical specification.

Instead of handing developers a legal document, the system generates a structured engineering task that explains exactly what needs to be built, modified, or verified. It also creates an evidence checklist describing what developers must submit later to prove that the requirement has been implemented correctly.

---

## Step 5 — Processing Regulatory Amendments

Amendment circulars follow a slightly different workflow.

Instead of building a new compliance baseline, the platform compares every amendment against the organization's existing obligations.

The document is first broken down into individual clauses, just like a Master Circular. Each clause is then analyzed to understand whether it introduces a completely new requirement or changes an existing one.

There are generally two possibilities:

- **New Requirement** — A brand-new obligation is added to the compliance database.
- **Modified Requirement** — An existing obligation is updated, replaced, or partially changed.

This allows the platform to understand exactly how regulations evolve instead of treating every circular as a completely new document.

---

## Step 6 — Intelligent Amendment Handling

This is one of the core features of RegMind.ai.

Rather than simply notifying developers that an amendment exists, the platform checks the current status of the related engineering task and decides what should happen next.

Before making any changes, the system separates administrative updates from technical engineering requirements. Only actionable changes move into the developer workflow.

If a technical requirement has changed, the platform evaluates the state of the existing task.

### If the task hasn't been started

The original task is updated with the latest technical specification so developers always work on the newest version.

### If development is already in progress

The assigned developer is notified immediately, the task is updated, and the revised implementation details are made available without creating duplicate work.

### If the task has already been completed

Instead of modifying production records, the platform creates a separate change request containing only the differences introduced by the amendment.

This allows developers to update production systems without losing the original implementation history.

### If the regulation removes a previous requirement

The existing engineering task is automatically deprecated and archived, preventing unnecessary work on requirements that are no longer valid.

This state-aware approach helps engineering teams stay synchronized with changing regulations while maintaining a complete audit trail.

---

## Step 7 — Automated Compliance Verification

Once developers finish implementing a task, the verification process begins.

Developers upload the required evidence to the platform. This can include configuration files, logs, API responses, screenshots, code snippets, or any other technical artifacts requested during task creation.

The Verification Agent then compares the submitted evidence against the original regulatory requirement.

### Successful Verification

If everything satisfies the compliance criteria, the task is automatically marked as complete and the compliance dashboard is updated in real time.

No manual approval is required.

### Failed Verification

If the evidence is incomplete or doesn't fully satisfy the regulation, the platform doesn't simply reject it.

Instead, an AI-powered assistant explains exactly what is missing, highlights the issue, and guides the developer toward a successful submission.

This creates a much faster feedback loop than traditional compliance reviews.

---

# Tech Stack

## Frontend

- React
- Responsive compliance dashboard

## Backend

- FastAPI (Python)

## AI & Agent Framework

- LangChain for multi-agent orchestration
- Llama 3 and Mistral as the primary language models
- Ollama and vLLM for secure local inference
- Private AWS GPU infrastructure for enterprise deployments

## Database & Search

- MongoDB for storing obligations and engineering tasks
- Pinecone for semantic search and retrieval

## Document Processing

- PyMuPDF for PDF parsing
- Tesseract OCR for scanned regulatory documents

---

# Security & Privacy

## Zero Data Retention

Documents, source code, configuration files, and uploaded evidence are processed only for compliance verification.

No customer data is stored permanently or used to train AI models.

## Automatic Data Masking

Sensitive information such as passwords, API keys, customer information, and internal IP addresses is automatically masked before being processed by the AI pipeline.

Only the information required for compliance verification is analyzed.

## Complete Audit Trail

Every action performed inside the platform is securely recorded.

From document upload to task creation, evidence verification, and final approval, every event is logged with timestamps, making regulatory audits much easier while preserving transparency.

---

# Business Model

### B2B SaaS Subscription

Organizations pay a recurring monthly or annual subscription based on the number of users, compliance documents, and overall platform usage.

### Private Cloud / On-Premise Deployment

Large financial institutions can deploy RegMind.ai inside their own infrastructure through a one-time implementation and setup package.

### Usage-Based Pricing

Customers can also pay based on the number of regulatory documents processed, AI requests made, or compliance tasks generated.

### Enterprise Support

Premium support plans include priority assistance, security updates, regulatory model updates, and dedicated technical support.

### Custom Integrations

Paid integrations are available for enterprise platforms such as Jira, ServiceNow, and ERP systems.

---

# What Makes RegMind.ai Different?

- Fully agentic workflow with minimal manual intervention.
- Intelligent amendment handling that updates live engineering tasks instead of creating duplicate work.
- Privacy-first architecture designed for deployment inside a customer's private cloud.
- AI models specialized for SEBI and RBI regulations instead of general-purpose language understanding.
- Automatic evidence verification that reduces manual compliance reviews.
- Clear developer-friendly technical specifications generated directly from legal documents.
- End-to-end audit trail for regulatory reporting and compliance.

---

# Team

**Team Square**  
SEBI Securities Market TechSprint 2026

- Anshu Roy
- Aayush Dubey

---

# Current Status

**Idea Submission Round**

The current repository represents the proposed architecture and workflow for RegMind.ai. 

---

# Planned Repository Structure

```text
regmind-ai/
├── frontend/
├── backend/
├── agents/
│   ├── sorting_layer/
│   ├── action_generation/
│   └── verification_layer/
├── models/
├── database/
├── docs/
└── README.md
```

---

# Contact

**Anshu Roy**  
24bph025@nith.ac.in

**Aayush Dubey**  
dubeyaayushop@gmail.com

For collaborations, partnerships, or discussions around regulatory technology, feel free to reach out.

---

# License

This project has been submitted as part of the **SEBI Securities Market TechSprint 2026**.
