# Content Generation Solution Accelerator

----------

<div align="center"><img src="../../assets/img/catalog/content-generation.svg" alt="Content Generation architecture" style="border-radius:10px;max-width:100%;"/></div>

## At a glance
| | |
|---|---|
| **Source** | [github.com/microsoft/content-generation-solution-accelerator](https://github.com/microsoft/content-generation-solution-accelerator) |
| **By** | Microsoft |
| **Use case** | Marketing content · Brand content pipelines |
| **Stack** | Microsoft Foundry · Azure OpenAI · Multi-agent |

## What it solves
Accelerates marketing content creation with a multi-agent pipeline: Planner decomposes the brief, Writer drafts brand-aligned content, Reviewer validates quality and compliance before publishing.

## Tech stack
| Component | Role |
|-----------|------|
| Microsoft Foundry | Agent orchestration |
| Azure OpenAI | Content generation |
| Multi-agent framework | Planner, Writer, Reviewer agents |
| Azure Cosmos DB | Workflow state |

## Adoption notes
Choose when content velocity and brand consistency are both important. The multi-agent approach ensures the review step is never skipped.