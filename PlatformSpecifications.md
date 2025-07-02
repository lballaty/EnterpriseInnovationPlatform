# 🧠 Enterprise Innovation Platform – Unified Architecture

## 🔧 Shared Platform Core

* **Workflow Builder (Flutter native)**

  * Drag-and-drop UI to create and edit workflows
  * Reused across all domain apps

* **Builder Metadata + Validator**

  * Defines step types, transitions, input/output schema
  * Validates against domain-specific logic

* **Shared Step Type DSL**

  * Core language to describe workflow logic
  * Domain-agnostic foundation for all apps

* **Workflow Templates per Domain**

  * Seeded default flows for Compliance, 5G, and Training

* **Natural Language Parser & Intent Router**

  * Routes user input into workflows or action triggers
  * Domain-aware, multi-intent compatible

* **Persistent AI Assistant UI Layer**

  * Every screen includes a context-aware chatbot popup
  * Understands user intent based on screen state, workflow position, and active data
  * Guides user through partial workflows, suggests next actions, and resumes unfinished tasks
  * Connected to domain-specific AI stack via orchestrator

---

```mermaid
graph TD
  subgraph "Core Modular Platform"
    A1[Workflow Builder UI (Flutter native)]
    A2[Builder Metadata Model]
    A3[Shared Step Type Library]
    A4[Shared DSL & Validator]
  end

  subgraph "Domain Configurations"
    B1[Compliance Config (AI Standards Consultant)]
    B2[5G Config (Arion5G Orchestrator)]
    B3[Training Config (TrainerOps)]
  end

  subgraph "Workflow Engine Package (Reusable Core)"
    C1[Engine Runtime Core]
    C2[Trigger & Step Resolver]
    C3[AI Orchestration Layer]
    C4[Logging & Traceability]
  end

  subgraph "Domain App Instances"
    D1[Compliance App (uses shared DB/schema)]
    D2[5G Orchestration App (dedicated DB + AI)]
    D3[TrainingOps App (separate deployment)]
  end

  subgraph "AI Backend(s)"
    E1[Compliance AI Stack (Prompt, RAG, Audit)]
    E2[5G AI Stack (Telemetry + NLP)]
    E3[Training AI Stack (Instructional Feedback)]
  end

  A1 --> A2 --> A3 --> A4
  A4 --> B1
  A4 --> B2
  A4 --> B3

  B1 -->|compile as| C1
  B2 -->|compile as| C1
  B3 -->|compile as| C1

  C1 --> C2 --> C3
  C3 --> E1
  C3 --> E2
  C3 --> E3
  C1 --> C4

  D1 --> C1
  D2 --> C1
  D3 --> C1

  D1 --> E1
  D2 --> E2
  D3 --> E3
```

---

## 📦 Workflow Runtime (Exportable Engine)

* **Runtime Engine Core**

  * Executes workflows created in builder
  * Deployed standalone or embedded per app

* **Trigger & Flow Resolver**

  * Handles event, manual, and chained triggers
  * Routes through appropriate workflow steps

* **Step Executor**

  * Invokes actions, sync calls, forms, and AI logic

* **Execution Logs & Audit Layer**

  * Captures run context, step results, timing, errors
  * Linked to org, domain, app, and user

* **AI Step Adapter (Domain-Specific)**

  * Bridges workflow engine and AI orchestration backend
  * Pluggable per domain app instance

* **Workflow Persistence**

  * Partially built workflows can be saved in `draft` state
  * AI assistant can track user's progress and resume workflows contextually

---

## 🧠 AI Orchestration Layer

* **NLU Handler**

  * Converts user queries into structured intents
  * Contextualizes by domain, role, user history

* **Prompt Builder + Domain Templates**

  * Domain-specific template resolver with LLM strategy config

* **Vector Search + Config Engine**

  * Document grounding, clause lookup, or semantic asset retrieval

* **LLM Orchestrator**

  * Executes prompt + context + logic per config
  * Chooses local or cloud model dynamically

* **Trace Logger + Explainability DB**

  * Logs every AI invocation
  * Links config, source context, prompt, and output

---

## 🚀 Domain Applications

### 1. **Compliance App (AI Standards Consultant)**

* Uses builder-created workflows tagged for compliance
* Scoped to ISO 27001, GDPR, NIS2, etc.
* Connects to **Compliance LLM stack**
* Enables SoA generation, gap analysis, clause-level traceability

### 2. **5G Orchestration App (Arion5G)**

* Uses exported engine instance, embedded in ops UI
* Drives RAN/NF orchestration, anomaly workflows, telemetry
* Connects to **5G LLM stack** trained on network operations

### 3. **TrainerOps App (Lab/Test Designer)**

* Exports test/training workflows
* AI helps author curriculum, auto-generate assessments, simulate user feedback
* Connects to **Training LLM stack** optimized for instructional design

---

## 🧩 Domain-Specific LLM 2.0 Compliant AI Stacks

* **Compliance LLM Stack**

  * Prompt templates grounded in regulations
  * Supports clause-based RAG, SoA comparison, audit prep

* **5G LLM Stack**

  * Ingests telemetry, DSLs, config files, error logs
  * Generates mitigation plans, performs anomaly reasoning

* **Training LLM Stack**

  * Pedagogical knowledge base + scoring rubrics
  * Generates lessons, questions, and feedback loops

All stacks:

* Follow LLM 2.0 guidelines: traceable, auditable, redactable
* Operate in local, hybrid, or cloud modes

---

## 📤 Export Strategy

* Engine + workflow packages exportable per domain
* Includes DSL, UI config, AI strategy, and vector index setup
* Deployable with isolated DB and LLM stack

---

Would you like a visual export of the Mermaid architecture diagram as well?
