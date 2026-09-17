# 09 — AI Basics for Developers

## 🎯 Learning Objectives
Understand foundational AI/LLM concepts and start using AI tools productively in your .NET workflow.

## 📚 Topics & Subtopics

### Core Concepts
- [ ] What an LLM is (conceptually) — tokens, prompts, completions
- [ ] Difference between AI, Machine Learning, Deep Learning, and Generative AI
- [ ] What "context window" and "temperature" mean
- [ ] Prompting basics: clear instructions, providing context, giving examples (few-shot)
- [ ] Limitations: hallucination, knowledge cutoffs, no real "understanding"

### AI-Assisted Development
- [ ] Using GitHub Copilot / Copilot Chat inside Visual Studio / VS Code
- [ ] Using an AI chat assistant (like Claude) for code review, debugging, refactoring suggestions
- [ ] Prompt engineering basics for coding tasks (be specific, provide code + error + goal)
- [ ] Reviewing AI-generated code critically — never blind-paste

### Calling AI APIs from .NET (Intro)
- [ ] What an API key is, and keeping it out of source control (tie back to Git basics)
- [ ] Making a basic HTTP call to an LLM API (e.g., OpenAI or Anthropic API) using `HttpClient`
- [ ] Parsing a JSON response from an AI API

## 🧪 Hands-on Practice
- Install GitHub Copilot (or similar) and use it to scaffold a small class in TaskFlow — review and correct its output
- Write a small .NET console app that calls an LLM API with `HttpClient`, sends a prompt like "Summarize this task list," and prints the response
- Practice writing 5 different prompts for the same coding task and compare output quality

## 📖 Resources
- Microsoft Learn: *AI fundamentals*
- OpenAI / Anthropic API documentation
- GitHub Docs: *GitHub Copilot*

## ❓ Self-Check Questions
- Why can an LLM "hallucinate" a wrong answer confidently?
- What's the risk of committing an AI API key to a public GitHub repo?
- Why should you still review AI-generated code line by line?

## 🏁 Beginner Level — Capstone Project
Build the **TaskFlow v1**:
- ASP.NET Core Web API (Beginner-level, no auth yet) with EF Core persistence
- Simple HTML/JS/TS frontend consuming it
- Proper error handling, structured logging, and Swagger docs
- Pushed to GitHub with a clean README, `.gitignore`, and PR history
- Bonus: one endpoint that uses an AI API to auto-summarize a user's task list

**When this works end-to-end, you're ready for → [`02-Intermediate/`](../02-Intermediate/01-CSharp-Intermediate.md)**
