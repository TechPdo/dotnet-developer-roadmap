# 02 — .NET Platform Basics

## 🎯 Learning Objectives
Understand the .NET ecosystem, project structure, and tooling well enough to create, build, and run any .NET project confidently.

## 📚 Topics & Subtopics

### .NET Ecosystem
- [ ] SDK vs Runtime, LTS vs STS release channels
- [ ] `dotnet` CLI: `new`, `build`, `run`, `test`, `publish`, `restore`
- [ ] Project files: `.csproj` structure, `TargetFramework`, implicit usings
- [ ] Solution files (`.sln`) and multi-project solutions
- [ ] NuGet package management (`dotnet add package`, `PackageReference`, lock files)
- [ ] `global.json` for SDK pinning

### Assemblies & Project Types
- [ ] Class Library vs Console App vs Web App project templates
- [ ] Namespaces & assembly organization
- [ ] `Main` method, top-level statements
- [ ] Debug vs Release configuration, build profiles
- [ ] Publishing modes: framework-dependent vs self-contained, single-file, trimming (awareness only)

### Configuration
- [ ] `appsettings.json` / `appsettings.{Environment}.json`
- [ ] Environment variables & `ASPNETCORE_ENVIRONMENT`
- [ ] `IConfiguration` basics — binding sections to POCOs
- [ ] User secrets for local development (`dotnet user-secrets`)

### Testing Basics
- [ ] Unit testing frameworks overview: xUnit vs NUnit vs MSTest
- [ ] Writing your first test project (`dotnet new xunit`)
- [ ] `Assert` basics, test naming conventions (Arrange-Act-Assert)

## 🧪 Hands-on Practice
- Create a solution with 2 projects: a Class Library (`TaskFlow.Core`) and a Console App (`TaskFlow.Console`) referencing it
- Move your Task Manager model classes from file 01 into the library
- Add an `appsettings.json` with a `MaxTasksAllowed` setting and read it via `IConfiguration`
- Create an xUnit test project and write 3 unit tests for your task logic

## 📖 Resources
- Microsoft Learn: *.NET CLI overview*
- Microsoft Learn: *Configuration in .NET*
- Microsoft Learn: *Unit testing in .NET with xUnit*

## ❓ Self-Check Questions
- What's the difference between framework-dependent and self-contained deployment?
- How does `appsettings.Development.json` override `appsettings.json`?
- Why should secrets never be committed to `appsettings.json`?

## ➡️ Next
[`03-AspNetCore-Intro.md`](./03-AspNetCore-Intro.md)
