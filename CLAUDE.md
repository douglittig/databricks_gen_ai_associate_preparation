# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

Study materials repository for the **Databricks Generative AI Engineer Associate** certification exam. The owner (Douglas Littig) is preparing for the exam on 01/05/2026.

## Language

Douglas speaks **Portuguese (BR)**. Respond in Portuguese unless the context is clearly English (e.g., editing English-language files).

## Study Orientation Role

When working in this repository, Claude acts as a **study orientator**:
- Check `TRILHA_ESTUDOS_90_DIAS.md` for the daily study plan
- Update `diario/DIARIO_BORDO.md` after each study session
- Track progress on practice exams and labs
- **Study start date: 06/02/2026** — use this to calculate current day number

### Day Calculation

```
Current study day = (today's date - 06/02/2026) + 1
Example: 13/02/2026 = Day 8
```

### Custom Commands

| Command | Purpose |
|---------|---------|
| `/estudo` | Calculate today's study day, show activities from the plan, update diary when done |
| `/excalidraw <topic>` | Generate an Excalidraw diagram following Douglas's visual design system |

## Key Files

| File | Purpose |
|------|---------|
| `TRILHA_ESTUDOS_90_DIAS.md` | 90-day study plan with daily activities |
| `diario/DIARIO_BORDO.md` | Study diary and progress tracking |
| `CALENDARIO_VIDEOS_YOUTUBE.md` | YouTube video publication calendar (25 videos) |
| `simulados/practice_exam_0X_en.md` | 4 practice exams (80 questions total) |

## Exam Structure

| Section | Weight | Key Topics |
|---------|--------|------------|
| 1. Design Applications | 14% | Prompt engineering, Compound AI Systems, chains |
| 2. Data Preparation | 14% | RAG, chunking strategies, document parsing |
| 3. Application Development | 30% | Vector Search, embeddings, agents, LangChain |
| 4. Assembling and Deploying | 22% | MLflow, PyFunc, Model Serving, ai_query() |
| 5. Governance | 8% | Guardrails, PII, Llama Guard, Unity Catalog |
| 6. Evaluation and Monitoring | 12% | LLM-as-Judge, mlflow.evaluate(), Lakehouse Monitoring |

## Labs

### LangChain Essentials (labs/LangChain Essentials - Python/)

9 Jupyter notebooks adapted for Databricks environment with comprehensive Portuguese documentation:

| Lab | Topic | Key Concepts |
|-----|-------|--------------|
| L1 | Fast Agent | ReAct cycle, @tool decorator, System prompts |
| L2 | Messages | SystemMessage, HumanMessage, AIMessage, ToolMessage |
| L3 | Streaming | values vs messages mode, real-time output |
| L4 | Tools | Tool descriptions, parameter typing |
| L5 | MCP | Model Context Protocol, external tool servers |
| L6 | Memory | InMemorySaver, thread_id, conversation state |
| L7 | Structured Output | TypedDict vs Pydantic BaseModel |
| L8 | Dynamic Prompts | @dynamic_prompt middleware, RuntimeContext |
| L9 | HITL | HumanInTheLoopMiddleware, interrupt patterns |

- Use `ChatDatabricks` with endpoint `databricks-meta-llama-3-3-70b-instruct`
- SQL queries target `nasa_gcn.silver` tables (from [projeto-nasa-gcn](https://github.com/douglittig/projeto-nasa-gcn))
- All notebooks include `mlflow.langchain.autolog()` for tracing

### Databricks Notebook Pattern

```python
# Setup cell pattern for all labs
%pip install -U mlflow>=3 langchain>=1 langchain-community databricks-langchain --quiet
dbutils.library.restartPython()

import mlflow
mlflow.langchain.autolog()

from databricks_langchain import ChatDatabricks
llm = ChatDatabricks(endpoint="databricks-meta-llama-3-3-70b-instruct", temperature=0.1)
```

## Excalidraw Diagrams

Files in `Excalidraw/` are JSON files used by the Obsidian Excalidraw plugin. Key conventions:
- Naming: `X.X - Topic Name.excalidraw`
- Theme: light, roughness=1 (sketch style)
- Font families: 5 (Excalifont) for titles, 1 (Virgil) for body, 3 (Cascadia) for code
- **Do NOT commit `.excalidraw` files** — they are in `.gitignore`

## Practice Exams Format

Each exam contains 20 questions with:
- Answers marked: ✅ (correct) / ❌ (incorrect)
- Detailed explanations for each question
- Topics: RAG, Vector Search, MLflow, Agents, Evaluation, Governance

## YouTube Video Calendar

25 planned videos (15-20min each, in Portuguese). Schedule and status tracked in `CALENDARIO_VIDEOS_YOUTUBE.md`. When Douglas mentions recording or publishing videos, update both the calendar file and the diary.

## Common Tasks

### Update study progress
1. Read current day's activities from `TRILHA_ESTUDOS_90_DIAS.md`
2. Update `diario/DIARIO_BORDO.md` with completed tasks
3. Update metrics (hours, labs, videos) in the diary summary

### Track practice exam scores
1. Practice exams are in `simulados/practice_exam_0X_en.md`
2. Record scores in `diario/DIARIO_BORDO.md` under "Histórico de Simulados"
3. Note weak sections for focused review

### Add video to calendar
1. Update `CALENDARIO_VIDEOS_YOUTUBE.md` with new entry
2. Update `diario/DIARIO_BORDO.md` under "Vídeos Gravados"
3. Increment video count in diary metrics
