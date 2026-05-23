---
tags:
  - ai
  - interview
  - cognizant
  - ace-team
date: 2026-05-23
status: in-progress
---

# AI / LLM — Complete Topic Checklist
## For Cognizant Ace Team — Full-Stack AI Engineer Interview

> [!quote] Purpose
> Single source of truth. Every AI topic you need for the interview.
> Mark each topic as you finish revising it.

---

## Priority Tiers

> [!danger] 🔴 Mission-Critical (Must Know Cold)
> Sections: 1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 13, 15, 16, 19, 21 (LangChain part), 22, 25, 26, 27, 32, 38, 39, 40, 41

> [!warning] 🟡 Nice-to-Have (One-Liner Awareness)
> Sections: 10, 12, 14, 17, 18, 20, 21 (other frameworks), 23, 24, 28, 29, 30, 31, 33, 34, 35, 36, 37

> [!note] ⚪ Skip Unless Time Permits
> - Detailed transformer math
> - LoRA/QLoRA/PEFT internals
> - ColBERT, speculative decoding, KV cache internals
> - EU AI Act details
> - Ray Serve, Triton internals
> - Image generation deep-dive
> - Semantic Kernel, Haystack details

---

## 1. LLM Fundamentals 🔴

- [ ] What is an LLM (high-level)
- [ ] Transformer architecture (conceptual, not math)
- [ ] Attention mechanism (conceptual)
- [ ] Self-attention vs cross-attention
- [ ] Encoder vs decoder vs encoder-decoder models
- [ ] Pre-training vs fine-tuning vs RLHF
- [ ] Instruction tuning
- [ ] Base models vs chat/instruct models
- [ ] Open-source vs closed-source models
- [ ] Model sizes (7B, 13B, 70B, 175B params)
- [ ] Popular model families — GPT, Claude, Llama, Mistral, Gemini, Qwen, DeepSeek
- [ ] Multimodal models (text + image + audio)

---

## 2. Tokens and Tokenization 🔴

- [ ] What is a token
- [ ] Tokenization algorithms — BPE, WordPiece, SentencePiece
- [ ] Tokens vs words vs characters
- [ ] Token counting rule of thumb (1 token ≈ 4 chars ≈ 0.75 words)
- [ ] Why non-English uses more tokens
- [ ] Tokenizers per model (tiktoken for OpenAI)

---

## 3. Context Window 🔴

- [ ] What is context window
- [ ] Input + output budget
- [ ] Typical sizes across models (8K, 32K, 128K, 200K, 1M, 2M)
- [ ] "Lost in the middle" problem
- [ ] Trade-offs of large context

---

## 4. Generation Parameters 🔴

- [ ] Temperature
- [ ] Top-p (nucleus sampling)
- [ ] Top-k
- [ ] max_tokens
- [ ] frequency_penalty
- [ ] presence_penalty
- [ ] Stop sequences
- [ ] Seed (for reproducibility)
- [ ] Log probabilities (logprobs)
- [ ] Streaming flag

---

## 5. Embeddings 🔴

- [ ] What is an embedding (vector representation)
- [ ] Embedding dimensions (384, 768, 1024, 1536, 3072)
- [ ] How embeddings encode meaning
- [ ] Cosine similarity
- [ ] Dot product
- [ ] Euclidean distance
- [ ] Manhattan distance
- [ ] Normalized vs unnormalized vectors
- [ ] Popular embedding models — OpenAI text-embedding-3, sentence-transformers (MiniLM, MPNet), BGE, Cohere embed-v3, Voyage
- [ ] Domain-specific embeddings (BioBERT, FinBERT, etc.)
- [ ] Multilingual embeddings
- [ ] Re-embedding when changing models

---

## 6. Fine-tuning vs Prompting vs RAG 🔴

- [ ] What each does
- [ ] When to use each
- [ ] Cost comparison
- [ ] Decision framework
- [ ] Hybrid approaches
- [ ] LoRA (Low-Rank Adaptation) — conceptual
- [ ] QLoRA — conceptual
- [ ] PEFT (Parameter Efficient Fine-Tuning) — conceptual
- [ ] Instruction tuning vs domain fine-tuning

---

## 7. Hallucinations 🔴

- [ ] What hallucinations are
- [ ] Why LLMs hallucinate
- [ ] Types — factual, faithfulness, logical, citation
- [ ] Mitigation techniques — RAG, low temperature, prompt instructions, structured outputs, citation enforcement, fact-checking pipelines, guardrails, human-in-the-loop
- [ ] Hallucination detection methods

---

## 8. Prompt Engineering 🔴

- [ ] Anatomy of a prompt (system / user / assistant)
- [ ] Zero-shot prompting
- [ ] One-shot prompting
- [ ] Few-shot prompting
- [ ] Chain-of-Thought (CoT) prompting
- [ ] Zero-shot CoT ("Let's think step by step")
- [ ] Self-Consistency
- [ ] ReAct prompting (Reason + Act)
- [ ] Tree-of-Thoughts
- [ ] Skeleton-of-Thought
- [ ] Prompt chaining
- [ ] Role prompting / persona prompting
- [ ] Negative prompting (what NOT to do)
- [ ] Delimiters and formatting
- [ ] Output format specification
- [ ] Prompt templates (parameterization)
- [ ] Variable injection
- [ ] Prompt versioning
- [ ] Prompt A/B testing

---

## 9. Structured Outputs 🔴

- [ ] Why structured outputs matter
- [ ] JSON mode (OpenAI, Anthropic)
- [ ] Function calling / tool calling
- [ ] Pydantic models with Instructor library
- [ ] LangChain output parsers
- [ ] JSON Schema enforcement
- [ ] Retry on schema violation
- [ ] Constrained decoding (Outlines, Guidance) — conceptual

---

## 10. Prompt Injection and Security 🟡

- [ ] Direct prompt injection
- [ ] Indirect prompt injection (in retrieved docs)
- [ ] Jailbreaks
- [ ] Defenses — input sanitization, system-prompt sandwiching, role separation, output filtering, least privilege, content moderation APIs
- [ ] OpenAI Moderation API
- [ ] Azure Content Safety
- [ ] LlamaGuard

---

## 11. RAG — Retrieval Augmented Generation 🔴

- [ ] What RAG is and why
- [ ] Full pipeline (load → chunk → embed → store → retrieve → augment → generate)
- [ ] Indexing phase vs query phase
- [ ] When RAG helps vs hurts
- [ ] RAG vs long context

---

## 12. Document Loading (RAG Step 1) 🟡

- [ ] File formats — PDF, DOCX, HTML, Markdown, CSV, JSON, TXT
- [ ] PDF parsers — PyPDF, PDFPlumber, Unstructured, PyMuPDF
- [ ] HTML — BeautifulSoup
- [ ] Office docs — python-docx, openpyxl
- [ ] Database loaders
- [ ] Web loaders
- [ ] Metadata preservation (source, page, section)

---

## 13. Chunking (RAG Step 2) 🔴

- [ ] Why chunking matters
- [ ] Fixed-size chunking
- [ ] Recursive character splitting (most common)
- [ ] Token-based chunking
- [ ] Semantic chunking
- [ ] Sentence-window chunking
- [ ] Markdown/HTML-aware chunking
- [ ] Code-aware chunking
- [ ] Parent-document chunking (small for retrieval, large for context)
- [ ] Chunk size tuning
- [ ] Chunk overlap (why and how much)
- [ ] Metadata per chunk

---

## 14. Embedding for RAG (RAG Step 3) 🟡

- [ ] Choosing embedding model
- [ ] Batching embeddings
- [ ] Caching embeddings
- [ ] Re-embedding when model changes
- [ ] Domain adaptation
- [ ] Cost of embedding (per token)

---

## 15. Vector Databases (RAG Step 4) 🔴

- [ ] What a vector DB does
- [ ] Exact search vs Approximate Nearest Neighbor (ANN)
- [ ] HNSW (Hierarchical Navigable Small World)
- [ ] IVF (Inverted File Index)
- [ ] PQ (Product Quantization)
- [ ] LSH (Locality Sensitive Hashing) — conceptual
- [ ] Vector DB options — FAISS, Chroma, Pinecone, Weaviate, Qdrant, Milvus, pgvector, Redis Vector
- [ ] Self-hosted vs managed
- [ ] Hybrid storage (vectors + metadata)
- [ ] Metadata filtering
- [ ] Persistence and durability
- [ ] Scaling vector DBs (sharding, replication)
- [ ] Cost considerations

---

## 16. Retrieval (RAG Step 5–6) 🔴

- [ ] Top-k retrieval
- [ ] Choosing k
- [ ] Similarity threshold cutoffs
- [ ] Hybrid search (vector + BM25 keyword)
- [ ] Reciprocal Rank Fusion (RRF)
- [ ] MMR (Maximal Marginal Relevance)
- [ ] Multi-query retrieval
- [ ] HyDE (Hypothetical Document Embeddings)
- [ ] Self-querying retriever
- [ ] Contextual retrieval (Anthropic technique)
- [ ] Query expansion / rewriting
- [ ] Query decomposition

---

## 17. Reranking (RAG Step 7) 🟡

- [ ] Why rerank
- [ ] Bi-encoder vs cross-encoder
- [ ] Cohere Rerank API
- [ ] sentence-transformers cross-encoders
- [ ] BGE rerankers
- [ ] ColBERT (late interaction) — conceptual
- [ ] LLM-as-reranker

---

## 18. Prompt Augmentation (RAG Step 8) 🟡

- [ ] Context injection patterns
- [ ] Citation prompts
- [ ] Instructions for "answer only from context"
- [ ] Handling no-results case
- [ ] Quote-and-answer pattern

---

## 19. RAG Evaluation 🔴

- [ ] Why evaluation is hard
- [ ] RAGAS framework
- [ ] Faithfulness
- [ ] Answer Relevancy
- [ ] Context Precision
- [ ] Context Recall
- [ ] Context Relevancy
- [ ] DeepEval
- [ ] TruLens
- [ ] LangSmith
- [ ] LLM-as-judge approach
- [ ] Golden test sets / regression tests
- [ ] A/B testing in production

---

## 20. Advanced RAG Patterns 🟡

- [ ] Conversational RAG (chat history rewriting)
- [ ] Multi-hop RAG
- [ ] Agentic RAG
- [ ] GraphRAG (knowledge graph + RAG)
- [ ] Corrective RAG (CRAG)
- [ ] Self-RAG
- [ ] Adaptive RAG (route by query type)
- [ ] Long-context vs RAG trade-offs

---

## 21. LLM Orchestration Frameworks 🔴 (LangChain) / 🟡 (others)

### LangChain 🔴

- [ ] Core abstractions (LLM, PromptTemplate, OutputParser, Chain, Retriever, VectorStore, Memory, Agent, Tool, Document)
- [ ] LCEL (LangChain Expression Language)
- [ ] When to use, when not to

### LangGraph 🟡

- [ ] State machines for agents
- [ ] Nodes, edges, state
- [ ] When to use

### LlamaIndex 🟡

- [ ] RAG-first framework
- [ ] Query engines
- [ ] Index types

### CrewAI 🟡

- [ ] Multi-agent collaboration
- [ ] Roles, goals, tools

### AutoGen 🟡

- [ ] Microsoft's multi-agent framework
- [ ] Conversation patterns

### Others 🟡

- [ ] Haystack
- [ ] Semantic Kernel (Microsoft)
- [ ] DSPy (prompt optimization)
- [ ] Direct SDK usage (when to skip frameworks)

---

## 22. Agentic Workflows 🔴

- [ ] What is an agent
- [ ] Plain LLM vs RAG vs Agent
- [ ] Agent components — LLM, tools, memory, planner, loop controller
- [ ] ReAct pattern (full loop)
- [ ] Plan-and-Execute pattern
- [ ] Reflexion / self-critique
- [ ] Tool calling / function calling
- [ ] Native tool calling (OpenAI, Anthropic)
- [ ] Tool design principles (atomic, self-describing, idempotent, validated, least privilege)
- [ ] Multi-agent systems
- [ ] Communication patterns — sequential, hierarchical, debate, broadcast
- [ ] Manager-worker pattern
- [ ] Specialist agents
- [ ] Human-in-the-loop agents
- [ ] When to use an agent vs simpler approach
- [ ] Agent failure modes — loops, hallucinated tool calls, cost explosion
- [ ] Agent observability and debugging

---

## 23. Memory in LLM Apps 🟡

- [ ] No memory (stateless)
- [ ] Conversation buffer memory
- [ ] Window memory (last N turns)
- [ ] Summary memory (LLM summarizes history)
- [ ] Vector memory (embed and retrieve past turns)
- [ ] Entity memory
- [ ] Long-term memory vs session memory
- [ ] Memory persistence (Redis, SQL)

---

## 24. AI Evaluation & Metrics 🟡

- [ ] Why LLM evaluation is hard
- [ ] Reference-based metrics — BLEU, ROUGE, METEOR, F1, exact match
- [ ] Reference-free / LLM-as-judge
- [ ] Pairwise comparison
- [ ] Human evaluation
- [ ] A/B testing online
- [ ] Regression test suites
- [ ] Faithfulness
- [ ] Relevance
- [ ] Coherence
- [ ] Toxicity
- [ ] Bias detection
- [ ] Robustness testing
- [ ] Adversarial testing

---

## 25. Guardrails 🔴

- [ ] Input guardrails — PII detection, prompt injection detection, toxicity, rate limiting
- [ ] Output guardrails — schema validation, PII redaction, toxicity filters, factuality checks, business rules
- [ ] Guardrails AI library
- [ ] NVIDIA NeMo Guardrails
- [ ] LlamaGuard
- [ ] Custom validators
- [ ] Microsoft Presidio (PII)

---

## 26. Cost Optimization 🔴

- [ ] Token-level — shorter prompts, prompt caching, compression
- [ ] Provider-side prompt caching (Anthropic, OpenAI)
- [ ] Model-level — model routing, cascading, smaller models
- [ ] Architecture-level — semantic caching, batching, async
- [ ] Quantization (for self-hosted)
- [ ] Distillation — conceptual
- [ ] Cost monitoring and budgets
- [ ] Cost per query / per user calculations

---

## 27. Latency Optimization 🔴

- [ ] Streaming responses (SSE, WebSocket)
- [ ] Smaller models for latency-sensitive paths
- [ ] Caching (exact, semantic, prefix)
- [ ] Parallel tool calls
- [ ] Reduce input tokens (prefill latency)
- [ ] Speculative decoding — conceptual
- [ ] KV cache — conceptual
- [ ] Async vs sync calls
- [ ] Time to first token (TTFT) vs total latency

---

## 28. Caching Strategies 🟡

- [ ] Exact-match cache
- [ ] Semantic cache (embedding-based)
- [ ] GPTCache, Redis Vector Search
- [ ] Prompt prefix caching (provider-side)
- [ ] TTL strategies
- [ ] Cache invalidation

---

## 29. Monitoring and Observability 🟡

- [ ] What to log (inputs, outputs, latency, tokens, cost, errors, feedback)
- [ ] LangSmith
- [ ] Langfuse
- [ ] Arize Phoenix
- [ ] TruLens
- [ ] Helicone
- [ ] Datadog / Prometheus / Grafana for custom metrics
- [ ] Token usage tracking
- [ ] Cost dashboards
- [ ] Hallucination rate sampling
- [ ] User feedback signals (thumbs up/down)

---

## 30. Fallback and Degradation 🟡

- [ ] Retry with exponential backoff
- [ ] Model failover (primary → secondary provider)
- [ ] Graceful degradation (cached / canned responses)
- [ ] Circuit breaker pattern for LLM calls
- [ ] Timeout enforcement
- [ ] Schema-validation retry
- [ ] Rate limit handling

---

## 31. Responsible AI 🟡

- [ ] Bias in training data
- [ ] Fairness across demographics
- [ ] Privacy and PII
- [ ] Transparency (disclose AI use)
- [ ] Explainability
- [ ] Accountability
- [ ] Auditability
- [ ] Content safety
- [ ] Copyright concerns
- [ ] GDPR, DPDP Act (India), HIPAA-equivalents
- [ ] RBI guidelines for AI in financial services (relevant to AcquirerX)
- [ ] EU AI Act — conceptual

---

## 32. Security and Privacy 🔴

- [ ] PII handling — detection, redaction, re-injection
- [ ] Microsoft Presidio
- [ ] AWS Comprehend PII
- [ ] On-prem / in-VPC LLMs
- [ ] Bedrock (AWS), Azure OpenAI in VPC
- [ ] Data residency
- [ ] Encryption in transit and at rest
- [ ] Audit logs
- [ ] Access control for LLM endpoints
- [ ] Prompt injection defenses (revisited)
- [ ] Model output risks — harmful content, copyright, fake citations
- [ ] Sandbox for agent tool execution

---

## 33. LLM APIs and SDKs 🟡

### OpenAI API

- [ ] Chat completions
- [ ] Embeddings
- [ ] Moderations
- [ ] Function calling
- [ ] Assistants API
- [ ] Batch API
- [ ] Streaming
- [ ] Rate limits and tiers

### Anthropic Claude API

- [ ] Messages endpoint
- [ ] System prompt as separate field
- [ ] Tool use
- [ ] Vision
- [ ] Prompt caching

### Others

- [ ] Google Gemini API
- [ ] Hugging Face — transformers library, sentence-transformers, datasets, Inference Endpoints
- [ ] AWS Bedrock — multi-provider gateway, IAM-based access, VPC integration
- [ ] Azure OpenAI Service
- [ ] Vertex AI (GCP)
- [ ] Ollama (local models)
- [ ] LM Studio (local)
- [ ] vLLM (high-throughput serving)
- [ ] Text Generation Inference (TGI)

---

## 34. Design Patterns and Architecture 🟡

- [ ] RAG Q&A pattern
- [ ] Conversational RAG
- [ ] Agent with tools
- [ ] LLM-augmented search
- [ ] Document processing pipeline (extract → structure → store)
- [ ] Code generation / refactoring pattern
- [ ] Multi-step workflow automation
- [ ] Human-in-the-loop pattern
- [ ] LLM Gateway pattern
- [ ] Multi-model routing
- [ ] Streaming response pattern
- [ ] Asynchronous LLM jobs
- [ ] Event-driven AI (Kafka + LLM)

---

## 35. LLM Gateway 🟡

- [ ] Why use a gateway
- [ ] LiteLLM
- [ ] Portkey
- [ ] Custom gateway (e.g., Spring Boot) — your differentiator
- [ ] Responsibilities — auth, rate limiting, cost tracking, logging, routing, caching, fallback

---

## 36. Multimodal AI 🟡

- [ ] Vision models — GPT-4V, Claude Vision, Gemini Vision
- [ ] OCR vs vision LLMs
- [ ] Image embeddings — CLIP
- [ ] Speech — Whisper (STT), TTS models
- [ ] Image generation — DALL-E, Stable Diffusion, Flux
- [ ] Use cases for multimodal in enterprise

---

## 37. Open-source Model Deployment 🟡

- [ ] Hugging Face Inference Endpoints
- [ ] vLLM
- [ ] Text Generation Inference (TGI)
- [ ] Ollama
- [ ] Ray Serve
- [ ] Triton Inference Server
- [ ] Quantization (GGUF, AWQ, GPTQ) — conceptual
- [ ] GPU vs CPU inference

---

## 38. Common Interview Questions 🔴

> [!tip] Rehearse these aloud, not just in your head

- [ ] Explain RAG to a non-technical person
- [ ] How to reduce hallucinations
- [ ] When to use agent vs chain vs plain LLM
- [ ] Fine-tuning vs RAG
- [ ] How to evaluate LLM responses
- [ ] Cost optimization strategies
- [ ] Prompt injection and defenses
- [ ] Cosine vs dot product
- [ ] Walk through Care++ end-to-end
- [ ] How would you add AI to AcquirerX
- [ ] Design a RAG system for X
- [ ] Pick a vector DB and justify

---

## 39. Care++ Specific (Your Project) 🔴

- [ ] Why FAISS
- [ ] Chunking strategy and parameters
- [ ] Embedding model choice (sentence-transformers)
- [ ] Why ResNet50 (image classification)
- [ ] Why BioBERT (biomedical NER)
- [ ] Why Llama-3 (summarization)
- [ ] Prompt template design
- [ ] Structured JSON output design
- [ ] Hallucination mitigation in clinical context
- [ ] Scaling Care++ (vector DB scaling, multi-tenancy)
- [ ] PII / HIPAA-equivalent handling

---

## 40. AcquirerX + AI (Your Differentiator) 🔴

- [ ] RAG over compliance documents (PCI-DSS, RBI, internal SOPs)
- [ ] LLM-powered transaction anomaly summarization
- [ ] Agentic dispute resolution assistant
- [ ] AI-powered merchant onboarding chatbot
- [ ] Fraud detection augmentation
- [ ] LLM Gateway as Spring Boot microservice
- [ ] Resilience4J around LLM calls
- [ ] Integration with existing JWT auth and observability
- [ ] Cost and latency considerations for fintech

---

## 41. AI Coding Assistants 🔴

> [!info] JD explicitly mentions "ship at 2x velocity using AI coding assistants". Be ready.

- [ ] GitHub Copilot — autocomplete, inline suggestions, when it helps vs hurts
- [ ] Claude Code / Cursor / Windsurf — agentic coding tools
- [ ] Code review with LLMs
- [ ] Test generation with LLMs
- [ ] Documentation generation
- [ ] Refactoring with AI assistance
- [ ] AI-augmented debugging workflows
- [ ] Treating AI output like a junior developer's PR (always review)
- [ ] Your honest personal workflow with AI tools — what you use, when, why

> [!example] Sample answer to rehearse
> "I use Claude for architectural discussions and complex debugging, Copilot for boilerplate and test generation. I always review AI-generated code carefully — I treat it like a junior developer's PR. The productivity gain is real but it requires discipline to not blindly accept output, especially for security-sensitive code in a payments platform like AcquirerX."

---

## What to Skip

> [!warning] Be ruthless about time — these are too deep / too niche for a fresher Ace Team interview
> - ❌ Detailed transformer math (Q/K/V, multi-head attention computation)
> - ❌ LoRA / QLoRA / PEFT internals beyond the name
> - ❌ ColBERT, late interaction details
> - ❌ Speculative decoding internals
> - ❌ KV cache internals
> - ❌ EU AI Act details
> - ❌ Ray Serve, Triton Inference Server internals
> - ❌ Image generation deep-dive (DALL-E, Stable Diffusion architecture)
> - ❌ Semantic Kernel, Haystack details
> - ❌ Pre-training data curation
>
> Know they exist. Don't go deep.

---

## Final Interview-Day Checklist

- [ ] Can draw the full RAG pipeline on a whiteboard from memory
- [ ] Can explain Care++ end-to-end in 2 minutes
- [ ] Have a memorized answer for "how would you add AI to AcquirerX" with 3 concrete use cases
- [ ] Can define cold: tokens, embeddings, context window, temperature, cosine similarity
- [ ] Can list prompt techniques: zero-shot, few-shot, CoT, ReAct
- [ ] Can list RAGAS metrics: faithfulness, relevance, context precision, context recall
- [ ] Can describe: ReAct agent loop, tool calling, when to use agent vs chain
- [ ] Can describe: at least 3 hallucination mitigations
- [ ] Can describe: prompt injection and 3 defenses
- [ ] Can describe: at least 3 cost optimization strategies
- [ ] Can describe: how you use AI coding assistants in your daily workflow
- [ ] Know names: LangChain, LangGraph, CrewAI, AutoGen, LlamaIndex, RAGAS, DeepEval
- [ ] Know names: FAISS, Chroma, Pinecone, Weaviate, Qdrant, pgvector
- [ ] One-line answer for: RAG vs fine-tuning vs prompting decision
- [ ] One-line answer for: cosine vs dot product
- [ ] At least 2 smart questions to ask the interviewer
- [ ] LLM Gateway as Spring Boot microservice — pitch ready

---

## Coverage Scorecard

| Area | Coverage | Notes |
|---|---|---|
| Breadth of topics | 10/10 | Nothing missing from JD |
| RAG depth | 10/10 | Sections 11–20 cover everything |
| Agent depth | 9/10 | Section 22 plus LangGraph |
| Production/Ops | 9/10 | Sections 24–30 |
| Security | 9/10 | Sections 10, 25, 32 |
| Project-specific | 10/10 | Sections 39, 40 |
| JD coding-assistant requirement | 10/10 | Section 41 |

> [!success] Verdict
> This list is over-provisioned. Stop expanding the syllabus. Start drilling aloud.

---

## Study Strategy

> [!tip] Follow this sequence
> 1. **Knowledge phase** — Go through each 🔴 section, ensure you can explain every bullet in your own words.
> 2. **Articulation phase** — Pick 10 topics from Section 38 and explain each aloud in 60-90 seconds.
> 3. **Project phase** — Rehearse Care++ (Section 39) and AcquirerX+AI (Section 40) walkthroughs until automatic.
> 4. **Buffer phase** — Skim 🟡 sections, just enough to recognize and one-liner.
> 5. **Final phase** — Final Interview-Day Checklist above.
>
> Knowing 100 topics shallowly is worse than knowing 30 topics deeply enough to explain unprompted. Articulation under pressure is what wins these rounds.

---

**End of checklist. Earn your place, Kailash.**
