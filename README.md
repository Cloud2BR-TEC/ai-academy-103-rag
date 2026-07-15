# RAG Enterprise Scale

[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/)
[Cloud2BR TEC](https://github.com/Cloud2BR-TEC)

Last updated: 2026-07-15

----------

> Guidance for architecting, securing, and governing production-grade Retrieval-Augmented Generation (RAG) systems on Azure at enterprise scale.

## Scope

- What Enterprise RAG is and how it differs from a demo or PoC — per Microsoft's baseline architecture guidance.
- How the three governing frameworks — **Zero Trust Architecture (ZTA)**, **Cloud Adoption Framework (CAF)**, and **Well-Architected Framework (WAF)** — apply to enterprise RAG.
- Architecture patterns for large-scale, multi-tenant, and high-availability RAG deployments.
- Governance and security design: identity, network isolation, data classification, and compliance.
- Zero Trust implementation across every RAG component — identities, devices, networks, data, infrastructure, and applications.
- Implementation approaches from PoC to production.

## Documentation Site

Published at: **[https://cloud2br-tec.github.io/ai-academy-103-rag/](https://cloud2br-tec.github.io/ai-academy-103-rag/)**

| Section | Content |
|---------|---------|
| 01. Fundamentals | Enterprise RAG overview · CAF · WAF · ZTA · Implementation approaches |
| 02. Enterprise Design | Architecture patterns · Governance and security |
| 03. Security | Zero Trust Architecture — principles, pillars, Azure architecture, maturity |

## Local Development

```bash
pip install mkdocs mkdocs-material pymdown-extensions
mkdocs serve        # live preview at http://127.0.0.1:8000
mkdocs build --strict   # validate before pushing
```

## Related Repositories

| Repo | Focus |
|------|-------|
| [ai-academy-101-rag](https://github.com/Cloud2BR-TEC/ai-academy-101-rag) | RAG fundamentals — patterns, private architecture, Zero Trust basics, Terraform |
| [ai-academy-102-rag](https://github.com/Cloud2BR-TEC/ai-academy-102-rag) | Multi-Agent RAG — Agentic DevOps AI Shopping, Agentic AI Media Assistant |
| [ai-academy-103-rag](https://github.com/Cloud2BR-TEC/ai-academy-103-rag) | **This repo** — Enterprise Scale RAG |

<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-0-limegreen" alt="Total views">
  <p>Refresh Date: 2026-07-15</p>
</div>
<!-- END BADGE -->