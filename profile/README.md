# CommitKings - FlowPilot 

Welcome to the **CommitKings** organization, the architects behind **FlowPilot**—a production-grade, AI-driven fintech orchestration engine built for the **Interswitch Hackathon**.

##  The FlowPilot Project

**FlowPilot** is a web-based multi-agent fintech execution system for SMEs. It uses Interswitch's Quickteller Transfer Service APIs to verify recipient accounts, execute approved disbursements, and track settlement status. AI agents score payout risk, coordinate multi-step treasury workflows with strict human approval gates, and produce full audit traces, enabling faster operations, safer payouts, and explainable decision intelligence.

###  The Repositories

| Repository | Description |
| :--- | :--- |
| [**flow-pilot-infra**](https://github.com/commitkings/flow-pilot-infra) | Production-ready Kubernetes infrastructure (Argo CD, Harbour, GitOps, Network Management). |
| [**flowpilot-backend**](https://github.com/commitkings/flowpilot-backend) | The AI core. Multi-agent system (Python/FastAPI) using a custom persistent state machine for orchestration. |
| [**flow-pilot-frontend**](https://github.com/commitkings/flow-pilot-frontend) | Real-time monitoring and approval dashboard (Next.js/React) for financial stakeholders. |

---

##  Problem Statement
FlowPilot exists because running payouts as an SME is still painful: you juggle spreadsheets, bank portals, and ad hoc checks, with little structure for who gets paid, whether amounts look right, whether accounts are real, or who approved what. That gap is risky for fraud, errors, and compliance, especially when you scale beyond a handful of transfers. This leads to:
- **Execution Latency**: Manual processes slow down time-to-value.
- **Accuracy Risks**: Human errors in reconciliation and risk scoring cause financial loss.
- **Vendor Lock-in**: Hardcoded integrations make it difficult to pivot between providers.

**FlowPilot** solves this by providing an **autonomous orchestration layer** that interprets high-level business goals, plans the required steps (via LLMs), and executes them using secure API integrations (like Interswitch) while maintaining a strict **Human-in-the-Loop** approval gate.

---

##  Technical Execution

###  The AI Core (Backend)
The backend is built on a custom **Agentic State Machine** rather than standard LangChain/LangGraph, providing deeper persistence and reliability:
- **Multi-Agent Swarm**: Specialized agents (Planner, Risk, Execution, Reconciliation, Audit) that collaborate on a shared state.
- **Persistence Redundancy**: Every agent reasoning step, tool call, and plan modification is persisted in a PostgreSQL database for full auditability.
- **Interswitch Integration**: Deep integration with Interswitch APIs for real-time payment execution and validation.

###  The Platform (Frontend)
A modern, real-time dashboard built with **Next.js**:
- **Interactive Approvals**: Visualizes the AI's plan and provides one-click approval/rejection for high-stakes financial operations.
- **Real-time Observability**: Streams events from the orchestrator so users can watch the AI "think" and "act" in real-time.

###  Infrastructure & DevOps
A **Security-First, GitOps-ready** infrastructure:
- **Kubernetes Orchestration**: Using K8s for scalability and micro-segmentation.
- **Argo CD**: Fully automated deployments using pull-based synchronization from this repository.
- **Harbour Registry**: Private container registry ensuring image integrity and secure artifact storage.
- **Zero-Trust Networking**: Granular NetworkPolicies to isolate sensitive AI workloads.

---

##  The Team (CommitKings)

We are a group of engineers dedicated to pushing the boundaries of AI in fintech.

| Member | Role | GitHub Profile |
| :--- | :--- | :--- |
| **Abdulraqib20** | **AI Engineer** | [@Abdulraqib20](https://github.com/Abdulraqib20) |
| **Chideraozigbo** | **Data Platform Engineer** | [@Chideraozigbo](https://github.com/Chideraozigbo) |
| **mohawwal** | **Software Engineer** | [@mohawwal](https://github.com/mohawwal) |

---
*Created with ❤️ by the CommitKings Team for the Interswitch Hackathon.*
