# 04 — Web API Basics

## 🎯 Learning Objectives
Be able to design and build a RESTful Web API with proper HTTP semantics, and document it with OpenAPI/Swagger.

## 📚 Topics & Subtopics

### REST Fundamentals
- [ ] What REST means, resource-based URLs
- [ ] HTTP verbs: GET, POST, PUT, PATCH, DELETE and their semantics/idempotency
- [ ] HTTP status codes — using the right ones (200, 201, 204, 400, 401, 403, 404, 409, 422, 500)
- [ ] Request/response bodies, content negotiation (`Accept`, `Content-Type`)

### Building APIs in ASP.NET Core
- [ ] Controller-based APIs (`[ApiController]`, `[Route]`, `[HttpGet]`, etc.)
- [ ] Minimal APIs (`app.MapGet`, `app.MapPost`) — when to prefer minimal vs controllers
- [ ] Model binding: `[FromBody]`, `[FromQuery]`, `[FromRoute]`, `[FromHeader]`
- [ ] DTOs vs domain models — why not expose your EF entities directly
- [ ] `ActionResult<T>` and `IResult` patterns

### API Documentation
- [ ] Swagger/OpenAPI via Swashbuckle (or `Microsoft.AspNetCore.OpenApi` in .NET 9+)
- [ ] Documenting endpoints, summaries, example values
- [ ] Testing endpoints via Swagger UI / `.http` files / Postman

### Validation & Error Responses
- [ ] Data annotations for basic validation
- [ ] `ProblemDetails` (RFC 7807) for consistent error responses
- [ ] Basic global exception handling middleware (deep dive later)

### Versioning Basics
- [ ] Why API versioning matters
- [ ] URL-based vs header-based versioning (intro awareness)

## 🧪 Hands-on Practice
Convert **TaskFlow** into a proper Web API:
- `GET /api/tasks`, `GET /api/tasks/{id}`, `POST /api/tasks`, `PUT /api/tasks/{id}`, `DELETE /api/tasks/{id}`
- Use DTOs (`CreateTaskDto`, `TaskResponseDto`) instead of exposing the domain model
- Add Swagger UI and try every endpoint through it
- Return proper status codes and `ProblemDetails` on validation failure

## 📖 Resources
- Microsoft Learn: *Create a web API with ASP.NET Core*
- Microsoft Learn: *Minimal APIs overview*
- restfulapi.net — REST API design best practices

## ❓ Self-Check Questions
- Why should POST/PUT/PATCH/DELETE differ in idempotency, and what does idempotent mean?
- Why use DTOs instead of returning EF entities directly from an API?
- What's the difference between 401 and 403?

## ➡️ Next
[`05-EFCore-Basics.md`](./05-EFCore-Basics.md)
