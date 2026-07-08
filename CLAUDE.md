# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

---

# Project

**Project Name**

ai-customer-agent

**Description**

An open-source AI Customer Service Agent Framework for browser-based customer service platforms.

The goal is to use Browser Automation + LLMs to help customer service agents process conversations more efficiently.

Version 1 focuses on **reply suggestions only**. Human confirmation is always required before sending.

---

# Vision

Build a production-ready framework that can:

- Observe browser-based customer service systems
- Read customer conversations
- Generate AI reply suggestions
- Fill replies into the input box
- Wait for human confirmation
- Support multiple customer service platforms through adapters
- Support multiple LLM providers

---

# MVP Scope (V1)

## Included

- Browser automation (Playwright)
- One customer-service platform
- Adapter architecture
- Workflow orchestration
- Conversation memory (in-memory)
- OpenAI Compatible API
- Ollama
- Reply suggestion
- Human review
- Logging
- Configuration

## NOT Included

- Auto send
- Dashboard
- OCR
- Plugin Marketplace
- Multi-platform support
- RAG
- Database persistence

Keep V1 as simple as possible.

---

# Technology Stack

| Component | Technology |
|------------|------------|
| Language | Python 3.12+ |
| Browser | Playwright |
| Async | asyncio |
| HTTP | httpx |
| Configuration | pydantic-settings |
| Logging | structlog |
| Testing | pytest |
| Formatter | ruff |
| Type Checking | mypy (later stage) |
| Dependency Management | pip |

---

# Project Structure

```
src/
└── ai_customer_agent/
    ├── adapters/
    ├── browser/
    ├── config/
    ├── llm/
    ├── memory/
    ├── models/
    ├── review/
    ├── utils/
    └── workflow/

docs/
examples/
tests/
```

---

# Module Responsibilities

## browser

Wrap Playwright.

Responsible for:

- Browser lifecycle
- Page management
- DOM interaction
- Session management

---

## adapters

Platform-specific implementations.

Responsible for:

- Message parsing
- DOM selectors
- Conversation list
- Reply input
- Platform differences

---

## workflow

Business orchestration.

Responsible for:

- Scan
- Read
- Generate
- Review
- Fill reply

---

## llm

Unified LLM interface.

Support:

- OpenAI Compatible API
- Ollama

Future:

- Gemini
- Claude
- DeepSeek

---

## memory

Conversation context.

Responsible for:

- Current conversation
- Message history
- Context window

---

## review

Human-in-the-loop.

Responsible for:

- Reply review
- Approval
- Reject
- Future audit

---

## config

Application configuration.

Responsible for:

- Environment variables
- Settings
- API Keys

---

## models

Pure domain models.

Examples:

- Message
- Conversation
- ReplySuggestion

No business logic.

---

## utils

Shared utilities.

Examples:

- Logger
- Retry
- Time
- Helpers

---

# Architecture Principles

The project must follow:

- Clean Architecture
- SOLID
- DRY
- KISS
- Dependency Injection
- High Cohesion
- Low Coupling

Rules:

- Domain models must not depend on infrastructure.
- Browser and LLM are infrastructure.
- Workflow coordinates modules.
- Adapters depend on abstractions.
- No circular imports.

---

# Coding Standards

Every Python file should:

- Use type hints
- Use dataclass or Pydantic models
- Avoid mutable default arguments
- No wildcard imports
- Keep functions small
- Prefer composition over inheritance
- Public APIs require docstrings

Naming:

| Item | Style |
|------|-------|
| File | snake_case |
| Function | snake_case |
| Variable | snake_case |
| Class | PascalCase |
| Constant | UPPER_SNAKE_CASE |

---

# AI Development Workflow

This repository follows an AI-assisted development process.

Architecture Design

↓

Module Design

↓

Implementation

↓

Unit Tests

↓

Code Review

↓

Git Commit

Rules:

- Never implement before architecture is clear.
- Implement one module at a time.
- Keep commits small.
- Do not mix refactoring with new features.
- Every module should be reviewed before merge.

---

# Development Order

The recommended implementation order is:

1. Browser
2. Adapter
3. Workflow
4. LLM
5. Memory
6. Review
7. Configuration
8. Examples

Do not change this order unless necessary.

---

# Testing

Every core module should include tests.

Testing levels:

- Unit Test
- Integration Test
- End-to-End Test

Use:

- pytest
- pytest-asyncio

Browser tests should use Playwright.

---

# Commit Convention

Use Conventional Commits.

Examples:

feat(browser): implement browser session

fix(adapter): fix unread message parsing

docs(readme): update quick start

refactor(workflow): simplify pipeline

test(llm): add provider tests

---

# Design Philosophy

Human-in-the-loop first.

The framework should assist customer service agents,
not replace them.

Keep Version 1 simple.

Design for extensibility.

Avoid over-engineering.

Simple is better than clever.

---

# Future Roadmap

## V1

- Single platform
- Reply suggestion
- Human review

## V2

- Multiple platforms
- Persistent memory
- Multiple LLM providers

## V3

- Plugin system
- Browser Use
- Computer Use
- Rule engine
- Analytics Dashboard

---

# Notes for Claude Code

When implementing code:

- Respect module boundaries.
- Do not introduce unnecessary abstractions.
- Prefer readability over cleverness.
- Generate production-quality code.
- Add tests for public APIs.
- Explain important design decisions in comments when necessary.