# Session 1 — Build a RAG Application with Databricks

## Goal

Build a practical **Retrieval-Augmented Generation (RAG)** application using documents, embeddings, vector search, and a large language model in Databricks.
Created 8th Sept 2026

Videos and Walkthrough available at https://nas.com/aiguild/courses/ai-learning-tracks-2026
---

## What We Cover

1. Upload and access documents in Databricks
2. Extract text from PDF, TXT, or Markdown files
3. Split documents into chunks
4. Create embeddings
5. Store document chunks and metadata
6. Perform semantic similarity search
7. Retrieve relevant context
8. Send retrieved context to an LLM
9. Generate grounded answers
10. Connect the RAG workflow to a simple AI application

---

## Models Used

**Embedding Model**

```text
databricks-qwen3-embedding-0-6b
```

**LLM**

```text
databricks-meta-llama-3-3-70b-instruct
```

---

## RAG Flow

```text
Documents
   ↓
Extract Text
   ↓
Chunk Documents
   ↓
Create Embeddings
   ↓
Vector Search
   ↓
Retrieve Relevant Context
   ↓
LLM
   ↓
Grounded Answer
```

---

## Session Folder

This folder will contain the materials used during Session 1:

```text
Session_1/
├── readme.md
├── Code / Notebooks
├── Data
└── Supporting Files
```

Review the README first, then work through the code and data used during the session.

---

**Key takeaway:** Embeddings help us **find the right information**, while the LLM helps us **use and explain that information**.
