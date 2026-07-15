# Enterprise RAG Overview

----------

<details markdown="block">
<summary><b>References</b> (Click to expand)</summary>

- [Baseline enterprise chat architecture — Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/architecture/baseline-openai-e2e-chat)
- [What is Cloud Adoption Framework (CAF) — Microsoft Learn](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/overview)
- [CAF AI adoption scenario](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai/strategy)
- [Azure Well-Architected Framework (WAF) — Microsoft Learn](https://learn.microsoft.com/en-us/azure/well-architected/)
- [WAF AI workloads design guidance](https://learn.microsoft.com/en-us/azure/well-architected/ai/get-started)
- [Zero Trust Architecture — Microsoft Security](https://www.microsoft.com/en-us/security/business/zero-trust)
- [GPT-RAG — Azure GitHub](https://github.com/Azure/GPT-RAG)
- [Azure AI Foundry Baseline architecture](https://learn.microsoft.com/en-us/azure/architecture/ai-ml/architecture/baseline-microsoft-foundry-chat)

</details>

## What Is Enterprise RAG?

> Enterprise RAG is a `production-grade Retrieval-Augmented Generation deployment` that goes beyond a demo or prototype. It integrates an LLM with your organization's private knowledge — documents, databases, SharePoint, APIs — and `wraps that capability in the security, governance, scalability, and operational controls required by a real enterprise workload`.

Basic RAG (a PoC or demo) connects a language model to a search index and produces answers. It works. But it is not production-ready. Enterprise RAG adds everything that makes a workload safe to run at scale: identity controls, private networking, cost guardrails, observability, disaster recovery, and a governance model that satisfies compliance requirements.

> From the Microsoft Azure Architecture Center: _"Enterprise chat applications let employees interact with AI agents through natural language conversations. These applications use language models, like OpenAI GPT models, and consist of a chat UI, domain-specific data repositories, a language model, and a persisted orchestration definition that oversees the interactions between data sources, models, and the user."_

<div align="center">
  <img src="../assets/img/rag-enterprise-overview.svg" alt="Enterprise RAG — How It Works" style="border-radius: 10px; max-width: 100%;"/>
</div>

| Basic RAG (PoC/Demo) | Enterprise RAG (Production) |
|---------------------|----------------------------|
| Public API endpoints | Private Endpoints only — no public exposure |
| API keys in code or env vars | Azure Key Vault + Managed Identity |
| Single region, no redundancy | Zone-redundant, multi-region failover strategy |
| No access controls | Microsoft Entra ID + Conditional Access + MFA |
| No audit trail | Azure Monitor + Sentinel — full audit log |
| No cost governance | Token budgets, Provisioned Throughput Units (PTU), alerts |
| Manual deployment | IaC (Bicep/Terraform) + CI/CD pipelines |
| No data classification | Microsoft Purview — sensitivity labels + DLP |

## Why Three Frameworks?

No single framework covers everything. Enterprise RAG sits at the intersection of `security`, `cloud governance`, and `workload quality`. Microsoft addresses each dimension with a dedicated framework, and all three must be applied together for a production-ready deployment.

<div align="center">
  <img src="../assets/img/rag-frameworks-overview.svg" alt="Enterprise RAG Three Frameworks" style="border-radius: 10px; max-width: 100%;"/>
</div>

| Framework | Focus | What it answers for RAG |
|-----------|-------|------------------------|
| **Zero Trust Architecture (ZTA)** | Security | Who can access what, from where, under what conditions? |
| **Cloud Adoption Framework (CAF)** | Governance & strategy | How do we adopt AI at enterprise scale with the right controls? |
| **Well-Architected Framework (WAF)** | Workload quality | Is this system reliable, secure, cost-efficient, observable, and performant? |

!!! note
    These frameworks are **complementary, not alternatives**. ZTA tells you *what* security controls to apply. WAF tells you *how* to design the workload quality attributes. CAF tells you *how* to govern and operate it as part of your broader cloud estate.

## Cloud Adoption Framework (CAF)

> The Microsoft Cloud Adoption Framework is a `structured roadmap that helps organizations successfully adopt Azure and integrate it into their existing IT environments`. It provides proven practices to govern, secure, and manage all workloads — including AI and RAG systems.

CAF organizes guidance into **seven methodologies**: four sequential (foundational) phases that you go through once per workload, plus three operational phases that run continuously once workloads are live.

<div align="center">
  <img src="../assets/img/caf-seven-phases.svg" alt="CAF Seven Methodologies" style="border-radius: 10px; max-width: 100%;"/>
</div>

| CAF Phase | Purpose | Applied to Enterprise RAG |
|-----------|---------|--------------------------|
| **1. Strategy** | Align cloud adoption to business goals | Define AI KPIs: query accuracy, user adoption, cost per query |
| **2. Plan** | Build the cloud adoption plan | AI skills roadmap, migration plan for knowledge sources, cost estimation |
| **3. Ready** | Prepare the Azure environment | AI Landing Zone: VNet, Private Endpoints, Entra ID tenant setup, Policy baselines |
| **4. Adopt** | Deploy workloads | Deploy RAG solution (Terraform/Bicep), onboard data sources, run UAT |
| **5. Govern** | Control and mitigate risks | Azure Policy for AI: enforce Private Endpoints, Key Vault, no public keys |
| **6. Secure** | Protect the environment | Apply Zero Trust controls, Defender for Cloud, Sentinel SIEM integration |
| **7. Manage** | Operate and optimize | Monitor query latency, token usage, index freshness; automated incident response |

!!! tip
    For AI-specific CAF guidance, Microsoft publishes a dedicated [AI adoption scenario](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ai/strategy) within CAF that covers strategy, platform decisions, landing zone design, and governance for both generative and non-generative AI workloads.

### AI Landing Zone (CAF Ready Phase)

A core output of the CAF Ready phase for Enterprise RAG is an **AI Landing Zone** — a pre-configured, governed Azure environment that all RAG workloads deploy into. It includes:

- **Networking**: VNet with private subnets, Private DNS zones, Azure Firewall for egress control
- **Identity**: Entra ID tenant, Managed Identity patterns, PIM for privileged roles
- **Governance**: Azure Policy assignments enforcing security baselines (no public endpoints, Key Vault required, encryption enabled)
- **Monitoring**: Log Analytics workspace, Azure Monitor alerts, Sentinel SIEM onboarded
- **Cost management**: Budgets, alerts, tagging policy for chargeback

## Well-Architected Framework (WAF)

> The Azure Well-Architected Framework is a `set of quality-driven tenets, architectural decision points, and review tools` that help solution architects build a technical foundation for their workloads. It is organized around five pillars.

<div align="center">
  <img src="../assets/img/waf-five-pillars.svg" alt="WAF Five Pillars" style="border-radius: 10px; max-width: 100%;"/>
</div>

| WAF Pillar | For Enterprise RAG |
|------------|--------------------|
| **Reliability** | Zone-redundant AI Search (3+ replicas), multi-datacenter model deployments, Cosmos DB continuous backup, DR runbook for chat history |
| **Security** | Private Endpoints for all services, Managed Identity everywhere, WAF at edge (OWASP rules), content safety filters on all model responses |
| **Cost Optimization** | Token budgets per agent, Provisioned Throughput Units (PTU) for predictable load, reserved capacity for Cosmos DB, delete stale agents |
| **Operational Excellence** | IaC for all resources, CI/CD pipelines for agents, Application Insights for token tracking, version-pinned model deployments |
| **Performance Efficiency** | AI Search replicas and partition tuning, PTU for latency SLOs, same-region model and data deployment, load test before production |

!!! note
    Microsoft publishes a dedicated [WAF AI workloads design guide](https://learn.microsoft.com/en-us/azure/well-architected/ai/get-started) with review checklists for each pillar, specifically for generative AI and RAG workloads.

### WAF Review and Assessment

The WAF is not just a reading exercise. Microsoft provides an **[Azure Architecture Review assessment tool](https://learn.microsoft.com/en-us/assessments/azure-architecture-review/)** that evaluates your workload against each pillar and produces a score with prioritized recommendations. For Enterprise RAG, run this assessment before go-live and after any major architecture change.

## Zero Trust Architecture

ZTA is covered in depth in the [03.1 Zero Trust Architecture](../4_Zero_Trust_Architecture.md) page. In the context of Enterprise RAG, ZTA is the security layer that enforces the "never trust, always verify" principle at every hop of the pipeline — from the user's browser to the final LLM response.

!!! warning
    Every production Enterprise RAG deployment on Azure **must** implement Zero Trust controls. Without them, a single compromised credential or misconfigured network rule can expose your entire knowledge base and conversation history.

## How They Work Together

| Concern | Who Answers It | How |
|---------|---------------|-----|
| Can this user access the RAG system? | ZTA | Entra ID + MFA + Conditional Access |
| Can this service call Azure OpenAI? | ZTA | Managed Identity + Private Endpoint |
| Is the environment governed by policy? | CAF | Azure Policy + Landing Zone |
| Are AI workloads in the right platform topology? | CAF | AI Platform sharing/isolation guidance |
| Will the system stay up if one zone fails? | WAF (Reliability) | Zone-redundant AI Search + Cosmos DB |
| Are we spending within budget? | WAF (Cost Optimization) | Token budgets + PTU + cost alerts |
| Can we trace every user query end-to-end? | WAF (Operational Excellence) | App Insights + Log Analytics + Sentinel |

!!! tip
    A useful mental model: **CAF** sets up the *house* (the cloud environment and governance). **WAF** designs each *room* (workload quality attributes). **ZTA** locks every *door and window* (security at every access point).