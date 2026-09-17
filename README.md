# dotnet-developer-roadmap

> A complete, self-paced .NET developer roadmap — from C# fundamentals to ASP.NET Core, EF Core, CQRS, microservices, security, and agentic AI. Beginner → Advanced.

This repo is a **syllabus**, not a textbook: each file lists the topics, subtopics, learning outcomes, hands-on tasks, and curated resource pointers for that subject. Use it as a checklist, a study planner, or a curriculum for mentoring others.

---

## 📁 How This Repo Is Organized

```
dotnet-developer-roadmap/
├── 00-Getting-Started/       → How to use this course, prerequisites, tooling setup
├── 01-Beginner/               → Foundations: C#, .NET, ASP.NET Core, Web API, SQL/EF Core, Git, AI basics
├── 02-Intermediate/           → DI, layered architecture, security/Identity/JWT, EF Core deep dive, React/Angular/TS
├── 03-Advanced/               → CQRS/MediatR, microservices, performance, advanced security, agentic AI
├── 04-Resources/              → Microsoft Learn links, verified YouTube channels, books, project ideas, interview prep
└── README.md                  → You are here
```

Each level folder contains numbered `.md` files — study them in order, but feel free to jump around based on your existing experience.

---

## 🎯 Learning Tracks Covered

| Track | Beginner | Intermediate | Advanced |
|---|---|---|---|
| C# Language | ✅ | ✅ | ✅ |
| ASP.NET Core (MVC/Web API) | ✅ | ✅ | ✅ |
| Entity Framework Core | ✅ | ✅ | ✅ (perf & complex queries) |
| Dependency Injection | intro | ✅ | ✅ (advanced lifetimes, patterns) |
| Exception Handling & Logging | ✅ | ✅ | ✅ (observability, distributed tracing) |
| Security / Identity / RBAC | intro | ✅ | ✅ (OAuth2/OIDC, hardening) |
| CQRS / MediatR | — | intro | ✅ |
| Microservices | — | intro | ✅ |
| Frontend (HTML/CSS/JS/TS) | ✅ | ✅ (React/Angular) | ✅ (advanced patterns) |
| Git & GitHub | ✅ | ✅ | ✅ (Actions, workflows) |
| AI for Developers | ✅ (basics) | ✅ (Copilot, RAG basics) | ✅ (agentic AI, MCP, AI-driven pipelines) |

---

## 🗺️ Suggested Study Path

1. **Beginner (4–8 weeks)** — build a solid foundation. Finish with a simple CRUD Web API + EF Core + a basic frontend.
2. **Intermediate (6–10 weeks)** — layered architecture, DI, Identity-based auth, React/Angular frontend, structured logging.
3. **Advanced (8–12 weeks)** — CQRS/MediatR, microservices, performance tuning, advanced security, CI/CD, agentic AI tooling.

Each level's final file includes a **capstone project** to consolidate the skills.

---

## ✅ How to Use With GitHub

1. Unzip this folder and push it as a new repository named **`dotnet-developer-roadmap`**.
2. Add a short description to the repo's "About" section, e.g.:
   > A complete, self-paced .NET developer roadmap — from C# fundamentals to ASP.NET Core, EF Core, CQRS, microservices, security, and agentic AI. Beginner → Advanced.
3. Add topics/tags for discoverability: `dotnet` `aspnet-core` `csharp` `entity-framework-core` `roadmap` `learning-resources` `cqrs` `mediatr` `web-api` `microservices`
4. Turn each `##` heading into a GitHub Issue or Project board card to track your progress.
5. Use the checkboxes (`- [ ]`) inside each file as a personal progress tracker — GitHub renders them as interactive checklists.
6. Fork it, adapt it, or use it to plan a training curriculum for a team.

---

## 📌 Prerequisites

- Basic programming knowledge (any language)
- .NET SDK (latest LTS) installed — see `00-Getting-Started/`
- A code editor (Visual Studio / VS Code / Rider)
- A GitHub account

Start here → [`00-Getting-Started/README.md`](./00-Getting-Started/README.md)
