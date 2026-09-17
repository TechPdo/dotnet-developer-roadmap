# 07 — Security Advanced

## 🎯 Learning Objectives
Design authentication/authorization for real-world, multi-client, enterprise-grade systems, and proactively harden applications against modern threats.

## 📚 Topics & Subtopics

### OAuth 2.0 & OpenID Connect (OIDC)
- [ ] OAuth 2.0 fundamentals: authorization code flow, client credentials flow, PKCE
- [ ] OIDC as an identity layer on top of OAuth 2.0 — ID tokens vs access tokens
- [ ] When to build your own auth (ASP.NET Core Identity, from Intermediate) vs delegate to an Identity Provider (IdP)
- [ ] Using external IdPs: Microsoft Entra ID (Azure AD), Auth0, Keycloak, Duende IdentityServer
- [ ] Social login integration (Google, Microsoft, GitHub external providers in ASP.NET Core)
- [ ] Single Sign-On (SSO) concepts across multiple applications

### Advanced Authorization
- [ ] Fine-grained/attribute-based access control (ABAC) beyond simple roles
- [ ] Multi-tenant authorization (users belonging to multiple orgs/tenants with different roles per tenant)
- [ ] Scopes vs roles vs claims — designing a clean permission model
- [ ] API-to-API authorization (service accounts, client credentials flow, machine-to-machine tokens)

### Secure Coding & Hardening
- [ ] Threat modeling basics (STRIDE) — thinking like an attacker at design time
- [ ] Input validation & output encoding as defense-in-depth
- [ ] Preventing mass assignment / over-posting vulnerabilities (binding only intended DTO fields)
- [ ] Secure file upload handling (content-type validation, storage isolation, malware scanning awareness)
- [ ] Secrets & key management at scale: Azure Key Vault / AWS Secrets Manager, key rotation
- [ ] Data protection API in ASP.NET Core (`IDataProtector`) for encrypting sensitive data at rest
- [ ] Auditing sensitive actions (who did what, when — audit log design)

### Compliance & Standards Awareness
- [ ] OWASP Top 10 — revisit each item with concrete ASP.NET Core mitigations
- [ ] GDPR/data privacy basics (right to be forgotten, data minimization) — awareness for developers
- [ ] Dependency vulnerability scanning (Dependabot/`dotnet list package --vulnerable`, `dotnet restore --locked-mode`)

### Penetration-Testing Mindset (Awareness)
- [ ] Common tools: OWASP ZAP for automated scanning
- [ ] Reading a basic pentest report and prioritizing fixes

## 🧪 Hands-on Practice
- Integrate an external OIDC provider (e.g., Microsoft Entra ID or Auth0) into TaskFlow alongside (or replacing) local Identity, using the authorization code flow with PKCE from the frontend
- Design a multi-tenant permission model for TaskFlow (a user can belong to multiple "workspaces" with different roles per workspace) and implement it with a custom `IAuthorizationHandler`
- Run `dotnet list package --vulnerable` and fix any flagged dependencies
- Run OWASP ZAP against a local instance of TaskFlow and address at least 2 findings
- Add an audit log table capturing "who deleted which task, when"

## 📖 Resources
- OWASP Top 10 (owasp.org) — revisit at this depth
- Microsoft Learn: *Microsoft identity platform* (Entra ID / OAuth2/OIDC)
- Duende IdentityServer documentation
- OWASP ZAP documentation

## ❓ Self-Check Questions
- Why would a serious enterprise app delegate to an external IdP instead of rolling its own login with ASP.NET Core Identity alone?
- What's the difference between authorization *scopes* and *roles*, and when do you need both?
- What is over-posting/mass assignment, and how does using DTOs (from earlier files) already partially protect against it?

## ➡️ Next
[`08-Identity-RBAC-Advanced.md`](./08-Identity-RBAC-Advanced.md)
