# Task 1 Plan: Call an LLM from Code

## Provider Choice
Using Qwen Code API on my VM. Free tier (1000 requests/day), works fine from here. Model: `qwen3-coder-plus` from the example.

## Implementation

**agent.py** will:
- Read question from CLI arg
- Load API settings from `.env.agent.secret` (API base, key, model)
- Call the LLM via OpenAI-compatible endpoint
- Print JSON: `{"answer": "...", "tool_calls": []}`
- Stderr for debug/errors

**Structure** is dead simple for now - just plumbing. No tools yet.

## Files
- `agent.py` - the CLI
- `AGENT.md` - docs: how it works, how to run
- `plans/task-1.md` - this file
- `tests/test_agent.py` - one test checking JSON output format

## Steps
1. Set up `.env.agent.secret` with VM proxy details
2. Write agent - requests library, env vars, json output
3. Add timeout (50s) to stay under 60s limit
4. Test manually
5. Write the regression test
6. Document in AGENT.md

The main trick: keep stdout clean, only the JSON. Everything else to stderr.