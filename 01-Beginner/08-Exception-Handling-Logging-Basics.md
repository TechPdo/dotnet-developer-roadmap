# 08 — Exception Handling & Logging Basics

## 🎯 Learning Objectives
Handle errors predictably and produce useful log output for a basic ASP.NET Core application.

## 📚 Topics & Subtopics

### Exception Handling Fundamentals
- [ ] Exception hierarchy in .NET (`Exception`, `SystemException`, `ApplicationException`)
- [ ] `try/catch/finally` best practices — catch specific exceptions, avoid empty catches
- [ ] Creating custom exception types
- [ ] `throw` vs `throw ex` — why the difference matters (stack trace preservation)
- [ ] When to catch vs when to let it bubble up

### ASP.NET Core Error Handling
- [ ] Developer Exception Page vs production error handling
- [ ] `UseExceptionHandler` middleware
- [ ] Returning consistent error responses (`ProblemDetails`)
- [ ] Status code pages (`UseStatusCodePages`)

### Logging Basics
- [ ] `ILogger<T>` and the built-in logging abstraction
- [ ] Log levels: Trace, Debug, Information, Warning, Error, Critical
- [ ] Structured logging — message templates vs string interpolation (`_logger.LogInformation("User {UserId} logged in", userId)`)
- [ ] Console & Debug logging providers
- [ ] Configuring log levels per namespace in `appsettings.json`

## 🧪 Hands-on Practice
- Add a global exception handling middleware to TaskFlow API that returns a consistent `ProblemDetails` JSON on unhandled errors
- Create a custom `TaskNotFoundException` and handle it distinctly (404) vs generic exceptions (500)
- Add structured logging to your controllers/services (log every create/delete with relevant IDs)
- Configure `appsettings.json` so your app logs `Information` in Development and `Warning` in Production

## 📖 Resources
- Microsoft Learn: *Handle errors in ASP.NET Core*
- Microsoft Learn: *Logging in .NET*

## ❓ Self-Check Questions
- Why is `throw;` preferred over `throw ex;` when rethrowing?
- What's the danger of catching `Exception` broadly everywhere?
- Why does structured logging (message templates) matter over string concatenation?

## ➡️ Next
[`09-AI-Basics-For-Developers.md`](./09-AI-Basics-For-Developers.md)
