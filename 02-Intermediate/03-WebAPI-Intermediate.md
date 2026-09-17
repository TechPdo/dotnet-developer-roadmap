# 03 — Web API Intermediate

## 🎯 Learning Objectives
Build production-quality APIs with proper testing, validation, and integration patterns.

## 📚 Topics & Subtopics

### Advanced Validation
- [ ] FluentValidation — rules, custom validators, async validation
- [ ] Validation pipelines (integrating with filters or MediatR pipeline behaviors — teaser for Advanced)

### HTTP Client Usage
- [ ] `IHttpClientFactory` — why not `new HttpClient()` everywhere
- [ ] Typed clients, named clients
- [ ] Retry/backoff basics with Polly (resilience intro — deep dive in Advanced)
- [ ] Calling third-party/external APIs safely (timeouts, error handling)

### 🧪 Unit Testing — Deep Dive
- [ ] What a unit test is: testing one unit of logic (a method/class) in isolation from its dependencies
- [ ] Test framework choice: **xUnit** (most common in modern .NET, used throughout this course) vs **NUnit** vs **MSTest** — syntax differences, all are valid choices
- [ ] The **Arrange-Act-Assert (AAA)** pattern — structuring every test the same way for readability
- [ ] Naming conventions for tests (e.g., `MethodName_Scenario_ExpectedBehavior`)
- [ ] `[Fact]` vs `[Theory]` + `[InlineData]`/`[MemberData]` in xUnit — data-driven tests
- [ ] Assertions: built-in `Assert` vs a fluent assertion library (**FluentAssertions**) for more readable failures
- [ ] Test doubles explained: **dummy, stub, fake, spy, mock** — the differences, and where each fits
- [ ] Mocking dependencies with **Moq** or **NSubstitute** — isolating the class under test from its interfaces
- [ ] What to unit test: business/domain logic, validators, mappers, pure functions — **not** EF Core itself or third-party libraries
- [ ] Code coverage: what it tells you and what it doesn't (100% coverage ≠ bug-free) — tools like Coverlet + ReportGenerator
- [ ] Test-Driven Development (TDD) — red/green/refactor cycle, and when it's worth adopting
- [ ] Keeping tests fast, isolated, and deterministic (no shared state, no reliance on execution order, no real network/DB calls in a *unit* test)

### Integration & API Testing
- [ ] Integration testing with `WebApplicationFactory<T>` — spinning up the app in-memory for realistic HTTP-level tests
- [ ] Testing with a real-ish database: SQLite in-memory vs **Testcontainers** (spins up a real, disposable SQL Server/Postgres in Docker per test run — closer to production behavior)
- [ ] API/end-to-end style testing — asserting on actual HTTP status codes, headers, and response bodies
- [ ] Test data builders / object mothers pattern for constructing realistic test data without duplication
- [ ] Test automation — running the full suite automatically in CI (ties into the Git/GitHub file), failing the build on any red test

### API Documentation & Contracts
- [ ] OpenAPI advanced: grouping endpoints, tags, request/response examples
- [ ] Generating client SDKs from OpenAPI (NSwag / Kiota)
- [ ] Contract-first vs code-first API design

### File Uploads & Streaming
- [ ] Handling file uploads (`IFormFile`), size limits
- [ ] Streaming large responses

## 🧪 Hands-on Practice
- Add FluentValidation to all TaskFlow DTOs, replacing data annotations
- Wrap an external API call (e.g., a public weather or quotes API) using `IHttpClientFactory` with a typed client
- **Unit test** your task service's business logic in isolation: mock the repository with Moq/NSubstitute, use `[Theory]`/`[InlineData]` to test edge cases (empty title, past due date, etc.), and assert with FluentAssertions
- **Integration test** the Tasks endpoints using `WebApplicationFactory` + SQLite in-memory DB (or Testcontainers for a closer-to-prod setup)
- Add a code coverage report (Coverlet) to see which parts of TaskFlow are untested
- Add file attachment upload support to tasks

## 📖 Resources
- Microsoft Learn: *Unit testing C# in .NET using dotnet test and xUnit* — https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-csharp-with-xunit
- Microsoft Learn: *Integration tests in ASP.NET Core* — https://learn.microsoft.com/en-us/aspnet/core/test/integration-tests
- Microsoft Learn: *IHttpClientFactory* — https://learn.microsoft.com/en-us/aspnet/core/fundamentals/http-requests
- xUnit official docs — https://xunit.net/
- Moq GitHub — https://github.com/devlooped/moq
- FluentAssertions official docs — https://fluentassertions.com/
- Testcontainers for .NET — https://dotnet.testcontainers.org/
- FluentValidation official docs — https://docs.fluentvalidation.net/
- YouTube: *Nick Chapsas — Unit Testing & xUnit deep dives* — https://www.youtube.com/@nickchapsas
- YouTube: *Milan Jovanović — Integration testing ASP.NET Core APIs* — https://www.youtube.com/@MilanJovanovicTech

## ❓ Self-Check Questions
- Why is `IHttpClientFactory` recommended over manually creating `HttpClient` instances?
- What's the difference between a unit test and an integration test for a Web API, and what should live in each?
- What's the difference between a stub and a mock?
- Why doesn't 100% code coverage guarantee your code is correct?
- Why keep validation logic out of controllers?

## ➡️ Next
[`04-EFCore-Intermediate.md`](./04-EFCore-Intermediate.md)
