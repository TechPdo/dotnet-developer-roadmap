# 02 — ASP.NET Core Intermediate

## 🎯 Learning Objectives
Structure an ASP.NET Core application using clean, layered architecture principles suitable for real-world team projects.

## 📚 Topics & Subtopics

### Architecture & Project Structure
- [ ] Layered architecture: Presentation / Application / Domain / Infrastructure
- [ ] Clean Architecture / Onion Architecture overview
- [ ] Separating concerns: Controllers → Services → Repositories
- [ ] Solution structure for multi-project apps (Api, Core, Infrastructure, Tests projects)

### Configuration & Options Pattern
- [ ] Strongly-typed configuration with `IOptions<T>`, `IOptionsSnapshot<T>`, `IOptionsMonitor<T>`
- [ ] Validating options (`ValidateDataAnnotations`, `IValidateOptions<T>`)
- [ ] Named options

### Filters & Action Behavior
- [ ] Action filters, exception filters, authorization filters, resource filters
- [ ] Model validation filters — automatic `[ApiController]` behavior
- [ ] Custom filter attributes

### AutoMapper / Object Mapping
- [ ] Manual mapping vs AutoMapper vs Mapster
- [ ] Setting up mapping profiles between entities and DTOs
- [ ] Pitfalls: over-relying on auto-mapping hiding business logic

### API Design Deep Dive
- [ ] Pagination, filtering, sorting patterns
- [ ] HATEOAS awareness
- [ ] API versioning strategies in depth (URL, query string, header, media type)
- [ ] Rate limiting middleware (`Microsoft.AspNetCore.RateLimiting`)
- [ ] Response caching & output caching

### Background Processing
- [ ] `IHostedService` / `BackgroundService`
- [ ] Use cases: scheduled cleanup jobs, queue processors

## 🧪 Hands-on Practice
- Restructure TaskFlow into `TaskFlow.Api`, `TaskFlow.Application`, `TaskFlow.Domain`, `TaskFlow.Infrastructure` projects
- Introduce AutoMapper for entity ↔ DTO mapping
- Add pagination + filtering to `GET /api/tasks` (`?page=1&pageSize=20&status=pending`)
- Build a `BackgroundService` that marks overdue tasks and logs a daily summary

## 📖 Resources
- Microsoft Learn: *Options pattern in ASP.NET Core*
- Microsoft Learn: *Background tasks with hosted services*
- Book: *Clean Architecture* by Robert C. Martin (concepts, language-agnostic)

## ❓ Self-Check Questions
- Why separate Domain from Infrastructure in Clean Architecture?
- What's the risk of over-using AutoMapper for complex business mappings?
- When would you use `BackgroundService` vs a separate worker/microservice?

## ➡️ Next
[`03-WebAPI-Intermediate.md`](./03-WebAPI-Intermediate.md)
