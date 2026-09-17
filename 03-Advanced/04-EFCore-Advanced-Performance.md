# 04 — EF Core Advanced: Complex Queries & Performance

## 🎯 Learning Objectives
Write and optimize complex EF Core queries, diagnose performance problems, and know when to step outside the ORM.

## 📚 Topics & Subtopics

### Complex Query Patterns
- [ ] Complex joins, projections into DTOs directly (`Select` projection to avoid over-fetching)
- [ ] Grouping with aggregation translated to SQL (`GroupBy` + `Select` with `Count`/`Sum`)
- [ ] Subqueries and correlated subqueries via LINQ
- [ ] Window functions (ranking, running totals) — raw SQL or EF Core 8+ translation support
- [ ] Recursive/hierarchical data (self-referencing entities, common table expressions via raw SQL)
- [ ] `FromSqlRaw` / `FromSqlInterpolated` for complex queries EF can't translate, and `ExecuteUpdate`/`ExecuteDelete` (bulk operations without loading entities)
- [ ] Compiled queries (`EF.CompileQuery`) for hot-path query reuse

### Performance Diagnosis
- [ ] The N+1 query problem — how it happens, how to spot it, `Include`/`ThenInclude`/split queries to fix it
- [ ] Split queries vs single query with multiple includes (`AsSplitQuery`)
- [ ] Reading generated SQL (`ToQueryString()`, logging SQL via `LogTo`)
- [ ] `AsNoTracking()` / `AsNoTrackingWithIdentityResolution()` for read-heavy paths
- [ ] Indexing strategy — how EF Core migrations create indexes, when to add composite/covering indexes manually
- [ ] Query plan analysis basics (`EXPLAIN ANALYZE` / execution plans) — cross-referencing with EF-generated SQL
- [ ] Connection pooling & `DbContext` pooling (`AddDbContextPool`)
- [ ] Batch operations & bulk insert/update libraries (EFCore.BulkExtensions) when `SaveChanges` isn't enough

### Scaling Data Access
- [ ] Read replicas — routing read-only queries to a replica
- [ ] Caching query results appropriately (tie back to Advanced caching topic)
- [ ] Pagination at scale: offset pagination vs keyset/cursor pagination
- [ ] Sharding awareness (when a single database no longer scales)

## 🧪 Hands-on Practice
- Find and fix a deliberately-introduced N+1 problem in TaskFlow's "tasks with categories and comments" endpoint; measure query count before/after with `LogTo`
- Rewrite a heavy list endpoint to use keyset pagination instead of offset pagination and measure the performance difference at scale (seed 100k+ rows)
- Write a raw SQL query using a window function for "task rank by priority per category" and map results to a DTO
- Enable `DbContext` pooling and benchmark the difference under load

## 📖 Resources
- Microsoft Learn: *Performance — EF Core*
- Microsoft Learn: *Advanced query capabilities — EF Core*
- Use the Index, Luke! (use-the-index-luke.com) — database indexing deep dive (DB-agnostic)
- EFCore.BulkExtensions GitHub repo

## ❓ Self-Check Questions
- Why does `AsSplitQuery` sometimes outperform a single query with many `Include`s, and sometimes not?
- Why is keyset pagination preferred over offset pagination for very large datasets?
- When is it appropriate to drop to raw SQL instead of fighting LINQ translation?

## ➡️ Next
[`05-CQRS-MediatR.md`](./05-CQRS-MediatR.md)
