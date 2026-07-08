# AI Customer Agent

> An open-source Browser Agent Framework for browser-based customer service platforms.

[![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()
[![Status](https://img.shields.io/badge/Status-Under%20Development-orange.svg)]()

## Overview

AI Customer Agent is an open-source framework that combines **Browser Automation** and **Large Language Models (LLMs)** to assist customer service agents working on browser-based customer service systems.

Instead of replacing human agents, the framework acts as an AI assistant:

- Reads new customer messages from the browser
- Understands conversation context
- Generates reply suggestions using an LLM
- Fills the reply into the input box
- Waits for human confirmation before sending

The project is designed to be extensible, allowing support for multiple customer service platforms and multiple LLM providers through a unified architecture.

---

## Features

### Browser Automation

- Playwright-based browser control
- Multi-session support
- DOM observation
- Message monitoring

### Adapter Architecture

- Platform-independent design
- One adapter per customer service platform
- Easy to extend

### LLM Integration

- OpenAI Compatible API
- Ollama (local models)
- Multiple providers (planned)

### Human Review

- AI generates reply suggestions
- Human reviews before sending
- Safety-first workflow

### Conversation Memory

- Maintain conversation context
- Multi-turn dialogue support

---

## Architecture

```
Browser
    │
    ▼
Adapter
    │
    ▼
Workflow
    │
    ├────────► Memory
    │
    ├────────► LLM
    │
    ▼
Review
    │
    ▼
Human
```

---

## Project Structure

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
```

---

## Roadmap

### Version 1

- Browser abstraction
- Playwright implementation
- One platform adapter
- OpenAI Compatible API
- Ollama support
- Human review
- Reply suggestion

### Version 2

- Multiple platform adapters
- Persistent conversation memory
- More LLM providers
- Workflow enhancements

### Version 3

- Plugin system
- Browser Use
- Computer Use
- Analytics Dashboard

---

## Development

Clone the repository:

```bash
git clone https://github.com/azhqiang-alt/ai-customer-agent.git

cd ai-customer-agent
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate:

macOS / Linux

```bash
source .venv/bin/activate
```

Windows

```bash
.venv\Scripts\activate
```

Install dependencies:

```bash
pip install -e .
```

---

## Design Principles

- Clean Architecture
- SOLID
- Dependency Injection
- Human-in-the-loop
- Extensible by Design
- Platform Agnostic
- LLM Agnostic

---

## Current Status

This project is currently under active development.

Version 1 focuses on building a stable browser automation framework for customer service systems.

Auto-send is intentionally **not** included in Version 1.

---

## Contributing

Contributions are welcome.

If you'd like to:

- add a new platform adapter
- improve browser automation
- support another LLM provider
- fix bugs
- improve documentation

please feel free to open an Issue or submit a Pull Request.

---

## License

MIT License

---

## Author

Maintained by **Jack Zhang**

GitHub:

https://github.com/azhqiang-alt