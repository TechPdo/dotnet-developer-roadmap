# 03 — ASP.NET Core Introduction

## 🎯 Learning Objectives
Understand how an ASP.NET Core application starts up, how the middleware pipeline works, and be able to build a basic MVC/Razor app.

## 📚 Topics & Subtopics

### Hosting & Startup
- [ ] `Program.cs` minimal hosting model (`WebApplication.CreateBuilder`)
- [ ] `WebApplicationBuilder` vs the older `Startup.cs`/`ConfigureServices`/`Configure` model (know both — many jobs still use old style)
- [ ] Kestrel web server, reverse proxy basics (IIS/Nginx awareness)
- [ ] Environments (`Development`, `Staging`, `Production`)

### Middleware Pipeline
- [ ] What middleware is, request/response pipeline as a chain
- [ ] Built-in middleware: routing, static files, HTTPS redirection, exception handling
- [ ] Writing a custom middleware (`app.Use`, `IMiddleware`)
- [ ] Order of middleware matters — why

### Routing
- [ ] Conventional routing vs attribute routing
- [ ] Route parameters, constraints, optional segments

### MVC & Razor Pages Basics
- [ ] MVC pattern: Model-View-Controller
- [ ] Controllers, actions, action results (`ViewResult`, `JsonResult`, etc.)
- [ ] Razor syntax basics (`@`, loops, conditionals in views)
- [ ] Razor Pages vs MVC vs Minimal APIs — when to use which
- [ ] Model binding & validation basics (`[Required]`, `[Range]`, etc.)
- [ ] TempData, ViewData, ViewBag differences

### Static Files & wwwroot
- [ ] Serving CSS/JS/images
- [ ] Bundling/minification awareness

## 🧪 Hands-on Practice
- Create `dotnet new mvc` project called `TaskFlow.Web`
- Build a Tasks controller with Index/Create/Edit/Delete views (in-memory list for now)
- Add a custom middleware that logs each request's method + path to console
- Add basic model validation on the Create form

## 📖 Resources
- Microsoft Learn: *ASP.NET Core fundamentals*
- Microsoft Learn: *Middleware in ASP.NET Core*
- Microsoft Learn: *Routing in ASP.NET Core*

## ❓ Self-Check Questions
- What happens, step by step, from an HTTP request hitting Kestrel to a response being returned?
- Why does middleware order matter (e.g., authentication before authorization)?
- When would you choose Razor Pages over MVC?

## ➡️ Next
[`04-WebAPI-Basics.md`](./04-WebAPI-Basics.md)
