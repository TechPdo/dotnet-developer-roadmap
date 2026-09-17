# 10 — AI for Developers: Intermediate (RAG, Embeddings, AI-Assisted Engineering)

## 🎯 Learning Objectives
Go beyond prompting — integrate AI capabilities into a .NET application and understand the building blocks behind modern AI features (embeddings, RAG, semantic search).

## 📚 Topics & Subtopics

### Deeper LLM Concepts
- [ ] System prompts vs user prompts vs few-shot examples
- [ ] Function calling / tool calling — how an LLM can invoke your code
- [ ] Structured output (asking a model to return JSON matching a schema)
- [ ] Embeddings — what a vector representation of text is and why it enables semantic search

### Retrieval-Augmented Generation (RAG)
- [ ] The RAG pattern: retrieve relevant context, then generate an answer grounded in it
- [ ] Chunking documents, generating embeddings, storing them in a vector store
- [ ] Vector databases/options: Azure AI Search, Pinecone, Qdrant, pgvector (PostgreSQL extension)
- [ ] Similarity search basics (cosine similarity)

### Building AI Features into .NET Apps
- [ ] **Semantic Kernel** (Microsoft's SDK) — plugins, planners, memory
- [ ] Calling AI APIs (OpenAI/Anthropic/Azure OpenAI) from a .NET service layer, with proper DI, retries, and timeouts
- [ ] Streaming AI responses to a frontend (Server-Sent Events / streaming HTTP responses)
- [ ] Cost & latency considerations — caching AI responses, token usage tracking

### AI-Assisted Software Engineering Workflow
- [ ] Using AI for code review, generating unit tests, generating documentation
- [ ] AI-assisted debugging (pasting stack traces + context)
- [ ] Prompt patterns specific to codebases (providing relevant file context, constraints, existing conventions)
- [ ] Responsible use: verifying AI-suggested dependencies/packages actually exist and are safe

## 🧪 Hands-on Practice
- Add an **AI-powered task summarization feature** to TaskFlow: given a user's task list, call an LLM to produce a natural-language daily briefing
- Implement a simple RAG feature: let users upload notes, chunk + embed them, store in pgvector or a simple in-memory vector store, and answer questions grounded in those notes
- Use Semantic Kernel to wrap at least one "plugin" (e.g., a function that queries TaskFlow's own API) that the AI can call
- Stream the AI's response back to the React/Angular frontend token-by-token

## 📖 Resources
- Microsoft Learn: *Semantic Kernel documentation*
- OpenAI / Anthropic API docs — function calling & structured outputs
- pgvector GitHub repo
- "What is RAG?" — Microsoft/AWS/Anthropic explainer articles

## ❓ Self-Check Questions
- What problem does RAG solve that a plain LLM prompt cannot?
- Why is function/tool calling powerful for building AI agents?
- What are the cost/latency trade-offs of calling an LLM API on every request vs caching results?

## 🏁 Intermediate Level — Capstone Project
Evolve **TaskFlow v2**:
- [ ] Clean, layered architecture (Api / Application / Domain / Infrastructure)
- [ ] Full ASP.NET Core Identity auth with JWT + refresh tokens, roles, and resource-based policies
- [ ] React or Angular frontend with auth-aware routing/UI
- [ ] Structured Serilog logging + centralized exception handling with correlation IDs
- [ ] Integration tests covering the auth flow and core CRUD
- [ ] An AI-powered feature (task summarization or RAG-based Q&A over notes)
- [ ] CI pipeline via GitHub Actions running build + tests on every PR
- [ ] Deployed locally via Docker Compose (API + DB + frontend)

**Ready for → [`03-Advanced/`](../03-Advanced/01-CSharp-Advanced.md)**
