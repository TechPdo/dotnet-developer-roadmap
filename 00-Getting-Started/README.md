# 00 — Getting Started

## 🎯 Goal
Set up your environment and understand how to navigate this course before diving into content.

## 🛠️ Tooling Setup Checklist

- [ ] Install the latest **.NET SDK (LTS)** — verify with `dotnet --version`
- [ ] Install **Visual Studio 2022** (Community/Pro) *or* **VS Code** with the C# Dev Kit extension *or* **JetBrains Rider**
- [ ] Install **Git** and configure `user.name` / `user.email`
- [ ] Create a **GitHub** account and set up SSH keys
- [ ] Install **Node.js (LTS)** + npm/yarn (needed for React/Angular sections)
- [ ] Install **Docker Desktop** (used from Intermediate level onward)
- [ ] Install **SQL Server Express / PostgreSQL** locally, or use Docker containers
- [ ] Install **Postman** or **Insomnia** for API testing (or use `.http` files in VS Code/Rider)
- [ ] Install a database GUI: **Azure Data Studio** / **DBeaver** / **SSMS**
- [ ] (Optional but recommended) Install **GitHub Copilot** or another AI coding assistant — used heavily in the AI track

## 📐 How to Study Each Topic File

Every topic file in this course follows the same structure:

1. **Learning Objectives** — what you should be able to do after finishing
2. **Topics & Subtopics** — the checklist of concepts to learn
3. **Hands-on Practice** — a mini-exercise or feature to build
4. **Resources** — where to learn the concept (official docs first, videos/books second)
5. **Self-Check Questions** — quiz yourself before moving on

## 🧭 Recommended Order

```
01-Beginner  →  02-Intermediate  →  03-Advanced
```

Within each level, follow the numeric file order — later files often assume knowledge from earlier ones (e.g., DI is assumed once you reach CQRS).

## 🏗️ The Running Project

Throughout this course you'll incrementally build **one evolving application** — a **"TaskFlow" project/task management system** — adding features as your skills grow:

| Level | What You Add to TaskFlow |
|---|---|
| Beginner | Console app → Basic Web API with in-memory data → simple EF Core persistence |
| Intermediate | Layered architecture, DI, Identity auth, React/Angular frontend, structured logging |
| Advanced | CQRS/MediatR, microservices split, caching, advanced security, CI/CD, AI copilot features |

Having one continuous project makes the learning concrete and gives you a strong portfolio piece by the end.

## ✅ Self-Check Before Moving On
- [ ] I can run `dotnet new webapi` and start the app locally
- [ ] I can create a GitHub repo and push a commit
- [ ] I understand the folder structure of this course

Next → [`01-Beginner/01-CSharp-Fundamentals.md`](../01-Beginner/01-CSharp-Fundamentals.md)
