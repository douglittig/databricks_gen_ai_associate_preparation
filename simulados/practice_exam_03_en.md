# Practice Exam 03: Generative AI and Mosaic AI (Databricks)

This practice exam contains 20 questions about LLM Evaluation, RAG Metrics, Security, and Generative AI Governance in the Databricks Mosaic AI ecosystem.

---

## 1. LLM-as-a-Judge - Best Practices

When using "LLM-as-a-Judge" to evaluate complex cases where reference data is not available, what is the recommended best practice to improve metric reliability?

- ✅ **A)** Implement a "Human-in-the-loop" process to review LLM-generated metrics and handle ambiguities.
- ❌ **B)** Rely exclusively on the "toxicity" metric as it is the only stable metric for LLMs.
- ❌ **C)** Use the smallest possible model (e.g., 7B parameters) to ensure faster processing speeds.
- ❌ **D)** Avoid providing a rubric or specific instructions to prevent bias in the judge model.

> **Explanation:** When ground truth is not available, humans should review and validate LLM judgments to catch errors, handle ambiguous cases, and improve reliability. Clear rubrics also improve consistency.

---

## 2. BLEU vs ROUGE

Which statement correctly contrasts the BLEU and ROUGE evaluation metrics?

- ❌ **A)** BLEU is a recall-oriented metric used primarily for summarization; ROUGE is a precision-oriented metric used for translation.
- ❌ **B)** BLEU measures output toxicity, while ROUGE measures request latency.
- ✅ **C)** BLEU compares n-gram similarities for translation (precision-oriented); ROUGE calculates n-gram recall, making it suitable for summarization.
- ❌ **D)** Both metrics are semantic evaluators that use embeddings to determine the emotional tone of the text.

> **Explanation:** BLEU (Bilingual Evaluation Understudy) is precision-focused, measuring how many n-grams from the output appear in the reference - good for translation. ROUGE (Recall-Oriented Understudy for Gisting Evaluation) is recall-focused - good for summarization.

---

## 3. Offline vs Online Evaluation

Which distinction best describes the difference between Offline and Online Evaluation of LLMs?

- ❌ **A)** Offline evaluation measures latency; online evaluation measures accuracy.
- ❌ **B)** Offline evaluation is manual; online evaluation is fully automated by MLflow.
- ✅ **C)** Offline evaluation uses benchmark datasets and reference data (or LLM-as-a-Judge) before production; online evaluation uses real user behavior and feedback within production.
- ❌ **D)** Offline evaluation occurs in the cloud; online evaluation occurs on-device.

> **Explanation:** Offline = pre-deploy with prepared datasets and benchmarks. Online = in production with real users, measuring behavior, feedback, and real performance.

---

## 4. Resources: LLM vs Classical ML

When comparing LLM evaluation to classical ML evaluation, what distinct resource requirement is a primary challenge for LLMs?

- ❌ **A)** LLMs require significantly less storage because they don't use feature stores.
- ❌ **B)** LLMs rely exclusively on CPU compute, making them cheaper to evaluate than classical regression models.
- ❌ **C)** Classical ML requires human judges for every prediction, while LLMs never require human feedback.
- ✅ **D)** LLMs require massive amounts of data and substantial computational resources (GPUs/TPUs) compared to the less expensive hardware of classical ML.

> **Explanation:** LLMs need significantly more computational resources (GPUs/TPUs), more memory, more storage, and more data. Classical models often run on CPUs with modest resources.

---

## 5. Answer Relevancy Metric

What does the "Answer Relevancy" metric specifically assess in a RAG pipeline?

- ❌ **A)** Whether the retrieved documents contain the correct answer.
- ❌ **B)** The percentage of n-grams in the response that appear in the context.
- ✅ **C)** The alignment of the generated response with the user's initial query intent.
- ❌ **D)** The semantic similarity between the generated response and the ground truth.

> **Explanation:** Answer Relevancy measures whether the generated response actually answers the user's question. It evaluates alignment between the response and the original query intent, not factual correctness.

---

## 6. Llama Guard

Which description best characterizes the architecture and function of Llama Guard as a safeguard model?

- ❌ **A)** It is a vector database tool that removes high-perplexity tokens from the context window.
- ❌ **B)** It is a keyword-matching filter that blocks any prompt containing words from a static "banned list."
- ✅ **C)** It is an LLM-based classifier that uses a taxonomy of risks and guidelines to classify and mitigate safety risks in both user prompts and model responses.
- ❌ **D)** It is a post-processing script that only evaluates the final model output for grammatical correctness.

> **Explanation:** Llama Guard is an LLM-based safety classifier developed by Meta. It uses a defined taxonomy of safety categories (violence, sexual content, hate speech, etc.) to classify BOTH input prompts AND output responses as safe or unsafe.

---

## 7. Answer Correctness vs Faithfulness

How does "Answer Correctness" differ from "Faithfulness" in RAG evaluation?

- ❌ **A)** There is no difference; they are synonymous terms in the Mosaic AI framework.
- ✅ **B)** Answer Correctness requires a Ground Truth to measure accuracy; Faithfulness checks if the answer is derived purely from the retrieved context.
- ❌ **C)** Faithfulness compares the response to the ground truth; Answer Correctness compares the response to the context.
- ❌ **D)** Answer Correctness is an offline metric; Faithfulness is only available in online evaluation.

> **Explanation:** Answer Correctness compares the generated response with a ground truth (reference answer) to measure factual correctness. Faithfulness (groundedness) verifies if the response is supported by the retrieved context - if there are no hallucinations of information outside the context.

---

## 8. Prompt Injection

An attacker inputs a query designed to override a GenAI system's instructions to extract private information or generate harmful responses. Which term best describes this security risk, and what is the primary mitigation strategy discussed?

- ❌ **A)** Model Poisoning; mitigated by increasing the size of the validation dataset.
- ❌ **B)** Hallucination; mitigated by lowering the model's temperature parameter.
- ❌ **C)** Data Drift; mitigated by retraining the model with fresh data using Lakehouse Monitoring.
- ✅ **D)** Prompt Injection; mitigated by implementing guardrails to filter inputs and outputs.

> **Explanation:** Prompt Injection is exactly this - an attacker creates input to manipulate model behavior, override instructions, or extract sensitive information. The primary mitigation is implementing guardrails (like Llama Guard) to filter BOTH inputs AND outputs.

---

## 9. Context Recall

To calculate "Context Recall", which two specific data elements are required?

- ❌ **A)** The User Query and Latency logs.
- ✅ **B)** The Ground Truth and the Retrieved Context(s).
- ❌ **C)** The User Query and the Generated Response.
- ❌ **D)** The Generated Response and the Retrieved Context.

> **Explanation:** Context Recall measures how much of the relevant information from the ground truth is present in the retrieved context. It compares what SHOULD have been retrieved (ground truth) with what WAS retrieved (retrieved context). It answers: "Did we retrieve all the necessary information?"

---

## 10. DASF - Stakeholder Gap

According to the Data and AI Security Framework (DASF), identifying security risks is complex because few practitioners have a complete picture of the system. Which stakeholder gap is explicitly identified as a challenge in AI security?

- ✅ **A)** Data scientists typically have not performed security tasks, and security teams are often new to AI architectures.
- ❌ **B)** Executive leadership prioritizes speed over compliance in 90% of organizations.
- ❌ **C)** Cloud providers do not offer encryption for vector databases.
- ❌ **D)** Legal teams often refuse to review the code of generative models.

> **Explanation:** There is a well-known skill gap in AI security. Data scientists focus on ML/AI but may lack security expertise, while security professionals may lack knowledge about AI/ML architectures. This creates a gap in understanding the complete security picture.

---

## 11. Data Licensing

When evaluating data legality for a GenAI application intended for commercial profit, which of the following scenarios presents a violation based on the course's discussion of data licensing?

- ❌ **A)** Using a pre-trained model that includes a "Safety Filter" to block toxic outputs.
- ❌ **B)** Using a dataset with an open-source license that permits modification and redistribution for any purpose.
- ❌ **C)** Training a model on internal company data that has been fully anonymized and approved by the legal team.
- ✅ **D)** Using a dataset licensed for "personal and research purposes" to train a model that powers a paid subscription service.

> **Explanation:** Clear licensing violation. If a dataset is licensed only for "personal and research purposes", using it for a commercial paid subscription service violates the license terms.

---

## 12. DASF - Catalog

Within the Data and AI Security Framework (DASF), which component focuses on the governance of data assets through centralized access control, lineage, and auditing to ensure data quality and reliability?

- ❌ **A)** Model Management
- ❌ **B)** Evaluation
- ✅ **C)** Catalog
- ❌ **D)** Algorithm

> **Explanation:** The Catalog (like Unity Catalog in Databricks) provides centralized governance including: access control (permissions), data lineage tracking, auditing capabilities, and data quality and reliability management.

---

## 13. BLEU and ROUGE Limitations

What is a shared limitation of both BLEU and ROUGE metrics when evaluating Generative AI outputs?

- ❌ **A)** They rely on "LLM-as-a-Judge" to generate a score, making them non-deterministic.
- ❌ **B)** They are only applicable to image generation tasks, not text.
- ✅ **C)** Both require a reference dataset and rely on n-gram matching rather than semantic understanding.
- ❌ **D)** They can only be calculated using the Mosaic AI Agent Framework.

> **Explanation:** Both BLEU and ROUGE: require reference texts for comparison, use n-gram matching (lexical/token-based), and do NOT capture semantic meaning. A paraphrase with different words but the same meaning would score poorly.

---

## 14. Perplexity

If a base foundation model exhibits a sharp peak in its probability distribution for next token prediction, how is this reflected in the Perplexity metric and the model's confidence?

- ❌ **A)** High Perplexity, indicating high confidence and high accuracy.
- ❌ **B)** Low Perplexity, indicating low confidence and low accuracy.
- ✅ **C)** Low Perplexity, indicating high confidence and accuracy.
- ❌ **D)** High Perplexity, indicating low confidence and accuracy.

> **Explanation:** Perplexity is inversely related to confidence. Sharp peak = low perplexity = high confidence = generally more accurate. High perplexity indicates flat distribution (uncertainty), low perplexity indicates concentrated distribution (certainty).

---

## 15. Faithfulness

Which RAG evaluation metric measures the factual accuracy of the generated answer specifically in relation to the provided context, without necessarily checking against a ground truth?

- ❌ **A)** Toxicity
- ❌ **B)** Context Recall
- ❌ **C)** Answer Correctness
- ✅ **D)** Faithfulness

> **Explanation:** Faithfulness (groundedness) measures whether the generated response is factually supported by/derived from the provided context. It checks if the response hallucinates information that is NOT in the context. It does NOT require ground truth - only compares response vs context.

---

## 16. Unity Catalog and GenAI

How does Unity Catalog support the governance of GenAI applications specifically regarding vector search and retrieval?

- ✅ **A)** It governs vector indexes in Vector Search, manages GenAI models, and tracks end-to-end lineage of application data.
- ❌ **B)** It encrypts the GPU memory used during the foundation model inference process.
- ❌ **C)** It automatically rewrites user prompts to remove toxic language before they reach the model.
- ❌ **D)** It provides a proprietary "LLM-as-a-Judge" model to score the accuracy of vector embeddings.

> **Explanation:** Unity Catalog provides: governance of vector indexes in Databricks Vector Search, management of GenAI models (registered in UC), end-to-end lineage tracking, access control/permissions, and auditing capabilities.

---

## 17. Truth in GenAI vs Classical ML

In the context of Generative AI evaluation, how does the concept of "Truth" differ from classical Machine Learning (ML) evaluation, presenting a specific challenge for governance?

- ✅ **A)** In GenAI, there is often no single true or correct answer for a given input, unlike classical ML which typically compares predictions to specific target label data.
- ❌ **B)** GenAI models automatically filter "Truth" based on training data toxicity scores, while classical ML requires manual intervention.
- ❌ **C)** GenAI models are incapable of processing labeled data, while classical ML relies exclusively on unsupervised learning.
- ❌ **D)** Classical ML produces probabilistic outputs that are impossible to audit, while GenAI outputs are deterministic.

> **Explanation:** Fundamental challenge in GenAI evaluation. Classical ML has clear ground truths (classification labels, regression targets). GenAI outputs are often open-ended with multiple valid answers - there is no single "correct" answer for many prompts.

---

## 18. MLflow Custom Metrics Workflow

In an MLflow evaluation workflow for a custom "Professionalism" metric, what are the three essential steps required to perform the evaluation?

- ❌ **A)** 1) Define a BLEU score, 2) Define a ROUGE score, 3) Average them together.
- ❌ **B)** 1) Ingest data into Delta Lake, 2) Run a SQL query, 3) Visualize in a dashboard.
- ❌ **C)** 1) Train a new model, 2) Deploy to production, 3) Check latency.
- ✅ **D)** 1) Create evaluation records, 2) Create a metric object (including definition, grading prompt, and scoring criteria), 3) Evaluate the model against a dataset using the metric.

> **Explanation:** The correct workflow is: 1) Create evaluation records (data to evaluate), 2) Create custom metric object with definition, grading prompt, and scoring criteria, 3) Run mlflow.evaluate() with the metric against the dataset.

---

## 19. Mosaic AI Agent Framework

The Mosaic AI Agent Framework facilitates "Agent Evaluation" by providing which specific set of capabilities?

- ❌ **A)** A strictly manual spreadsheet for logging errors found by QA testers.
- ❌ **B)** A tool that automatically rewrites the underlying Python code of the agent to improve performance.
- ❌ **C)** A dashboard that only displays the cost of API calls and no quality metrics.
- ✅ **D)** A suite of tools to trace agent behavior, evaluate quality with RAG-specific metrics, and collect human feedback via a Review App.

> **Explanation:** The Mosaic AI Agent Framework provides: Tracing for agent behavior (MLflow Tracing), RAG-specific evaluation metrics (faithfulness, relevancy, etc.), Review App for collecting human feedback, and quality assessment tools.

---

## 20. Context Precision

In a RAG (Retrieval Augmented Generation) architecture, why is it critical to evaluate the "Context Precision" metric?

- ❌ **A)** To ensure the user's query does not contain PII (Personally Identifiable Information).
- ❌ **B)** To measure the grammatical correctness of the final answer generated by the LLM.
- ❌ **C)** To calculate the cost of the embedding model in dollars per token.
- ✅ **D)** To determine the signal-to-noise ratio of the retrieved context, ensuring relevant chunks are ranked higher than irrelevant ones.

> **Explanation:** Context Precision measures retrieval ranking quality. It evaluates whether relevant chunks appear at the top of results (high precision) vs having irrelevant chunks mixed in. High context precision = relevant documents ranked higher, low noise.

---
