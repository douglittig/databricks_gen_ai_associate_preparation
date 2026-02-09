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
├── labs/                     # Hands-on labs (9 total, Databricks notebooks)
├── oficial_databricks_material/  # Official Databricks Academy courses (4 modules)
├── Excalidraw/               # Visual diagrams (Obsidian Excalidraw plugin format)
├── diario/                   # Study diary
└── .claude/commands/         # Custom slash commands (estudo.md, excalidraw.md)
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

## Excalidraw Diagrams

Files in `Excalidraw/` are JSON files (`.excalidraw`) used by the Obsidian Excalidraw plugin. The `/excalidraw` command generates new diagrams following Douglas's established design system (colors, fonts, layout patterns). Key conventions:
- Naming: `X.X - Topic Name.excalidraw`
- Theme: light, roughness=1 (sketch style)
- Font families: 5 (Excalifont) for titles, 1 (Virgil) for body, 3 (Cascadia) for code
- **Do NOT commit `.excalidraw` files** — they are in `.gitignore`
- Obsidian may convert `.excalidraw` to `.excalidraw.md` (compressed format). Recovery is possible with LZ-string decompression.

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

## YouTube Video Calendar

25 planned videos (15-20min each, in Portuguese). Schedule and status tracked in `CALENDARIO_VIDEOS_YOUTUBE.md`. When Douglas mentions recording or publishing videos, update both the calendar file and the diary.
