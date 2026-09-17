# 08 — Logging & Exception Handling (Intermediate)

## 🎯 Learning Objectives
Move from basic console logging to structured, centralized logging suitable for real deployments, and design a robust global error-handling strategy.

## 📚 Topics & Subtopics

### Structured & Centralized Logging
- [ ] Serilog — sinks, enrichers, structured logging in depth
- [ ] Writing logs to file, database, or centralized platforms (Seq, Elasticsearch, Application Insights)
- [ ] Correlation IDs — tracking a single request across logs
- [ ] Log scopes (`BeginScope`) for contextual data (e.g., UserId across a request)
- [ ] Configuring log levels dynamically per environment

### Exception Handling Strategy
- [ ] Designing an exception hierarchy for your domain (`NotFoundException`, `ValidationException`, `ConflictException`, `ForbiddenException`)
- [ ] Centralizing exception → HTTP status code mapping in one place
- [ ] `IExceptionHandler` (new in .NET 8+) vs `UseExceptionHandler` middleware vs exception filters — choosing the right layer
- [ ] Returning `ProblemDetails` with correlation IDs and trace IDs for client-side debugging
- [ ] Avoiding leaking sensitive info (stack traces, connection strings) in production error responses

### Result Pattern (Alternative to Exceptions for Control Flow)
- [ ] Exceptions for exceptional cases vs Result/Either pattern for expected failures
- [ ] Implementing a simple `Result<T>` type
- [ ] Trade-offs: readability vs performance vs consistency with the rest of .NET ecosystem

## 🧪 Hands-on Practice
- Swap TaskFlow's default logging provider for **Serilog**, writing structured JSON logs to a file and console
- Add a correlation ID middleware that generates/propagates an ID and includes it in every log line and error response
- Implement `IExceptionHandler` to centrally map your domain exceptions to correct HTTP responses
- Refactor one service method to use a `Result<T>` pattern instead of throwing for expected validation failures, and discuss the trade-off in a comment/README

## 📖 Resources
- Serilog official docs + Serilog.AspNetCore
- Microsoft Learn: *IExceptionHandler interface*
- Vladimir Khorikov — discussions on Result pattern vs exceptions (blog/book: *Unit Testing Principles, Practices, and Patterns*)

## ❓ Self-Check Questions
- What's a correlation ID and why is it critical in production debugging?
- When is the Result pattern preferable to throwing exceptions?
- What sensitive information must never appear in a production error response?

## ➡️ Next
[`09-Git-GitHub-Intermediate.md`](./09-Git-GitHub-Intermediate.md)
