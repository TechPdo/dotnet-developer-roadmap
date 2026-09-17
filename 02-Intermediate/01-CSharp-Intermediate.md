# 01 — C# Intermediate

## 🎯 Learning Objectives
Write idiomatic, maintainable, modern C# and understand the language features that power well-architected .NET applications.

## 📚 Topics & Subtopics

### Generics
- [ ] Generic classes, methods, interfaces
- [ ] Constraints (`where T : class, new()`, etc.)
- [ ] Covariance/contravariance (`out`/`in`) in depth

### Delegates, Events, Functional Style
- [ ] `Action`, `Func`, `Predicate`
- [ ] Custom delegates, multicast delegates
- [ ] Events and the observer pattern (`event` keyword, `EventHandler`)
- [ ] Lambda expressions and closures — capturing variables correctly

### LINQ Deep Dive
- [ ] Deferred execution vs immediate execution
- [ ] `IQueryable<T>` vs `IEnumerable<T>` — where the query actually runs
- [ ] Grouping (`GroupBy`), joining (`Join`, `GroupJoin`), aggregation (`Sum`, `Average`, `Aggregate`)
- [ ] Writing efficient LINQ — avoiding N+1 and multiple enumeration pitfalls

### Records, Pattern Matching & Modern Syntax
- [ ] `record` vs `record struct`, value equality semantics
- [ ] Advanced pattern matching: property patterns, positional patterns, relational patterns
- [ ] `switch` expressions with pattern combinations
- [ ] `init` accessors, `with` expressions

### Async/Await Deep Dive
- [ ] Task-based Asynchronous Pattern (TAP)
- [ ] `Task` vs `Task<T>` vs `ValueTask<T>`
- [ ] `ConfigureAwait(false)` — when and why
- [ ] Avoiding deadlocks (blocking on async code with `.Result`/`.Wait()`)
- [ ] `async` streams: `IAsyncEnumerable<T>` and `await foreach`
- [ ] Cancellation with `CancellationToken`

### Memory & Performance Awareness
- [ ] Stack vs heap allocation basics
- [ ] `Span<T>` and `Memory<T>` — intro awareness
- [ ] Garbage collection basics (Gen 0/1/2)
- [ ] `IDisposable` and the `using`/`await using` pattern in depth

## 🧪 Hands-on Practice
- Refactor TaskFlow's service layer to use `IAsyncEnumerable<T>` for streaming large task lists
- Implement a generic repository interface `IRepository<T>` with constraints
- Convert your task/category models to `record` types where immutability makes sense
- Add `CancellationToken` support through your service and controller methods

## 📖 Resources
- Microsoft Learn: *Asynchronous programming in C#*
- Book: *C# 12 in a Nutshell* (LINQ & async chapters)
- Microsoft Learn: *Pattern matching overview*

## ❓ Self-Check Questions
- Why is blocking on `Task.Result` in ASP.NET Core dangerous?
- What's the difference between `IEnumerable<T>` and `IQueryable<T>` when calling `.Where()`?
- When would you choose `record` over `class`?

## ➡️ Next
[`02-AspNetCore-Intermediate.md`](./02-AspNetCore-Intermediate.md)
