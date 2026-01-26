# Simulado: IA Generativa e Mosaic AI (Databricks)

Este repositório contém 20 questões fundamentais sobre arquitetura de IA Generativa, RAG, Bancos de Dados Vetoriais e o ecossistema Mosaic AI da Databricks.

---

## 1. RAG vs. Fine-Tuning

Ao arquitetar uma solução de IA Generativa, qual fator distingue principalmente a decisão de implementar uma arquitetura de Geração Aumentada de Recuperação (RAG) em vez do Ajuste Fino (Fine-Tuning) de um LLM?

- ❌ **A)** O Fine-tuning é necessário quando a janela de contexto de entrada do modelo é pequena demais.
- ❌ **B)** O Fine-tuning permite que o modelo recorde fatos com 100% de precisão.
- ✅ **C)** O RAG aborda a lacuna de conhecimento ao recuperar dados proprietários atualizados sem os altos custos de computação do treinamento.
- ❌ **D)** O RAG altera o estilo do modelo para uma persona específica, enquanto o fine-tuning não.

> **Explicação:** O RAG é a escolha para dados dinâmicos/externos. O Fine-tuning foca em especialização de tarefa ou estilo, sendo caro e ineficiente para atualização de fatos.

---

## 2. Reranking com Cross-Encoders

Em um pipeline de RAG, por que um desenvolvedor implementaria uma etapa de "Reranking" usando um Cross-Encoder após a recuperação vetorial inicial?

- ❌ **A)** Para acelerar o processo de recuperação ignorando a lógica interna do Vector Store.
- ❌ **B)** Para reduzir o custo filtrando documentos antes que eles cheguem ao Vector DB.
- ✅ **C)** Para abordar as limitações de precisão da busca ANN ao avaliar a relevância real dos documentos usando uma comparação semântica mais profunda.
- ❌ **D)** Para traduzir os documentos recuperados para o idioma nativo do usuário.

> **Explicação:** A busca ANN (Approximate Nearest Neighbor) é rápida mas imprecisa. O Cross-Encoder avalia a relação (Query, Documento) com maior profundidade semântica para garantir o melhor contexto.

---

## 3. Product Quantization (PQ)

Qual é o propósito primário de aplicar a Quantização de Produto (PQ) dentro de um índice de busca vetorial?

- ❌ **A)** Reordenar resultados com base no feedback do usuário.
- ❌ **B)** Aumentar a dimensionalidade dos vetores para capturar mais nuances.
- ❌ **C)** Converter embeddings de texto em imagem para busca multimodal.
- ✅ **D)** Comprimir vetores de alta dimensão em códigos compactos, reduzindo a pegada de memória e permitindo busca de similaridade eficiente.

> **Explicação:** PQ é uma técnica de compressão de vetores essencial para manter grandes volumes de embeddings na RAM de forma performática.

---

## 4. Banco Vetorial vs. Relacional

Como um Banco de Dados Vetorial difere fundamentalmente de um banco de dados relacional tradicional?

- ❌ **A)** Bancos vetoriais não suportam filtragem de metadados.
- ✅ **B)** Bancos vetoriais atendem a consultas baseadas na similaridade semântica de vetores, enquanto relacionais otimizam para correspondências exatas.
- ❌ **C)** Bancos vetoriais armazenam dados em linhas e colunas; relacionais usam blobs.
- ❌ **D)** Bancos vetoriais dependem de B-Tree; relacionais usam correspondência probabilística.

---

## 5. Similaridade de Cosseno

Como um desenvolvedor deve interpretar a relação entre "Similaridade de Cosseno" e distância vetorial?

- ❌ **A)** Score mais alto indica vetores menos similares.
- ✅ **B)** Score mais alto indica vetores mais similares, representando um ângulo menor entre eles.
- ❌ **C)** Cosseno só se aplica a imagens; texto exige distância de Manhattan.
- ❌ **D)** Cosseno mede magnitude; Euclidiana mede o ângulo.

---

## 6. Model Serving Endpoint

Qual a função do "Model Serving Endpoint" na arquitetura RAG do Databricks?

- ✅ **A)** Fornecer uma interface unificada para implantar e consultar modelos de fundação e modelos externos (APIs) para gerar respostas.
- ❌ **B)** Atuar como camada de armazenamento para PDFs brutos.
- ❌ **C)** Realizar o chunking de dados durante a ingestão.
- ❌ **D)** Calcular a similaridade de cosseno entre vetores.

---

## 7. Papel da Delta Table

Qual o papel da Delta Table imediatamente anterior ao Índice de Busca Vetorial no Databricks?

- ✅ **A)** Atuar como fonte da verdade contendo chunks e metadados, com os quais o índice se sincroniza automaticamente.
- ❌ **B)** Substituir o Vector Store via buscas SQL.
- ❌ **C)** Armazenar respostas geradas para cache.
- ❌ **D)** Armazenar PDFs brutos antes do parsing.

> **Explicação:** O Vector Search no Databricks é integrado ao Unity Catalog e sincroniza automaticamente os dados a partir de uma Delta Table.

---

## 8. Segurança e ACLs

Como o Mosaic AI Vector Search suporta segurança e controle de acesso (ACLs)?

- ✅ **A)** Integrando-se com o Unity Catalog para aplicar permissões e permitir filtros de metadados para restringir o escopo.
- ❌ **B)** Criptografando a query antes do envio ao LLM.
- ❌ **C)** Criando um índice separado para cada usuário.
- ❌ **D)** Exigindo credenciais de SQL Warehouse no prompt.

---

## 9. Requisito de Embedding Space

Qual o requisito crítico do "Espaço de Embedding" ao selecionar modelos para RAG?

- ✅ **A)** O modelo da consulta (query) e o do documento devem ser os mesmos para garantir que os vetores estejam no mesmo espaço matemático.
- ❌ **B)** A consulta deve usar um modelo diferente dos documentos para evitar overfitting.
- ❌ **C)** O modelo deve ser proprietário para garantir privacidade.
- ❌ **D)** Dimensões devem ser menores que 256 para compatibilidade.

---

## 10. Componente de Retrieval

Qual a função técnica primária do componente de "Recuperação" (Retrieval) no workflow RAG?

- ❌ **A)** Resumir a query para reduzir tokens.
- ❌ **B)** Ajustar pesos do modelo de fundação.
- ❌ **C)** Converter linguagem natural em SQL.
- ✅ **D)** Identificar e recuperar contexto relevante de um Vector Store para aumentar o prompt enviado ao LLM.

---

## 11. Lost in the Middle

Que fenômeno da janela de contexto deve ser mitigado para garantir recall factual em prompts longos?

- ❌ **A)** Token Drift.
- ❌ **B)** Alucinação de Contexto.
- ❌ **C)** Needle in a Haystack.
- ✅ **D)** Lost in the Middle (informações no meio do contexto são frequentemente ignoradas pelo modelo).

---

## 12. HNSW vs. KNN

Por que o algoritmo HNSW é preferido em relação ao KNN em produção?

- ❌ **A)** HNSW garante 100% de precisão.
- ❌ **B)** HNSW é para preparação de dados; KNN é para busca.
- ❌ **C)** HNSW comprime vetores em binário.
- ✅ **D)** HNSW permite busca ANN (aproximada), trocando mínima precisão por ganhos massivos de velocidade via grafos.

---

## 13. Documentos Complexos (Imagens/Tabelas)

Estratégia avançada para documentos complexos (tabelas/imagens) em RAG?

- ✅ **A)** Usar modelos de layout para extrair texto e LLMs para sumarizar tabelas/imagens, indexando os resumos enquanto mantém referências aos originais.
- ❌ **B)** Criar Vector Stores separados para imagens.
- ❌ **C)** Descartar imagens/tabelas para focar em texto bruto.
- ❌ **D)** Indexar binários de imagens diretamente no espaço de texto.

---

## 14. Trade-off de Chunking

Qual o trade-off entre chunks pequenos vs. grandes?

- ❌ **A)** Pequenos exigem mais armazenamento.
- ❌ **B)** Grandes reduzem chamadas de API.
- ✅ **C)** Pequenos focam em significados específicos (precisão), mas podem carecer de contexto; grandes mantêm contexto, mas introduzem ruído.
- ❌ **D)** Pequenos capturam temas amplos; grandes focam em detalhes.

---

## 15. Windowed Summarization ⚠️

Técnica para mitigar perda de contexto entre chunks consecutivos incluindo sumários prévios?

- ✅ **A)** Windowed summarization (Sumarização em janela).
- ❌ **B)** Fixed-size chunking.
- ❌ **C)** Semantic overlap.
- ❌ **D)** Product Quantization.

> **⚠️ Questão errada no simulado** - A resposta correta é **A) Windowed summarization**.
>
> **Explicação:** A sumarização em janela condensa o contexto anterior e o injeta no chunk atual, garantindo continuidade semântica sem redundância textual excessiva.

---

## 16. Mosaic AI Vector Search

Componente Databricks responsável pelo "Index & Embed" e busca de contexto via sincronia Delta?

- ❌ **A)** Databricks Jobs.
- ❌ **B)** Unity Catalog Governance.
- ✅ **C)** Mosaic AI Vector Search.
- ❌ **D)** Mosaic AI Model Serving.

---

## 17. Injeção de Contexto na Inferência

Em que ponto o "Contexto" é injetado na fase de Inferência?

- ✅ **A)** Na estrutura do prompt junto à query, após a recuperação e antes do envio ao Model Serving.
- ❌ **B)** No Banco Vetorial como nova linha.
- ❌ **C)** Manualmente pelo usuário.
- ❌ **D)** Durante o pré-treinamento do modelo.

---

## 18. MLflow e Avaliação

Papel do MLflow na fase de Avaliação de um RAG?

- ❌ **A)** Gerar ground-truth via scraping.
- ❌ **B)** Armazenar datasets de avaliação.
- ❌ **C)** Retreinar modelos de embedding.
- ✅ **D)** Fornecer um "Evaluation Harness" para testar métricas (faithfulness, relevância) usando LLMs como juízes.

---

## 19. Sincronização e CDC

Recurso do Vector Search que garante atualização automática sem reconstrução manual?

- ❌ **A)** Comandos OPTIMIZE.
- ✅ **B)** Delta Sync API (utiliza Change Data Capture - CDC da Delta Table de origem).
- ❌ **C)** Geração de embedding em tempo real.
- ❌ **D)** Algoritmos HNSW preditivos.

---

## 20. Chain-of-Thought (CoT)

Diferença entre Chain-of-Thought (CoT) e Few-shot prompting?

- ✅ **A)** CoT força a articulação de passos de raciocínio intermediários; Few-shot depende de exemplos estáticos de entrada-saída.
- ❌ **B)** CoT foca em estilo; Few-shot não usa exemplos.
- ❌ **C)** CoT reduz latência; Few-shot aumenta.
- ❌ **D)** CoT é para sumários; Few-shot para aritmética.