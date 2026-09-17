# 🚀 Project Ideas & Final Capstone

## 🏁 TaskFlow v3 — Final Capstone (ties together the whole syllabus)

Build the final version of the running project used throughout this course. This is meant to be portfolio-quality.

### Functional Scope
- [ ] Multi-tenant task/project management system ("workspaces" with members and roles)
- [ ] Full CRUD for tasks, categories/projects, comments, attachments
- [ ] Real-time updates (SignalR) when tasks change
- [ ] AI features: natural-language task summarization + an MCP-exposed agent interface for managing tasks conversationally

### Architecture Requirements
- [ ] Split into at least 2 services (e.g., Tasks service + Notifications service) communicating via a message broker
- [ ] CQRS + MediatR with Vertical Slice Architecture in the Tasks service
- [ ] EF Core with optimized queries (no N+1, proper indexing, keyset pagination on large lists)
- [ ] Outbox pattern for reliable event publishing

### Security Requirements
- [ ] ASP.NET Core Identity (or external OIDC provider) with JWT + refresh tokens
- [ ] Dynamic, database-driven permission system (not hardcoded roles)
- [ ] Multi-tenant authorization (role differs per workspace)
- [ ] Security headers, rate limiting on auth endpoints, dependency vulnerability scanning clean

### Quality & Operations Requirements
- [ ] Unit + integration + at least a few E2E tests (Playwright/Cypress)
- [ ] Structured logging (Serilog) + correlation IDs + centralized exception handling
- [ ] Full OpenTelemetry instrumentation (traces visible across both services) + a Grafana dashboard
- [ ] GitHub Actions CI/CD pipeline: build → test → scan → containerize → deploy to a staging environment
- [ ] Dockerized with Docker Compose (or .NET Aspire) for one-command local startup

### Frontend Requirements
- [ ] React or Angular SPA, TypeScript strict mode, generated API client from OpenAPI
- [ ] BFF-pattern auth (httpOnly cookies, no raw JWT in browser storage)
- [ ] Real-time UI updates via SignalR, optimistic updates on task completion

### Documentation Requirements
- [ ] Clean README with architecture diagram, setup instructions
- [ ] At least 2 ADRs (Architecture Decision Records) explaining key choices (e.g., "why CQRS," "why this permission model")
- [ ] `docs/ai-usage.md` reflecting on your use of AI throughout the build

---

## 🎯 Smaller Practice Project Ideas (per level, if you want variety beyond TaskFlow)

### Beginner-level ideas
- A personal expense tracker (console → simple Web API)
- A recipe box API with categories and search
- A URL shortener service

### Intermediate-level ideas
- A blogging platform with user accounts, roles (Author/Admin), and a React/Angular frontend
- A simple e-commerce catalog with cart + basic checkout flow (no real payment) and Identity-based auth
- A bookmarking/reading-list app with tagging and full-text search

### Advanced-level ideas
- A support ticketing system split into services (Tickets, Notifications, Reporting) with CQRS and an event bus
- A multi-tenant SaaS starter kit (auth, billing stub, workspace management) as a reusable template
- An AI-powered code review bot: an agent that reviews PRs via GitHub webhooks + MCP tools and posts review comments

Use these as alternates or supplements if you want more reps on a concept before moving to the next file.
