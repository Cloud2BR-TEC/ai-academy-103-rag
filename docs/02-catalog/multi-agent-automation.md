# Multi-Agent Custom Automation Engine

----------

<div align="center"><img src="../../assets/img/catalog/multi-agent-automation.svg" alt="Multi-Agent Automation architecture" style="border-radius:10px;max-width:100%;"/></div>

## At a glance
| | |
|---|---|
| **Source** | [github.com/microsoft/Multi-Agent-Custom-Automation-Engine-Solution-Accelerator](https://github.com/microsoft/Multi-Agent-Custom-Automation-Engine-Solution-Accelerator) |
| **By** | Microsoft |
| **Use case** | Workflow automation · Task orchestration |
| **Stack** | Microsoft Agent Framework · Azure Foundry · Cosmos DB |

## What it solves
An AI-driven reference system that coordinates a group of specialized agents — Orchestrator, Research, Execution, and Validator — to complete complex multi-step tasks based on user input.

## Best fit for
- Business process automation requiring multiple specialization steps
- Workflows that need research, execution, and quality validation in sequence
- Teams adopting agentic AI patterns with clear task boundaries

## Tech stack
| Component | Role |
|-----------|------|
| Microsoft Agent Framework | Agent definition and coordination |
| Azure Foundry | Agent hosting and runtime |
| Azure Cosmos DB | Task state and conversation history |
| Azure OpenAI | Agent reasoning and generation |

## Adoption notes
Use when one agent is not sufficient. The engine is extensible — specialist agents can be swapped for your domain.