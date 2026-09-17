# 07 — Security & ASP.NET Core Identity (Authentication, Authorization, JWT Tokenization, RBAC)

## 🎯 Learning Objectives
Implement full user management — registration, login, password handling, roles — using ASP.NET Core Identity, and deeply understand the three pillars this file centers on: **authentication** (proving who you are), **authorization** (what you're allowed to do), and **JWT tokenization** (how identity and permissions travel with a stateless API request).

## 📚 Topics & Subtopics

### 🔑 Authentication — Deep Dive
- [ ] Authentication (who are you) vs Authorization (what can you do) — the core distinction, and why mixing them up leads to bugs
- [ ] Authentication **schemes** in ASP.NET Core — a scheme is a named authentication handler (Cookies, JwtBearer, etc.); an app can register multiple and pick per-endpoint
- [ ] `AddAuthentication(options => { options.DefaultScheme = ...; options.DefaultChallengeScheme = ...; })` — what "default scheme" actually controls
- [ ] Cookie-based auth vs token-based auth (JWT) — how each works mechanically, and when to use which (server-rendered MVC/Razor apps → cookies; SPA/mobile/service-to-service → tokens)
- [ ] The authentication middleware pipeline: `UseAuthentication()` populates `HttpContext.User` from the incoming credential; `UseAuthorization()` then checks it — **order matters** (`UseRouting` → `UseAuthentication` → `UseAuthorization` → endpoints)
- [ ] The `ClaimsPrincipal` / `ClaimsIdentity` model — how .NET represents "the current user" internally, regardless of whether they came from a cookie or a JWT
- [ ] Multi-scheme setups — e.g., cookie auth for a Razor admin panel + JWT bearer auth for the API, coexisting in one app
- [ ] External authentication providers (Google, Microsoft, GitHub) — the OAuth handshake at a conceptual level, and how ASP.NET Core's `AddGoogle`/`AddMicrosoftAccount` wire into the same `ClaimsPrincipal` model

### 🛡️ Authorization — Deep Dive
- [ ] Authorization runs **after** authentication — it only asks "is this already-identified user allowed to do this?"
- [ ] Simple authorization: `[Authorize]` (any authenticated user) vs `[AllowAnonymous]`
- [ ] Role-based authorization: `[Authorize(Roles = "Admin")]`, `[Authorize(Roles = "Admin,Manager")]` (OR logic), stacking `[Authorize]` attributes for AND logic
- [ ] Claims-based authorization: checking for a specific claim type/value (e.g., a `"CanExport"` claim) via a policy
- [ ] Policy-based authorization — the recommended approach for anything beyond trivial checks:
  - [ ] `AddAuthorization(options => options.AddPolicy("Over18", policy => policy.RequireClaim("DateOfBirth")))`
  - [ ] Combining multiple requirements in one policy
  - [ ] Applying policies with `[Authorize(Policy = "...")]`
- [ ] Custom requirements & handlers — `IAuthorizationRequirement` + `AuthorizationHandler<TRequirement>` for logic that can't be expressed declaratively (e.g., "user can only edit their own tasks")
- [ ] Resource-based authorization — checking authorization against a specific loaded entity (`IAuthorizationService.AuthorizeAsync(User, task, "TaskOwnerPolicy")`) rather than just the route
- [ ] Authorization in Minimal APIs (`.RequireAuthorization()`, `.RequireAuthorization("PolicyName")`) vs controller attributes
- [ ] Global authorization fallback policy (require auth by default everywhere, opt out with `[AllowAnonymous]`) — a common hardening pattern
- [ ] Testing authorization logic in isolation (unit-testing an `AuthorizationHandler` without spinning up the whole pipeline)

### ASP.NET Core Identity Setup
- [ ] Adding Identity to a project (`AddIdentity`, `AddIdentityCore` for API-only scenarios)
- [ ] `IdentityUser`, `IdentityRole`, extending `IdentityUser` with custom fields
- [ ] Identity's own `DbContext` (`IdentityDbContext`) and migrations
- [ ] Password hashing — how Identity does it (PBKDF2) and why you never roll your own

### Registration & Login Flows
- [ ] Building a `POST /api/auth/register` endpoint with `UserManager<T>`
- [ ] Building a `POST /api/auth/login` endpoint with `SignInManager<T>`
- [ ] Email confirmation flow (tokens, confirmation links)
- [ ] Password reset flow ("forgot password")
- [ ] Account lockout policies (max failed attempts, lockout duration)
- [ ] Password complexity & policy configuration

### 🎫 JWT Tokenization — Deep Dive
- [ ] What a JWT actually is: three Base64Url-encoded parts — **Header.Payload.Signature** — and why it's "encoded, not encrypted" by default (never put secrets in the payload)
- [ ] **Header**: signing algorithm (`alg`, e.g., `HS256` vs `RS256`) and token type (`typ: JWT`)
- [ ] **Payload / Claims**:
  - [ ] Registered/standard claims: `sub` (subject/user id), `iss` (issuer), `aud` (audience), `exp` (expiry), `iat` (issued-at), `nbf` (not-before), `jti` (unique token id — used for revocation lists)
  - [ ] Custom claims: roles, permissions, tenant id, display name — designing a lean payload (JWTs are sent on every request; keep them small)
  - [ ] Mapping ASP.NET Core Identity's `ClaimsPrincipal` into JWT claims when issuing a token
- [ ] **Signature**: how it guarantees integrity (any tampering with header/payload invalidates the signature) — but again, does **not** provide confidentiality
- [ ] Symmetric signing (`HS256`, shared secret key — simpler, both issuer and validator need the same key) vs asymmetric signing (`RS256`/`ES256`, private key signs / public key validates — needed when a separate service only validates tokens and shouldn't be able to issue them)
- [ ] Issuing a token in code: `JwtSecurityTokenHandler`, `SecurityTokenDescriptor`, `SigningCredentials`, setting `Issuer`, `Audience`, `Expires`, and the `Claims` collection
- [ ] Validating a token: `AddAuthentication().AddJwtBearer(options => options.TokenValidationParameters = new TokenValidationParameters { ... })` and each validation flag:
  - [ ] `ValidateIssuer` / `ValidIssuer`
  - [ ] `ValidateAudience` / `ValidAudience`
  - [ ] `ValidateLifetime` (rejects expired tokens) and `ClockSkew` (default 5-minute leeway — often worth tightening)
  - [ ] `ValidateIssuerSigningKey` / `IssuerSigningKey`
- [ ] Access token vs refresh token — why access tokens are short-lived (minutes) and refresh tokens are long-lived (days/weeks) and stored more carefully
- [ ] Refresh token flow end-to-end: client exchanges an expired-but-not-too-old access token + valid refresh token for a new pair; **refresh token rotation** (issue a new refresh token every time, invalidate the old one, detect reuse as a theft signal)
- [ ] Where to store tokens client-side: `localStorage`/`sessionStorage` (simple, but exposed to XSS) vs in-memory JS variable vs httpOnly cookie (safer, but needs CSRF handling) — trade-offs revisited in depth in the Advanced security file (BFF pattern)
- [ ] Revoking/invalidating JWTs before expiry — the core problem with stateless tokens, and mitigation approaches: short expiries, a server-side denylist keyed by `jti`, or rotating signing keys
- [ ] Reading/debugging a JWT (jwt.io or `System.IdentityModel.Tokens.Jwt` locally) — never paste a **real production** token into a third-party website

### Role-Based & Claims-Based Access Control (via Identity)
- [ ] Roles: creating roles, assigning users to roles (`RoleManager<T>`)
- [ ] `[Authorize(Roles = "Admin")]` on controllers/actions
- [ ] Claims-based authorization — custom claims, `[Authorize(Policy = "...")]`
- [ ] Policy-based authorization (`AddAuthorization(options => options.AddPolicy(...))`)
- [ ] Custom `IAuthorizationHandler` / `IAuthorizationRequirement` for complex rules (e.g., "user can only edit their own tasks")
- [ ] Resource-based authorization

### General Web Security Hardening
- [ ] HTTPS enforcement, HSTS
- [ ] CSRF (Cross-Site Request Forgery) — anti-forgery tokens, when relevant (cookie auth) vs not needed (pure JWT bearer APIs)
- [ ] XSS (Cross-Site Scripting) — output encoding, CSP headers
- [ ] SQL Injection — why parameterized queries/EF Core protect you, and where raw SQL can reopen the risk
- [ ] Secure headers (`X-Content-Type-Options`, `X-Frame-Options`, `Content-Security-Policy`)
- [ ] Secrets management basics recap (never in source control; Azure Key Vault / user secrets / environment variables)
- [ ] Rate limiting & brute-force protection on auth endpoints

## 🧪 Hands-on Practice
Add full user management to **TaskFlow**:

**Authentication**
- Integrate ASP.NET Core Identity with a custom `ApplicationUser` (add `DisplayName`, `CreatedAt`)
- Build `POST /api/auth/register` and `POST /api/auth/login` using `UserManager<T>` / `SignInManager<T>`
- Add email confirmation and password reset flows (can mock the email sender for local dev)
- Add account lockout after 5 failed login attempts

**JWT Tokenization**
- On successful login, issue a signed JWT access token containing `sub`, `email`, `role`, and a `jti`, with a short (e.g., 15-minute) expiry
- Configure `AddJwtBearer` with explicit `TokenValidationParameters` (issuer, audience, lifetime, signing key) — don't rely on defaults
- Implement a refresh token endpoint (`POST /api/auth/refresh`) with **rotation**: issuing a new refresh token each time and invalidating the previous one
- Implement a `jti`-based denylist (e.g., in Redis or a DB table) so a logout/compromise can revoke a specific token before it expires
- Decode one of your own issued tokens on jwt.io locally to confirm the claims and expiry look correct

**Authorization**
- Create `Admin` and `User` roles; seed an initial Admin account
- Restrict task deletion to the `Admin` role using `[Authorize(Roles = "Admin")]`
- Restrict task editing to the task's own owner using a custom `IAuthorizationHandler` + resource-based authorization (`AuthorizeAsync(User, task, "TaskOwnerPolicy")`)
- Add a global fallback policy requiring authentication on all endpoints by default, then explicitly mark public ones with `[AllowAnonymous]`

**General Hardening**
- Add security headers middleware and enforce HTTPS
- Update the React/Angular frontend to store the JWT and attach it via an `Authorization: Bearer` header, showing/hiding UI based on role/claims

## 📖 Resources
- Microsoft Learn: *ASP.NET Core Identity*
- Microsoft Learn: *JWT bearer authentication*
- Microsoft Learn: *Authorization in ASP.NET Core* (roles, policies, resource-based)
- OWASP Top 10 (owasp.org) — foundational web security risks
- OWASP ASVS (Application Security Verification Standard) — reference checklist

## ❓ Self-Check Questions
- What's the precise difference between authentication and authorization, and which one runs first in the ASP.NET Core pipeline?
- Why shouldn't you store plaintext passwords, and how does Identity protect them?
- What are the three parts of a JWT, and what does each one guarantee (and *not* guarantee)?
- Why is `ValidateLifetime` alone not enough to fully secure JWT validation — what else must you check, and why?
- What's the difference between symmetric (`HS256`) and asymmetric (`RS256`) JWT signing, and when would you need asymmetric?
- Why are refresh tokens needed if you already have an access token, and why does *rotating* them matter?
- How do you revoke a single JWT before it expires, given JWTs are stateless by design?
- What's the difference between role-based and policy-based authorization, and when would you need the latter?
- How does EF Core protect against SQL injection by default, and when could that protection be bypassed?

## ➡️ Next
[`08-Logging-Exception-Handling-Intermediate.md`](./08-Logging-Exception-Handling-Intermediate.md)
