# Document Knowledge Mining Solution Accelerator

----------

<div align="center"><img src="../../assets/img/catalog/document-knowledge-mining.svg" alt="Document Knowledge Mining architecture" style="border-radius:10px;max-width:100%;"/></div>

## At a glance
| | |
|---|---|
| **Source** | [github.com/microsoft/Document-Knowledge-Mining-Solution-Accelerator](https://github.com/microsoft/Document-Knowledge-Mining-Solution-Accelerator) |
| **By** | Microsoft |
| **Use case** | Document intelligence · Enterprise knowledge extraction |
| **Stack** | Azure OpenAI · Azure AI Document Intelligence · Azure AI Search |

## What it solves
Processes and extracts summaries, entities, and metadata from unstructured multi-modal documents at scale, then enables hybrid search and conversational chat over the resulting knowledge base.

## Tech stack
| Component | Role |
|-----------|------|
| Azure AI Document Intelligence | Layout extraction, OCR, form recognition |
| Azure OpenAI | Summarization, entity extraction |
| Azure AI Search | Hybrid search + vector index |
| Azure Blob Storage | Document staging |

## Adoption notes
Deploy before your RAG pipeline when documents are complex (forms, scanned PDFs, mixed media). High-quality extraction at this stage directly improves answer accuracy.