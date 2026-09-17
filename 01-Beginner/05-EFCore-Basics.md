# 05 — SQL Fundamentals & Entity Framework Core Basics

## 🎯 Learning Objectives
Understand relational databases and SQL well enough to design and query a schema directly, then layer EF Core on top as an ORM, be able to model entities, run migrations, and perform basic CRUD.

> 💡 Added per the Microsoft .NET Developer Roadmap: databases are a skill in their own right, separate from the ORM. Knowing raw SQL makes you far better at EF Core — you'll immediately recognize *what* EF Core is generating and *why* a query is slow.

## 📚 Topics & Subtopics

### 🗄️ Relational Database & SQL Fundamentals (do this before EF Core)
- [ ] Relational model basics: tables, rows, columns, primary keys, foreign keys
- [ ] `SELECT`, `WHERE`, `ORDER BY`, `DISTINCT`
- [ ] `JOIN` types: `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, `FULL OUTER JOIN` — and when each returns what
- [ ] `GROUP BY` + aggregates (`COUNT`, `SUM`, `AVG`, `MIN`, `MAX`) and `HAVING` vs `WHERE`
- [ ] Subqueries (correlated vs non-correlated)
- [ ] Common Table Expressions (`WITH ... AS`) for readable, composable queries
- [ ] Window functions (`ROW_NUMBER()`, `RANK()`, `OVER (PARTITION BY ...)`) — intro
- [ ] Indexes — what they are, clustered vs non-clustered, when an index helps vs hurts write performance
- [ ] Transactions — `BEGIN TRAN`/`COMMIT`/`ROLLBACK`, ACID properties in plain terms
- [ ] Database design & normalization (1NF/2NF/3NF) — and when denormalizing is a deliberate trade-off
- [ ] Query optimization basics — reading an execution plan, spotting a missing index or a table scan

### ORM Concepts
- [ ] What an ORM is and the problems it solves
- [ ] EF Core vs Dapper vs ADO.NET — trade-offs (awareness)
- [ ] `DbContext` and `DbSet<T>`
- [ ] Code-First vs Database-First approach

### Modeling
- [ ] Entity classes & conventions (primary keys, naming conventions)
- [ ] Data Annotations vs Fluent API (`OnModelCreating`)
- [ ] Relationships: one-to-many, many-to-many, one-to-one
- [ ] Navigation properties, foreign keys

### Migrations
- [ ] `dotnet ef migrations add`, `dotnet ef database update`
- [ ] Understanding the migration files (`Up`/`Down`)
- [ ] Seeding data (`HasData`, or seed methods)

### CRUD Operations
- [ ] Querying with LINQ (`Where`, `FirstOrDefault`, `Include` for related data)
- [ ] Adding, updating, removing entities; `SaveChanges()`
- [ ] Tracking vs no-tracking queries (`AsNoTracking()`) — intro
- [ ] Connection strings & providers (SQL Server, PostgreSQL, SQLite)

### Basic Async Patterns
- [ ] `async`/`await` fundamentals
- [ ] Why async matters for I/O-bound DB calls
- [ ] `ToListAsync`, `FirstOrDefaultAsync`, `SaveChangesAsync`

## 🧪 Hands-on Practice
- Design a small normalized schema by hand (Tasks, Categories, Users) and write the raw `CREATE TABLE` statements with proper keys and indexes
- Write 8–10 practice SQL queries against a sample database (joins, group by, a subquery, a CTE) — [SQLBolt](https://sqlbolt.com/) or [Mode SQL Tutorial](https://mode.com/sql-tutorial/) are good free practice grounds
- Add EF Core to TaskFlow with SQL Server (or SQLite for simplicity)
- Model `TaskItem` and a related `Category` entity (one-to-many)
- Create and apply your first migration, then open the database and compare the generated schema to what you designed by hand
- Replace the in-memory list in your API with real EF Core-backed CRUD, fully async

## 📖 Resources
- Microsoft Learn: *Entity Framework Core documentation hub* — https://learn.microsoft.com/en-us/ef/core/
- Microsoft Learn: *Getting started with EF Core* — https://learn.microsoft.com/en-us/ef/core/get-started/overview/first-app
- Microsoft Learn: *SQL Server documentation* — https://learn.microsoft.com/en-us/sql/sql-server/
- Microsoft Learn Training: *Write your first Transact-SQL statements* — https://learn.microsoft.com/en-us/training/modules/write-first-transact-sql-statements/
- SQLBolt — free interactive SQL exercises — https://sqlbolt.com/
- Use The Index, Luke! — free, DB-agnostic guide to SQL indexing — https://use-the-index-luke.com/
- YouTube: *Programming with Mosh — SQL Tutorial for Beginners* — https://www.youtube.com/@programmingwithmosh
- YouTube: *freeCodeCamp.org — SQL/Databases full courses* — https://www.youtube.com/@freecodecamp

## ❓ Self-Check Questions
- What's the difference between an `INNER JOIN` and a `LEFT JOIN`, with a concrete example?
- Why can adding an index speed up reads but slow down writes?
- What does `AsNoTracking()` do and why would you use it?
- What's the purpose of a migration, and how do you roll one back?
- Why should DB calls in a web API be async?

## ➡️ Next
[`06-Frontend-Basics.md`](./06-Frontend-Basics.md)
