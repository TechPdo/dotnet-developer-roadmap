# 🎤 .NET Interview Prep — Question Bank by Level

Use these to self-test after finishing each level. Try answering out loud or in writing before checking references back in the relevant syllabus file.

## Beginner-Level Questions
- What's the difference between a value type and a reference type in C#?
- Explain the ASP.NET Core middleware pipeline in your own words.
- What's the difference between `IEnumerable<T>` and `List<T>`?
- What is dependency injection, at a basic level, and why use it?
- What does a migration do in EF Core?
- What HTTP status code would you return for a validation failure? For a missing resource?
- What's the purpose of `.gitignore`?

## Intermediate-Level Questions
- Explain the three DI lifetimes and give a real example of when each is appropriate.
- What is the N+1 query problem and how do you detect/fix it in EF Core?
- Walk through how JWT authentication works end-to-end, including refresh tokens.
- What's the difference between role-based and policy-based authorization?
- Why would you use `IHttpClientFactory` instead of `new HttpClient()`?
- Explain deferred execution in LINQ with an example that could surprise a developer.
- What's the difference between unit tests and integration tests, and when do you write each?
- How would you structure a solution to follow Clean Architecture?

## Advanced-Level Questions
- Explain CQRS and when it's (and isn't) worth adopting.
- What problem does the Outbox pattern solve, and what happens without it?
- Compare optimistic vs pessimistic concurrency control with a concrete EF Core example.
- Explain the Saga pattern (orchestration vs choreography) with a real scenario.
- How does `async`/`await` avoid blocking a thread — explain the state machine at a high level.
- What's the difference between a circuit breaker and a retry policy, and why combine them?
- How would you design a multi-tenant authorization system that scales beyond simple roles?
- Explain the three pillars of observability and how they complement each other.
- What is Model Context Protocol (MCP) and why does it matter for building AI agents?
- Describe a time you'd choose a modular monolith over microservices, and why.

## System Design Style Questions (Advanced)
- Design a task management system's backend: what services, database boundaries, and communication patterns would you choose, and why?
- How would you scale the read path of a high-traffic API that's mostly read-heavy?
- How would you roll out a breaking database schema change with zero downtime?
- How would you add real-time notifications to an existing REST API-based system?
- How would you secure an internal AI agent that can take actions on behalf of users?

## Behavioral / Engineering Practice Questions
- Describe a time you had to debug a production issue under pressure. What was your process?
- How do you approach reviewing a large, AI-generated pull request?
- How do you decide when a piece of code needs a design pattern vs when it's over-engineering?
- Tell me about a time you disagreed with an architectural decision — how did you handle it?
