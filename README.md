# Copilot-Agent
Copilot Agent automating knowledge retrieving and user redirecting to organizational tools and systems
#  Enterprise AI Agent

An end-to-end, multi-departmental AI Copilot agent and enterprise integration engine. 

This system transforms manual organizational data lookup and IT/HR workflows into an instant, interactive conversational experience inside **Microsoft Teams**. Powered by custom **Copilot Studio** topics, **JSON Adaptive Cards**, and **REST API integrations** (HiBob HR).

---

# Executive Summary & Impact

Enterprise knowledge bases are often fragmented across legacy databases, HR platforms, and static documentation. This project solves internal data access bottlenecks by building a **"Queryable Company" architecture**:

1. **Autonomous Conversational Search:** Replaced manual HR/IT querying with multi-source AI agents utilizing Few-Shot system prompts and topic fallback logic.
2. **Interactive UI Workflows:** Designed and deployed responsive JSON Adaptive Cards in MS Teams to streamline troubleshooting and route secure ticketing requests with maximum data privacy.
3. **Enterprise Scalability:** Executed phased departmental rollouts across HR, Procurement, and Finance backed by real-time user feedback frameworks.

---

# System Architecture

```mermaid
flowchart TD
    %% Styling Zone
    classDef client fill:#d0e1fd,stroke:#1d4ed8,stroke-width:2px,color:#0f172a;
    classDef agent fill:#fef08a,stroke:#ca8a04,stroke-width:2px,color:#0f172a;
    classDef integration fill:#bbf7d0,stroke:#16a34a,stroke-width:2px,color:#0f172a;
    classDef qa fill:#fed7aa,stroke:#ea580c,stroke-width:2px,color:#0f172a;

    %% Client & Interaction Layer
    subgraph ClientLayer ["1. User Interface & Interaction"]
        User(["👤 Enterprise User / Employee"])
        Teams["💬 Microsoft Teams Canvas"]
        AdaptiveCard["🎴 JSON Adaptive Cards<br/><i>(IT Routing & Ticketing)</i>"]
    end

    %% Copilot Studio Core
    subgraph AgentLayer ["2. Conversational Orchestration Layer"]
        Copilot["🤖 Microsoft Copilot Studio Agent"]
        PromptEngine["🧠 Prompt & Topic Engine<br/><i>(Few-Shot & Fallback Logic)</i>"]
        KB["📚 Multi-Source Knowledge Base<br/><i>(Schema-Optimized Documents)</i>"]
    end

    %% Integration & External Services
    subgraph IntegrationLayer ["3. Enterprise API & Sourcing Layer"]
        PowerAutomate["⚡ Power Automate Flows"]
        HiBobAPI["👥 HiBob HR REST API"]
        ExternalAPI["🌐 External REST APIs<br/><i>(IT & Ticketing Systems)</i>"]
    end

    %% Quality & Feedback Store
    subgraph QALayer ["4. Verification & Feedback Loop"]
        GroundTruth["🛡️ Ground-Truth Verification<br/>& Continuous Feedback Store"]
    end

    %% Data Flow Connections
    User -->|1. Natural Language Prompt| Teams
    Teams <-->|2. Real-time Interaction| Copilot
    Copilot <-->|3. Topic & Intent Matching| PromptEngine
    Copilot <-->|4. Semantic Search| KB

    %% Workflows & Triggers
    Copilot -->|5a. Render Custom Card| AdaptiveCard
    AdaptiveCard -->|5b. Submit Form Action| PowerAutomate
    Copilot -->|6. Direct API Calls| PowerAutomate

    PowerAutomate <-->|7. Sync HR Data| HiBobAPI
    PowerAutomate <-->|8. IT Ticket Creation| ExternalAPI

    %% Feedback Connections
    Copilot -.->|9. Log Responses & Ratings| GroundTruth
    GroundTruth -.->|10. Continuous System Improvement| PromptEngine

    %% Class Assignments
    class User,Teams,AdaptiveCard client;
    class Copilot,PromptEngine,KB agent;
    class PowerAutomate,HiBobAPI,ExternalAPI integration;
    class GroundTruth qa;
