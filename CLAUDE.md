# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

Study materials repository for the **Databricks Generative AI Engineer Associate** certification exam. The owner (Douglas Littig) is preparing for the exam on 01/05/2026.

## Study Orientation Role

When working in this repository, Claude acts as a **study orientator**:
- Check `TRILHA_ESTUDOS_90_DIAS.md` for the daily study plan
- Update `diario/DIARIO_BORDO.md` after each study session
- Use `/estudo` command to get today's study activities
- Track progress on practice exams and labs

## Key Files

| File | Purpose |
|------|---------|
| `TRILHA_ESTUDOS_90_DIAS.md` | 90-day study plan with daily activities |
| `diario/DIARIO_BORDO.md` | Study diary and progress tracking |
| `knowledge_base/INDEX.md` | Index of all study materials by exam section |
| `simulados/practice_exam_0X_en.md` | 4 practice exams (80 questions total) |

## Repository Structure

```
├── knowledge_base/           # Study materials organized by exam sections (1-6)
│   ├── Section1-Design-Applications/
│   ├── Section2-Data-Preparation/
│   ├── Section3-Application-Development/
│   ├── Section4-Assembling-Deploying/
│   ├── Section5-Governance/
│   ├── Section6-Evaluation-Monitoring/
│   └── 00-OReilly-Book/      # O'Reilly study guide chapters
├── simulados/                # Practice exams in English
├── labs/                     # Hands-on labs (9 total)
│   ├── lab-02b-multi-agent/
│   ├── lab-03-chunking-indexing/
│   ├── lab-04-rag-app/
│   ├── lab-05-deployment/
│   ├── lab-06-model-management/
│   ├── lab-07-guardrails/
│   ├── lab-08-monitoring/
│   ├── lab-09-vector-optimization/
│   └── lab-10-readiness/
├── oficial_databricks_material/  # Official Databricks Academy courses
│   ├── 1 - generative-ai-solution-development-2.0.2/
│   ├── 2 - generative-ai-application-development-2.1.2/
│   ├── 3 - generative-ai-deployment-and-monitoring-2.0.2/
│   └── 4 - generative-ai-evaluation-and-governance-2.0.6/
└── diario/                   # Study diary
```

## Exam Structure

| Section | Weight | Key Topics |
|---------|--------|------------|
| 1. Design Applications | 14% | Prompt engineering, Compound AI Systems, chains |
| 2. Data Preparation | 14% | RAG, chunking strategies, document parsing |
| 3. Application Development | 30% | Vector Search, embeddings, agents, LangChain |
| 4. Assembling and Deploying | 22% | MLflow, PyFunc, Model Serving, ai_query() |
| 5. Governance | 8% | Guardrails, PII, Llama Guard, Unity Catalog |
| 6. Evaluation and Monitoring | 12% | LLM-as-Judge, mlflow.evaluate(), Lakehouse Monitoring |

## Labs Execution

Labs are Databricks notebooks (.py files) meant to run on a Databricks workspace. They use:
- Mosaic AI Vector Search
- MLflow for tracking and deployment
- Unity Catalog for governance
- Model Serving endpoints

## Practice Exams Format

Each exam contains 20 questions with:
- Answers marked: ✅ (correct) / ❌ (incorrect)
- Detailed explanations for each question
- Topics: RAG, Vector Search, MLflow, Agents, Evaluation, Governance
