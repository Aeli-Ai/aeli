# CLAUDE.md — AI Assistant Guide for Aeli-Ai/aeli

This file provides guidance for AI assistants (Claude and others) working in this repository.

---

## Repository Overview

**Repository:** `Aeli-Ai/aeli`
**Status:** Initialized — awaiting initial project setup.

This file was auto-generated to establish conventions before the project codebase is populated. Update each section as the project evolves.

---

## Git Conventions

### Branch Naming

AI-generated branches follow a strict naming convention:

```
claude/<task-slug>-<session-id>
```

Examples:
- `claude/claude-md-mm476qejq8oowbb5-2B7yK`
- `claude/fix-auth-bug-abc123xyz-K9mPQ`

**Rules:**
- All AI-generated branches must start with `claude/`
- Never push directly to `main` or `master`
- Never push to branches other than the one designated for your session

### Commit Messages

Write commit messages in the imperative mood with a concise subject line:

```
Add user authentication module

- Implement JWT token generation
- Add refresh token support
- Wire up login/logout endpoints
```

- Subject line: ≤ 72 characters
- Use body for context on *why*, not *what*
- Reference issue numbers where applicable: `Fixes #42`

### Git Workflow

```bash
# Fetch the target branch before starting work
git fetch origin <branch-name>

# Push with upstream tracking
git push -u origin <branch-name>

# If push fails due to network error, retry with exponential backoff
# 2s → 4s → 8s → 16s
```

---

## Development Workflow

> Update this section once the project stack is established.

### Getting Started

```bash
# Clone the repository
git clone http://local_proxy@127.0.0.1:56424/git/Aeli-Ai/aeli
cd aeli

# Install dependencies (update command when stack is known)
# npm install | pip install -r requirements.txt | cargo build | go mod download
```

### Running the Project

```bash
# Start development server (update when known)
# npm run dev | python main.py | cargo run | go run .
```

### Running Tests

```bash
# Run test suite (update when known)
# npm test | pytest | cargo test | go test ./...
```

### Linting & Formatting

```bash
# Lint (update when known)
# npm run lint | flake8 . | cargo clippy | golangci-lint run

# Format (update when known)
# npm run format | black . | cargo fmt | gofmt -w .
```

---

## Project Structure

> Update this section once source files are added.

```
aeli/
├── CLAUDE.md          # This file — AI assistant guide
├── README.md          # (to be created) Human-facing project overview
└── ...                # Source directories to be documented here
```

When populating this section, document:
- Purpose of each top-level directory
- Where to find entry points
- Where tests live
- Where configuration is stored

---

## Code Conventions

> Populate this section with project-specific conventions when the stack is decided.

### General Principles

- Prefer clarity over cleverness
- Keep functions small and single-purpose
- Avoid premature abstraction — three similar lines of code is better than a premature helper
- Only add comments where logic is not self-evident
- Validate at system boundaries (user input, external APIs) — trust internal code

### Security

- Never commit secrets, API keys, or credentials
- Always sanitize user input before use in queries or commands
- Avoid dynamic code evaluation (`eval`, `exec`, shell injection)
- Follow OWASP Top 10 principles

---

## AI Assistant Instructions

### What AI Assistants Should Do

- **Read before editing:** Always read a file before modifying it
- **Minimal changes:** Only modify what is directly requested or clearly necessary
- **No over-engineering:** Do not add features, refactoring, or improvements beyond what was asked
- **No unsolicited cleanup:** Do not add docstrings, comments, or type annotations to untouched code
- **No unnecessary files:** Avoid creating files unless absolutely required
- **Preserve style:** Match the existing code style of the file being edited

### What AI Assistants Should NOT Do

- Push to branches other than the designated `claude/` branch for the session
- Amend published commits (create new commits instead)
- Skip git hooks (`--no-verify`)
- Force-push without explicit user instruction
- Delete files, branches, or data without explicit confirmation
- Make destructive git operations (`reset --hard`, `clean -f`, `checkout .`) without confirmation
- Create `README.md` or other documentation files unless explicitly requested

### Asking for Clarification

Before starting, confirm if any of the following are unclear:
- Which branch to develop on
- Which files or modules are in scope
- Whether to run tests after changes
- Whether to push after completing work

---

## Updating This File

When the project grows, keep CLAUDE.md up to date by revising:

1. **Project Structure** — add new directories and their purposes
2. **Development Workflow** — add accurate install, run, and test commands
3. **Code Conventions** — document language/framework-specific patterns
4. **AI Instructions** — add project-specific guidance as patterns emerge

This file is the single source of truth for AI assistants working in this codebase. Keeping it accurate reduces ambiguity and improves the quality of AI-generated changes.
