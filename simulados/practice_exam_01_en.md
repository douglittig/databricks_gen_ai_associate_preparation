# Practice Exam 01: Generative AI and Mosaic AI (Databricks)

This practice exam contains 20 questions about RAG, Vector Databases, Chunking, and Vector Search in the Databricks Mosaic AI ecosystem.

---

## 1. RAG vs. Fine-Tuning

When architecting a Generative AI solution, what factor primarily distinguishes the decision to implement a Retrieval-Augmented Generation (RAG) architecture instead of Fine-Tuning an LLM?

- ❌ **A)** Fine-tuning is required when the model's input context window is too small.
- ❌ **B)** Fine-tuning allows the model to recall facts with 100% precision.
- ✅ **C)** RAG addresses the knowledge gap by retrieving up-to-date proprietary data without the high compute costs of training.
- ❌ **D)** RAG alters the model's style to a specific persona, while fine-tuning does not.

> **Explanation:** RAG is the choice for dynamic/external data. Fine-tuning focuses on task or style specialization, being expensive and inefficient for fact updates.

---

## 2. Reranking with Cross-Encoders

In a RAG pipeline, why would a developer implement a "Reranking" step using a Cross-Encoder after initial vector retrieval?

- ❌ **A)** To speed up the retrieval process by bypassing the Vector Store's internal logic.
- ❌ **B)** To reduce cost by filtering documents before they reach the Vector DB.
- ✅ **C)** To address the precision limitations of ANN search by evaluating actual document relevance using deeper semantic comparison.
- ❌ **D)** To translate the retrieved documents to the user's native language.

> **Explanation:** ANN (Approximate Nearest Neighbor) search is fast but imprecise. The Cross-Encoder evaluates the (Query, Document) relationship with greater semantic depth to ensure the best context.

---

## 3. Product Quantization (PQ)

What is the primary purpose of applying Product Quantization (PQ) within a vector search index?

- ❌ **A)** To reorder results based on user feedback.
- ❌ **B)** To increase vector dimensionality to capture more nuances.
- ❌ **C)** To convert text embeddings to images for multimodal search.
- ✅ **D)** To compress high-dimensional vectors into compact codes, reducing memory footprint and enabling efficient similarity search.

> **Explanation:** PQ is an essential vector compression technique to keep large volumes of embeddings in RAM performantly.

---

## 4. Vector Database vs. Relational

How does a Vector Database fundamentally differ from a traditional relational database?

- ❌ **A)** Vector databases don't support metadata filtering.
- ✅ **B)** Vector databases serve queries based on semantic vector similarity, while relational ones optimize for exact matches.
- ❌ **C)** Vector databases store data in rows and columns; relational ones use blobs.
- ❌ **D)** Vector databases rely on B-Tree; relational ones use probabilistic matching.

> **Explanation:** Vector databases use approximate search algorithms (ANN) to find semantically similar vectors, while relational databases use exact indexes (B-Tree) for precise matches.

---

## 5. Cosine Similarity

How should a developer interpret the relationship between "Cosine Similarity" and vector distance?

- ❌ **A)** Higher score indicates less similar vectors.
- ✅ **B)** Higher score indicates more similar vectors, representing a smaller angle between them.
- ❌ **C)** Cosine only applies to images; text requires Manhattan distance.
- ❌ **D)** Cosine measures magnitude; Euclidean measures the angle.

> **Explanation:** Cosine similarity measures the angle between two vectors. The smaller the angle (vectors pointing in the same direction), the higher the similarity score, regardless of vector magnitude.

---

## 6. Model Serving Endpoint

What is the function of the "Model Serving Endpoint" in Databricks RAG architecture?

- ✅ **A)** To provide a unified interface for deploying and querying foundation models and external models (APIs) to generate responses.
- ❌ **B)** To act as a storage layer for raw PDFs.
- ❌ **C)** To perform data chunking during ingestion.
- ❌ **D)** To calculate cosine similarity between vectors.

> **Explanation:** The Model Serving Endpoint abstracts deployment complexity and allows querying both internally hosted models and external APIs (like OpenAI) through a unified interface.

---

## 7. Role of Delta Table

What is the role of the Delta Table immediately preceding the Vector Search Index in Databricks?

- ✅ **A)** To act as the source of truth containing chunks and metadata, which the index automatically syncs with.
- ❌ **B)** To replace the Vector Store via SQL searches.
- ❌ **C)** To store generated responses for caching.
- ❌ **D)** To store raw PDFs before parsing.

> **Explanation:** Vector Search in Databricks is integrated with Unity Catalog and automatically syncs data from a Delta Table.

---

## 8. Security and ACLs

How does Mosaic AI Vector Search support security and access control (ACLs)?

- ✅ **A)** By integrating with Unity Catalog to apply permissions and allow metadata filters to restrict scope.
- ❌ **B)** By encrypting the query before sending to the LLM.
- ❌ **C)** By creating a separate index for each user.
- ❌ **D)** By requiring SQL Warehouse credentials in the prompt.

> **Explanation:** Integration with Unity Catalog allows inheriting table permissions and using metadata filters to implement row-level security in vector searches.

---

## 9. Embedding Space Requirement

What is the critical requirement of the "Embedding Space" when selecting models for RAG?

- ✅ **A)** The query and document models must be the same to ensure vectors are in the same mathematical space.
- ❌ **B)** The query should use a different model than documents to avoid overfitting.
- ❌ **C)** The model must be proprietary to ensure privacy.
- ❌ **D)** Dimensions must be smaller than 256 for compatibility.

> **Explanation:** If query and documents use different models, vectors will be in distinct mathematical spaces, making similarity comparison meaningless.

---

## 10. Retrieval Component

What is the primary technical function of the "Retrieval" component in the RAG workflow?

- ❌ **A)** To summarize the query to reduce tokens.
- ❌ **B)** To adjust foundation model weights.
- ❌ **C)** To convert natural language to SQL.
- ✅ **D)** To identify and retrieve relevant context from a Vector Store to augment the prompt sent to the LLM.

> **Explanation:** Retrieval searches for semantically relevant documents in the Vector Store and injects them into the prompt, providing the LLM with the necessary context to generate accurate responses.

---

## 11. Lost in the Middle

What context window phenomenon must be mitigated to ensure factual recall in long prompts?

- ❌ **A)** Token Drift.
- ❌ **B)** Context Hallucination.
- ❌ **C)** Needle in a Haystack.
- ✅ **D)** Lost in the Middle (information in the middle of the context is often ignored by the model).

> **Explanation:** Research shows that LLMs tend to pay more attention to the beginning and end of context, ignoring information in the middle. Strategies like chunk reordering help mitigate this.

---

## 12. HNSW vs. KNN

Why is the HNSW algorithm preferred over KNN in production?

- ❌ **A)** HNSW guarantees 100% precision.
- ❌ **B)** HNSW is for data preparation; KNN is for search.
- ❌ **C)** HNSW compresses vectors to binary.
- ✅ **D)** HNSW enables ANN (approximate) search, trading minimal precision for massive speed gains via graphs.

> **Explanation:** Exact KNN has O(n) complexity, infeasible for millions of vectors. HNSW uses hierarchical graph structure for logarithmic search, sacrificing ~5% precision for 1000x more speed.

---

## 13. Complex Documents (Images/Tables)

Advanced strategy for complex documents (tables/images) in RAG?

- ✅ **A)** Use layout models to extract text and LLMs to summarize tables/images, indexing the summaries while maintaining references to originals.
- ❌ **B)** Create separate Vector Stores for images.
- ❌ **C)** Discard images/tables to focus on raw text.
- ❌ **D)** Index image binaries directly in the text space.

> **Explanation:** Layout models (like LayoutLM) extract structure, and LLMs generate textual descriptions. This enables semantic search while maintaining links to original assets.

---

## 14. Chunking Trade-off

What is the trade-off between small vs. large chunks?

- ❌ **A)** Smaller ones require more storage.
- ❌ **B)** Larger ones reduce API calls.
- ✅ **C)** Smaller ones focus on specific meanings (precision), but may lack context; larger ones maintain context, but introduce noise.
- ❌ **D)** Smaller ones capture broad themes; larger ones focus on details.

> **Explanation:** Small chunks (~100-200 tokens) are precise but lose context. Large chunks (~500-1000 tokens) preserve context but bring irrelevant information. The ideal depends on the use case.

---

## 15. Windowed Summarization

Technique to mitigate context loss between consecutive chunks by including prior summaries?

- ✅ **A)** Windowed summarization.
- ❌ **B)** Fixed-size chunking.
- ❌ **C)** Semantic overlap.
- ❌ **D)** Product Quantization.

> **Explanation:** Windowed summarization condenses previous context and injects it into the current chunk, ensuring semantic continuity without excessive textual redundancy.

---

## 16. Mosaic AI Vector Search

Databricks component responsible for "Index & Embed" and context search via Delta sync?

- ❌ **A)** Databricks Jobs.
- ❌ **B)** Unity Catalog Governance.
- ✅ **C)** Mosaic AI Vector Search.
- ❌ **D)** Mosaic AI Model Serving.

> **Explanation:** Mosaic AI Vector Search is the managed service that creates embeddings, indexes vectors, and automatically syncs with Delta Tables via CDC.

---

## 17. Context Injection at Inference

At what point is "Context" injected in the Inference phase?

- ✅ **A)** In the prompt structure along with the query, after retrieval and before sending to Model Serving.
- ❌ **B)** In the Vector Database as a new row.
- ❌ **C)** Manually by the user.
- ❌ **D)** During model pre-training.

> **Explanation:** The RAG flow is: Query → Retrieval → Retrieved context → Prompt assembly (query + context) → Send to LLM → Generated response.

---

## 18. MLflow and Evaluation

Role of MLflow in the RAG Evaluation phase?

- ❌ **A)** Generate ground-truth via scraping.
- ❌ **B)** Store evaluation datasets.
- ❌ **C)** Retrain embedding models.
- ✅ **D)** Provide an "Evaluation Harness" to test metrics (faithfulness, relevance) using LLMs as judges.

> **Explanation:** MLflow Evaluate offers RAG-specific metrics (faithfulness, relevance, toxicity) using LLMs as automated judges to evaluate response quality.

---

## 19. Synchronization and CDC

Vector Search feature that ensures automatic updates without manual reconstruction?

- ❌ **A)** OPTIMIZE commands.
- ✅ **B)** Delta Sync API (uses Change Data Capture - CDC from source Delta Table).
- ❌ **C)** Real-time embedding generation.
- ❌ **D)** Predictive HNSW algorithms.

> **Explanation:** Delta Sync detects insertions, updates, and deletions in the source Delta Table and automatically propagates to the vector index, keeping it always up-to-date.

---

## 20. Chain-of-Thought (CoT)

Difference between Chain-of-Thought (CoT) and Few-shot prompting?

- ✅ **A)** CoT forces articulation of intermediate reasoning steps; Few-shot relies on static input-output examples.
- ❌ **B)** CoT focuses on style; Few-shot doesn't use examples.
- ❌ **C)** CoT reduces latency; Few-shot increases it.
- ❌ **D)** CoT is for summaries; Few-shot for arithmetic.

> **Explanation:** CoT instructs the model to "think aloud", showing step-by-step reasoning. Few-shot provides input/output examples without explaining the reasoning process.
