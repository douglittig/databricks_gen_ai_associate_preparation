# Practice Exam 04: Generative AI Application Deployment and Monitoring

This practice exam contains 20 questions about GenAI Application Deployment, MLflow, Model Serving, and Monitoring in the Databricks ecosystem.

---

## 1. MLflow Model Flavor

Which MLflow model "flavor" is described as the default model interface that ensures any MLflow Python model can be loaded as a python function, providing the necessary commands to `log_model`, `save_model`, and `predict`?

- ❌ **A)** mlflow.spark
- ✅ **B)** mlflow.pyfunc
- ❌ **C)** mlflow.langchain
- ❌ **D)** mlflow.transformers

> **Explanation:** `mlflow.pyfunc` is the default/universal Python function interface in MLflow. It provides a generic way to load any MLflow model as a Python function, regardless of the underlying framework, with standardized `log_model`, `save_model`, and `predict` methods.

---

## 2. Databricks Lakehouse Monitoring

What is the primary purpose of Databricks Lakehouse Monitoring when applied to data and ML pipelines?

- ✅ **A)** To provide automated insights and out-of-the-box metrics (such as profile and drift metrics) via generated dashboards
- ❌ **B)** To serve as a vector database for RAG applications
- ❌ **C)** To retrain models automatically when accuracy drops below a threshold
- ❌ **D)** To manage the CI/CD deployment of Asset Bundles

> **Explanation:** Lakehouse Monitoring provides automated data quality monitoring with profile metrics (statistics about your data) and drift metrics (detecting changes over time), all visualized through auto-generated dashboards. It monitors but doesn't automatically retrain models.

---

## 3. Lakehouse Monitoring - Testing Stage

When configuring Lakehouse Monitoring workflows, what is the specific recommendation for the "Testing" architecture stage?

- ❌ **A)** Disable all monitoring to save costs
- ✅ **B)** Develop integration tests that run a few iterations to ensure all monitoring metrics are working correctly
- ❌ **C)** Only monitor system performance (CPU/RAM), not data quality
- ❌ **D)** Use production data to establish a baseline

> **Explanation:** In the Testing stage, you should develop integration tests that validate your monitoring setup works correctly before deploying to production. This ensures metrics are captured properly and alerts function as expected.

---

## 4. Deploy Code vs Deploy Model

Why is the "Deploy Code" pattern recommended over the "Deploy Model" pattern in modern LLMOps architectures?

- ❌ **A)** It allows developers to bypass Git version control
- ❌ **B)** It eliminates the need for a Model Registry
- ✅ **C)** It ensures the training/inference pipeline is run in each environment (Dev, Staging, Prod), validating the entire process rather than just moving a static artifact
- ❌ **D)** Deploying code is faster because code files are smaller than model artifacts

> **Explanation:** "Deploy Code" means the same pipeline code runs in each environment (Dev → Staging → Prod), validating the entire workflow works correctly. "Deploy Model" just moves a static artifact, missing potential environment-specific issues.

---

## 5. Real-time AI Infrastructure Challenge

What is identified as the primary infrastructure challenge when attempting to build Real-time AI Systems versus Batch systems?

- ❌ **A)** The inability to use Python for real-time requests
- ❌ **B)** The lack of available Foundation Models for real-time applications
- ❌ **C)** The difficulty in tokenizing text data in real-time
- ✅ **D)** The requirement for fast and scalable serving infrastructure, which is costly to build and maintain

> **Explanation:** Real-time AI systems require low-latency, high-throughput serving infrastructure with GPUs/TPUs that can handle concurrent requests. This infrastructure is expensive to build, maintain, and scale compared to batch processing systems.

---

## 6. Model Serving - Serverless Operations

Which feature of Databricks Model Serving directly enables "Serverless" operations, allowing the system to handle unpredictable traffic spikes without manual infrastructure management?

- ❌ **A)** Integration with Feature Store
- ❌ **B)** Support for MLflow flavors
- ✅ **C)** Autoscaling and scale-to-zero compute
- ❌ **D)** Built-in A/B testing

> **Explanation:** Autoscaling automatically adjusts compute resources based on traffic, while scale-to-zero means the endpoint uses no resources (and incurs no cost) when idle. This eliminates manual infrastructure management for handling traffic variability.

---

## 7. LLM GPU RAM Requirements

When scaling batch inference workloads for a Large Language Model with approximately 10 billion parameters at FP32 (32-bit floating precision), what is the estimated GPU RAM requirement per model copy?

- ✅ **A)** ~40 GB
- ❌ **B)** ~80 GB
- ❌ **C)** ~10 GB
- ❌ **D)** ~20 GB

> **Explanation:** At FP32, each parameter requires 4 bytes. For 10 billion parameters: 10B × 4 bytes = 40 GB. This is why quantization techniques (FP16, INT8) are used to reduce memory requirements by 2-4x.

---

## 8. Model Serving Categories

Databricks Model Serving offers a unified UI and API to manage three specific categories of models. Which list correctly identifies these three categories?

- ❌ **A)** TensorFlow Models, PyTorch Models, and Scikit-Learn Models
- ✅ **B)** Custom Models, Foundation Models APIs, and External Models
- ❌ **C)** Internal Models, Third-Party Models, and On-Premise Models
- ❌ **D)** Batch Models, Streaming Models, and Real-time Models

> **Explanation:** Databricks Model Serving supports: Custom Models (your own MLflow models), Foundation Models APIs (Databricks-hosted LLMs like DBRX, Llama), and External Models (third-party APIs like OpenAI, Anthropic proxied through Databricks).

---

## 9. Inference Table Processing for Monitoring

In the context of monitoring a GenAI model's responses, what data engineering step must typically occur *after* capturing data in an Inference Table but *before* enabling Lakehouse Monitoring?

- ✅ **A)** The raw JSON payloads in the Inference Table must be "unpacked" and flattened into a processed table
- ❌ **B)** The data must be manually labeled by human reviewers
- ❌ **C)** The Inference Table must be converted into Parquet format
- ❌ **D)** The table must be dropped and recreated to clear the cache

> **Explanation:** Inference Tables store raw request/response payloads as JSON. Before Lakehouse Monitoring can analyze the data, these nested JSON structures must be unpacked and flattened into individual columns for proper metric computation.

---

## 10. Inference Tables Storage

When "Inference Tables" are enabled in Databricks Model Serving, where are the incoming requests and outgoing responses persistently stored?

- ❌ **A)** In a proprietary NoSQL database managed by Databricks
- ✅ **B)** Appended to a Delta table in Unity Catalog
- ❌ **C)** In a temporary in-memory cache for 24 hours
- ❌ **D)** Saved as JSON files in the driver node's local storage

> **Explanation:** Inference Tables are Delta tables stored in Unity Catalog. Every request and response is automatically logged and appended to this table, enabling persistent storage, governance, lineage tracking, and downstream analysis.

---

## 11. Batch Deployment Characteristics

When selecting a deployment paradigm, which set of characteristics indicates that Batch Deployment is the most appropriate strategy for a GenAI application?

- ✅ **A)** The pace of input records is slower than 30 minutes, volume is high, and immediate predictions are not necessary
- ❌ **B)** Low latency (milliseconds) is required, and predictions must be generated instantly for individual requests
- ❌ **C)** Throughput requirements are low, and the model must run on an embedded edge device
- ❌ **D)** Requests are asynchronous and require micro-batch processing with moderate latency (seconds to minutes)

> **Explanation:** Batch deployment is ideal when: data arrives in bulk (not real-time), high volume processing is needed, and there's no urgency for immediate predictions. B describes real-time serving, C describes edge deployment, D describes streaming.

---

## 12. LLMOps Packaging

How does "Packaging" in LLMOps differ significantly from traditional MLOps?

- ❌ **A)** LLMOps only requires packaging the model weights, whereas MLOps requires code
- ❌ **B)** LLMOps packaging is handled exclusively by the model provider (e.g., OpenAI), removing the need for local packaging
- ✅ **C)** LLMOps requires packaging entire applications (including chains, prompts, and API calls) rather than just a single model artifact
- ❌ **D)** LLMOps does not use containers, while MLOps relies heavily on Docker

> **Explanation:** In LLMOps, you package the entire application—chains, prompts, retrieval logic, API configurations, and dependencies—not just a model artifact. This is because GenAI applications are compound systems with multiple interacting components.

---

## 13. vLLM for Memory-Efficient Inference

Which Open Source Software (OSS) integration is explicitly highlighted in the course as a "Transformer-friendly" library designed for memory-efficient inference on both NVIDIA® and AMD GPUs?

- ❌ **A)** TensorRT
- ✅ **B)** vLLM
- ❌ **C)** Ray on Spark
- ❌ **D)** MLServer

> **Explanation:** vLLM is an open-source library optimized for fast, memory-efficient LLM inference. It uses PagedAttention for efficient memory management and supports both NVIDIA and AMD GPUs, making it ideal for serving large language models.

---

## 14. ai_query() Function

A data engineer wants to perform batch inference using a Foundation Model served via an API, but needs to invoke it directly from a Databricks SQL environment. Which function allows for this integration?

- ✅ **A)** ai_query()
- ❌ **B)** spark_udf()
- ❌ **C)** mlflow_predict()
- ❌ **D)** db_serving()

> **Explanation:** `ai_query()` is a Databricks SQL function that allows you to invoke Model Serving endpoints directly from SQL queries. This enables batch inference on large datasets using simple SQL syntax without needing Python code.

---

## 15. Human Feedback in LLMOps

In a recommended LLMOps architecture, what is the role of "Human Feedback" that distinguishes it from traditional MLOps monitoring?

- ❌ **A)** It is used solely for regulatory compliance audits
- ❌ **B)** It is only required during the pre-training phase of the Foundation Model
- ✅ **C)** It serves as an important datasource from Dev to Prod for evaluation, iteration, and augmenting traditional monitoring
- ❌ **D)** It replaces automated testing entirely in the Staging environment

> **Explanation:** Human feedback is crucial in LLMOps across all stages—Dev, Staging, and Production. It provides qualitative evaluation data that complements automated metrics, helps identify edge cases, and enables continuous improvement of GenAI applications.

---

## 16. Databricks Asset Bundles (DABs)

What is the primary function of Databricks Asset Bundles (DABs)?

- ❌ **A)** To automatically fine-tune LLMs without user intervention
- ❌ **B)** To compress large datasets for faster transfer
- ❌ **C)** To serve as a replacement for the Unity Catalog
- ✅ **D)** To enable "write code once, deploy everywhere" using YAML configurations for artifacts, resources, and CI/CD

> **Explanation:** Databricks Asset Bundles (DABs) provide infrastructure-as-code for Databricks. Using YAML configuration files, you define jobs, pipelines, and resources that can be deployed consistently across Dev, Staging, and Production environments with CI/CD integration.

---

## 17. Environment Separation

Regarding "Environment Separation" in an MLOps/LLMOps strategy, what approach does the course recommend for scalability and security?

- ❌ **A)** Indirect Separation: Using a single Databricks workspace with folder-level permissions
- ✅ **B)** Direct Separation: Using completely separate Databricks workspaces for Development, Staging, and Production
- ❌ **C)** Hybrid Separation: Combining Dev and Staging in one workspace, with Production in another
- ❌ **D)** No Separation: Allowing all developers admin access to a single workspace to speed up deployment

> **Explanation:** Direct Separation with separate workspaces for Dev, Staging, and Production provides the strongest security isolation, clearest access control, and best practices for enterprise-grade MLOps/LLMOps at scale.

---

## 18. MLflow Registry and Unity Catalog

In the context of the MLflow and Unity Catalog (UC) integration, how does the Registry specifically facilitate the "Deployment" phase of the lifecycle after a model has been built and tracked?

- ❌ **A)** It automatically retrains the model using new data in the Delta Lake
- ❌ **B)** It converts the model automatically into ONNX format for edge deployment
- ❌ **C)** It provides a visualization dashboard for training loss curves
- ✅ **D)** It serves as a centralized store using Aliases (e.g., @champion, @challenger) to manage lifecycle versions and ACLs

> **Explanation:** The MLflow Registry in Unity Catalog provides centralized model management with aliases (@champion, @challenger) for lifecycle stage management, version control, and ACL-based access control—enabling safe model promotion through environments.

---

## 19. GenAI Packaging Components

When conceptualizing "Packaging" for Generative AI deployment compared to traditional ML, the course emphasizes that ML logic takes on new forms. Which of the following components constitutes a valid "model" or "pipeline" that can be packaged and managed via MLflow for GenAI?

- ✅ **A)** An engineered prompt template, a LangChain "chain," or a lightweight call to an external LLM API service
- ❌ **B)** Only locally hosted Foundation Models running on GPUs
- ❌ **C)** The raw training dataset and the tokenization vocabulary file
- ❌ **D)** Only binary model weights (e.g., .bin or .pt files)

> **Explanation:** In GenAI, the concept of a "model" expands beyond traditional weights. Prompt templates, chains, agents, and API wrappers are all valid packagable artifacts in MLflow. This reflects the shift from training models to composing applications.

---

## 20. A/B Testing and Traffic Distribution

To support online evaluation strategies such as Canary Deployments or A/B testing, how does Databricks Model Serving manage traffic distribution?

- ❌ **A)** It requires deploying separate endpoints for each model version and managing routing via a load balancer
- ✅ **B)** It allows serving multiple models (e.g., @champion and @challenger) behind a single serving endpoint with configurable traffic splits
- ❌ **C)** It uses ai_query() to determine which model version to call based on the user ID
- ❌ **D)** It randomly assigns requests to models based on GPU availability

> **Explanation:** Databricks Model Serving supports serving multiple model versions behind a single endpoint with configurable traffic percentages. This enables A/B testing (e.g., 90% to @champion, 10% to @challenger) and gradual canary rollouts without managing multiple endpoints.
