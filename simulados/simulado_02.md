# Simulado 02: IA Generativa e Mosaic AI (Databricks)

Este simulado contém 20 questões sobre Arquiteturas de Agentes, MLflow Tracing, Vector Search, Multimodalidade e Desenvolvimento de Aplicações GenAI no ecossistema Databricks.

---

## 1. Processamento de Input Visual em Smart Home Assistant

Em uma arquitetura de exemplo para um "Smart Home Assistant" Multimodal, como o input visual (ex: feed de câmera) é processado antes de ser armazenado no Vector Store?

- ❌ **A)** O arquivo de vídeo bruto é enviado diretamente ao Vector Store sem processamento.
- ✅ **B)** Um M-LLM gera uma descrição da imagem, que é então dividida em chunks e embedded por um modelo de embedding.
- ❌ **C)** O sistema ignora o Vector Store e envia a imagem diretamente ao usuário.
- ❌ **D)** A imagem é convertida em ASCII art e então tokenizada por um LLM de texto padrão.

> **Explicação:** Em arquiteturas multimodais para RAG, o M-LLM processa a imagem e gera uma descrição textual, que é então tratada como texto (chunked e embedded) para armazenamento no Vector Store.

---

## 2. Sincronização do Vector Index no Databricks

Como o Databricks Vector Search garante que o índice vetorial permaneça atualizado com os dados subjacentes?

- ❌ **A)** Regenera o índice inteiro do zero para cada nova consulta para garantir consistência.
- ❌ **B)** Requer que o usuário acione manualmente um job de "Re-Index" a cada 24 horas.
- ❌ **C)** Depende do LLM para detectar dados ausentes e solicitar uma nova busca.
- ✅ **D)** Utiliza um mecanismo "Delta Sync" para sincronizar automaticamente as mudanças da Delta Table de origem para o índice vetorial.

> **Explicação:** O Databricks Vector Search é integrado nativamente com Delta Lake e utiliza Change Data Capture (CDC) para manter o índice automaticamente atualizado.

---

## 3. Padrão "Tool Use" em Agentes

Como o padrão "Tool Use" permite que agentes resolvam problemas que estão fora do escopo dos seus dados de treinamento?

- ✅ **A)** Permitindo que as habilidades de raciocínio do agente decidam quais ferramentas externas (como mecanismos de busca ou bancos de dados) usar e quando/como usá-las.
- ❌ **B)** Pedindo ao usuário que forneça o código necessário para resolver o problema.
- ❌ **C)** Retreinando automaticamente o modelo na internet em tempo real.
- ❌ **D)** Gerando dados sintéticos para preencher as lacunas em seu conhecimento.

> **Explicação:** O padrão Tool Use permite que o agente use seu raciocínio para decidir qual ferramenta externa invocar (calculadora, busca, APIs, etc.), formular o input correto e incorporar o resultado na resposta.

---

## 4. Code-Based vs Serialization-Based Logging no MLflow

Por que o Databricks recomenda "code-based logging" em vez de serialization-based logging ao rastrear agentes com MLflow?

- ❌ **A)** Serialization-based logging não é suportado pela linguagem Python.
- ✅ **B)** Code-based logging captura um "ponto no tempo" do código e configuração do agente, o que é mais robusto do que serialização, que pode ser frágil.
- ❌ **C)** Serialization-based logging consome significativamente mais tokens durante o processo de inferência.
- ❌ **D)** Code-based logging faz fine-tuning automático do modelo, enquanto serialização não.

> **Explicação:** Serialização pode quebrar com mudanças de versões de bibliotecas ou definições de classes. Code-based logging captura código-fonte, configs e dependências, criando um snapshot reproduzível e robusto.

---

## 5. DBRX Instruct vs DBRX Base

O que distingue o modelo "DBRX Instruct" do modelo "DBRX Base"?

- ✅ **A)** DBRX Instruct é construído sobre o DBRX Base e é especificamente fine-tuned em dados de domínio específico para responder perguntas e seguir instruções.
- ❌ **B)** DBRX Instruct é uma versão menor destilada projetada para dispositivos móveis.
- ❌ **C)** DBRX Instruct funciona como um autocomplete inteligente e só é útil para fine-tuning adicional.
- ❌ **D)** DBRX Instruct é um modelo vision-language capaz de processar imagens, enquanto Base é apenas texto.

> **Explicação:** Modelos "Instruct" são o modelo base + fine-tuning com dados de instrução (conversas, Q&A) para seguir comandos. Modelos "Base" são preditores de próximo token, ideais para fine-tuning adicional.

---

## 6. Estabilidade e Complexidade em Bibliotecas Gen AI

Ao escolher uma biblioteca ou framework para desenvolvimento de IA Generativa, por que "Estabilidade e Complexidade" é frequentemente citada como um fator de risco importante?

- ✅ **A)** Essas bibliotecas evoluem rapidamente, e a instabilidade nas APIs pode ser um grande problema, potencialmente tornando-as difíceis de entender e manter.
- ❌ **B)** Bibliotecas como LangChain e Haystack não suportam Python, dificultando a integração.
- ❌ **C)** Bibliotecas open-source são legalmente proibidas de serem usadas em aplicações comerciais.
- ❌ **D)** A maioria das bibliotecas é muito madura e tem código legado que desacelera a inferência.

> **Explicação:** O ecossistema Gen AI evolui rapidamente com breaking changes frequentes, documentação desatualizada e complexidade crescente, tornando difícil manter código de produção estável.

---

## 7. MLflow Tracing vs Standard Logging

Qual é o principal benefício de usar MLflow Tracing em vez de logging padrão ao depurar aplicações de IA Generativa?

- ✅ **A)** Permite a visualização interativa da call stack, rastreando inputs, outputs e latência para cada span (etapa) da chain.
- ❌ **B)** Criptografa os logs para que apenas o dono do modelo possa visualizar os prompts.
- ❌ **C)** Comprime os logs em formato binário para economizar custos de armazenamento.
- ❌ **D)** Reescreve automaticamente o código Python para otimizar a latência da chain.

> **Explicação:** MLflow Tracing oferece observabilidade estruturada com spans para cada etapa, visualização hierárquica da call stack, e tracking de inputs/outputs/latência com interface interativa.

---

## 8. Agentic Workflow vs Non-Agentic (Chain)

Qual é a característica definidora que diferencia um "Agentic Workflow" de um "Non-Agentic Workflow" (Chain)?

- ✅ **A)** Agentes envolvem workflows iterativos e não-determinísticos onde o LLM decide dinamicamente a sequência de ações e ferramentas a usar.
- ❌ **B)** Chains requerem ferramentas externas, enquanto Agentes operam inteiramente dentro da memória paramétrica do modelo.
- ❌ **C)** Chains usam LLMs para raciocínio, enquanto Agentes só usam LLMs para sumarização.
- ❌ **D)** Agentes são determinísticos e sempre seguem uma sequência de ações hard-coded.

> **Explicação:** Agentes são autônomos com loops iterativos (observe → think → act) onde o LLM decide dinamicamente as ações. Chains são sequências pré-definidas e determinísticas.

---

## 9. Estado "Observe" no ReAct

No padrão de raciocínio ReAct (Reason + Act), qual é o propósito do estado "Observe"?

- ❌ **A)** Gerar a resposta final em linguagem natural para o usuário.
- ❌ **B)** Executar as chamadas de API específicas para serviços externos.
- ❌ **C)** Armazenar o histórico de conversação e preferências do usuário.
- ✅ **D)** Executar ações futuras e definir a lógica de como tarefas são decompostas e sequenciadas.

> **Explicação:** Segundo o gabarito oficial, o estado "Observe" é responsável por executar ações futuras e definir a lógica de decomposição e sequenciamento de tarefas.

---

## 10. Arquitetura para Múltiplos Intents

Em um cenário de prompt real envolvendo múltiplos intents (ex: "Traduza esta review, resuma-a e depois analise o sentimento"), qual é a abordagem arquitetural necessária para lidar com a requisição efetivamente?

- ❌ **A)** Aumentar a temperatura do modelo para encorajar multitasking criativo.
- ❌ **B)** Implementar um agente de classificação "One-Shot" que roteia todo o prompt apenas para um modelo de sentimento.
- ❌ **C)** Usar um único prompt "Chain of Thought" que força o modelo a outputar todos os três resultados em um bloco JSON.
- ✅ **D)** Projetar um pipeline estruturado onde a requisição é decomposta em sub-tarefas (tradução, sumarização, análise de sentimento) que podem depender umas das outras.

> **Explicação:** Para requests complexos, decomponha em sub-tarefas discretas, ordene por dependências, e execute sequencialmente. Isso permite melhor debugging, modularidade e tratamento de erros granular.

---

## 11. Fase de "Analysis" no Ciclo de Desenvolvimento

Durante a fase de "Analysis" do ciclo de vida de desenvolvimento de aplicações, quais são os objetivos primários definidos antes de passar para o design de arquitetura?

- ✅ **A)** Definir os objetivos do projeto, requisitos do usuário, escopo, funcionalidades e restrições.
- ❌ **B)** Testes rigorosos e correção de problemas no processo de desenvolvimento.
- ❌ **C)** Delinear o comportamento técnico e codificar os componentes do sistema.
- ❌ **D)** Avaliar o desempenho e usabilidade do deployment contra benchmarks.

> **Explicação:** A fase Analysis foca em entender O QUE construir (requisitos, escopo, restrições) antes de definir COMO construir (arquitetura/design).

---

## 12. Multi-Modal Retrieval com CLIP

Em Multi-Modal Retrieval, qual é a abordagem primária usada por métodos como CLIP para lidar com diferentes tipos de dados?

- ✅ **A)** Embedding de todas as modalidades (texto, imagens, etc.) no mesmo espaço vetorial para permitir busca cross-modal.
- ❌ **B)** Treinar um modelo separado para cada par possível de modalidades (ex: texto-para-imagem, imagem-para-áudio).
- ❌ **C)** Converter todas as imagens em descrições de texto e descartar os dados visuais.
- ❌ **D)** Depender exclusivamente de tags de metadados para recuperação de imagens.

> **Explicação:** CLIP usa aprendizado contrastivo para embeddar texto e imagens no MESMO espaço vetorial, permitindo busca cross-modal onde a similaridade é comparável entre modalidades.

---

## 13. Framework para Inteligência Colaborativa

Qual framework de ferramentas é explicitamente descrito como habilitando inteligência colaborativa ao orquestrar agentes de IA autônomos para trabalharem juntos seamlessly em tarefas complexas?

- ❌ **A)** AutoGPT
- ❌ **B)** Transformers Agents
- ❌ **C)** HuggingGPT
- ✅ **D)** Crew AI

> **Explicação:** Crew AI é especificamente projetado para criar "crews" de agentes de IA colaborativos, cada um com papel/expertise específica, trabalhando juntos em tarefas complexas.

---

## 14. "Signatures" no DSPy

Dentro do framework DSPy, o que são "Signatures"?

- ❌ **A)** Os pesos específicos do modelo fine-tuned.
- ❌ **B)** Os logs gerados pelo compilador automático durante a otimização.
- ❌ **C)** As chaves criptográficas usadas para proteger as chamadas de API do LLM.
- ✅ **D)** Módulos declarativos que guiam LLMs seguindo uma estrutura Pythonica para definir inputs e outputs (ex: ChainOfThought).

> **Explicação:** DSPy Signatures são especificações declarativas de input/output (ex: "question -> answer") que permitem programar LLMs de forma Pythonica sem prompt engineering manual.

---

## 15. Modelo de Pricing para Produção High-Throughput

Qual modelo de pricing da Databricks Foundation Model API é mais adequado para aplicações de produção high-throughput que requerem garantias de performance?

- ✅ **A)** Provisioned Throughput
- ❌ **B)** Pay-per-token
- ❌ **C)** Serverless Compute
- ❌ **D)** Spot Instance Pricing

> **Explicação:** Provisioned Throughput reserva capacidade dedicada com garantias de latência e throughput, ideal para produção crítica. Pay-per-token não garante performance; Spot pode ser interrompido.

---

## 16. Compound AI Systems

De acordo com a definição de "Compound AI Systems", qual é a vantagem primária dessa arquitetura sobre usar um único modelo monolítico?

- ❌ **A)** Elimina a necessidade de prompt engineering ao automatizar o processo de classificação de intent.
- ✅ **B)** Aborda tarefas de IA usando múltiplos componentes interagindo, como retrievers e ferramentas externas, permitindo workflows mais complexos e confiáveis.
- ❌ **C)** Depende exclusivamente de um único Foundation Model para lidar com todas as tarefas de raciocínio e recuperação para minimizar latência.
- ❌ **D)** Força todo o processamento de dados a ocorrer dentro da memória GPU do LLM para garantir privacidade de dados.

> **Explicação:** Compound AI Systems combinam múltiplos componentes (LLMs, retrievers, tools, etc.) para resolver tarefas complexas, sendo mais flexíveis e confiáveis que modelos monolíticos.

---

## 17. DSPy vs Manual Prompting

Como o framework DSPy difere fundamentalmente das técnicas de prompting manual ao programar com LLMs?

- ✅ **A)** Usa um "Automatic Compiler" para rastrear a execução do programa e gerar prompts de alta qualidade ou fazer fine-tune de LLMs para internalizar detalhes procedurais.
- ❌ **B)** Requer que o desenvolvedor escreva manualmente cada instrução e exemplo few-shot para cada interação.
- ❌ **C)** Depende exclusivamente de templates de prompt hard-coded que não podem ser otimizados.
- ❌ **D)** É um construtor visual no-code que impede o uso de estruturas Pythonicas.

> **Explicação:** O Compiler/Optimizer do DSPy gera automaticamente prompts otimizados baseado em Signatures declarativas, eliminando prompt engineering manual.

---

## 18. Componente "Planning" em Sistemas de Agentes

Em uma arquitetura típica de sistema de Agentes, qual é o papel específico do componente "Planning"?

- ✅ **A)** Agentes envolvem workflows iterativos e não-determinísticos onde o LLM dinamicamente decide a sequência de ações e ferramentas a usar.
- ❌ **B)** Chains requerem ferramentas externas, enquanto Agentes operam inteiramente dentro da memória paramétrica do modelo.
- ❌ **C)** Chains usam LLMs para raciocínio, enquanto Agentes só usam LLMs para sumarização.
- ❌ **D)** Agentes são determinísticos e sempre seguem uma sequência de ações hard-coded.

> **Explicação:** O componente Planning é responsável por decompor tarefas, decidir a sequência de execução e determinar quais ferramentas usar dinamicamente.

---

## 19. Definição de "Chain" no LangChain

No contexto do framework LangChain, como uma "Chain" é especificamente definida?

- ❌ **A)** Um input de texto estruturado projetado para comunicar uma tarefa específica a um modelo de linguagem.
- ❌ **B)** Uma interface de banco de dados que retorna documentos relevantes baseados em consultas não-estruturadas.
- ❌ **C)** Uma função standalone que um agente pode ativar, como uma chamada de API ou lookup em banco de dados.
- ✅ **D)** Uma sequência de ações ou componentes automatizados que processam a query do usuário para produzir o output do modelo.

> **Explicação:** Uma Chain no LangChain é uma sequência de componentes conectados que automatizam o fluxo da query até o output. A=Prompt, B=Retriever, C=Tool.

---

## 20. Multi-agent Collaboration - Desafio de Escalabilidade

Qual desafio de escalabilidade em tarefas complexas o padrão "Multi-agent Collaboration" especificamente aborda?

- ❌ **A)** Garante que todos os agentes compartilhem exatamente a mesma memória e janela de contexto para prevenir alucinações.
- ✅ **B)** Aborda a dificuldade de escalar o comportamento de um único agente utilizando agentes especializados que trabalham colaborativamente em diferentes aspectos da tarefa.
- ❌ **C)** Elimina a necessidade de um LLM "Cérebro" central ao distribuir a lógica para o banco de dados vetorial.
- ❌ **D)** Reduz o custo de inferência usando modelos menores e não-especializados para todas as tarefas.

> **Explicação:** Multi-agent Collaboration resolve escalabilidade decompondo tarefas em sub-tarefas com agentes especializados que colaboram, sendo mais escalável que um único agente sobrecarregado.
