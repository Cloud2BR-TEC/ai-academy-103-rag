# Content Processing Solution Accelerator

----------

<div align="center"><img src="../../assets/img/catalog/content-processing.svg" alt="Content Processing architecture" style="border-radius:10px;max-width:100%;"/></div>

## At a glance
| | |
|---|---|
| **Source** | [github.com/microsoft/content-processing-solution-accelerator](https://github.com/microsoft/content-processing-solution-accelerator) |
| **By** | Microsoft |
| **Use case** | Document ingestion · Structured extraction |
| **Stack** | Azure AI Foundry · Azure OpenAI · AI Content Understanding · Cosmos DB |

## What it solves
Programmatically extracts data and applies schemas to unstructured documents (text and multi-modal), solving the pre-RAG problem of transforming raw files into clean, structured, searchable records.

## Tech stack
| Component | Role |
|-----------|------|
| Azure AI Foundry | Extraction orchestration |
| Azure AI Content Understanding | Multi-modal processing |
| Azure OpenAI | Enrichment and field completion |
| Azure Cosmos DB | Structured output storage |

## Adoption notes
Deploy before your RAG indexing pipeline if document quality is inconsistent. Clean, schema-validated records improve retrieval precision significantly.