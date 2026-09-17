# 05 — Dependency Injection (Intermediate → Advanced Intro)

## 🎯 Learning Objectives
Deeply understand DI in ASP.NET Core: lifetimes, registration patterns, and common pitfalls.

## 📚 Topics & Subtopics

### DI Fundamentals
- [ ] Inversion of Control vs Dependency Injection — the distinction
- [ ] The built-in `IServiceCollection` / `IServiceProvider`
- [ ] Constructor injection (preferred) vs property/method injection
- [ ] Registering services: `AddTransient`, `AddScoped`, `AddSingleton` — real differences and when to use each

### Lifetimes Deep Dive
- [ ] Captive dependency problem (singleton capturing a scoped service) — why it's dangerous
- [ ] Scoped services in background services / non-HTTP contexts (`IServiceScopeFactory`)
- [ ] Disposal and `IDisposable`/`IAsyncDisposable` services

### Registration Patterns
- [ ] Interface segregation for testability
- [ ] Registering multiple implementations of the same interface (`IEnumerable<IService>`)
- [ ] Factory pattern registration (`Func<T>` factories, `AddTransient<Func<T>>`)
- [ ] Decorator pattern with DI (e.g., Scrutor library)
- [ ] Open generic registration (`AddScoped(typeof(IRepository<>), typeof(Repository<>))`)
- [ ] Named/keyed services (`AddKeyedScoped` in .NET 8+)

### Third-Party DI Containers (Awareness)
- [ ] Autofac, Lamar — when the built-in container isn't enough
- [ ] Module-based registration for large apps

### Testability
- [ ] Designing services for easy mocking
- [ ] Avoiding service locator anti-pattern

## 🧪 Hands-on Practice
- Audit TaskFlow's service registrations — justify each lifetime choice in a comment
- Deliberately create a captive dependency bug (singleton depending on scoped `DbContext`), observe the failure, then fix it
- Implement a decorator around your `ITaskService` that adds caching, using Scrutor or manual factory registration
- Register an open generic repository for all your entity types in one line

## 📖 Resources
- Microsoft Learn: *Dependency injection in ASP.NET Core*
- Mark Seemann — *Dependency Injection Principles, Practices, and Patterns* (book)
- Scrutor GitHub repo (decorator/assembly-scanning registration)

## ❓ Self-Check Questions
- Why is injecting a scoped service into a singleton dangerous, and how does ASP.NET Core detect/prevent it?
- What's the difference between the Service Locator anti-pattern and proper DI?
- When would you reach for a third-party container like Autofac?

## ➡️ Next
[`06-Frontend-React-Angular-TS.md`](./06-Frontend-React-Angular-TS.md)
