# Deploy Your AI Application in Production

----------

<div align="center"><img src="../../assets/img/catalog/deploy-ai-production.svg" alt="Deploy AI in Production architecture" style="border-radius:10px;max-width:100%;"/></div>

## At a glance
| | |
|---|---|
| **Source** | [github.com/microsoft/deploy-your-ai-application-in-production](https://github.com/microsoft/deploy-your-ai-application-in-production) |
| **By** | Microsoft |
| **Use case** | Production hardening · Secure AI deployment baseline |
| **Stack** | Azure AI Foundry · VNet · Private Endpoints · Azure Monitor · WAF |

## What it solves
A deployment accelerator for running Azure AI Foundry workloads in production with all essential security, networking, and observability controls aligned to the Microsoft Well-Architected Framework.

## Architecture (layered)
| Layer | Controls |
|-------|---------|
| **Edge** | Azure Front Door + WAF, DDoS Protection, TLS |
| **Identity** | Entra ID, Conditional Access, MFA, Managed Identity |
| **Network** | VNet, Private Endpoints, NSGs, Azure Firewall |
| **AI Services** | Azure Foundry, Azure OpenAI, AI Search, Key Vault, Cosmos DB |
| **Observability** | Azure Monitor, App Insights, Sentinel |

## Adoption notes
Use as your production baseline for any AI Foundry workload. Implements all five WAF pillars and the Zero Trust controls described in the [Zero Trust Architecture](../04-security/index.md) page.