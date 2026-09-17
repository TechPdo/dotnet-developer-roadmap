# 09 — Frontend Advanced (React / Angular / TypeScript)

## 🎯 Learning Objectives
Build performant, well-architected, production-grade SPA frontends that integrate deeply and securely with your ASP.NET Core backend.

## 📚 Topics & Subtopics

### Advanced TypeScript
- [ ] Advanced generics, conditional types, mapped types
- [ ] Type-safe API client generation from your OpenAPI spec (openapi-typescript, NSwag, Kiota) — keeping frontend types in sync with backend DTOs automatically
- [ ] Strict mode (`strict: true`) and why it matters at scale

### Architecture at Scale
- [ ] Feature-based folder structure (mirroring the backend's vertical slices)
- [ ] Micro-frontends — awareness of when/why large orgs split frontends
- [ ] Design systems & component libraries (Storybook for isolated component development)
- [ ] Monorepo tooling (Nx / Turborepo) for multi-app frontend workspaces

### Performance
- [ ] Code splitting & lazy loading (React `lazy`/`Suspense`, Angular lazy-loaded modules/routes)
- [ ] Memoization (`useMemo`, `useCallback`, `React.memo` / Angular `OnPush` change detection strategy)
- [ ] Virtualized lists for large datasets (react-window / Angular CDK virtual scroll)
- [ ] Bundle analysis & tree-shaking
- [ ] Core Web Vitals awareness (LCP, CLS, INP)

### Real-Time & Advanced Data
- [ ] Consuming SignalR from React/Angular for live updates
- [ ] Optimistic UI updates with rollback on failure
- [ ] Offline-first patterns (service workers, background sync) — awareness

### Security on the Frontend
- [ ] Secure token storage revisited: httpOnly cookie + BFF pattern vs SPA token storage trade-offs, at depth
- [ ] Content Security Policy configuration for SPAs
- [ ] Protecting against XSS in a component-based framework (React/Angular auto-escape, and where `dangerouslySetInnerHTML`/`[innerHTML]` reopens risk)

### Testing the Frontend
- [ ] Unit testing components (Jest/Vitest + React Testing Library, or Jasmine/Karma/Jest for Angular)
- [ ] End-to-end testing (Playwright or Cypress) across the full stack

## 🧪 Hands-on Practice
- Generate a fully-typed API client for TaskFlow from its OpenAPI spec and replace manual `fetch` calls
- Add code splitting/lazy loading to the TaskFlow frontend's routes
- Implement optimistic UI updates for marking a task complete, with rollback if the API call fails
- Write Playwright/Cypress E2E tests covering login → create task → complete task → logout
- Migrate token storage to the BFF pattern (backend sets an httpOnly cookie; frontend never touches the raw JWT) and explain the security improvement in your README

## 📖 Resources
- web.dev — Core Web Vitals guidance
- Playwright / Cypress official docs
- Microsoft Learn: *Secure a SPA with the BFF pattern*
- Storybook official docs

## ❓ Self-Check Questions
- What's the security benefit of the BFF pattern (httpOnly cookies) over storing JWTs client-side?
- When does optimistic UI improve UX, and what's the risk if not handled carefully?
- Why does keeping frontend DTO types generated (not hand-written) reduce a whole class of bugs?

## ➡️ Next
[`10-Observability-Logging-Advanced.md`](./10-Observability-Logging-Advanced.md)
