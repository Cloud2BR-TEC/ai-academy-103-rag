# Azure GPT-RAG

----------

<div align="center">
  <img src="../../assets/img/catalog/gpt-rag.svg" alt="Azure GPT-RAG architecture" style="border-radius:10px;max-width:100%;"/>
</div>

## At a glance

| | |
|---|---|
| **Source** | [github.com/Azure/GPT-RAG](https://github.com/Azure/GPT-RAG) |
| **By** | Microsoft Azure |
| **Use case** | Enterprise knowledge assistant · Secure document Q&A |
| **Stack** | Azure AI Search · Azure OpenAI · Azure Functions · VNet |

## What it solves

GPT-RAG is Microsoft's reference architecture for running Retrieval-Augmented Generation at enterprise scale in a secure, private Azure environment. It covers the full lifecycle: document ingestion, vector embedding, hybrid retrieval, and grounded response generation - all inside a Zero Trust network boundary.

## Best fit for

- Internal knowledge search and Q&A over corporate documents
- Secure, air-gapped AI deployments with no public endpoint exposure
- Organizations requiring Zero Trust compliance for AI workloads
- Teams that need a supported, production-ready RAG baseline

## Architecture overview

| Stage | Components |
|-------|-----------|
| **Ingestion** | Document chunking, vector embedding, Azure AI Search indexing |
| **Retrieval** | Hybrid search (vector + keyword), semantic ranking |
| **Orchestration** | Azure Function orchestrator, Managed Identity, Key Vault |
| **Generation** | Azure OpenAI via Private Endpoint, grounded response |
| **Security** | VNet, Private Endpoints, Entra ID, Zero Trust controls |

## Tech stack

| Component | Role |
|-----------|------|
| Azure AI Search | Vector + keyword retrieval |
| Azure OpenAI | Language model generation |
| Azure Functions | Orchestration layer |
| Azure Key Vault | Secrets management |
| Azure VNet + Private Endpoints | Network isolation |
| Microsoft Entra ID | Identity and access |

## Adoption notes

Start here if you need a well-supported, Zero Trust-ready RAG foundation. This is the most battle-tested enterprise RAG pattern from Microsoft and maps directly to the CAF and WAF guidance covered in this documentation.
