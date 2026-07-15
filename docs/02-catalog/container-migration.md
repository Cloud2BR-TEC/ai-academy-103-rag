# Container Migration Solution Accelerator

----------

<div align="center"><img src="../../assets/img/catalog/container-migration.svg" alt="Container Migration architecture" style="border-radius:10px;max-width:100%;"/></div>

## At a glance
| | |
|---|---|
| **Source** | [github.com/microsoft/Container-Migration-Solution-Accelerator](https://github.com/microsoft/Container-Migration-Solution-Accelerator) |
| **By** | Microsoft |
| **Use case** | Container platform migration to AKS |
| **Stack** | Multi-agent AI · Azure Kubernetes Service · Azure OpenAI |

## What it solves
Multi-agent, AI-driven solution that analyzes container configurations from other cloud platforms, translates YAML/Helm specs, and produces validated AKS deployment artifacts.

## Tech stack
| Component | Role |
|-----------|------|
| Azure OpenAI | Configuration analysis and translation |
| Multi-agent framework | Coordinated migration workflow |
| Azure Kubernetes Service | Target deployment platform |
| Azure Container Registry | Image hosting post-migration |

## Adoption notes
Use when migration complexity is high. The AI-assisted approach reduces effort but team validation is required before production deployment.