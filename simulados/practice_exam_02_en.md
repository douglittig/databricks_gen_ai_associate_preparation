# Practice Exam 02: Generative AI and Mosaic AI (Databricks)

This practice exam contains 20 questions about Agent Architectures, MLflow Tracing, Vector Search, Multimodality, and GenAI Application Development in the Databricks ecosystem.

---

## 1. Visual Input Processing in Smart Home Assistant

In an example architecture for a "Smart Home Assistant" Multimodal, how is visual input (e.g., camera feed) processed before being stored in the Vector Store?

- ❌ **A)** The raw video file is sent directly to the Vector Store without processing.
- ✅ **B)** An M-LLM generates an image description, which is then split into chunks and embedded by an embedding model.
- ❌ **C)** The system ignores the Vector Store and sends the image directly to the user.
- ❌ **D)** The image is converted to ASCII art and then tokenized by a standard text LLM.

> **Explanation:** In multimodal architectures for RAG, the M-LLM processes the image and generates a textual description, which is then treated as text (chunked and embedded) for storage in the Vector Store.

---

## 2. Vector Index Synchronization in Databricks

How does Databricks Vector Search ensure the vector index stays updated with underlying data?

- ❌ **A)** Regenerates the entire index from scratch for each new query to ensure consistency.
- ❌ **B)** Requires the user to manually trigger a "Re-Index" job every 24 hours.
- ❌ **C)** Relies on the LLM to detect missing data and request a new search.
- ✅ **D)** Uses a "Delta Sync" mechanism to automatically sync changes from the source Delta Table to the vector index.

> **Explanation:** Databricks Vector Search is natively integrated with Delta Lake and uses Change Data Capture (CDC) to keep the index automatically updated.

---

## 3. "Tool Use" Pattern in Agents

How does the "Tool Use" pattern allow agents to solve problems that are outside the scope of their training data?

- ✅ **A)** By allowing the agent's reasoning abilities to decide which external tools (such as search engines or databases) to use and when/how to use them.
- ❌ **B)** By asking the user to provide the necessary code to solve the problem.
- ❌ **C)** By automatically retraining the model on the internet in real-time.
- ❌ **D)** By generating synthetic data to fill gaps in its knowledge.

> **Explanation:** The Tool Use pattern allows the agent to use its reasoning to decide which external tool to invoke (calculator, search, APIs, etc.), formulate the correct input, and incorporate the result into the response.

---

## 4. Code-Based vs Serialization-Based Logging in MLflow

Why does Databricks recommend "code-based logging" instead of serialization-based logging when tracking agents with MLflow?

- ❌ **A)** Serialization-based logging is not supported by the Python language.
- ✅ **B)** Code-based logging captures a "point in time" of the agent's code and configuration, which is more robust than serialization, which can be fragile.
- ❌ **C)** Serialization-based logging consumes significantly more tokens during the inference process.
- ❌ **D)** Code-based logging automatically fine-tunes the model, while serialization does not.

> **Explanation:** Serialization can break with library version changes or class definitions. Code-based logging captures source code, configs, and dependencies, creating a reproducible and robust snapshot.

---

## 5. DBRX Instruct vs DBRX Base

What distinguishes the "DBRX Instruct" model from the "DBRX Base" model?

- ✅ **A)** DBRX Instruct is built on top of DBRX Base and is specifically fine-tuned on domain-specific data to answer questions and follow instructions.
- ❌ **B)** DBRX Instruct is a smaller distilled version designed for mobile devices.
- ❌ **C)** DBRX Instruct works as an intelligent autocomplete and is only useful for additional fine-tuning.
- ❌ **D)** DBRX Instruct is a vision-language model capable of processing images, while Base is text-only.

> **Explanation:** "Instruct" models are the base model + fine-tuning with instruction data (conversations, Q&A) to follow commands. "Base" models are next-token predictors, ideal for additional fine-tuning.

---

## 6. Stability and Complexity in Gen AI Libraries

When choosing a library or framework for Generative AI development, why is "Stability and Complexity" often cited as an important risk factor?

- ✅ **A)** These libraries evolve rapidly, and API instability can be a major problem, potentially making them difficult to understand and maintain.
- ❌ **B)** Libraries like LangChain and Haystack don't support Python, making integration difficult.
- ❌ **C)** Open-source libraries are legally prohibited from being used in commercial applications.
- ❌ **D)** Most libraries are very mature and have legacy code that slows down inference.

> **Explanation:** The Gen AI ecosystem evolves rapidly with frequent breaking changes, outdated documentation, and increasing complexity, making it difficult to maintain stable production code.

---

## 7. MLflow Tracing vs Standard Logging

What is the main benefit of using MLflow Tracing instead of standard logging when debugging Generative AI applications?

- ✅ **A)** Enables interactive visualization of the call stack, tracking inputs, outputs, and latency for each span (step) of the chain.
- ❌ **B)** Encrypts logs so only the model owner can view prompts.
- ❌ **C)** Compresses logs into binary format to save storage costs.
- ❌ **D)** Automatically rewrites Python code to optimize chain latency.

> **Explanation:** MLflow Tracing offers structured observability with spans for each step, hierarchical visualization of the call stack, and tracking of inputs/outputs/latency with an interactive interface.

---

## 8. Agentic Workflow vs Non-Agentic (Chain)

What is the defining characteristic that differentiates an "Agentic Workflow" from a "Non-Agentic Workflow" (Chain)?

- ✅ **A)** Agents involve iterative and non-deterministic workflows where the LLM dynamically decides the sequence of actions and tools to use.
- ❌ **B)** Chains require external tools, while Agents operate entirely within the model's parametric memory.
- ❌ **C)** Chains use LLMs for reasoning, while Agents only use LLMs for summarization.
- ❌ **D)** Agents are deterministic and always follow a hard-coded sequence of actions.

> **Explanation:** Agents are autonomous with iterative loops (observe → think → act) where the LLM dynamically decides actions. Chains are pre-defined and deterministic sequences.

---

## 9. "Observe" State in ReAct

In the ReAct (Reason + Act) reasoning pattern, what is the purpose of the "Observe" state?

- ❌ **A)** Generate the final response in natural language for the user.
- ❌ **B)** Execute specific API calls to external services.
- ❌ **C)** Store conversation history and user preferences.
- ✅ **D)** Execute future actions and define the logic of how tasks are decomposed and sequenced.

> **Explanation:** According to the official answer key, the "Observe" state is responsible for executing future actions and defining task decomposition and sequencing logic.

---

## 10. Architecture for Multiple Intents

In a real prompt scenario involving multiple intents (e.g., "Translate this review, summarize it, and then analyze the sentiment"), what is the architectural approach needed to handle the request effectively?

- ❌ **A)** Increase the model temperature to encourage creative multitasking.
- ❌ **B)** Implement a "One-Shot" classification agent that routes the entire prompt only to a sentiment model.
- ❌ **C)** Use a single "Chain of Thought" prompt that forces the model to output all three results in a JSON block.
- ✅ **D)** Design a structured pipeline where the request is decomposed into sub-tasks (translation, summarization, sentiment analysis) that can depend on each other.

> **Explanation:** For complex requests, decompose into discrete sub-tasks, order by dependencies, and execute sequentially. This allows better debugging, modularity, and granular error handling.

---

## 11. "Analysis" Phase in Development Lifecycle

During the "Analysis" phase of the application development lifecycle, what are the primary objectives defined before moving to architecture design?

- ✅ **A)** Define project objectives, user requirements, scope, functionalities, and constraints.
- ❌ **B)** Rigorous testing and fixing issues in the development process.
- ❌ **C)** Outline technical behavior and code system components.
- ❌ **D)** Evaluate deployment performance and usability against benchmarks.

> **Explanation:** The Analysis phase focuses on understanding WHAT to build (requirements, scope, constraints) before defining HOW to build (architecture/design).

---

## 12. Multi-Modal Retrieval with CLIP

In Multi-Modal Retrieval, what is the primary approach used by methods like CLIP to handle different data types?

- ✅ **A)** Embedding all modalities (text, images, etc.) in the same vector space to enable cross-modal search.
- ❌ **B)** Training a separate model for each possible pair of modalities (e.g., text-to-image, image-to-audio).
- ❌ **C)** Converting all images to text descriptions and discarding visual data.
- ❌ **D)** Relying exclusively on metadata tags for image retrieval.

> **Explanation:** CLIP uses contrastive learning to embed text and images in the SAME vector space, enabling cross-modal search where similarity is comparable across modalities.

---

## 13. Framework for Collaborative Intelligence

Which tools framework is explicitly described as enabling collaborative intelligence by orchestrating autonomous AI agents to work together seamlessly on complex tasks?

- ❌ **A)** AutoGPT
- ❌ **B)** Transformers Agents
- ❌ **C)** HuggingGPT
- ✅ **D)** Crew AI

> **Explanation:** Crew AI is specifically designed to create "crews" of collaborative AI agents, each with a specific role/expertise, working together on complex tasks.

---

## 14. "Signatures" in DSPy

Within the DSPy framework, what are "Signatures"?

- ❌ **A)** The specific weights of the fine-tuned model.
- ❌ **B)** The logs generated by the automatic compiler during optimization.
- ❌ **C)** The cryptographic keys used to protect LLM API calls.
- ✅ **D)** Declarative modules that guide LLMs following a Pythonic structure to define inputs and outputs (e.g., ChainOfThought).

> **Explanation:** DSPy Signatures are declarative input/output specifications (e.g., "question -> answer") that allow programming LLMs in a Pythonic way without manual prompt engineering.

---

## 15. Pricing Model for High-Throughput Production

Which Databricks Foundation Model API pricing model is most suitable for high-throughput production applications requiring performance guarantees?

- ✅ **A)** Provisioned Throughput
- ❌ **B)** Pay-per-token
- ❌ **C)** Serverless Compute
- ❌ **D)** Spot Instance Pricing

> **Explanation:** Provisioned Throughput reserves dedicated capacity with latency and throughput guarantees, ideal for critical production. Pay-per-token doesn't guarantee performance; Spot can be interrupted.

---

## 16. Compound AI Systems

According to the definition of "Compound AI Systems", what is the primary advantage of this architecture over using a single monolithic model?

- ❌ **A)** Eliminates the need for prompt engineering by automating the intent classification process.
- ✅ **B)** Addresses AI tasks using multiple interacting components, such as retrievers and external tools, enabling more complex and reliable workflows.
- ❌ **C)** Relies exclusively on a single Foundation Model to handle all reasoning and retrieval tasks to minimize latency.
- ❌ **D)** Forces all data processing to occur within the LLM's GPU memory to ensure data privacy.

> **Explanation:** Compound AI Systems combine multiple components (LLMs, retrievers, tools, etc.) to solve complex tasks, being more flexible and reliable than monolithic models.

---

## 17. DSPy vs Manual Prompting

How does the DSPy framework fundamentally differ from manual prompting techniques when programming with LLMs?

- ✅ **A)** Uses an "Automatic Compiler" to trace program execution and generate high-quality prompts or fine-tune LLMs to internalize procedural details.
- ❌ **B)** Requires the developer to manually write each instruction and few-shot example for each interaction.
- ❌ **C)** Relies exclusively on hard-coded prompt templates that cannot be optimized.
- ❌ **D)** Is a no-code visual builder that prevents the use of Pythonic structures.

> **Explanation:** DSPy's Compiler/Optimizer automatically generates optimized prompts based on declarative Signatures, eliminating manual prompt engineering.

---

## 18. "Planning" Component in Agent Systems

In a typical Agent system architecture, what is the specific role of the "Planning" component?

- ✅ **A)** Agents involve iterative and non-deterministic workflows where the LLM dynamically decides the sequence of actions and tools to use.
- ❌ **B)** Chains require external tools, while Agents operate entirely within the model's parametric memory.
- ❌ **C)** Chains use LLMs for reasoning, while Agents only use LLMs for summarization.
- ❌ **D)** Agents are deterministic and always follow a hard-coded sequence of actions.

> **Explanation:** The Planning component is responsible for decomposing tasks, deciding the execution sequence, and determining which tools to use dynamically.

---

## 19. Definition of "Chain" in LangChain

In the context of the LangChain framework, how is a "Chain" specifically defined?

- ❌ **A)** A structured text input designed to communicate a specific task to a language model.
- ❌ **B)** A database interface that returns relevant documents based on unstructured queries.
- ❌ **C)** A standalone function that an agent can activate, such as an API call or database lookup.
- ✅ **D)** A sequence of automated actions or components that process the user's query to produce the model's output.

> **Explanation:** A Chain in LangChain is a sequence of connected components that automate the flow from query to output. A=Prompt, B=Retriever, C=Tool.

---

## 20. Multi-agent Collaboration - Scalability Challenge

What scalability challenge in complex tasks does the "Multi-agent Collaboration" pattern specifically address?

- ❌ **A)** Ensures all agents share exactly the same memory and context window to prevent hallucinations.
- ✅ **B)** Addresses the difficulty of scaling a single agent's behavior by utilizing specialized agents that work collaboratively on different aspects of the task.
- ❌ **C)** Eliminates the need for a central "Brain" LLM by distributing logic to the vector database.
- ❌ **D)** Reduces inference cost by using smaller, non-specialized models for all tasks.

> **Explanation:** Multi-agent Collaboration solves scalability by decomposing tasks into sub-tasks with specialized agents that collaborate, being more scalable than a single overloaded agent.
