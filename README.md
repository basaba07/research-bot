# Research Bot

An autonomous research assistant built on [Hermes](https://hermes-agent.nousresearch.com). Monitors arXiv, summarizes papers, and delivers weekly digests on configurable topics.

## Features

- arXiv paper search and summarization
- Weekly digest of new research (Monday 8am by default)
- Citation lookup and cross-referencing
- Data science notebook integration via Jupyter

## Requirements

| Variable | Description | Required |
|---|---|---|
| `ANTHROPIC_API_KEY` | API key for your model provider | Yes |
| `SERPAPI_KEY` | SerpAPI key for web search | No |

> If using a different provider, update `model.provider` and `model.default` in `config.yaml`.

## Installation

```bash
hermes install basaba07/research-bot
```

## Configuration

Edit `config.yaml` to set your model and provider:

```yaml
model:
  default: claude-sonnet-4-6
  provider: anthropic
```

For local models (e.g. Ollama), uncomment the `base_url` and `custom_providers` sections in `config.yaml`.

## Scheduled Tasks

| Job | Schedule | Description |
|---|---|---|
| `weekly-digest` | Mon 8am | arXiv digest for configured topics |

To change topics, edit the `prompt` field in `cron/weekly-digest.json`.
