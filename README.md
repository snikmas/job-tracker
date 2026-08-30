# Personal job-search assistant

This is a learning project and a local product for a remote technical job search.

The assistant will search permitted sources, import job advertisements, check eligibility, rank useful opportunities, explain decisions with evidence, prepare truthful application drafts, and track outcomes.

The first version is for one user. It does not submit applications, send messages, complete identity checks, or make legal, payment, contract, or trust decisions.

## Required learning stack

The first complete version must use all three tools in the LangChain ecosystem:

| Tool | Responsibility in this project |
| --- | --- |
| LangChain | Model initialization and validated structured output for search criteria. |
| LangGraph | Workflow state, nodes, routing, interrupts, and durable resume. |
| LangSmith | Safe tracing, curated datasets, and repeatable evaluations. |

Normal Python remains responsible for hard gates, score calculation, normalization, deduplication, fact-ID validation, and database writes.

The supporting stack is Python, Pydantic, HTTPX, pytest, and SQLite. PostgreSQL, RAG, and a web UI are optional later work.

## Product flow

```text
profile defaults + search request
              |
              v
LangChain structured parsing
              |
              v
mock, manual, or approved API jobs
              |
              v
normalize + preserve source evidence
              |
              v
hard eligibility gates
              |
              v
transparent deterministic ranking
              |
              v
evidence-based fit analysis
              |
              v
save, skip, or select
              |
              v
truthful application draft
              |
              v
LangGraph human-review interrupt
```

LangSmith traces safe development runs and evaluates the parts whose output can vary.

## Learning approach

Mary writes and explains the learning-critical parts:

- domain models;
- eligibility rules;
- ranking;
- LangChain structured output;
- LangGraph state, nodes, edges, and routing;
- LangGraph interrupts and checkpointing;
- LangSmith datasets and evaluators;
- the first source adapter.

AI may explain concepts, ask design questions, review Mary's code, explain failures, and help with repetitive work after Mary defines the contract.

Each stage ends with an understanding check. A feature is not complete merely because generated code runs.

## Milestones

```text
V0.1  Mock jobs + eligibility + ranking + LangChain + LangGraph + LangSmith
V0.2  Manual import + SQLite job history
V0.3  One real source for one supported country
V0.4  Durable human selection + evidence-based fit analysis
V0.5  Fact-grounded application drafts + bounded review loop
V1.0  Reliable personal product with tests, evals, and restart recovery
```

## Read before coding

1. [Product contract](docs/00_product_contract.md)
2. [Project structure and architecture](docs/project_structure.md)
3. [Learning roadmap](docs/roadmap.md)

The files under `docs/archive/` preserve the original plan. They are historical references, not current instructions. The original concept screenshot is also historical.

## Current status

The product is still in the documentation stage. Start with Stage 0 in the learning roadmap. Do not generate the full repository in one AI-written change.
