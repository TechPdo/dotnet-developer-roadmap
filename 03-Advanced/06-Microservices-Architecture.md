# 06 — Microservices Architecture

## 🎯 Learning Objectives
Understand when and how to decompose a monolith into services, and the operational complexity that comes with it.

## 📚 Topics & Subtopics

### Foundations
- [ ] Monolith vs modular monolith vs microservices — decision framework (start with a modular monolith, most teams don't need microservices day one)
- [ ] Bounded Contexts (Domain-Driven Design) as the basis for service boundaries
- [ ] Database-per-service principle, why shared databases between services cause coupling

### Inter-Service Communication
- [ ] Synchronous: REST/gRPC calls between services, and their coupling risk (cascading failures)
- [ ] Asynchronous: message brokers (RabbitMQ, Azure Service Bus, Kafka) for event-driven communication
- [ ] Choosing sync vs async per interaction
- [ ] Message contracts/schemas, versioning events over time

### Reliability Patterns
- [ ] Saga pattern (orchestration vs choreography) for distributed transactions
- [ ] Outbox pattern (recap) as the reliable event-publishing mechanism per service
- [ ] Circuit breaker/bulkhead at the service-mesh or client level (recap from Polly)
- [ ] Idempotent consumers for message processing

### Service Discovery & Configuration
- [ ] Service discovery basics (DNS-based vs registry-based)
- [ ] Centralized configuration (e.g., Azure App Configuration / Consul) awareness

### Observability Across Services
- [ ] Distributed tracing — propagating a trace/correlation ID across service boundaries (ties into Observability file)
- [ ] Health checks (`Microsoft.Extensions.Diagnostics.HealthChecks`) — liveness vs readiness probes

### Containers & Orchestration
- [ ] Dockerizing a .NET service — multi-stage Dockerfiles
- [ ] Docker Compose for local multi-service development
- [ ] Kubernetes fundamentals (Pods, Deployments, Services, ConfigMaps/Secrets) — awareness level
- [ ] .NET Aspire — Microsoft's opinionated stack for building/orchestrating distributed .NET apps locally

## 🧪 Hands-on Practice
- Split TaskFlow into at least 2 services: `TaskFlow.Tasks.Api` and `TaskFlow.Notifications.Api`, communicating via a message broker (RabbitMQ) when a task is completed
- Implement the Outbox pattern in the Tasks service to reliably publish `TaskCompleted` events
- Add health check endpoints (`/health/live`, `/health/ready`) to each service
- Containerize both services + RabbitMQ + DB with Docker Compose, and get the whole system running with one command
- (Stretch) Explore .NET Aspire to orchestrate the same setup and compare the developer experience

## 📖 Resources
- Sam Newman — *Building Microservices* (book)
- Chris Richardson — microservices.io (pattern catalog)
- Microsoft Learn: *.NET microservices architecture e-book (eShopOnContainers)*
- Microsoft Learn: *.NET Aspire overview*

## ❓ Self-Check Questions
- Why is "database per service" so central to microservices, and what breaks if you skip it?
- When is a modular monolith the *better* choice over microservices?
- What's the difference between orchestration and choreography in the Saga pattern?

## ➡️ Next
[`07-Security-Advanced.md`](./07-Security-Advanced.md)
