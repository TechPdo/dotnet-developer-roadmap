# 06 — Frontend Basics (HTML, CSS, JavaScript, TypeScript Intro)

## 🎯 Learning Objectives
Be comfortable enough with core web frontend technologies to consume your Web APIs from a browser-based UI, before diving into React/Angular in the Intermediate section.

## 📚 Topics & Subtopics

### HTML & CSS Essentials
- [ ] Semantic HTML, forms, tables
- [ ] CSS box model, flexbox, grid basics
- [ ] Responsive design basics (media queries)
- [ ] CSS frameworks overview (Bootstrap / Tailwind) — pick one to practice with

### JavaScript Fundamentals
- [ ] Variables (`let`/`const`), functions, arrow functions
- [ ] Arrays/objects, destructuring, spread/rest
- [ ] `fetch` API — calling a REST API from JS
- [ ] Promises and `async`/`await` in JS
- [ ] DOM manipulation basics, event listeners
- [ ] JSON parsing/serialization

### Introduction to TypeScript
- [ ] Why TypeScript over plain JS (types, tooling, refactor safety)
- [ ] Basic types, interfaces, type aliases
- [ ] Compiling TS to JS (`tsc`), `tsconfig.json` basics
- [ ] Typing API responses/DTOs to mirror your C# DTOs

### CORS Basics
- [ ] What CORS is and why browsers enforce it
- [ ] Configuring CORS in ASP.NET Core to allow your frontend origin

## 🧪 Hands-on Practice
- Build a plain HTML/CSS/JS page that calls your TaskFlow API (`fetch`) to list, add, and complete tasks
- Convert the JS logic to TypeScript, defining an interface matching your `TaskResponseDto`
- Configure CORS on the API so the static page (served from a different port) can call it successfully

## 📖 Resources
- MDN Web Docs — HTML/CSS/JS reference
- TypeScript Handbook (official docs)
- Microsoft Learn: *Enable CORS in ASP.NET Core*

## ❓ Self-Check Questions
- Why does the browser block a `fetch` call without proper CORS headers?
- What's the benefit of typing your API responses in TypeScript?
- What's the difference between `let`, `const`, and (legacy) `var`?

## ➡️ Next
[`07-Git-GitHub-Basics.md`](./07-Git-GitHub-Basics.md)
