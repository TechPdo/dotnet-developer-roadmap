# 10 — Observability & Advanced Logging

## 🎯 Learning Objectives
Implement the three pillars of observability — logs, metrics, traces — so a production system's behavior is understandable without attaching a debugger.

## 📚 Topics & Subtopics

### The Three Pillars
- [ ] Logs — event records (what you already built in Intermediate)
- [ ] Metrics — numeric time-series data (request rate, error rate, latency, custom business metrics)
- [ ] Traces — following a single request across services/components (distributed tracing)

### OpenTelemetry in .NET
- [ ] OpenTelemetry as the vendor-neutral standard for logs/metrics/traces
- [ ] Instrumenting ASP.NET Core, `HttpClient`, and EF Core automatically via OTel instrumentation packages
- [ ] Exporting to a backend: Jaeger, Zipkin, Azure Monitor/Application Insights, Grafana + Prometheus + Tempo stack
- [ ] Custom spans/activities (`ActivitySource`) for business-relevant tracing
- [ ] Custom metrics (`Meter`, counters, histograms) for domain-specific KPIs (e.g., "tasks completed per minute")

### Dashboards & Alerting
- [ ] Building dashboards in Grafana (or Azure Monitor/App Insights)
- [ ] The RED method (Rate, Errors, Duration) and USE method (Utilization, Saturation, Errors) for dashboard design
- [ ] Setting meaningful alerts (avoiding alert fatigue) — SLIs/SLOs basics

### Health & Diagnostics in Production
- [ ] Health checks deep dive: dependency health checks (DB, Redis, external APIs), readiness vs liveness in Kubernetes
- [ ] Structured error tracking (Sentry / Application Insights exceptions)
- [ ] Feature flag-driven debugging (enabling verbose logging for specific users/tenants on demand)

## 🧪 Hands-on Practice
- Instrument TaskFlow with OpenTelemetry: traces across the Tasks API → Notifications service (from the Microservices file) → message broker
- Export traces to a local Jaeger instance (via Docker) and visualize a full request trace across both services
- Add custom business metrics (tasks created/completed per hour) exported to Prometheus, visualized in a Grafana dashboard
- Define 2–3 SLOs for TaskFlow (e.g., "99% of task-creation requests complete under 300ms") and set up an alert for violations

## 📖 Resources
- OpenTelemetry .NET documentation
- Microsoft Learn: *.NET observability with OpenTelemetry*
- Google SRE Book (free online) — chapters on SLIs/SLOs and monitoring
- Grafana + Prometheus official docs

## ❓ Self-Check Questions
- What's the difference between a log, a metric, and a trace, and why do you need all three?
- Why is the RED method a useful starting point for service dashboards?
- What causes alert fatigue, and how do SLO-based alerts help avoid it?

## ➡️ Next
[`11-DevOps-GitHub-Advanced.md`](./11-DevOps-GitHub-Advanced.md)
