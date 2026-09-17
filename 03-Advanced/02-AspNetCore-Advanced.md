# 02 — ASP.NET Core Advanced

## 🎯 Learning Objectives
Design and implement advanced architectural patterns used in large-scale, production ASP.NET Core systems.

## 📚 Topics & Subtopics

### Advanced Middleware & Pipeline
- [ ] Writing middleware with dependencies via constructor vs `InvokeAsync` injection
- [ ] Branching the pipeline (`app.Map`, `app.MapWhen`, `app.UseWhen`)
- [ ] Endpoint routing internals, `IEndpointRouteBuilder`
- [ ] Custom `IEndpointFilter` for Minimal APIs

### Resilience & Fault Tolerance
- [ ] **Polly** deep dive: retry, circuit breaker, timeout, bulkhead isolation policies
- [ ] Combining policies (wrap), `Microsoft.Extensions.Http.Resilience` (the newer standard resilience handler)
- [ ] Designing for graceful degradation

### Caching Strategies
- [ ] In-memory caching (`IMemoryCache`) — eviction policies, size limits
- [ ] Distributed caching (`IDistributedCache` with Redis)
- [ ] Output caching vs response caching vs application-level caching — when to use which
- [ ] Cache invalidation strategies (the "hard problem")

### Real-Time Communication
- [ ] SignalR fundamentals — hubs, groups, connections
- [ ] Use cases: real-time task updates/notifications in TaskFlow
- [ ] Scaling SignalR across multiple instances (Redis backplane)

### gRPC (Awareness/Practice)
- [ ] When gRPC makes sense over REST (internal service-to-service calls)
- [ ] Protobuf contracts, streaming RPCs

### Multi-Tenancy Patterns (Awareness)
- [ ] Single database with tenant discriminator vs database-per-tenant vs schema-per-tenant
- [ ] Implementing tenant resolution middleware

## 🧪 Hands-on Practice
- Add Redis-backed distributed caching for frequently-read task lists in TaskFlow
- Wrap the external API call (from Intermediate) with Polly retry + circuit breaker policies
- Add SignalR so connected clients see real-time task updates without refreshing
- (Stretch) Add a small internal gRPC service (e.g., a notification service) that the main API calls

## 📖 Resources
- Microsoft Learn: *Build resilient HTTP apps* (Polly / resilience handler)
- Microsoft Learn: *SignalR overview*
- Microsoft Learn: *Caching in ASP.NET Core*
- Microsoft Learn: *gRPC in .NET*

## ❓ Self-Check Questions
- What's the difference between a retry policy and a circuit breaker, and why combine them?
- Why does scaling SignalR across multiple server instances require a backplane?
- When would gRPC be a better fit than REST for a given communication path?

## ➡️ Next
[`03-WebAPI-Advanced.md`](./03-WebAPI-Advanced.md)
