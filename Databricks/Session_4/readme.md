# Session 4 — Understanding LLMs & Embedding Models in Databricks

## Goal

Understand the different **large language models (LLMs)** and **embedding models** available through Databricks, what they are used for, and how to choose the right model for an AI application.

---

## What We Cover

1. What an LLM does
2. What an embedding model does
3. Difference between generation and retrieval
4. Databricks-hosted model endpoints
5. External models available through Databricks integrations
6. Common model families used for RAG and AI applications
7. How to choose a model based on cost, latency, accuracy, and use case
8. How LLMs and embedding models work together in a RAG pipeline

---

## LLM vs Embedding Model

| LLM | Embedding Model |
|---|---|
| Generates language | Generates vectors |
| Answers questions | Finds similar information |
| Summarizes and reasons | Represents semantic meaning |
| Can generate SQL or code | Supports semantic search |
| Used after retrieval in RAG | Used during retrieval in RAG |

---

## Models Used in Our RAG Project

### Embedding Model

```text
databricks-qwen3-embedding-0-6b
```

### LLM

```text
databricks-meta-llama-3-3-70b-instruct
```

---

## How They Work Together

```text
Documents
   ↓
Embedding Model
   ↓
Vector Search
   ↓
Relevant Context
   ↓
LLM
   ↓
Final Answer
```

---

## Model Selection Factors

When selecting a model, consider:

```text
Accuracy
Cost
Latency
Context Window
Reasoning Capability
Application Type
Data Privacy
Region Availability
Throughput
```

---

## Session Folder

This folder will contain:

```text
Session_4/
├── readme.md
├── Code / Notebooks
├── Data
└── Supporting Files
```

---

**Key takeaway:** Embedding models help the application **retrieve the right knowledge**, while LLMs help the application **reason over and communicate that knowledge**.
