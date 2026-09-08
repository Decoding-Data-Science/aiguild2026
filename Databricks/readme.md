# Databricks for AI Projects

A practical two-session learning series focused on building AI applications with **Databricks** using both unstructured documents and structured SQL data.

---

## Session 1 — RAG with Files in Databricks

### Goal

Build a simple **Retrieval-Augmented Generation (RAG)** application that can answer questions from enterprise documents.

### Data Used

* PDF files
* TXT files
* Markdown files

### What We Cover

1. Upload and access documents in Databricks
2. Read and extract text from files
3. Split documents into smaller chunks
4. Create embeddings
5. Store document chunks and metadata
6. Convert a user question into an embedding
7. Perform similarity search
8. Retrieve the most relevant chunks
9. Send retrieved context to an LLM
10. Generate a grounded answer

---

### RAG Flow

```text
Documents
   ↓
Extract Text
   ↓
Chunk Text
   ↓
Create Embeddings
   ↓
Store Vectors
   ↓
User Question
   ↓
Similarity Search
   ↓
Retrieve Relevant Context
   ↓
LLM
   ↓
Grounded Answer
```

---

### Models Used

#### Embedding Model

```text
databricks-qwen3-embedding-0-6b
```

Used to convert document chunks and user questions into numerical vectors for semantic search.

#### LLM

```text
databricks-meta-llama-3-3-70b-instruct
```

Used to generate the final answer using the retrieved document context.

---

### Key Takeaway

> Embeddings help us **find the right information**.
> The LLM helps us **understand and explain that information**.

---

# Session 2 — AI with SQL Data in Databricks

### Goal

Use structured business data stored in Databricks tables to answer analytical questions and generate useful insights.

### Data Used

Structured tables such as:

```text
Employees
Leave Records
Departments
Transactions
Sales
Operations
```

---

### What We Cover

1. Load structured data into Databricks
2. Create or access SQL tables
3. Explore data using SQL
4. Filter and aggregate business data
5. Ask business questions using structured data
6. Generate SQL queries for analysis
7. Execute SQL inside Databricks
8. Return results to an AI application
9. Use an LLM to explain query results
10. Connect structured data with AI workflows

---

### SQL + AI Flow

```text
User Question
      ↓
Understand the Question
      ↓
Generate / Select SQL
      ↓
Databricks SQL
      ↓
Execute Query
      ↓
Structured Result
      ↓
LLM
      ↓
Business-Friendly Answer
```

---

### Example Questions

```text
How many employees are currently on leave?

Which department has taken the most leave?

What is the average leave duration by department?

Show monthly leave trends.

Which employees have the highest remaining leave balance?
```

---

# RAG vs SQL

| RAG                                    | SQL                                                 |
| -------------------------------------- | --------------------------------------------------- |
| Works with documents                   | Works with tables                                   |
| Handles unstructured data              | Handles structured data                             |
| Uses embeddings                        | Uses queries                                        |
| Retrieves text chunks                  | Retrieves rows and aggregations                     |
| Best for policies, manuals and reports | Best for metrics, transactions and operational data |

---

# The Bigger Picture

Real enterprise AI applications rarely use only one type of data.

A Databricks AI application may eventually combine:

```text
                 User Question
                       ↓
               AI Application
                 ↙           ↘
        Document RAG        SQL Data
        PDF / TXT / MD      Tables
                 ↘           ↙
                 LLM / Agent
                       ↓
                  Final Answer
```

This allows an application to answer questions such as:

> "According to our leave policy, how much annual leave is allowed, and how many employees currently exceed that amount?"

The **policy information** can come from RAG.

The **employee statistics** can come from SQL.

---

# Learning Objective

After completing both sessions, you should understand how Databricks can be used as a foundation for AI applications that work with:

* Documents
* Embeddings
* LLMs
* SQL
* Structured data
* Unstructured data
* Retrieval
* Analytics
* Enterprise AI workflows

---

# Recommended Learning Approach

Do not just run the notebooks.

For every step, ask:

```text
What data is entering this step?

What transformation is happening?

What is the output?

Why is this step required?
```

Understanding the flow is more important than memorizing the code.

---

**Databricks for AI Projects — Documents → Data → Intelligence**


# Session 4 — Understanding LLMs & Embedding Models in Databricks

## Goal

Understand the different **LLMs and embedding models available through Databricks**, what they are designed for, and how to select the right model for an AI application.

Databricks provides access to both:

* **Databricks-hosted foundation models**
* **External models** from providers such as OpenAI, Anthropic, Google and Cohere

---

# 1. Large Language Models

LLMs are used for tasks such as:

* Question answering
* Summarization
* Reasoning
* SQL generation
* Information extraction
* Conversational applications
* AI agents
* RAG answer generation
* Code generation

---

## Major Model Families Available in Databricks

### Meta Llama

```text
databricks-llama-4-maverick
databricks-meta-llama-3-3-70b-instruct
databricks-meta-llama-3-1-8b-instruct
```

Useful for:

* General-purpose AI
* RAG
* Question answering
* Summarization
* Instruction following

For our RAG project we use:

```text
databricks-meta-llama-3-3-70b-instruct
```

---

## OpenAI GPT OSS

```text
databricks-gpt-oss-20b
databricks-gpt-oss-120b
```

Useful for:

* Reasoning
* AI agents
* Coding
* General-purpose applications

---

## Google Gemma

```text
databricks-gemma-3-12b
```

A relatively smaller general-purpose model useful for experimentation and applications where a very large model may not be necessary.

---

## Qwen

Examples currently available include:

```text
databricks-qwen35-122b-a10b
databricks-qwen3-next-80b-a3b-instruct
```

Qwen models can be useful for:

* Reasoning
* Coding
* Agentic applications
* Multilingual applications

---

## Anthropic Claude

Databricks also provides access to several Claude models, depending on workspace and region.

Examples include:

```text
databricks-claude-sonnet-5
databricks-claude-sonnet-4-6
databricks-claude-sonnet-4-5
databricks-claude-haiku-4-5
databricks-claude-opus-5
```

Useful for:

* Advanced reasoning
* Agents
* Coding
* Document analysis
* Long-context tasks

---

## Google Gemini

Different Gemini models are also available through Databricks depending on the workspace and region.

These are useful for:

* General AI
* Reasoning
* Multimodal applications
* Image understanding
* Agentic workflows

---

## Other Model Families

Databricks' model ecosystem also includes models from families such as:

```text
GLM
Kimi
Grok
DeepSeek
```

The exact models available can change as Databricks adds or retires endpoints.

---

# 2. Embedding Models

Embedding models have a completely different job from an LLM.

They convert text into a numerical representation:

```text
Text
 ↓
Embedding Model
 ↓
Vector
```

Example:

```text
"What is the annual leave policy?"
        ↓
Embedding Model
        ↓
[0.017, -0.091, 0.34, ...]
```

These vectors allow applications to compare the **meaning** of different pieces of text.

---

# Databricks-Hosted Embedding Models

The main Databricks-hosted embedding models currently include:

### Qwen3 Embedding

```text
databricks-qwen3-embedding-0-6b
```

This is the embedding model we use in our RAG application.

Useful for:

* RAG
* Semantic search
* Document retrieval
* Similarity search
* Clustering

It also supports configurable embedding dimensions in Databricks.

---

### GTE Large

```text
databricks-gte-large-en
```

A strong English-language embedding model suitable for:

* Semantic search
* RAG
* Document retrieval
* Similarity comparison

---

### BGE Large

```text
databricks-bge-large-en
```

Available in supported Databricks environments and commonly used for English semantic retrieval.

Useful for:

* Vector search
* Document retrieval
* RAG

---

# External Embedding Models

Databricks can also integrate with external embedding providers.

Examples include:

### OpenAI

```text
OpenAI text embedding models
```

### Cohere

```text
Cohere embedding models
```

### Google

```text
Google text embedding models
```

---

# LLM vs Embedding Model

This distinction is extremely important.

| LLM                         | Embedding Model              |
| --------------------------- | ---------------------------- |
| Generates language          | Generates vectors            |
| Answers questions           | Finds similar information    |
| Summarizes information      | Represents semantic meaning  |
| Generates SQL               | Retrieves relevant context   |
| Can reason                  | Performs similarity matching |
| Used after retrieval in RAG | Used during retrieval in RAG |

---

# How They Work Together in RAG

```text
                DOCUMENTS
                    ↓
              Split into Chunks
                    ↓
            Embedding Model
                    ↓
              Vector Store
                    ↓

User Question
      ↓
Embedding Model
      ↓
Question Vector
      ↓
Similarity Search
      ↓
Relevant Chunks
      ↓
LLM
      ↓
Final Answer
```

The embedding model answers:

> **"Which information is relevant?"**

The LLM answers:

> **"How should I explain this information to the user?"**

---

# What We Are Using

For our Databricks RAG application:

### Embeddings

```text
databricks-qwen3-embedding-0-6b
```

### LLM

```text
databricks-meta-llama-3-3-70b-instruct
```

Therefore:

```text
Documents
    ↓
Qwen3 Embedding
    ↓
Vector Search
    ↓
Relevant Chunks
    ↓
Llama 3.3 70B
    ↓
Answer
```

---

# How Do We Choose a Model?

Don't choose a model simply because it is the largest.

Consider:

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

For experimentation, a smaller model may be sufficient.

For complex reasoning or agentic applications, a more capable model may be appropriate.

For RAG retrieval, choose a strong **embedding model** separately from the **generative LLM**.

---

# Key Learning

> **LLMs generate. Embedding models retrieve.**

A modern AI application frequently needs both.

```text
Embedding Model → Find the knowledge

LLM → Use the knowledge

Application → Deliver the experience
```

---

## Important Databricks Note

The exact model endpoints available can vary by:

* Databricks cloud
* Workspace region
* Model availability
* Pay-per-token support
* Provisioned throughput support
* Databricks product updates

Always check the models available inside your own Databricks workspace before selecting one for a production project.
