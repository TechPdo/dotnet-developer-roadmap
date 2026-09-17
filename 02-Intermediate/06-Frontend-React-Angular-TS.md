# 06 — Frontend: React / Angular / TypeScript (Intermediate)

## 🎯 Learning Objectives
Build a real single-page application frontend (choose **React** or **Angular** — both tracks outlined) that consumes your ASP.NET Core Web API, using TypeScript throughout.

> 💡 Pick ONE framework to go deep on first. Both outlines are provided so you can compare, or learn both over time.

## 📚 Topics & Subtopics

### TypeScript (shared prerequisite — deepen from Beginner)
- [ ] Generics, utility types (`Partial`, `Pick`, `Omit`, `Record`)
- [ ] Interfaces vs types, discriminated unions
- [ ] Type-safe API clients (mirroring your C# DTOs as TS interfaces)
- [ ] `enum` vs union string literal types

### Track A — React
- [ ] Project setup with Vite, folder structure
- [ ] Components, props, JSX/TSX
- [ ] State: `useState`, `useEffect`, `useContext`, `useReducer`
- [ ] Custom hooks
- [ ] Routing with React Router
- [ ] Data fetching patterns: plain `fetch`/`axios` vs **React Query / TanStack Query**
- [ ] Form handling (React Hook Form + validation, e.g., Zod)
- [ ] State management overview: Context API vs Redux Toolkit vs Zustand (when each is warranted)
- [ ] Component styling: CSS Modules / Tailwind / styled-components (pick one)

### Track B — Angular
- [ ] Angular CLI, project structure, modules vs standalone components
- [ ] Components, templates, data binding (interpolation, `[property]`, `(event)`, `[(ngModel)]`)
- [ ] Services & Angular's own DI system (parallels to ASP.NET Core DI — good comparison point)
- [ ] `HttpClient` module for API calls, typed responses
- [ ] RxJS basics: Observables, `subscribe`, `pipe`, common operators (`map`, `switchMap`, `catchError`)
- [ ] Routing (`RouterModule`), route guards
- [ ] Reactive Forms vs Template-driven Forms
- [ ] State management overview: services with RxJS vs NgRx (when NgRx is warranted)

### Authentication on the Frontend (teaser — full depth in Security file)
- [ ] Storing tokens (memory vs localStorage vs httpOnly cookies — trade-offs)
- [ ] Attaching JWT to API requests (Axios interceptor / Angular `HttpInterceptor`)
- [ ] Handling 401 responses / token refresh flow

## 🧪 Hands-on Practice
- Scaffold a **TaskFlow frontend** in React (Vite + TS) or Angular (Angular CLI)
- Implement Tasks list, create/edit forms, delete with confirmation, all calling your Web API
- Add client-side validation matching your FluentValidation rules
- Add an HTTP interceptor that attaches an auth token and handles 401 redirects (prep for Identity integration next)

## 📖 Resources
- React official docs (react.dev) + TanStack Query docs
- Angular official docs (angular.dev) + RxJS docs
- Microsoft Learn: *Build a full-stack app with ASP.NET Core and React/Angular*

## ❓ Self-Check Questions
- How do Angular services + DI compare conceptually to ASP.NET Core DI?
- Why prefer React Query/TanStack Query over manual `useEffect` fetching for server state?
- Why is storing a JWT in `localStorage` a security trade-off compared to an httpOnly cookie?

## ➡️ Next
[`07-Security-Identity-Basics.md`](./07-Security-Identity-Basics.md)
