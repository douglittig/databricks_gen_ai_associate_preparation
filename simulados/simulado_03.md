# Simulado 03: IA Generativa e Mosaic AI (Databricks)

Este simulado contém 20 questões sobre Avaliação de LLMs, Métricas RAG, Segurança e Governança de IA Generativa no ecossistema Mosaic AI da Databricks.

---

## 1. LLM-as-a-Judge - Melhores Práticas

Ao usar "LLM-as-a-Judge" para avaliar casos complexos onde dados de referência não estão disponíveis, qual é a melhor prática recomendada para melhorar a confiabilidade das métricas?

- ✅ **A)** Implementar um processo "Human-in-the-loop" para revisar métricas geradas pelo LLM e lidar com ambiguidades.
- ❌ **B)** Depender exclusivamente da métrica "toxicity" pois é a única métrica estável para LLMs.
- ❌ **C)** Usar o menor modelo possível (ex: 7B parâmetros) para garantir velocidades de processamento mais rápidas.
- ❌ **D)** Evitar fornecer uma rubrica ou instruções específicas para prevenir viés no modelo juiz.

> **Explicação:** Quando não há ground truth disponível, humanos devem revisar e validar os julgamentos do LLM para capturar erros, lidar com casos ambíguos e melhorar a confiabilidade. Rubricas claras também melhoram consistência.

---

## 2. BLEU vs ROUGE

Qual afirmação contrasta corretamente as métricas de avaliação BLEU e ROUGE?

- ❌ **A)** BLEU é uma métrica orientada a recall usada principalmente para sumarização; ROUGE é uma métrica orientada a precision usada para tradução.
- ❌ **B)** BLEU mede a toxicidade do output, enquanto ROUGE mede a latência da requisição.
- ✅ **C)** BLEU compara similaridades de n-grams para tradução (orientada a precision); ROUGE calcula recall de n-grams, tornando-a adequada para sumarização.
- ❌ **D)** Ambas as métricas são avaliadores semânticos que usam embeddings para determinar o tom emocional do texto.

> **Explicação:** BLEU (Bilingual Evaluation Understudy) é precision-focused, medindo quantos n-grams do output aparecem na referência - bom para tradução. ROUGE (Recall-Oriented Understudy for Gisting Evaluation) é recall-focused - bom para sumarização.

---

## 3. Offline vs Online Evaluation

Qual distinção melhor descreve a diferença entre Avaliação Offline e Online de LLMs?

- ❌ **A)** Avaliação offline mede latência; avaliação online mede acurácia.
- ❌ **B)** Avaliação offline é manual; avaliação online é totalmente automatizada pelo MLflow.
- ✅ **C)** Avaliação offline usa datasets de benchmark e dados de referência (ou LLM-as-a-Judge) antes da produção; avaliação online usa comportamento real do usuário e feedback dentro da produção.
- ❌ **D)** Avaliação offline ocorre na nuvem; avaliação online ocorre no dispositivo.

> **Explicação:** Offline = pré-deploy com datasets preparados e benchmarks. Online = em produção com usuários reais, medindo comportamento, feedback e performance real.

---

## 4. Recursos: LLM vs Classical ML

Ao comparar avaliação de LLMs com avaliação de ML clássico, qual requisito de recurso distinto é um desafio primário para LLMs?

- ❌ **A)** LLMs requerem significativamente menos armazenamento porque não usam feature stores.
- ❌ **B)** LLMs dependem exclusivamente de computação CPU, tornando-os mais baratos de avaliar que modelos de regressão clássicos.
- ❌ **C)** ML clássico requer juízes humanos para cada predição, enquanto LLMs nunca requerem feedback humano.
- ✅ **D)** LLMs requerem quantidades massivas de dados e recursos computacionais substanciais (GPUs/TPUs) comparados ao hardware menos caro do ML clássico.

> **Explicação:** LLMs precisam de significativamente mais recursos computacionais (GPUs/TPUs), mais memória, mais armazenamento e mais dados. Modelos clássicos frequentemente rodam em CPUs com recursos modestos.

---

## 5. Métrica Answer Relevancy

O que a métrica "Answer Relevancy" avalia especificamente em um pipeline RAG?

- ❌ **A)** Se os documentos recuperados contêm a resposta correta.
- ❌ **B)** A porcentagem de n-grams na resposta que aparecem no contexto.
- ✅ **C)** O alinhamento da resposta gerada com a intenção inicial da query do usuário.
- ❌ **D)** A similaridade semântica entre a resposta gerada e o ground truth.

> **Explicação:** Answer Relevancy mede se a resposta gerada realmente responde à pergunta do usuário. Avalia o alinhamento entre a resposta e o intent original da query, não a correção factual.

---

## 6. Llama Guard

Qual descrição melhor caracteriza a arquitetura e função do Llama Guard como modelo de salvaguarda?

- ❌ **A)** É uma ferramenta de banco de dados vetorial que remove tokens de alta perplexidade da janela de contexto.
- ❌ **B)** É um filtro de correspondência de palavras-chave que bloqueia qualquer prompt contendo palavras de uma "lista banida" estática.
- ✅ **C)** É um classificador baseado em LLM que usa uma taxonomia de riscos e diretrizes para classificar e mitigar riscos de segurança tanto em prompts de usuários quanto em respostas do modelo.
- ❌ **D)** É um script de pós-processamento que avalia apenas a saída final do modelo para correção gramatical.

> **Explicação:** Llama Guard é um classificador de segurança baseado em LLM desenvolvido pela Meta. Usa uma taxonomia definida de categorias de segurança (violência, conteúdo sexual, discurso de ódio, etc.) para classificar TANTO prompts de entrada QUANTO respostas de saída como seguros ou inseguros.

---

## 7. Answer Correctness vs Faithfulness

Como "Answer Correctness" difere de "Faithfulness" na avaliação RAG?

- ❌ **A)** Não há diferença; são termos sinônimos no framework Mosaic AI.
- ✅ **B)** Answer Correctness requer um Ground Truth para medir acurácia; Faithfulness verifica se a resposta é derivada puramente do contexto recuperado.
- ❌ **C)** Faithfulness compara a resposta ao ground truth; Answer Correctness compara a resposta ao contexto.
- ❌ **D)** Answer Correctness é uma métrica offline; Faithfulness só está disponível em avaliação online.

> **Explicação:** Answer Correctness compara a resposta gerada com um ground truth (resposta de referência) para medir correção factual. Faithfulness (groundedness) verifica se a resposta é suportada pelo contexto recuperado - se não há alucinações de informações fora do contexto.

---

## 8. Prompt Injection

Um atacante insere uma query projetada para sobrescrever as instruções de um sistema GenAI para extrair informações privadas ou gerar respostas prejudiciais. Qual termo melhor descreve esse risco de segurança, e qual é a estratégia de mitigação primária discutida?

- ❌ **A)** Model Poisoning; mitigado aumentando o tamanho do dataset de validação.
- ❌ **B)** Hallucination; mitigado diminuindo o parâmetro de temperatura do modelo.
- ❌ **C)** Data Drift; mitigado retreinando o modelo com dados novos usando Lakehouse Monitoring.
- ✅ **D)** Prompt Injection; mitigado implementando guardrails para filtrar inputs e outputs.

> **Explicação:** Prompt Injection é exatamente isso - um atacante cria input para manipular o comportamento do modelo, sobrescrever instruções ou extrair informações sensíveis. A mitigação primária é implementar guardrails (como Llama Guard) para filtrar TANTO inputs QUANTO outputs.

---

## 9. Context Recall

Para calcular "Context Recall", quais dois elementos de dados específicos são necessários?

- ❌ **A)** A User Query e os logs de Latência.
- ✅ **B)** O Ground Truth e o(s) Contexto(s) Recuperado(s).
- ❌ **C)** A User Query e a Resposta Gerada.
- ❌ **D)** A Resposta Gerada e o Contexto Recuperado.

> **Explicação:** Context Recall mede quanto da informação relevante do ground truth está presente no contexto recuperado. Compara o que DEVERIA ter sido recuperado (ground truth) com o que FOI recuperado (retrieved context). Responde: "Recuperamos toda a informação necessária?"

---

## 10. DASF - Stakeholder Gap

De acordo com o Data and AI Security Framework (DASF), identificar riscos de segurança é complexo porque poucos profissionais têm uma visão completa do sistema. Qual lacuna de stakeholder é explicitamente identificada como um desafio na segurança de IA?

- ✅ **A)** Data scientists tipicamente não realizaram tarefas de segurança, e equipes de segurança frequentemente são novas em arquiteturas de IA.
- ❌ **B)** Liderança executiva prioriza velocidade sobre compliance em 90% das organizações.
- ❌ **C)** Provedores de nuvem não oferecem criptografia para bancos de dados vetoriais.
- ❌ **D)** Equipes jurídicas frequentemente se recusam a revisar o código de modelos generativos.

> **Explicação:** Existe uma lacuna de habilidades bem conhecida em segurança de IA. Data scientists focam em ML/AI mas podem carecer de expertise em segurança, enquanto profissionais de segurança podem carecer de conhecimento sobre arquiteturas AI/ML. Isso cria uma lacuna na compreensão do quadro completo de segurança.

---

## 11. Data Licensing

Ao avaliar a legalidade de dados para uma aplicação GenAI destinada a lucro comercial, qual dos seguintes cenários apresenta uma violação baseada na discussão do curso sobre licenciamento de dados?

- ❌ **A)** Usar um modelo pré-treinado que inclui um "Safety Filter" para bloquear outputs tóxicos.
- ❌ **B)** Usar um dataset com licença open-source que permite modificação e redistribuição para qualquer propósito.
- ❌ **C)** Treinar um modelo com dados internos da empresa que foram totalmente anonimizados e aprovados pela equipe jurídica.
- ✅ **D)** Usar um dataset licenciado para "propósitos pessoais e de pesquisa" para treinar um modelo que alimenta um serviço de assinatura pago.

> **Explicação:** Violação clara de licenciamento. Se um dataset é licenciado apenas para "propósitos pessoais e de pesquisa", usá-lo para um serviço comercial de assinatura paga viola os termos da licença.

---

## 12. DASF - Catalog

Dentro do Data and AI Security Framework (DASF), qual componente foca na governança de ativos de dados através de controle de acesso centralizado, linhagem e auditoria para garantir qualidade e confiabilidade dos dados?

- ❌ **A)** Model Management
- ❌ **B)** Evaluation
- ✅ **C)** Catalog
- ❌ **D)** Algorithm

> **Explicação:** O Catalog (como Unity Catalog no Databricks) fornece governança centralizada incluindo: controle de acesso (permissões), rastreamento de linhagem de dados, capacidades de auditoria, e gerenciamento de qualidade e confiabilidade dos dados.

---

## 13. Limitações de BLEU e ROUGE

Qual é uma limitação compartilhada das métricas BLEU e ROUGE ao avaliar outputs de IA Generativa?

- ❌ **A)** Elas dependem de "LLM-as-a-Judge" para gerar uma pontuação, tornando-as não-determinísticas.
- ❌ **B)** Elas são aplicáveis apenas a tarefas de geração de imagem, não texto.
- ✅ **C)** Ambas requerem um dataset de referência e dependem de correspondência de n-grams em vez de entendimento semântico.
- ❌ **D)** Elas só podem ser calculadas usando o Mosaic AI Agent Framework.

> **Explicação:** Tanto BLEU quanto ROUGE: requerem textos de referência para comparação, usam correspondência de n-grams (lexical/baseado em tokens), e NÃO capturam significado semântico. Uma paráfrase com palavras diferentes mas mesmo significado teria pontuação baixa.

---

## 14. Perplexity

Se um modelo de base foundation exibe um pico acentuado em sua distribuição de probabilidade para a predição do próximo token, como isso é refletido na métrica de Perplexity e na confiança do modelo?

- ❌ **A)** Alto Perplexity, indicando alta confiança e alta acurácia.
- ❌ **B)** Baixo Perplexity, indicando baixa confiança e baixa acurácia.
- ✅ **C)** Baixo Perplexity, indicando alta confiança e acurácia.
- ❌ **D)** Alto Perplexity, indicando baixa confiança e acurácia.

> **Explicação:** Perplexity é inversamente relacionado à confiança. Pico acentuado = baixo perplexity = alta confiança = geralmente mais acurado. Alto perplexity indica distribuição plana (incerteza), baixo perplexity indica distribuição concentrada (certeza).

---

## 15. Faithfulness

Qual métrica de avaliação RAG mede a acurácia factual da resposta gerada especificamente em relação ao contexto fornecido, sem necessariamente verificar contra um ground truth?

- ❌ **A)** Toxicity
- ❌ **B)** Context Recall
- ❌ **C)** Answer Correctness
- ✅ **D)** Faithfulness

> **Explicação:** Faithfulness (groundedness) mede se a resposta gerada é factualmente suportada/derivada do contexto fornecido. Verifica se a resposta alucina informações que NÃO estão no contexto. NÃO requer ground truth - apenas compara resposta vs contexto.

---

## 16. Unity Catalog e GenAI

Como o Unity Catalog suporta a governança de aplicações GenAI especificamente em relação a vector search e retrieval?

- ✅ **A)** Ele governa índices vetoriais no Vector Search, gerencia modelos GenAI, e rastreia linhagem end-to-end dos dados da aplicação.
- ❌ **B)** Ele criptografa a memória GPU usada durante o processo de inferência do foundation model.
- ❌ **C)** Ele automaticamente reescreve prompts de usuários para remover linguagem tóxica antes de chegarem ao modelo.
- ❌ **D)** Ele fornece um modelo proprietário "LLM-as-a-Judge" para pontuar a acurácia de embeddings vetoriais.

> **Explicação:** Unity Catalog fornece: governança de índices vetoriais no Databricks Vector Search, gerenciamento de modelos GenAI (registrados no UC), rastreamento de linhagem end-to-end, controle de acesso/permissões, e capacidades de auditoria.

---

## 17. Truth em GenAI vs Classical ML

No contexto de avaliação de IA Generativa, como o conceito de "Verdade" difere da avaliação de Machine Learning (ML) clássico, apresentando um desafio específico para governança?

- ✅ **A)** Em GenAI, frequentemente não há uma única resposta verdadeira ou correta para um dado input, diferente do ML clássico que tipicamente compara predições a dados de rótulos alvo específicos.
- ❌ **B)** Modelos GenAI automaticamente filtram "Verdade" baseado em scores de toxicidade dos dados de treino, enquanto ML clássico requer intervenção manual.
- ❌ **C)** Modelos GenAI são incapazes de processar dados rotulados, enquanto ML clássico depende exclusivamente de aprendizado não-supervisionado.
- ❌ **D)** ML clássico produz outputs probabilísticos que são impossíveis de auditar, enquanto outputs GenAI são determinísticos.

> **Explicação:** Desafio fundamental em avaliação GenAI. ML clássico tem ground truth claros (rótulos de classificação, targets de regressão). Outputs GenAI são frequentemente abertos com múltiplas respostas válidas - não há uma única resposta "correta" para muitos prompts.

---

## 18. MLflow Custom Metrics Workflow

Em um workflow de avaliação MLflow para uma métrica customizada de "Profissionalismo", quais são os três passos essenciais necessários para realizar a avaliação?

- ❌ **A)** 1) Definir um score BLEU, 2) Definir um score ROUGE, 3) Calcular a média deles.
- ❌ **B)** 1) Ingerir dados no Delta Lake, 2) Executar uma query SQL, 3) Visualizar em um dashboard.
- ❌ **C)** 1) Treinar um novo modelo, 2) Fazer deploy para produção, 3) Verificar latência.
- ✅ **D)** 1) Criar registros de avaliação, 2) Criar um objeto de métrica (incluindo definição, grading prompt, e critérios de pontuação), 3) Avaliar o modelo contra um dataset usando a métrica.

> **Explicação:** O workflow correto é: 1) Criar evaluation records (dados para avaliar), 2) Criar objeto de métrica customizada com definição, grading prompt e scoring criteria, 3) Executar mlflow.evaluate() com a métrica contra o dataset.

---

## 19. Mosaic AI Agent Framework

O Mosaic AI Agent Framework facilita "Agent Evaluation" fornecendo qual conjunto específico de capacidades?

- ❌ **A)** Uma planilha estritamente manual para registrar erros encontrados por testadores QA.
- ❌ **B)** Uma ferramenta que automaticamente reescreve o código Python subjacente do agente para melhorar performance.
- ❌ **C)** Um dashboard que exibe apenas o custo de chamadas de API e nenhuma métrica de qualidade.
- ✅ **D)** Um conjunto de ferramentas para rastrear comportamento do agente, avaliar qualidade com métricas específicas de RAG, e coletar feedback humano via Review App.

> **Explicação:** O Mosaic AI Agent Framework fornece: Tracing para comportamento do agente (MLflow Tracing), métricas de avaliação específicas de RAG (faithfulness, relevancy, etc.), Review App para coletar feedback humano, e ferramentas de avaliação de qualidade.

---

## 20. Context Precision

Em uma arquitetura RAG (Retrieval Augmented Generation), por que é crítico avaliar a métrica "Context Precision"?

- ❌ **A)** Para garantir que a query do usuário não contenha PII (Personally Identifiable Information).
- ❌ **B)** Para medir a correção gramatical da resposta final gerada pelo LLM.
- ❌ **C)** Para calcular o custo do modelo de embedding em dólares por token.
- ✅ **D)** Para determinar a razão sinal-ruído do contexto recuperado, garantindo que chunks relevantes sejam ranqueados mais alto que os irrelevantes.

> **Explicação:** Context Precision mede a qualidade do ranking de recuperação. Avalia se chunks relevantes aparecem no topo dos resultados (alta precision) vs ter chunks irrelevantes misturados. Alta context precision = documentos relevantes ranqueados mais alto, baixo ruído.

---
