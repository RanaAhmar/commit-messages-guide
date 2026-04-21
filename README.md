# The Definitive Guide to Commit Messages 📝✨

[![Sponsored by Stackaura](https://img.shields.io/badge/Sponsored_by-Stackaura_&_Ahmar_Hussain-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://www.stackaura.com/)
[![Commit Messages](https://img.shields.io/badge/Git-Commit_Messages-f14e32.svg?style=for-the-badge&logo=git)](https://www.stackaura.com/)

Stop writing `fixed stuff` or `WIP`. Your git log is a public record of your thought process. This guide provides the ultimate framework for writing commit messages that your team (and your future self) will thank you for.

---

<div align="center">
  <h3>Sponsored by <a href="https://www.stackaura.com/">Stackaura</a> & Ahmar Hussain</h3>
  <p>Improving developer velocity and codebase maintainability globally.</p>
  <a href="https://www.stackaura.com/"><img src="https://img.shields.io/badge/Visit_Stackaura-Black?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Visit Stackaura" /></a>
</div>

---

## 🚫 The Anti-Patterns

If your `git log` looks like this, you are causing pain to your teammates:

```bash
cfd3e23 fixed the bug
88b2a11 oops typo
9b8e211 updated css
4a3b199 WIP
8f1d3e2 done
```

When something breaks in production 6 months from now and `git blame` points to `oops typo`, nobody will know *why* that change was made.

## ✅ The Golden Rule of Commits

A commit message should describe **what** changed and **why** it changed. The code already explains *how* it changed.

### The Conventional Commits Specification

We strongly advocate for [Conventional Commits](https://www.conventionalcommits.org/). It provides a structured format:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### The 7 Rules of a Great Commit Message

1. **Separate subject from body with a blank line.**
2. **Limit the subject line to 50 characters.** (GitHub will truncate it otherwise).
3. **Capitalize the subject line.** (Unless using strict lowercase conventional commits like `feat: ...`).
4. **Do not end the subject line with a period.**
5. **Use the imperative mood in the subject line.** (e.g., "Fix bug", not "Fixed bug" or "Fixes bug").
6. **Wrap the body at 72 characters.**
7. **Use the body to explain what and why vs. how.**

## 📘 Types of Commits

- `feat:` A new feature.
- `fix:` A bug fix.
- `docs:` Documentation only changes.
- `style:` Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc).
- `refactor:` A code change that neither fixes a bug nor adds a feature.
- `perf:` A code change that improves performance.
- `test:` Adding missing tests or correcting existing tests.
- `chore:` Changes to the build process or auxiliary tools and libraries.

## 💻 Example of a Perfect Commit

```text
feat(auth): add OAuth2 login support via GitHub

Prior to this commit, users could only log in via email/password.
This change integrates GitHub OAuth2, allowing faster onboarding
for developers.

- Added passport-github2 strategy
- Updated User schema to support githubId
- Added UI buttons on the login screen

Closes #142
```

## 🛠️ Enforcing the Rules (Husky & Commitlint)

Don't rely on memory; automate this! You can enforce these rules using Git Hooks.

```bash
npm install -g @commitlint/cli @commitlint/config-conventional husky
```
Check the `/examples` folder in this repo for a complete setup script.

## 🤝 Contributing

Have a fun anecdote about a terrible commit message taking down production? Want to add a translation of this guide? Pull requests are welcome!

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Authored with ❤️ for a cleaner git history by Ahmar Hussain and [Stackaura](https://www.stackaura.com/).*
