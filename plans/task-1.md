# Task 1 Plan: Call an LLM from Code

**Goal:** Build `agent.py` that takes a question → calls LLM → prints JSON with `answer` and `tool_calls`.

## 1. LLM Provider Choice
- Use **OpenRouter**
- Use **Claude Sonnet model** (it has free tokens)

## 2. Environment Setup
- Copy `.env.agent.example` → `.env.agent.secret`
- Add: `LLM_API_KEY`, `LLM_API_BASE`, `LLM_MODEL`
- Use `python-dotenv` to load them

## 3. Testing Strategy
- Manual: `uv run agent.py "What is REST?"` → check JSON output
- 1 regression test (pytest):
  - Run subprocess, capture stdout
  - Parse JSON, assert keys exist, `tool_calls` is list

## 4. Documentation
- `AGENT.md`: provider choice, setup steps, how to run, example

## 5. Git Workflow
- Branch from `main`: `task-1-call-llm`
- Commit plan first
- PR → partner review → merge