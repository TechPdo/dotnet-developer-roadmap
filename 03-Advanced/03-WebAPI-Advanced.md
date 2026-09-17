# 03 — Web API Advanced

## 🎯 Learning Objectives
Design APIs and system boundaries that hold up under real-world scale, evolution, and integration demands.

## 📚 Topics & Subtopics

### API Gateway & BFF Patterns
- [ ] API Gateway concept (Ocelot / YARP as .NET options)
- [ ] Backend-for-Frontend (BFF) pattern — tailoring an API layer per client type
- [ ] Aggregating multiple downstream services behind a gateway

### GraphQL (Awareness/Alternative to REST)
- [ ] GraphQL fundamentals: schema, queries, mutations, resolvers
- [ ] HotChocolate (the main .NET GraphQL library) — basic setup
- [ ] REST vs GraphQL vs gRPC — decision framework

### Advanced Testing & Quality
- [ ] Contract testing (Pact) between API producer/consumer
- [ ] Mutation testing awareness (Stryker.NET)
- [ ] Load testing APIs (k6, JMeter, or `bombardier`) and interpreting results
- [ ] Consumer-driven contract awareness for microservices

### Idempotency & Reliability
- [ ] Idempotency keys for POST requests (safe retries)
- [ ] Outbox pattern for reliable event publishing alongside DB writes
- [ ] Handling duplicate message/webhook delivery

### API Lifecycle Management
- [ ] Deprecating endpoints gracefully (sunset headers, versioned docs)
- [ ] Feature flags (e.g., using Microsoft.FeatureManagement) for gradual rollout

## 🧪 Hands-on Practice
- Add idempotency key support to TaskFlow's task-creation endpoint to safely handle client retries
- Implement the Outbox pattern for a "TaskCreated" event that must reliably trigger a notification
- Write a basic load test against the Tasks API using k6 and analyze p95 latency under load
- (Stretch) Add a small GraphQL endpoint alongside REST for flexible task querying

## 📖 Resources
- Microsoft Learn: *YARP (Yet Another Reverse Proxy)*
- HotChocolate (GraphQL) official docs
- k6 official docs — load testing
- Microservices.io — *Outbox pattern*, *Idempotent consumer*

## ❓ Self-Check Questions
- Why is the Outbox pattern needed instead of just publishing an event right after `SaveChanges()`?
- What problem do idempotency keys solve for POST requests specifically?
- When would a BFF layer be worth the added complexity?

## ➡️ Next
[`04-EFCore-Advanced-Performance.md`](./04-EFCore-Advanced-Performance.md)
