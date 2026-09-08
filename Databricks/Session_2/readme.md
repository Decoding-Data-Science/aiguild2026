# Session 2 — Deploy the AI Application + SQL Analytics

## Goal

Take the application created in Session 1 and move it closer to a real-world Databricks solution by **deploying the application**, loading structured SQL data, and analyzing that data.

---

## Part 1 — Deploy the Application

### What We Cover

1. Prepare the application for deployment
2. Organize application code and dependencies
3. Connect the application to Databricks resources
4. Configure access to model endpoints
5. Deploy the application on Databricks
6. Open and test the deployed application
7. Debug common deployment issues

### Deployment Flow

```text
Notebook
   ↓
Python Application
   ↓
Databricks Resources
   ↓
Model Endpoint
   ↓
Deploy
   ↓
Web Application
   ↓
End User
```

---

## Part 2 — Load and Analyze SQL Data

### What We Cover

1. Load structured data into Databricks
2. Create or access SQL tables
3. Explore schemas, rows, and columns
4. Filter and aggregate data
5. Join multiple tables
6. Calculate business metrics
7. Analyze trends
8. Connect SQL results to the AI application

### Example Questions

```text
How many employees are currently on leave?
Which department has used the most leave?
What is the average leave duration?
How has leave usage changed month by month?
```

### SQL + AI Flow

```text
User Question
      ↓
Application
      ↓
SQL Query
      ↓
Databricks Table
      ↓
Query Result
      ↓
LLM
      ↓
Business-Friendly Answer
```

---

## Session Folder

This folder will contain:

```text
Session_2/
├── readme.md
├── Code / Notebooks
├── Data
└── Supporting Files
```

---

**Key takeaway:** Session 2 moves from **building** an AI workflow to **deploying and connecting it to structured enterprise data**.
