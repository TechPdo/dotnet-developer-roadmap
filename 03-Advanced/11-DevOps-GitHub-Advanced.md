# 11 — DevOps, GitHub Actions & CI/CD Advanced

## 🎯 Learning Objectives
Own the full path from commit to production: automated builds, tests, security scans, and deployments.

## 📚 Topics & Subtopics

### CI/CD Pipeline Design
- [ ] Continuous Integration vs Continuous Delivery vs Continuous Deployment — the distinctions
- [ ] Multi-stage GitHub Actions workflows: build → test → security scan → containerize → deploy
- [ ] Reusable workflows & composite actions (DRY CI/CD)
- [ ] Environment-based deployments (`environments` in GitHub Actions) with manual approval gates for production

### Containerization & Registries
- [ ] Multi-stage Dockerfiles for minimal, secure .NET images
- [ ] Pushing images to a container registry (GitHub Container Registry / Azure Container Registry / Docker Hub)
- [ ] Image scanning for vulnerabilities (Trivy / GitHub's built-in scanning)

### Deployment Targets & Strategies
- [ ] Deploying to Azure App Service / Azure Container Apps / AWS ECS (pick one to practice)
- [ ] Blue-green deployments, canary releases, rolling updates
- [ ] Database migration strategy in CI/CD (running migrations safely as part of a pipeline, backward-compatible schema changes)
- [ ] Infrastructure as Code awareness (Bicep/Terraform) — provisioning cloud resources from code

### GitHub Advanced Practices
- [ ] Monorepo vs polyrepo trade-offs for a microservices system
- [ ] GitHub Environments, required reviewers, deployment protection rules
- [ ] Release automation — semantic versioning, changelogs generated from conventional commits
- [ ] GitHub Packages for internal NuGet package sharing across services

### Security in the Pipeline (DevSecOps)
- [ ] Secret scanning & push protection
- [ ] SAST (static analysis) integration (CodeQL) in the pipeline
- [ ] Dependency vulnerability gating (fail the build on critical CVEs)
- [ ] Supply chain security awareness (SBOM generation)

## 🧪 Hands-on Practice
- Build a full GitHub Actions pipeline for TaskFlow: lint → build → unit test → integration test → build & scan Docker image → push to registry → deploy to a staging environment on merge to `main`, with manual approval for production
- Add CodeQL scanning and fix any flagged issues
- Generate an SBOM for your container image and review it
- Set up conventional commits + automated changelog/release generation on tagged releases
- Implement a backward-compatible EF Core migration strategy (e.g., expand-contract pattern) as part of the deploy pipeline

## 📖 Resources
- GitHub Docs: *Deploying with GitHub Actions*
- Microsoft Learn: *Docker & .NET*
- Martin Fowler — *Blue-Green Deployment*, *Canary Release*
- GitHub Docs: *About supply chain security*

## ❓ Self-Check Questions
- What's the difference between continuous delivery and continuous deployment?
- Why is the "expand-contract" pattern useful for zero-downtime database migrations?
- What does an SBOM give you that a simple dependency list doesn't?

## ➡️ Next
[`12-AI-Advanced-Agentic.md`](./12-AI-Advanced-Agentic.md)
