# `agent.py` Documentation

## Configuration

The agent loads its configuration from `.env.agent.secret`:

| Variable | Purpose |
| -------- | ------- |
| `LLM_API_KEY` | API key to authenticate with the LLM provider |
| `LLM_API_BASE` | Base endpoint URL for the LLM API |
| `LLM_MODEL` | Which model to use (e.g., qwen3-coder-plus) |
| `LLM_TEMPERATURE` | Controls randomness in responses (0.0–1.0) |

## Usage

Pass your question as a command-line argument:

```bash
uv run agent.py "Hello, how are you?"
```

## How It Works

1. Reads settings from `.env.agent.secret`
2. Sends your question to the configured LLM provider
3. Waits for the model's response

## Output Format

The agent prints a single JSON line to stdout:

```json
{
  "answer": "I'm doing well, thank you for asking!",
  "tool_calls": []
}
```

- `answer`: The LLM's response to your question
- `tool_calls`: Reserved for future use (always empty in this version)

