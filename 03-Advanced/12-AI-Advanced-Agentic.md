# 12 — AI Advanced: Agentic Systems & AI-Native Engineering

## 🎯 Learning Objectives
Understand and build AI **agents** — systems where an LLM plans, calls tools, and acts autonomously toward a goal — and integrate agentic patterns into .NET applications and your engineering workflow.

## 📚 Topics & Subtopics

### From Chat to Agents
- [ ] What makes something an "agent" vs a chatbot — planning, tool use, memory, autonomy
- [ ] The agent loop: observe → think/plan → act (call a tool) → observe result → repeat
- [ ] Single-agent vs multi-agent systems (agents that coordinate/hand off to each other)
- [ ] Guardrails: constraining what an agent is allowed to do, human-in-the-loop checkpoints

### Tool Use & Protocols
- [ ] Function/tool calling recap, and designing good tool schemas (clear names, descriptions, typed parameters)
- [ ] **Model Context Protocol (MCP)** — a standard way to expose tools/data/resources to AI agents; how it decouples "what tools exist" from "which AI model uses them"
- [ ] Building an MCP server that exposes your own application's capabilities (e.g., a TaskFlow MCP server exposing "create task", "list tasks" as tools)
- [ ] Security implications of giving an agent tool access (least privilege, sandboxing, approval gates for destructive actions)

### Building Agents in .NET
- [ ] Semantic Kernel's Agent Framework / planners — orchestrating multi-step tool use
- [ ] Memory for agents: short-term (conversation context) vs long-term (vector store-backed recall)
- [ ] Designing an agent's system prompt: role, constraints, available tools, failure/escalation behavior
- [ ] Handling agent failures gracefully (retries, fallbacks to human review, timeouts on runaway loops)
- [ ] Cost/latency control for multi-step agent runs (limiting tool-call iterations, caching intermediate results)

### AI-Native Software Engineering Practices
- [ ] Using coding agents (e.g., Claude Code, GitHub Copilot Workspace) for larger, multi-file tasks — not just autocomplete
- [ ] Writing agent-friendly repos: clear READMEs, consistent conventions, good test coverage (agents rely on tests as ground truth)
- [ ] Reviewing agent-generated PRs critically — treating AI output like a junior engineer's PR, not ground truth
- [ ] Evaluating AI features: building a small eval set (input/expected-output pairs) to regression-test prompt or agent changes over time
- [ ] Responsible AI considerations: hallucination risk in production features, user-facing disclaimers, human oversight for high-stakes actions (e.g., never let an agent delete production data unsupervised)

### Where This Is Heading (Awareness)
- [ ] Agent-to-agent communication standards (A2A) — how independent agents/services might interoperate
- [ ] AI-augmented CI/CD (agents that triage failing tests, suggest fixes) — current state and limitations

## 🧪 Hands-on Practice
- Build a **TaskFlow MCP server** exposing tools: `create_task`, `list_tasks`, `complete_task`, `summarize_overdue_tasks` — and connect it to an MCP-compatible AI client to control TaskFlow via natural language
- Build a small agent (using Semantic Kernel or a direct API + tool-calling loop) that, given "clean up my task list," can call `list_tasks`, reason about which are stale, and propose (not silently execute) deletions for human approval
- Add a human-in-the-loop approval step before any agent-initiated destructive action (delete/bulk-update) actually runs
- Create a small eval set (10–15 example prompts + expected behavior) for your AI summarization feature from the Intermediate AI file, and write a script that runs it and flags regressions
- Reflect in a short `docs/ai-usage.md`: which parts of building TaskFlow did you use AI assistance for, what did you double-check, and where did AI get something wrong

## 📖 Resources
- Model Context Protocol specification (modelcontextprotocol.io)
- Microsoft Learn: *Semantic Kernel Agent Framework*
- Anthropic / OpenAI documentation on agents and tool use
- Google's *Agents* whitepaper (概念 overview, vendor-neutral concepts)

## ❓ Self-Check Questions
- What's the core difference between a single tool-calling request and a true agent loop?
- Why does MCP matter — what problem does a standard protocol solve that "just calling a function" doesn't, once you have many tools and many possible AI clients?
- Why is a human-in-the-loop approval step non-negotiable for destructive agent actions in production?
- How would you evaluate whether a change to an agent's prompt made it *better* or *worse*, systematically rather than anecdotally?

## 🏁 Advanced Level — Final Capstone
See [`04-Resources/Project-Ideas.md`](../04-Resources/Project-Ideas.md) for the full **TaskFlow v3 (Final)** capstone specification, tying together every topic across all three levels.

**🎉 Completing this file means you've covered the full syllabus — from `Console.WriteLine` to a secured, observable, CI/CD-deployed, multi-service, AI-agentic system.**
