# 07 — Git & GitHub Basics

## 🎯 Learning Objectives
Be able to manage a codebase's history with Git and collaborate effectively using GitHub.

## 📚 Topics & Subtopics

### Git Fundamentals
- [ ] What version control is and why it matters
- [ ] `git init`, `git clone`, `git status`, `git add`, `git commit`
- [ ] `.gitignore` (know the standard .NET/Node ignores)
- [ ] Viewing history: `git log`, `git diff`, `git show`
- [ ] Branching: `git branch`, `git checkout`/`git switch`, `git merge`
- [ ] Undoing changes: `git reset`, `git revert`, `git checkout -- <file>`
- [ ] Stashing: `git stash`

### GitHub Basics
- [ ] Creating a repository, README, license
- [ ] Remotes: `git remote add`, `git push`, `git pull`, `git fetch`
- [ ] Forking vs cloning
- [ ] Pull Requests — creating, reviewing, requesting changes
- [ ] Issues, labels, milestones, Projects (Kanban boards)
- [ ] Branch protection rules basics

### Collaboration Workflow
- [ ] Git flow vs trunk-based development vs GitHub flow (awareness)
- [ ] Writing good commit messages (conventional commits intro)
- [ ] Resolving merge conflicts
- [ ] Code review etiquette

## 🧪 Hands-on Practice
- Initialize a Git repo for TaskFlow and push it to GitHub
- Create a feature branch, make a change, open a Pull Request against `main`
- Deliberately create a merge conflict (edit the same line on two branches) and resolve it
- Set up a proper `.gitignore` for a .NET + Node solution
- Write a README for TaskFlow describing setup and run instructions

## 📖 Resources
- *Pro Git* book (free online) — git-scm.com/book
- GitHub Docs — docs.github.com
- Microsoft Learn: *Introduction to Git*

## ❓ Self-Check Questions
- What's the difference between `git merge` and `git rebase` (at a conceptual level)?
- Why is a `.gitignore` important for a .NET project (what shouldn't be committed)?
- What makes a good Pull Request description?

## ➡️ Next
[`08-Exception-Handling-Logging-Basics.md`](./08-Exception-Handling-Logging-Basics.md)
