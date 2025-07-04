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
    A1["Workflow Builder UI<br/>Flutter native"]
    A2["Builder Metadata Model"]
    A3["Shared Step Type Library"]
    A4["Shared DSL & Validator"]
  end
  
  subgraph "Domain Configurations"
    B1["Compliance Config<br/>(AI Standards Consultant)"]
    B2["5G Config<br/>(Arion5G Orchestrator)"]
    B3["Training Config<br/>(TrainerOps)"]
  end
  
  subgraph "Workflow Engine Package"
    C1["Engine Runtime Core"]
    C2["Trigger & Step Resolver"]
    C3["AI Orchestration Layer"]
    C4["Logging & Traceability"]
  end
  
  subgraph "Domain App Instances"
    D1["Compliance App<br/>(shared DB/schema)"]
    D2["5G Orchestration App<br/>(dedicated DB + AI)"]
    D3["TrainingOps App<br/>(separate deployment)"]
  end
  
  subgraph "AI Backends"
    E1["Compliance AI Stack<br/>(Prompt, RAG, Audit)"]
    E2["5G AI Stack<br/>(Telemetry + NLP)"]
    E3["Training AI Stack<br/>(Instructional Feedback)"]
  end
  
  %% Core Platform Flow
  A1 --> A2
  A2 --> A3
  A3 --> A4
  
  %% Configuration Compilation
  A4 --> B1
  A4 --> B2
  A4 --> B3
  
  %% Engine Assembly
  B1 --> C1
  B2 --> C1
  B3 --> C1
  
  %% Engine Internal Flow
  C1 --> C2
  C2 --> C3
  C3 --> C4
  
  %% App-Engine Connections
  D1 --> C1
  D2 --> C1
  D3 --> C1
  
  %% AI Backend Connections
  C3 --> E1
  C3 --> E2
  C3 --> E3
  
  %% Direct App-AI Connections
  D1 --> E1
  D2 --> E2
  D3 --> E3
```
```mermaid
graph TD
  subgraph "Compliance App (AI Standards Consultant)"
    A1["Workflow Builder"]
    A2["DSL + Metadata"]
    A3["Engine Core"]
    A4["Compliance AI Stack"]
    A5["Domain Workflows + SoA"]
    A6["Exportable Runtime"]
    A7["Shared Supabase DB"]
    A8["Cloud/Hybrid AI Deployment"]
    A9["Trace Logger + Audit Trails"]
  end

  A1 --> A2 --> A3 --> A5
  A3 --> A4
  A3 --> A6
  A6 --> A7
  A4 --> A8
  A4 --> A9
```

```mermaid
graph TD
  subgraph "5G Orchestration App (Arion5G)"
    B1["Workflow Builder"]
    B2["DSL + Metadata"]
    B3["Exported Engine"]
    B4["5G AI Stack"]
    B5["Telemetry-Informed Workflows"]
    B6["Standalone Deployment"]
    B7["Dedicated 5G DB"]
    B8["Local + Cloud LLM Mix"]
    B9["Anomaly Logs + AI Justifications"]
  end

  B1 --> B2 --> B3 --> B5
  B3 --> B4
  B3 --> B6
  B6 --> B7
  B4 --> B8
  B4 --> B9
```

```mermaid
graph TD
  subgraph "TrainerOps App (Lab/Test Designer)"
    C1["Workflow Builder"]
    C2["DSL + Metadata"]
    C3["Exported Engine"]
    C4["Training AI Stack"]
    C5["Lesson/Assessment Workflows"]
    C6["Standalone or Edge Deployment"]
    C7["Edge-Optimized DB"]
    C8["Instructional LLM Model"]
    C9["Progress Trace + AI Feedback Logs"]
  end

  C1 --> C2 --> C3 --> C5
  C3 --> C4
  C3 --> C6
  C6 --> C7
  C4 --> C8
  C4 --> C9
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

Would you like visual exports of these new per-use-case diagrams or add annotations to highlight deployment boundaries?
