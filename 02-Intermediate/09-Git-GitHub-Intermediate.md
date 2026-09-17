# 09 — Git & GitHub Intermediate

## 🎯 Learning Objectives
Use Git effectively in a team setting and start automating workflows with GitHub Actions.

## 📚 Topics & Subtopics

### Advanced Git
- [ ] Interactive rebase (`git rebase -i`) — squashing, reordering, editing commits
- [ ] Cherry-picking commits
- [ ] `git bisect` for finding regressions
- [ ] Tags & releases (`git tag`, semantic versioning)
- [ ] Submodules vs monorepo awareness

### Branching Strategies
- [ ] Git Flow vs GitHub Flow vs trunk-based development — pros/cons for different team sizes
- [ ] Feature branches, release branches, hotfix branches
- [ ] Protected branches + required status checks/reviews

### GitHub Actions (CI/CD Intro)
- [ ] Workflow YAML basics: triggers (`on: push`, `pull_request`), jobs, steps
- [ ] Building & testing a .NET project on every PR
- [ ] Caching NuGet packages for faster builds
- [ ] Matrix builds (multiple .NET versions/OS)
- [ ] Secrets management in GitHub Actions

### Repository Hygiene
- [ ] CODEOWNERS file
- [ ] Issue/PR templates
- [ ] Dependabot for dependency updates & security alerts
- [ ] GitHub security features: secret scanning, CodeQL basics

## 🧪 Hands-on Practice
- Set up a GitHub Actions workflow that builds, tests, and lints TaskFlow on every PR to `main`
- Add branch protection requiring the workflow to pass + 1 review before merge
- Practice an interactive rebase to clean up a messy feature branch before opening a PR
- Add a `CODEOWNERS` file and a PR template with a checklist (tests added, docs updated, etc.)
- Enable Dependabot for NuGet and npm dependencies

## 📖 Resources
- GitHub Docs: *GitHub Actions*
- GitHub Docs: *About branch protection rules*
- Microsoft Learn: *Build and test .NET with GitHub Actions*

## ❓ Self-Check Questions
- When would you choose trunk-based development over Git Flow?
- Why is squashing commits before merge sometimes preferred, and when is it not?
- What's the benefit of caching NuGet packages in CI?

## ➡️ Next
[`10-AI-Intermediate.md`](./10-AI-Intermediate.md)
