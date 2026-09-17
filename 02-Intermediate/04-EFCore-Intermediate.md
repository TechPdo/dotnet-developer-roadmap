# 04 — EF Core Intermediate

## 🎯 Learning Objectives
Model complex domains correctly and use EF Core patterns that scale to real applications.

## 📚 Topics & Subtopics

### Advanced Modeling
- [ ] Value objects & owned types (`OwnsOne`, `OwnsMany`)
- [ ] Table-per-hierarchy (TPH), Table-per-type (TPT), Table-per-concrete-type (TPC) inheritance mapping
- [ ] Global query filters (e.g., soft-delete filtering)
- [ ] Shadow properties, backing fields
- [ ] Concurrency tokens (`[Timestamp]`, `IsRowVersion`) and optimistic concurrency handling

### Repository & Unit of Work Patterns
- [ ] Repository pattern pros/cons with EF Core (EF Core `DbContext` is already a UoW/repository — when it's worth adding a layer)
- [ ] Implementing a generic repository + specification pattern
- [ ] Unit of Work pattern with `SaveChanges` coordination across repositories

### Transactions
- [ ] Implicit transactions per `SaveChanges`
- [ ] Explicit transactions (`BeginTransaction`, `Commit`, `Rollback`)
- [ ] `TransactionScope` awareness for cross-DbContext scenarios

### Migrations in Depth
- [ ] Managing migrations across teams/branches
- [ ] Idempotent SQL scripts for deployment (`dotnet ef migrations script --idempotent`)
- [ ] Applying migrations at startup vs via CI/CD pipeline (trade-offs)

### Testing with EF Core
- [ ] In-memory provider vs SQLite in-memory vs Testcontainers — pros/cons of each for realistic tests
- [ ] Mocking `DbContext` (and why it's usually a bad idea)

## 🧪 Hands-on Practice
- Add a soft-delete pattern to TaskFlow entities using a global query filter
- Implement optimistic concurrency on `TaskItem` with a `RowVersion` column; handle `DbUpdateConcurrencyException`
- Build a generic repository + Unit of Work layer and refactor services to use it
- Set up a CI-friendly migration script generation step

## 📖 Resources
- Microsoft Learn: *EF Core — Modeling*
- Microsoft Learn: *Concurrency conflicts (EF Core)*
- Microsoft Learn: *Managing database schemas*

## ❓ Self-Check Questions
- What's the difference between optimistic and pessimistic concurrency control?
- When is the Repository pattern redundant on top of EF Core, and when is it genuinely useful?
- Why might applying migrations automatically at app startup be risky in production?

## ➡️ Next
[`05-Dependency-Injection.md`](./05-Dependency-Injection.md)
