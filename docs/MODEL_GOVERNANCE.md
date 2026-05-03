# Model Governance and AI Safety

## Required controls

1. Source-grounded generation only.
2. Retrieval provenance for every summary or case explanation.
3. Human review for high-impact workflows.
4. Prompt, context hash, model version, and output logging.
5. Model cards for every AI component.
6. Drift monitoring for data distribution, source latency, and model error patterns.
7. No confidential data reuse across tenants without explicit written permission.

## Risk classes

| System | Risk | Required control |
|---|---:|---|
| Court directory search | Low | Source links and sync timestamp |
| Case timeline extraction | Medium | Date/entity validation |
| Procedural signal scoring | Medium | Explainable deterministic features |
| GenAI case summary | High | RAG citations, uncertainty, human review |
| Outcome prediction | Very high | Avoid for MVP; requires legal, ethical, and statistical validation |

## Recommended evaluation metrics

- Citation precision
- Hallucination rate
- Source coverage
- Entity extraction accuracy
- Timeline extraction accuracy
- Alert precision/recall
- Ingestion latency
- Source outage recovery time
