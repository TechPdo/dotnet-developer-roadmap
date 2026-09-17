# 08 — ASP.NET Core Identity & RBAC — Advanced Patterns

## 🎯 Learning Objectives
Go beyond basic roles to build a flexible, maintainable permission system, and understand how to operate Identity at production scale.

## 📚 Topics & Subtopics

### Advanced Identity Customization
- [ ] Custom `IUserStore`/`IRoleStore` implementations (when not using EF Core-backed Identity)
- [ ] Extending Identity with custom tokens (custom `IUserTwoFactorTokenProvider`)
- [ ] Two-Factor Authentication (2FA) — TOTP authenticator apps, backup codes
- [ ] External login providers wired through Identity (`AddGoogle`, `AddMicrosoftAccount`, generic OAuth)
- [ ] Custom claims transformation (`IClaimsTransformation`) — enriching the user's claims principal after authentication

### Designing a Real Permission System
- [ ] Roles vs Permissions vs Claims — why large systems often move from "roles only" to "permissions grouped into roles"
- [ ] Dynamic/database-driven permissions (permissions stored in DB, assigned to roles, checked via policies) instead of hardcoded `[Authorize(Roles=...)]`
- [ ] Building a custom `IAuthorizationPolicyProvider` for dynamic policy resolution (`[Authorize(Permission = "tasks.delete")]`)
- [ ] Hierarchical roles/permission inheritance
- [ ] Caching permission checks for performance

### Multi-Tenancy + Identity
- [ ] Tenant-aware user store (a user belonging to multiple tenants with different roles)
- [ ] Isolating Identity data per tenant vs shared Identity with tenant claims

### Operating Identity at Scale
- [ ] Token signing key rotation without breaking active sessions
- [ ] Distributed session/token revocation (e.g., a Redis-backed denylist for revoked JWTs)
- [ ] Rate limiting & anomaly detection on auth endpoints (impossible travel, repeated failures)
- [ ] GDPR-driven account deletion/anonymization workflows

### Testing Auth
- [ ] Integration testing authenticated endpoints (faking `ClaimsPrincipal` in `WebApplicationFactory`)
- [ ] Testing authorization policies in isolation

## 🧪 Hands-on Practice
- Replace TaskFlow's hardcoded `[Authorize(Roles = "Admin")]` checks with a **dynamic permission system**: `Permission` entities, assigned to `Role`s, checked via a custom `IAuthorizationPolicyProvider` and `[Authorize(Policy = "tasks.delete")]`
- Add TOTP-based 2FA to the login flow (authenticator app support)
- Implement JWT revocation via a Redis-backed denylist, and write a test proving a revoked token is rejected
- Write integration tests that simulate different authenticated users/roles hitting protected endpoints

## 📖 Resources
- Microsoft Learn: *Custom policy-based authorization*
- Microsoft Learn: *Two-factor authentication with SMS/authenticator apps in ASP.NET Core*
- Duende / IdentityServer docs on token revocation strategies
- Auth0 blog — *RBAC vs ABAC vs PBAC* (concepts, vendor-neutral value)

## ❓ Self-Check Questions
- Why might a growing system move from role-checks in code to database-driven permissions?
- How do you revoke a JWT before its expiry, given JWTs are normally stateless?
- What's the testing strategy for verifying an authorization policy works correctly without hitting a real IdP?

## ➡️ Next
[`09-Frontend-Advanced.md`](./09-Frontend-Advanced.md)
