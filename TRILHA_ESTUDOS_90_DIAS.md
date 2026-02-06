# Trilha de Estudos 90 Dias - Databricks GenAI Engineer Associate

## Meta Final
- **Data da Prova:** 01/05/2026 (ou antes se score > 85% nos simulados)
- **Voucher Válido até:** 02/05/2026
- **Tempo diário:** 1h a 1h30

---

## Metodologia: Ultralearning Adaptado para 90 Dias

Esta trilha mantém os 9 princípios do Ultralearning com um ritmo mais sustentável:

1. **Metalearning** - Semana 1 para mapear todo o conteúdo
2. **Focus** - Sessões de 60-90min focadas
3. **Directness** - Labs práticos no Databricks desde a Semana 2
4. **Drill** - Sextas-feiras dedicadas a pontos fracos
5. **Retrieval** - Mini-quiz toda sexta + simulados mensais
6. **Feedback** - 4 practice exams distribuídos
7. **Retention** - Revisão espaçada semanal
8. **Intuition** - Projeto prático contínuo (NASA GCN)
9. **Experimentation** - Variar abordagens nos labs

---

## Estrutura do Exame (Referência Rápida)

| Seção | Peso | Foco Principal |
|-------|------|----------------|
| **Section 1: Design Applications** | 14% | Prompt engineering, Compound AI, Reasoning chains |
| **Section 2: Data Preparation** | 14% | Chunking, RAG data prep, Document parsing |
| **Section 3: Application Development** | 30% | Vector Search, Agents, LangChain, Embeddings |
| **Section 4: Assembling & Deploying** | 22% | MLflow, Model Serving, Pyfunc, Deployment |
| **Section 5: Governance** | 8% | Guardrails, PII, Security |
| **Section 6: Evaluation & Monitoring** | 12% | Metrics, LLM-as-Judge, Monitoring |

**Total:** 45 questões | 90 minutos | ~70% para passar | $200 USD

---

## Visão Geral dos 3 Meses

| Mês | Semanas | Foco | Horas | Vídeos YouTube |
|-----|---------|------|-------|----------------|
| **1** | 1-4 | Foundations + Section 3 (30%) | ~45h | 8 vídeos |
| **2** | 5-8 | Sections 4-5 + Labs Avançados | ~45h | 8 vídeos |
| **3** | 9-12 | Section 6 + Review + Simulados | ~45h | 8 vídeos |

**Total: ~135h de estudo | 24 vídeos para YouTube**

---

## Calendário Visual

```
FEVEREIRO 2026
Dom Seg Ter Qua Qui Sex Sáb
 1   2   3   4   5  [6]  7   ← INÍCIO (Sex 06/02)
[8] ─────────────────── 14   ← Dom 08: Revisão + Simulado #1
[15]─────────────────── 21   ← Dom 15: Revisão + Simulado #2
[22]─────────────────── 28   ← Dom 22: Revisão + Simulado #3

MARÇO 2026
Dom Seg Ter Qua Qui Sex Sáb
[1] ─────────────────── 7    ← Dom 01: Revisão + Simulado #3
 8 ─────────────────── [15]  ← Dom 15: Revisão + Simulado #4
16 ─────────────────── [22]  ← Dom 22: Revisão + Simulado #5
23  24  25  26  27  28 [29]  ← Dom 29: Revisão Mensal

ABRIL 2026
Qua Qui Sex Sáb Dom Seg Ter
 1   2   3   4  [5]  6   7   ← Dom 05: Revisão + Simulado #6
 8   9  10  11 [12] 13  14   ← Dom 12: Revisão + Simulado #7
15  16  17  18 [19] 20  21   ← Dom 19: Simulado Completo #1
22  23  24  25 [26] 27  28   ← Dom 26: Simulado Completo #2
29  30                       ← Buffer final

MAIO 2026
Sex Sáb Dom Seg Ter Qua Qui
[1]  2   3   4   5   6   7   ← PROVA DIA 01/05 (Sexta - Feriado)

Legenda: [X] = Dias importantes (início, revisões, simulados, prova)
```

### Estrutura Semanal Padrão
| Dia | Foco |
|-----|------|
| **Seg-Qui** | Estudo teórico + Labs práticos |
| **Sex** | Labs ou material oficial Databricks |
| **Sáb** | Labs práticos ou cursos oficiais |
| **Dom** | REVISÃO SEMANAL + SIMULADO |

---

# MÊS 1: FOUNDATIONS + APPLICATION DEVELOPMENT

## SEMANA 1: Metalearning & Setup (06/02 - 08/02)
*Semana curta: Sex-Dom (início do plano)*

### Dia 1 - Sex 06/02: Panorama Geral
**Tempo:** 1h15min

#### Estudo (45min)
1. Ler completamente: `knowledge_base/INDEX.md`
2. Ler: `00-OReilly-Book/1.-Exam-Details-and-Resources.md`

#### Prática (30min)
- Verificar acesso ao Databricks workspace
- Testar conexão com MLflow
- Verificar acesso ao Vector Search

#### YouTube Insight
**Vídeo #1:** "Roadmap Completo: Certificação Databricks GenAI em 90 dias"
- Apresentar estrutura do exame
- Mostrar peso de cada seção
- Preview do plano de estudos

---

### Dia 2 - Sáb 07/02: Exam Guide Deep Dive
**Tempo:** 1h15min

#### Estudo (1h)
1. Ler PDF: `00-Exam-Guide/databricks-certified-generative-ai-engineer-associate-guide.pdf`
2. Criar lista de tópicos por seção
3. Marcar tópicos que já domina vs precisa estudar

#### Self-Assessment (15min)
Para cada seção (1-6), dê uma nota de 1-5:
| Seção | Minha Nota | Prioridade |
|-------|------------|------------|
| 1. Design | _ | |
| 2. Data Prep | _ | |
| 3. App Dev | _ | |
| 4. Deploy | _ | |
| 5. Governance | _ | |
| 6. Evaluation | _ | |

---

### 🔄 Dia 3 - Dom 08/02: O'Reilly Book + REVISÃO + SIMULADO
**Tempo:** 2h

#### Estudo (1h)
Ler: `00-OReilly-Book/2.-Designing-Generative-AI-Applications.md`
- Foco em: Prompt Engineering, Task Types, Compound AI Systems
- Fazer anotações dos conceitos-chave

#### Flashcards (criar 10)
Exemplos:
- Q: Zero-shot vs Few-shot? A: Zero-shot não usa exemplos; Few-shot fornece 2-5 exemplos
- Q: Chain-of-thought prompting? A: Instrui o modelo a "pensar passo a passo"

#### Simulado (30min)
Resolver: `simulados/practice_exam_01_en.md` (questões 1-10)
- Timer: 20 minutos
- Sem consulta

#### Revisão (30min)
- Verificar respostas
- Anotar tópicos que errou
- Identificar 3 maiores gaps

#### YouTube Insight
**Vídeo #2:** "5 Conceitos Essenciais para a Certificação GenAI"
- Compound AI Systems
- RAG Architecture
- Vector Search
- MLflow Tracking
- LLM-as-Judge

---

## SEMANA 2: Prompt Engineering & Compound AI (09/02 - 15/02)
*Seg-Dom completa*

### Seg 09/02: Prompt Engineering Fundamentals
**Tempo:** 1h15min

#### Estudo (45min)
1. Ler: `Section1/01-Prompt-Engineering-Fundamentals.md`
2. Ler: `Section1/01-Introduction-Compound-AI.md`

#### Lab (30min)
No Databricks, criar notebook `01-prompt-engineering-lab.py`:
```python
# Zero-shot
prompt_zero = "Classify the sentiment of: 'The product exceeded my expectations!'"

# Few-shot
prompt_few = """
Examples:
- "Love it!" -> Positive
- "Terrible quality" -> Negative
- "It's okay" -> Neutral

Classify: "Best purchase I've made this year!" ->"""

# Chain-of-thought
prompt_cot = """
Question: Should this insurance claim be approved?
Claim: Water damage to basement due to pipe burst.
Policy: Standard home insurance with water damage coverage.

Let's analyze step by step:
1. First, identify the type of damage...
2. Then, check policy coverage...
3. Finally, determine approval status...
"""
```

---

### Ter 10/02: Compound AI Systems
**Tempo:** 1h15min

#### Estudo (45min)
1. Ler: `Section1/02-Defining-Compound-AI-Systems.md`
2. Ler: `Section1/03-Designing-Compound-AI-Systems.md`

#### Exercício (30min)
Desenhar pipeline para um use case:
- **Cenário:** Assistente de suporte técnico
- **Componentes:** Intent classifier → Knowledge retriever → Response generator → Safety checker

---

### Qua 11/02: Multi-Stage Reasoning Chains
**Tempo:** 1h30min

#### Estudo (45min)
1. Ler: `Section1/01-Introduction-Reasoning-Chains.md`
2. Ler: `Section1/02-Multi-stage-Reasoning-Chains.md`

#### Lab (45min)
Executar: `lab-02b-multi-agent/01-multi-agent-workflow.py`
- Entender estrutura do multi-agent
- Documentar cada componente

#### YouTube Insight
**Vídeo #3:** "Prompt Engineering: Zero-shot, Few-shot e Chain-of-Thought"
- Explicar as 3 técnicas
- Quando usar cada uma
- Demo prático no Databricks

---

### Qui 12/02: DEMO - Use Case Planning
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section1/DEMO-01-Deconstruct-Plan-Use-Case.md`

#### Prática (45min)
Aplicar o framework para decompor seu próprio use case:
1. **Intent:** O que o usuário quer?
2. **Tasks:** Quais subtarefas são necessárias?
3. **Pipeline:** Qual a ordem das operações?
4. **Data:** Quais dados são necessários?

---

### Sex 13/02: DEMO - Building Reasoning Chain
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section1/DEMO-01-Building-Reasoning-Chain.md`

#### Lab (45min)
Implementar reasoning chain no Databricks:
```python
from langchain.chains import LLMChain, SequentialChain
from langchain.prompts import PromptTemplate

# Chain 1: Extract entities
extract_template = PromptTemplate.from_template(
    "Extract key entities from: {input}"
)

# Chain 2: Classify intent
classify_template = PromptTemplate.from_template(
    "Given entities {entities}, classify the user intent"
)

# Chain 3: Generate response
response_template = PromptTemplate.from_template(
    "For intent {intent}, generate helpful response"
)
```

---

### Sáb 14/02: O'Reilly - Data Prep & LangChain
**Tempo:** 1h30min

#### Estudo (1h30min)
1. Ler: `00-OReilly-Book/3.-Preparing-and-Chunking-Data-for-RAG-Applications.md`
2. Ler início de: `00-OReilly-Book/4.-Building-GenAI-Applications-with-Python-and-LangChain.md`

#### Tabela de Chunking (completar)
| Estratégia | Tamanho Típico | Melhor Para | Overlap? |
|------------|----------------|-------------|----------|
| Fixed-Length | 500-1000 chars | ? | Opcional |
| Sentence | 1-3 sentenças | ? | Sim |
| Paragraph | 1-2 parágrafos | ? | Não |
| Sliding Window | 500 chars | ? | Sim (200) |
| Semantic | Variável | ? | Não |

---

### 🔄 Dom 15/02: REVISÃO SEMANAL + SIMULADO
**Tempo:** 1h30min

#### Simulado (45min)
Resolver: `simulados/practice_exam_01_en.md` (questões 11-20)
- Timer: 20 minutos
- Sem consulta

#### Revisão (30min)
- Flashcards da semana
- Revisar erros do Practice Exam

#### YouTube Insight
**Vídeo #4:** "Compound AI Systems: Arquitetura e Design"
- O que são sistemas compostos
- Diferença chains vs agents
- Demo: Pipeline de classificação

#### Checkpoint Semanal
- [ ] Sei explicar zero-shot, few-shot, chain-of-thought
- [ ] Entendo arquitetura de Compound AI Systems
- [ ] Implementei uma reasoning chain básica

---

## SEMANA 3: RAG Architecture & Chunking (16/02 - 22/02)

### Seg 16/02: RAG Architecture Introduction
**Tempo:** 1h15min

#### Estudo (45min)
1. Ler: `Section2/01-RAG-Architecture-Introduction.md`
2. Ler: `Section2/02-Context-Engineering.md`

#### Diagrama (30min)
Desenhar arquitetura RAG completa:
```
User Query → Query Embedding → Vector Search → Top-K Chunks →
→ Prompt Assembly → LLM → Response → Post-processing
```

---

### Ter 17/02: Document Parsing & Chunking
**Tempo:** 1h30min

#### Estudo (45min)
Ler: `Section2/03-Document-Parsing-Chunking.md`
- Foco em `ai_parse_document()`
- Entender filtros de qualidade

#### Lab (45min)
Executar: `lab-03-chunking-indexing/01-extract-circulars.py`
- Explorar dados NASA GCN
- Aplicar filtros de limpeza

---

### Qua 18/02: Chunking Strategies Deep Dive
**Tempo:** 1h30min

#### Lab (1h30min)
Executar: `lab-03-chunking-indexing/02-chunking.py`
- Implementar chunking por caracteres
- Implementar chunking por sentenças
- Comparar resultados

#### Documentar
| Estratégia | # Chunks | Tamanho Médio | Observações |
|------------|----------|---------------|-------------|
| Character (500) | ? | ? | |
| Sentence | ? | ? | |
| Paragraph | ? | ? | |

---

### Qui 19/02: DEMO - Preparing Data for RAG
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section2/DEMO-01-Preparing-Data-for-RAG.md`

#### Prática (45min)
Aplicar técnicas no seu notebook:
- Content filtering (remover boilerplate)
- Quality scoring
- Deduplication

#### YouTube Insight
**Vídeo #5:** "Chunking Strategies: O Guia Definitivo"
- 5 estratégias explicadas
- Trade-offs de cada uma
- Demo com dados reais

---

### Sex 20/02: DEMO - Assembling RAG
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section2/DEMO-02-Assembling-and-Evaluating-RAG.md`

#### Lab (45min)
Montar RAG básico com dados preparados

---

### Sáb 21/02: O'Reilly - Deployment Overview
**Tempo:** 1h15min

#### Estudo (1h15min)
Ler: `00-OReilly-Book/5.-Deploying-and-Integrating-RAG-Systems-on-Databricks.md`
- Foco em: MLflow, PyFunc, Model Serving
- Criar checklist de deployment

---

### 🔄 Dom 22/02: REVISÃO SEMANAL + SIMULADO
**Tempo:** 1h30min

#### Simulado (45min)
Resolver: `simulados/practice_exam_02_en.md` (questões 1-10)
- Timer: 20 minutos
- Sem consulta

#### Revisão (30min)
- Flashcards
- Resumo de chunking strategies

#### Planning (15min)
- Ajustar ritmo se necessário

#### Checkpoint Semanal
- [ ] Entendo arquitetura RAG end-to-end
- [ ] Implementei múltiplas estratégias de chunking
- [ ] Sei quando usar cada estratégia

---

## SEMANA 4: Vector Search & Embeddings (23/02 - 01/03)

### Seg 23/02: Mosaic AI Vector Search
**Tempo:** 1h30min

#### Estudo (45min)
1. Ler: `Section3/01-Mosaic-AI-Vector-Search.md`
2. Entender tipos de índice (Delta Sync vs Direct Access)

#### Lab (45min)
Executar: `lab-03-chunking-indexing/03-embeddings-vector-search.py`
- Criar Vector Search endpoint
- Configurar Delta Sync index

---

### Ter 24/02: Vector Store Algorithms
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section3/02-Vector-Store-Algorithms.md`
- HNSW (Hierarchical Navigable Small World)
- Product Quantization
- Reranking

#### Flashcards (criar 10)
- Q: O que é HNSW? A: Algoritmo de ANN que constrói grafo hierárquico para busca rápida
- Q: Product Quantization? A: Técnica de compressão que divide vetores em subvectores

---

### Qua 25/02: Embeddings & Similarity
**Tempo:** 1h30min

#### Estudo (45min)
Ler: `Section3/03-Embeddings-Similarity.md`
- Modelos de embedding (BGE, GTE, E5)
- Métricas de similaridade

#### Lab (45min)
Comparar embeddings no Databricks:
```python
from databricks.vector_search.client import VectorSearchClient

# Testar diferentes embedding models
models = [
    "databricks-bge-large-en",
    "databricks-gte-large-en",
    "databricks-e5-large-v2"
]

# Comparar similaridade para mesma query
```

#### YouTube Insight
**Vídeo #6:** "Vector Search no Databricks: Do Zero ao Deploy"
- Criar endpoint e index
- Delta Sync vs Direct Access
- Demo: busca semântica

---

### Qui 26/02: DEMO - Create Vector Search
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section3/DEMO-01-Create-Vector-Search.md`

#### Lab (45min)
Seguir demo passo a passo no Databricks

---

### Sex 27/02: DEMO - Building Vector Search
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section3/DEMO-02-Building-Vector-Search.md`

#### Lab (45min)
Completar implementação de Vector Search
- Testar queries
- Avaliar resultados

---

### Sáb 28/02: Official Training - Course 1
**Tempo:** 1h30min

#### Lab (1h30min)
Executar notebooks do curso oficial:
`oficial_databricks_material/1 - generative-ai-solution-development-2.0.2/`
- Module 1: From Prompt Engineering to RAG
- Module 2: Preparing Data

---

### 🔄 Dom 01/03: REVISÃO MENSAL #1 + SIMULADO COMPLETO
**Tempo:** 1h30min

#### Simulado Completo (1h)
Resolver: `simulados/practice_exam_02_en.md` (questões 11-20) + revisar erros anteriores
- Timer: 40 minutos
- Ambiente de prova (sem consulta)

#### Review (30min)
- Calcular score acumulado Practice Exam 01 + 02
- Identificar seções fracas

#### YouTube Insight
**Vídeo #7:** "Embeddings e Similaridade: Conceitos Essenciais"
- Como funcionam embeddings
- Cosine vs Euclidean vs Dot Product
- Demo: comparando modelos

#### 📊 Checkpoint Mensal #1
| Métrica | Meta | Resultado |
|---------|------|-----------|
| Practice Exam 01 | ≥70% | ___% |
| Practice Exam 02 | ≥70% | ___% |
| Horas estudadas | ~30h | ___h |
| Labs completados | 3 | ___ |

- Maior gap identificado: ___
- Ajuste no plano: ___

---

# MÊS 2: AGENTS, DEPLOYMENT & GOVERNANCE

## SEMANA 5: Agents Deep Dive (02/03 - 08/03)

### Seg 02/03: Introduction to Agents
**Tempo:** 1h15min

#### Estudo (45min)
1. Ler: `Section3/01-Introduction-Agents.md`
2. Ler início de: `Section3/02-Agents-Fundamentals.md`

#### Conceitos-Chave
- ReAct Pattern: Reasoning + Acting
- Tools: Funções que agents podem chamar
- Memory: ConversationBuffer, WindowMemory

---

### Ter 03/03: Agents Fundamentals
**Tempo:** 1h30min

#### Estudo (45min)
Completar: `Section3/02-Agents-Fundamentals.md`
- Multi-agent patterns
- Supervisor agents

#### Lab (45min)
Implementar agent básico:
```python
from langchain.agents import initialize_agent, Tool

def search_knowledge_base(query: str) -> str:
    """Search the vector store for relevant information."""
    # Implementation
    pass

tools = [
    Tool(
        name="SearchKnowledge",
        func=search_knowledge_base,
        description="Search knowledge base for information"
    )
]

agent = initialize_agent(
    tools=tools,
    llm=llm,
    agent="zero-shot-react-description",
    verbose=True
)
```

---

### Qua 04/03: Agent Bricks Framework
**Tempo:** 1h30min

#### Estudo (45min)
Ler: `Section3/03-Agent-Bricks-Framework.md`
- Knowledge Assistants
- Genie Spaces
- Multi-Agent Supervisors

#### Lab (45min)
Explorar Agent Bricks no Databricks UI

#### YouTube Insight
**Vídeo #8:** "Agents com LangChain: ReAct Pattern na Prática"
- O que são agents
- ReAct explicado
- Demo: Agent com tools

---

### Qui 05/03: DEMO - Agent Design
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section3/DEMO-01-Agent-Design-Databricks.md`

#### Lab (45min)
Executar: `lab-04-rag-app/01-retriever.py`
- Criar retriever sobre Vector Search
- Testar diferentes retrieval strategies

---

### Sex 06/03: DEMO - Retrieval Agent
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section3/DEMO-03-Building-and-Logging-Retrieval-Agent.md`

#### Lab (45min)
Implementar retrieval agent com logging

---

### Sáb 07/03: DEMO - Knowledge Assistant
**Tempo:** 1h30min

#### Estudo (30min)
Ler: `Section3/DEMO-04-Building-Knowledge-Assistant-Agent-Bricks.md`

#### Lab (1h)
Criar Knowledge Assistant usando Agent Bricks

---

### 🔄 Dom 08/03: REVISÃO SEMANAL + SIMULADO
**Tempo:** 1h30min

#### Simulado (45min)
Resolver: `simulados/practice_exam_03_en.md` (questões 1-10)
- Timer: 20 minutos
- Sem consulta

#### Revisão (30min)
- Flashcards de agents
- Comparar chains vs agents

#### YouTube Insight
**Vídeo #9:** "Multi-Agent Systems: Orquestrando Agentes no Databricks"
- Supervisor pattern
- Tool composition
- Demo: Sistema multi-agent

#### Checkpoint Semanal
- [ ] Entendo diferença entre chains e agents
- [ ] Implementei agent com tools customizadas
- [ ] Conheço Agent Bricks framework

---

## SEMANA 6: RAG Implementation Complete (09/03 - 15/03)

### Seg 09/03: RAG Chain Implementation
**Tempo:** 1h30min

#### Lab (1h30min)
Executar: `lab-04-rag-app/02-rag-chain.py`
- Construir RAG chain completa
- Integrar retriever + prompt + LLM
- Testar com queries reais

---

### Ter 10/03: RAG Evaluation Basics
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-04-rag-app/03-evaluation.py`
- Criar evaluation dataset
- Calcular métricas básicas
- Documentar resultados

---

### Qua 11/03: Official Training - Course 2
**Tempo:** 1h30min

#### Lab (1h30min)
Executar notebooks:
`oficial_databricks_material/2 - generative-ai-application-development-2.1.2/`
- Module 2: Building Multi-stage Reasoning Chains
- Module 3: Agents and Cognitive Architectures

#### YouTube Insight
**Vídeo #10:** "RAG Completo: Do Chunk ao Response"
- Pipeline end-to-end
- Integration patterns
- Demo: Q&A sobre dados NASA

---

### Qui 12/03: Vector Optimization - Part 1
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-09-vector-optimization/01-embedding-strategies.py`
- Comparar modelos de embedding
- Medir qualidade de retrieval

---

### Sex 13/03: Vector Optimization - Part 2
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-09-vector-optimization/02-index-tuning.py`
- Tuning de índices
- Filtering strategies

---

### Sáb 14/03: Vector Optimization - Benchmarking
**Tempo:** 1h30min

#### Lab (1h30min)
Executar: `lab-09-vector-optimization/03-benchmarking.py`
- Métricas: Precision, Recall, MRR
- Latency benchmarks

---

### 🔄 Dom 15/03: REVISÃO SEMANAL + SIMULADO
**Tempo:** 1h30min

#### Simulado (45min)
Resolver: `simulados/practice_exam_03_en.md` (questões 11-20)
- Timer: 20 minutos
- Sem consulta

#### Revisão (45min)
- Review das respostas
- Flashcards de RAG

#### Checkpoint Semanal
- [ ] RAG chain funcionando end-to-end
- [ ] Sei avaliar qualidade de retrieval
- [ ] Otimizei índices e embeddings

---

## SEMANA 7: MLflow & Model Management (16/03 - 22/03)

### Seg 16/03: MLflow for RAG
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section4/01-MLflow-for-RAG.md`
- Tracking experiments
- Logging parameters e metrics
- Model Registry

#### Lab (30min)
Implementar tracking básico:
```python
import mlflow

with mlflow.start_run():
    mlflow.log_param("retriever.top_k", 5)
    mlflow.log_param("llm.temperature", 0.1)
    mlflow.log_metric("retrieval_precision", 0.85)
```

---

### Ter 17/03: Model Deployment Fundamentals
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section4/02-Model-Deployment-Fundamentals.md`
- Unity Catalog integration
- Model flavors
- Dependencies management

#### Lab (30min)
Executar: `lab-06-model-management/01-register-model.py`

---

### Qua 18/03: MLflow Agent Development
**Tempo:** 1h30min

#### Estudo (45min)
Ler: `Section4/03-MLflow-Agent-Development.md`
- MLflow Tracing
- Agent experiments

#### Lab (45min)
Executar: `lab-06-model-management/02-versioning.py`

#### YouTube Insight
**Vídeo #11:** "MLflow para GenAI: Tracking, Registry e Tracing"
- Workflow completo
- Versioning patterns
- Demo: Registrar modelo RAG

---

### Qui 19/03: Model Versioning & Aliases
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-06-model-management/03-aliases.py`
- Champion vs Challenger
- Alias management
- Rollback strategies

---

### Sex 20/03: PyFunc Models Deep Dive
**Tempo:** 1h15min

#### Estudo (30min)
Revisar PyFunc patterns no O'Reilly book

#### Lab (45min)
Executar: `lab-05-deployment/01-pyfunc-model.py`
- Estruturar custom PyFunc
- load_context() e predict()

---

### Sáb 21/03: Official Training - Course 3
**Tempo:** 1h30min

#### Lab (1h30min)
Executar notebooks:
`oficial_databricks_material/3 - generative-ai-deployment-and-monitoring-2.0.2/`
- Module 1: Batch Deployment
- Module 2: Real-time Deployment

---

### 🔄 Dom 22/03: REVISÃO SEMANAL + SIMULADO
**Tempo:** 1h30min

#### Simulado (45min)
Resolver: `simulados/practice_exam_04_en.md` (questões 1-10)
- Timer: 20 minutos
- Sem consulta

#### Revisão (30min)
- Flashcards de MLflow
- Resumo de deployment steps

#### YouTube Insight
**Vídeo #12:** "PyFunc: Empacotando RAG para Production"
- Estrutura PyFunc
- Artifacts e dependencies
- Demo: Custom model wrapper

#### Checkpoint Semanal
- [ ] Domino MLflow tracking e registry
- [ ] Entendo model versioning com aliases
- [ ] Criei PyFunc model customizado

---

## SEMANA 8: Model Serving & Real-time Deployment (23/03 - 29/03)

### Seg 23/03: Batch Deployment
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section4/01-Batch-Deployment.md`
- Batch inference patterns
- ai_query() function

#### Lab (30min)
Ler: `Section4/DEMO-01-Batch-Deployment.md`
- Implementar batch inference

---

### Ter 24/03: Real-time Deployment
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section4/02-Real-Time-Deployment.md`
- Model Serving endpoints
- Autoscaling
- Scale-to-zero

#### Lab (30min)
Ler: `Section4/DEMO-02-Real-Time-Deployment.md`

---

### Qua 25/03: Deploy Endpoint
**Tempo:** 1h30min

#### Lab (1h30min)
Executar: `lab-05-deployment/02-deploy-endpoint.py`
- Criar endpoint
- Configurar recursos
- Enable inference logging

#### YouTube Insight
**Vídeo #13:** "Deploy de RAG: Batch vs Real-time"
- Quando usar cada um
- ai_query() para batch
- Model Serving para real-time

---

### Qui 26/03: Test Endpoint
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-05-deployment/03-test-endpoint.py`
- Testar via REST API
- Verificar inference logs
- Load testing básico

---

### Sex 27/03: Official Training - Course 3 (cont.)
**Tempo:** 1h15min

#### Lab (1h15min)
Completar notebooks do Course 3:
- Module 3: AI System Monitoring
- Module 4: Model building exercises

---

### Sáb 28/03: Practice Exam 04 - Part 1
**Tempo:** 1h30min

#### Simulado (1h)
Resolver: `simulados/practice_exam_04_en.md` (questões 11-20)
- Timer: 20 minutos

#### Review (30min)
- Calcular score
- Identificar gaps

---

### 🔄 Dom 29/03: REVISÃO MENSAL #2 + SIMULADO COMPLETO
**Tempo:** 1h30min

#### Simulado Completo (1h)
Revisar todos os 4 Practice Exams (respostas erradas)
- Refazer questões que errou
- Documentar padrões de erro

#### Revisão (30min)
- Flashcards de Sections 3-4
- Resumo de deployment

#### YouTube Insight
**Vídeo #14:** "Model Serving: Endpoints e Autoscaling"
- Criar serving endpoint
- Configurações de recursos
- Demo: teste end-to-end

#### 📊 Checkpoint Mensal #2
| Métrica | Meta | Resultado |
|---------|------|-----------|
| Practice Exam 01 | ≥75% | ___% |
| Practice Exam 02 | ≥75% | ___% |
| Practice Exam 03 | ≥75% | ___% |
| Practice Exam 04 | ≥75% | ___% |
| Horas estudadas (total) | ~60h | ___h |
| Labs completados | 7 | ___ |

- Progresso vs Mês 1: ___
- Ajustes necessários: ___

---

# MÊS 3: GOVERNANCE, EVALUATION & EXAM PREP

## SEMANA 9: Governance & Security (30/03 - 05/04)

### Seg 30/03: Securing GenAI Systems
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section5/01-Securing-and-Governing-GenAI.md`
- DASF framework
- Llama Guard
- Unity Catalog permissions

#### Conceitos-Chave
- PII Detection
- Prompt Injection protection
- Access Control

---

### Ter 31/03: PII Detection
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-07-guardrails/01-pii-detection.py`
- Implementar Presidio
- Detectar PII em documentos

---

### Qua 01/04: Masking & Anonymization
**Tempo:** 1h30min

#### Estudo (30min)
Ler: `Section5/DEMO-01-Prompt-Safety.md`

#### Lab (1h)
Executar: `lab-07-guardrails/02-masking.py`
- Estratégias de masking
- Anonymization techniques

#### YouTube Insight
**Vídeo #15:** "Guardrails para GenAI: PII e Prompt Safety"
- Detectando dados sensíveis
- Masking strategies
- Demo: Presidio no Databricks

---

### Qui 02/04: Prompt Injection Protection
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section5/DEMO-02-Implementing-Guardrails.md`

#### Lab (45min)
Executar: `lab-07-guardrails/03-prompt-protection.py`
- Detectar injection attempts
- Implementar blocking rules

---

### Sex 03/04: Official Training - Course 4
**Tempo:** 1h15min

#### Lab (1h15min)
Executar notebooks:
`oficial_databricks_material/4 - generative-ai-evaluation-and-governance-2.0.6/`
- Module 1: Data Legality and Guardrails
- Module 2: Securing and Governing AI Systems

---

### Sáb 04/04: Document Parsing Security
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section5/DEMO-03-Parse-Documents.md`

#### Prática (45min)
- Aplicar parsing seguro
- Sanitizar inputs

---

### 🔄 Dom 05/04: REVISÃO SEMANAL + SIMULADO
**Tempo:** 1h30min

#### Simulado (45min)
Resolver questões focadas em Governance (Section 5):
- Revisar todas as questões de Governance dos 4 exams
- Timer: 20 minutos

#### Revisão (30min)
- Flashcards de governance
- Checklist de segurança

#### YouTube Insight
**Vídeo #16:** "Governance em GenAI: Unity Catalog e Llama Guard"
- Access control patterns
- Audit logging
- Demo: Implementando guardrails

#### Checkpoint Semanal
- [ ] Implementei PII detection
- [ ] Conheço técnicas de prompt injection protection
- [ ] Entendo DASF framework

---

## SEMANA 10: Evaluation Deep Dive (06/04 - 12/04)

### Seg 06/04: Evaluating RAG Applications
**Tempo:** 1h15min

#### Estudo (45min)
1. Ler: `Section6/01-Evaluating-RAG-Applications.md`
2. Ler: `Section6/02-Importance-of-Evaluation.md`

#### Conceitos-Chave
- Faithfulness
- Answer Relevance
- Context Relevance
- Groundedness

---

### Ter 07/04: Evaluation Techniques
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section6/03-Evaluation-Techniques.md`
- BLEU, ROUGE
- Semantic similarity
- LLM-as-Judge

#### Lab (30min)
Ler: `Section6/DEMO-01-Exploring-Evaluation.md`

---

### Qua 08/04: End-to-End Evaluation
**Tempo:** 1h30min

#### Estudo (45min)
Ler: `Section6/04-End-to-End-Evaluation.md`

#### Lab (45min)
Implementar mlflow.evaluate():
```python
import mlflow

results = mlflow.evaluate(
    model=rag_chain,
    data=eval_data,
    targets="ground_truth",
    model_type="question-answering"
)
print(results.metrics)
```

#### YouTube Insight
**Vídeo #17:** "Métricas de RAG: Faithfulness, Relevance e Groundedness"
- Explicar cada métrica
- Quando usar cada uma
- Demo: mlflow.evaluate()

---

### Qui 09/04: LLM-as-Judge
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section6/DEMO-03-LLM-as-Judge.md`

#### Lab (45min)
Implementar custom scorers:
```python
from mlflow.genai.scorers import Guidelines

guidelines_scorer = Guidelines(
    guidelines="Response must cite sources. Response must be factual."
)

@mlflow.genai.scorer
def custom_accuracy(response, context):
    """Custom evaluation logic."""
    # Implementation
    pass
```

---

### Sex 10/04: Benchmarking
**Tempo:** 1h15min

#### Estudo (30min)
Ler: `Section6/DEMO-02-Benchmarking.md`

#### Lab (45min)
Criar benchmark suite para seu RAG

---

### Sáb 11/04: Official Training - Course 4 (cont.)
**Tempo:** 1h30min

#### Lab (1h30min)
Completar notebooks do Course 4:
- Module 3: Gen AI Evaluation Techniques
- Module 4: End-to-end Application Evaluation

---

### 🔄 Dom 12/04: REVISÃO SEMANAL + SIMULADO
**Tempo:** 1h30min

#### Simulado (45min)
Resolver questões focadas em Evaluation (Section 6):
- Revisar todas as questões de Evaluation dos 4 exams
- Timer: 20 minutos

#### Revisão (30min)
- Flashcards de evaluation
- Comparar métricas

#### YouTube Insight
**Vídeo #18:** "LLM-as-Judge: Avaliação Automatizada de GenAI"
- Como funciona
- Custom scorers
- Demo: Evaluation pipeline

#### Checkpoint Semanal
- [ ] Entendo métricas de RAG evaluation
- [ ] Implementei mlflow.evaluate()
- [ ] Criei custom scorers

---

## SEMANA 11: Monitoring & Production + Simulados Intensivos (13/04 - 19/04)

### Seg 13/04: AI System Monitoring
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section6/01-AI-System-Monitoring.md`
- Lakehouse Monitoring
- Drift detection
- Inference tables

#### Lab (30min)
Executar: `lab-08-monitoring/01-inference-tables.py`

---

### Ter 14/04: LLMOps Concepts
**Tempo:** 1h15min

#### Estudo (45min)
Ler: `Section6/02-LLMOps-Concepts.md`
- MLOps vs LLMOps
- DABs (Databricks Asset Bundles)
- CI/CD for GenAI

#### Lab (30min)
Ler: `Section6/DEMO-01-Online-Monitoring.md`

---

### Qua 15/04: Metrics Dashboard
**Tempo:** 1h30min

#### Lab (1h30min)
Executar: `lab-08-monitoring/02-metrics-dashboard.py`
- Criar dashboard de KPIs
- Configurar visualizações

#### YouTube Insight
**Vídeo #19:** "Monitoring GenAI: Inference Tables e Dashboards"
- O que monitorar
- Construindo dashboards
- Demo: KPIs em tempo real

---

### Qui 16/04: Alerting
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-08-monitoring/03-alerting.py`
- Configurar alerts
- Anomaly detection

---

### Sex 17/04: Production Readiness
**Tempo:** 1h15min

#### Lab (1h15min)
Executar: `lab-10-readiness/01-checklist.py`
- Automated checks
- Validation rules

---

### Sáb 18/04: Load Simulation
**Tempo:** 1h30min

#### Lab (1h30min)
Executar: `lab-10-readiness/02-simulation.py`
- Load testing
- Edge cases
- SLO validation

---

### 🔄 Dom 19/04: SIMULADO COMPLETO #1 (Prova Real)
**Tempo:** 2h

#### 🎯 Simulado Completo (1h30min)
Resolver TODOS os 4 Practice Exams (80 questões):
- **Timer RIGOROSO: 90 minutos** (como na prova real)
- Ambiente de prova: sem consulta, sem pausas
- Usar papel para rascunho se necessário

#### Review (30min)
- Calcular score por seção
- Documentar padrões de erro

#### YouTube Insight
**Vídeo #20:** "LLMOps: Do Notebook ao Production"
- Lifecycle completo
- DABs e CI/CD
- Demo: Deploy automatizado

#### 📊 Score Simulado #1
| Section | Questões | Acertos | % |
|---------|----------|---------|---|
| 1. Design (14%) | ~11 | | |
| 2. Data Prep (14%) | ~11 | | |
| 3. App Dev (30%) | ~24 | | |
| 4. Deploy (22%) | ~18 | | |
| 5. Governance (8%) | ~6 | | |
| 6. Evaluation (12%) | ~10 | | |
| **TOTAL** | **80** | | **____%** |

**Meta: ≥70% | Ideal: ≥80%**

---

## SEMANA 12: Review Final & Exam Prep (20/04 - 30/04)

### Seg 20/04: Review Section 1 & 2
**Tempo:** 1h15min

#### Revisão (1h15min)
- Reler resumos de Section 1-2
- Flashcards intensivos
- Refazer questões erradas dessas seções

---

### Ter 21/04: Review Section 3 (30% do exame!)
**Tempo:** 1h30min

#### Revisão (1h30min)
- Vector Search concepts
- Agents patterns
- RAG implementation
- **FOCO ESPECIAL: esta seção vale 30%!**

---

### Qua 22/04: Review Section 4
**Tempo:** 1h15min

#### Revisão (1h15min)
- MLflow workflow
- PyFunc models
- Model Serving
- Batch vs Real-time

#### YouTube Insight
**Vídeo #21:** "Review Completo: Sections 1-4"
- Quick recap de cada seção
- Pontos mais cobrados
- Dicas para o exame

---

### Qui 23/04: Review Sections 5 & 6
**Tempo:** 1h15min

#### Revisão (1h15min)
- Governance techniques
- Evaluation metrics
- Monitoring patterns

---

### Sex 24/04: Gap Analysis + Estudo Focado
**Tempo:** 1h30min

#### Análise (45min)
- Review todos os erros do Simulado #1
- Categorizar por seção
- Criar plano de revisão focada

#### Estudo (45min)
- Estudar apenas os tópicos com mais erros

---

### Sáb 25/04: Knowledge Base Review
**Tempo:** 1h30min

#### Revisão (1h30min)
Ler rapidamente todos os arquivos de DEMO:
- Section1/DEMO-*.md
- Section2/DEMO-*.md
- Section3/DEMO-*.md
- Section4/DEMO-*.md
- Section5/DEMO-*.md
- Section6/DEMO-*.md

---

### 🔄 Dom 26/04: SIMULADO COMPLETO #2 (Prova Final)
**Tempo:** 2h

#### 🎯 Simulado Completo (1h30min)
Refazer TODOS os 4 Practice Exams (80 questões):
- **Timer RIGOROSO: 90 minutos**
- Ambiente de prova real
- Meta: **≥85% em todas as seções**

#### Review (30min)
- Comparar com Simulado #1
- Documentar melhoria

#### YouTube Insight
**Vídeo #22:** "Review Completo: Sections 5-6"
- Governance essentials
- Evaluation techniques
- Monitoring must-knows

#### 📊 Score Simulado #2
| Section | Simulado #1 | Simulado #2 | Melhoria |
|---------|-------------|-------------|----------|
| 1. Design | ___% | ___% | |
| 2. Data Prep | ___% | ___% | |
| 3. App Dev | ___% | ___% | |
| 4. Deploy | ___% | ___% | |
| 5. Governance | ___% | ___% | |
| 6. Evaluation | ___% | ___% | |
| **TOTAL** | **____%** | **____%** | |

---

### Seg 27/04: Official Materials Final Review
**Tempo:** 1h15min

#### Revisão (1h15min)
Revisar notebooks dos cursos oficiais:
- Key takeaways de cada módulo
- Code patterns importantes

#### YouTube Insight
**Vídeo #23:** "Dicas Finais: O que Cai na Prova"
- Top 10 conceitos
- Pegadinhas comuns
- Estratégias de prova

---

### Ter 28/04: Final Practice
**Tempo:** 1h

#### Prática (1h)
- Flashcards finais (apenas os mais difíceis)
- Revisão rápida de código patterns
- Quick Reference Sheet (ler 2x)

---

### Qua 29/04: Rest Day
**Tempo:** 30min

#### Revisão Leve (30min)
- Apenas flashcards básicos
- Relaxar e descansar
- **Boa noite de sono!**

---

### Qui 30/04: Buffer Day (Véspera)
**Tempo:** 45min

#### Preparação Final (45min)
- Ler Quick Reference Sheet
- Verificar ambiente de prova (internet, webcam, documento)
- Relaxar e confiar na preparação

#### YouTube Insight
**Vídeo #24:** "Jornada Completa: Da Preparação à Certificação"
- Resumo da jornada de 90 dias
- Resultados dos simulados
- Próximos passos pós-certificação

---

# 🎯 DIA DA PROVA: SEXTA 01/05/2026 (Feriado - Dia do Trabalhador)

## Manhã do Exame

### ✅ Checklist Pré-Prova
- [ ] Documento de identidade válido (RG ou CNH)
- [ ] Ambiente silencioso e bem iluminado
- [ ] Mesa limpa (sem papéis, celular, etc.)
- [ ] Conexão de internet estável
- [ ] Água disponível
- [ ] Webcam e microfone funcionando
- [ ] Navegador atualizado
- [ ] Fechar todas as outras abas/aplicativos

### Última Revisão (30min)
- Reler apenas o Quick Reference abaixo
- **NÃO estudar nada novo**
- Confiar na preparação de 90 dias!

### Durante o Exame
1. **Ler com atenção:** Cuidado com "NOT", "EXCEPT", "BEST"
2. **Time management:** ~2 min/questão, flag e volte
3. **Eliminar erradas:** Remova opções claramente incorretas
4. **Usar todo o tempo:** Revisar respostas ao final
5. **Não mudar resposta** sem razão clara

### 📊 Checkpoint Final (Pré-Prova)
| Métrica | Meta | Alcançado |
|---------|------|-----------|
| Simulado #1 | ≥70% | ___% |
| Simulado #2 | ≥80% | ___% |
| Horas estudadas | ~90h | ___h |
| Labs completados | 9/9 | ___/9 |
| Vídeos gravados | 24 | ___ |

**Confiança geral:** ⭐⭐⭐⭐⭐ (marque de 1-5)

---

# QUICK REFERENCE - STUDY SHEET

## Section 1: Design Applications (14%)
```
Prompting:
- Zero-shot: Sem exemplos
- Few-shot: 2-5 exemplos
- Chain-of-thought: "Let's think step by step"

Task Types:
- Classification: Categorizar inputs
- Extraction: Extrair entidades estruturadas
- Transformation: Converter formatos
- Generation: Criar texto novo

Compound AI:
- Chains: Fluxo predefinido, estático
- Agents: Dinâmico, tool selection em runtime
```

## Section 2: Data Preparation (14%)
```
Chunking Strategies:
- Fixed-length: Simples, pode quebrar contexto
- Sentence: Preserva gramática
- Paragraph: Legível, tamanhos variados
- Sliding Window: Overlap preserva continuidade
- Semantic: Adaptativo, complexo

Filtering:
- Remove boilerplate, headers, footers
- Quality scoring
- Deduplication
```

## Section 3: Application Development (30%)
```
Vector Search:
- Delta Sync Index: Auto-sync com Delta table
- Direct Access Index: Upserts manuais
- Embedding: databricks-bge-large-en
- Similarity: cosine (default), euclidean, dot product

HNSW:
- Hierarchical Navigable Small World
- ANN algorithm for fast search
- Trade-off: accuracy vs speed

Agents:
- ReAct: Reasoning + Acting
- Tools: Functions agents can call
- Memory: Buffer, Window, Summary
```

## Section 4: Assembling & Deploying (22%)
```
MLflow:
- mlflow.start_run() → log_param, log_metric
- mlflow.pyfunc.log_model() → save model
- Model Registry: None → Staging → Production
- Aliases: champion, challenger

PyFunc:
- load_context(): Load artifacts
- predict(): Inference logic

Model Serving:
- Scale-to-zero: Cost optimization
- Autoscaling: Handle load spikes
- Inference logging: Track requests

Batch:
- ai_query(): SQL function for batch inference
```

## Section 5: Governance (8%)
```
Security:
- PII Detection: Presidio, regex
- Masking: [EMAIL], [PHONE]
- Prompt Injection: Input validation

Guardrails:
- Llama Guard: Safety classifier
- Custom validators
- Output constraints

Unity Catalog:
- Access control
- Lineage tracking
- Model governance
```

## Section 6: Evaluation & Monitoring (12%)
```
RAG Metrics:
- Faithfulness: Response based on context
- Answer Relevance: Addresses the question
- Context Relevance: Retrieved context useful
- Groundedness: Claims supported by sources

Evaluation:
- mlflow.evaluate(): Built-in metrics
- LLM-as-Judge: Custom scorers
- BLEU/ROUGE: Text similarity

Monitoring:
- Inference tables: Log all requests
- Lakehouse Monitoring: Drift detection
- Alerts: Latency, errors, anomalies
```

---

# ANEXO: Cronograma de Vídeos YouTube

## Mês 1 - Fevereiro/Março (8 vídeos)
| # | Data | Tema | Duração |
|---|------|------|---------|
| 1 | 06/02 (Sex) | Roadmap Completo: Certificação Databricks GenAI em 90 dias | 12min |
| 2 | 08/02 (Dom) | 5 Conceitos Essenciais para a Certificação GenAI | 10min |
| 3 | 11/02 (Qua) | Prompt Engineering: Zero-shot, Few-shot e Chain-of-Thought | 12min |
| 4 | 15/02 (Dom) | Compound AI Systems: Arquitetura e Design | 10min |
| 5 | 19/02 (Qui) | Chunking Strategies: O Guia Definitivo | 12min |
| 6 | 25/02 (Qua) | Vector Search no Databricks: Do Zero ao Deploy | 15min |
| 7 | 01/03 (Dom) | Embeddings e Similaridade: Conceitos Essenciais | 10min |
| 8 | 04/03 (Qua) | Agents com LangChain: ReAct Pattern na Prática | 12min |

## Mês 2 - Março (8 vídeos)
| # | Data | Tema | Duração |
|---|------|------|---------|
| 9 | 08/03 (Dom) | Multi-Agent Systems: Orquestrando Agentes no Databricks | 12min |
| 10 | 11/03 (Qua) | RAG Completo: Do Chunk ao Response | 15min |
| 11 | 18/03 (Qua) | MLflow para GenAI: Tracking, Registry e Tracing | 12min |
| 12 | 22/03 (Dom) | PyFunc: Empacotando RAG para Production | 10min |
| 13 | 25/03 (Qua) | Deploy de RAG: Batch vs Real-time | 12min |
| 14 | 29/03 (Dom) | Model Serving: Endpoints e Autoscaling | 10min |
| 15 | 01/04 (Qua) | Guardrails para GenAI: PII e Prompt Safety | 12min |
| 16 | 05/04 (Dom) | Governance em GenAI: Unity Catalog e Llama Guard | 10min |

## Mês 3 - Abril (8 vídeos)
| # | Data | Tema | Duração |
|---|------|------|---------|
| 17 | 08/04 (Qua) | Métricas de RAG: Faithfulness, Relevance e Groundedness | 12min |
| 18 | 12/04 (Dom) | LLM-as-Judge: Avaliação Automatizada de GenAI | 10min |
| 19 | 15/04 (Qua) | Monitoring GenAI: Inference Tables e Dashboards | 12min |
| 20 | 19/04 (Dom) | LLMOps: Do Notebook ao Production | 12min |
| 21 | 22/04 (Qua) | Review Completo: Sections 1-4 | 15min |
| 22 | 26/04 (Dom) | Review Completo: Sections 5-6 | 12min |
| 23 | 27/04 (Seg) | Dicas Finais: O que Cai na Prova | 10min |
| 24 | 30/04 (Qui) | Jornada Completa: Da Preparação à Certificação | 15min |

**Total: 24 vídeos | ~4h30min de conteúdo**

### Padrão de Publicação
- **Quartas-feiras:** Vídeos técnicos (conceitos, demos)
- **Domingos:** Vídeos de revisão e consolidação

---

# ANEXO: Recursos Utilizados

## Practice Exams
```
simulados/
├── practice_exam_01_en.md  # RAG, Vector Search, Chunking
├── practice_exam_02_en.md  # Agents, MLflow, Multi-modal
├── practice_exam_03_en.md  # Evaluation, Governance
└── practice_exam_04_en.md  # Deployment, Monitoring, LLMOps
```

## Labs NASA GCN
```
labs/
├── lab-02b-multi-agent/        # Multi-agent workflows
├── lab-03-chunking-indexing/   # Chunking + Vector Search
├── lab-04-rag-app/             # RAG implementation
├── lab-05-deployment/          # Model Serving
├── lab-06-model-management/    # MLflow & versioning
├── lab-07-guardrails/          # Security & PII
├── lab-08-monitoring/          # Inference tracking
├── lab-09-vector-optimization/ # Performance tuning
└── lab-10-readiness/           # Production checklist
```

## Official Databricks Courses
```
oficial_databricks_material/
├── 1 - generative-ai-solution-development-2.0.2/
├── 2 - generative-ai-application-development-2.1.2/
├── 3 - generative-ai-deployment-and-monitoring-2.0.2/
└── 4 - generative-ai-evaluation-and-governance-2.0.6/
```

## Knowledge Base
```
knowledge_base/
├── 00-OReilly-Book/           # 5 chapters
├── Section1-Design-Applications/
├── Section2-Data-Preparation/
├── Section3-Application-Development/
├── Section4-Assembling-Deploying/
├── Section5-Governance/
└── Section6-Evaluation-Monitoring/
```

---

# ANEXO: Decision Criteria para Fazer a Prova Antes

Se seu score nos simulados for consistentemente **> 85%**, considere antecipar a prova:

| Critério | Meta | Seu Score |
|----------|------|-----------|
| Practice Exam 01 | ≥ 17/20 (85%) | |
| Practice Exam 02 | ≥ 17/20 (85%) | |
| Practice Exam 03 | ≥ 17/20 (85%) | |
| Practice Exam 04 | ≥ 17/20 (85%) | |
| Confiança Geral | Alta | |

Se todos os critérios forem atingidos na **Semana 8** ou antes, você pode considerar agendar a prova para **meados de Abril**.

---

*Última atualização: Fevereiro 2026*
*Preparação para Databricks Certified Generative AI Engineer Associate*
*Meta: Prova em 01/05/2026 (ou antes se score > 85%)*
