# 05 — CQRS & MediatR

## 🎯 Learning Objectives
Understand CQRS as an architectural pattern and implement it in ASP.NET Core using MediatR, including cross-cutting pipeline behaviors.

## 📚 Topics & Subtopics

### CQRS Fundamentals
- [ ] Command Query Responsibility Segregation — separating reads (Queries) from writes (Commands)
- [ ] Why CQRS: independent scaling/optimization of read vs write models, simpler mental model per operation
- [ ] CQRS without a mediator (plain method calls) vs CQRS with a mediator pattern — when the extra layer is worth it
- [ ] Common misconception: CQRS does **not** require separate databases (that's CQRS + Event Sourcing, a bigger commitment — covered below)

### MediatR Deep Dive
- [ ] `IRequest<TResponse>` / `IRequestHandler<TRequest, TResponse>` — commands and queries as requests
- [ ] Registering MediatR, handler discovery/scanning
- [ ] Notifications (`INotification` / `INotificationHandler`) for pub/sub-style domain events within a process
- [ ] Pipeline Behaviors (`IPipelineBehavior<TRequest, TResponse>`) — the real power of MediatR:
  - [ ] Validation behavior (integrating FluentValidation into the pipeline)
  - [ ] Logging behavior (log every command/query with timing)
  - [ ] Transaction behavior (wrap commands in a DB transaction automatically)
  - [ ] Caching behavior for queries
  - [ ] Authorization behavior (check permissions before a handler runs)

### Structuring a CQRS + MediatR Application
- [ ] Feature folders (vertical slices) vs traditional layered folders — organizing by feature (`Features/Tasks/CreateTask/`) instead of by technical layer
- [ ] Vertical Slice Architecture — how it pairs naturally with CQRS/MediatR
- [ ] Separate read models/DTOs optimized per query vs reusing write-side entities
- [ ] Command validation vs domain validation — where each belongs

### Domain Events
- [ ] Raising domain events from entities/aggregates
- [ ] Dispatching domain events after `SaveChanges` succeeds (avoiding side effects on failed transactions)
- [ ] Domain events vs integration events (in-process vs cross-service — ties into Microservices file)

### CQRS + Event Sourcing (Awareness Only)
- [ ] What Event Sourcing is — storing state as a sequence of events instead of current state
- [ ] Why it's a much bigger architectural commitment; when it's actually justified
- [ ] Read models/projections rebuilt from the event stream

## 🧪 Hands-on Practice
- Refactor TaskFlow's Application layer to **Vertical Slice Architecture**: `Features/Tasks/CreateTask/{Command,Handler,Validator,Endpoint}.cs`, etc.
- Introduce MediatR for all commands/queries; remove direct service-layer calls from controllers (controllers just send a request to `IMediator`)
- Build pipeline behaviors: `ValidationBehavior`, `LoggingBehavior`, and a `TransactionBehavior` that wraps commands in an EF Core transaction
- Add a domain event `TaskCompletedEvent` raised when a task is marked done, handled by an `INotificationHandler` that logs an achievement/sends a notification
- Write a short ADR (Architecture Decision Record) in `/docs` explaining why (or why not) you'd choose CQRS+MediatR for a project this size

## 📖 Resources
- MediatR GitHub repo & wiki (Jimmy Bogard)
- Jimmy Bogard's blog — *Vertical Slice Architecture*
- Martin Fowler — *CQRS* (martinfowler.com)
- Microsoft Learn: *CQRS pattern* (Azure Architecture Center)

## ❓ Self-Check Questions
- What's the actual problem CQRS solves, separate from "just splitting classes"?
- Why put validation and logging into MediatR pipeline behaviors instead of inside each handler?
- What's the difference between a domain event and an integration event?
- When would full Event Sourcing be overkill for a project?

## ➡️ Next
[`06-Microservices-Architecture.md`](./06-Microservices-Architecture.md)
