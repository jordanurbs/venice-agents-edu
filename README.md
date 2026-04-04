# Venice AI API — Complete Agent Reference

A single-page, comprehensive reference for AI agents to use the [Venice AI](https://venice.ai) API. Covers every endpoint, every model type, and every gotcha an agent will encounter.

**Live:** [venice-agents-edu.netlify.app](https://venice-agents-edu.netlify.app)

## What This Is

An agent-friendly HTML page designed to be the **only resource an AI agent needs** to use the entire Venice API — text, image, video, audio, embeddings, and beyond.

Built from the ground up based on:
- [docs.venice.ai](https://docs.venice.ai) (official documentation)
- [docs.venice.ai/llms.txt](https://docs.venice.ai/llms.txt) (LLM-readable index)
- [Venice API Swagger spec](https://api.venice.ai/doc/api/swagger.yaml)
- Agent stress-testing (simulated naive agent walkthrough)
- [Mochi accessibility audit](https://docs.google.com/document/d/1) (agent discoverability report)

## What's Covered

| Section | Description |
|---------|-------------|
| **Agent Pitfalls** | Critical gotchas (text-only `/models`, `?type=audio` bug, invisible STT, image API incompatibility) |
| **Model Discovery** | How to query `/models` by type, recommended defaults per capability |
| **Quickstart** | API key setup, SDK install, first request in Python/JS/cURL |
| **Chat Completions** | Full request/response spec with all parameters |
| **Venice Parameters** | `venice_parameters` extensions (web search, characters, reasoning) |
| **Streaming** | SSE streaming examples |
| **Structured Responses** | JSON schema mode with gotchas |
| **Reasoning Models** | Effort levels, model support matrix, disabling reasoning |
| **Vision / Multimodal** | Image + text input |
| **Function / Tool Calling** | Complete round-trip example (request → tool_calls → feed result → final) |
| **Web Search & Scraping** | Enable search, citations, X search |
| **Image Generation** | Request params, response schema, save-to-file, binary mode |
| **Image Editing & Upscaling** | Edit, multi-edit, upscale, background removal — all with working examples |
| **Audio (TTS, STT, Music)** | TTS with 60+ voices, STT multipart, music async queue/retrieve |
| **Video Generation** | Full async flow: quote → queue → poll → download with Python loop |
| **Embeddings** | Request, response schema, 1024 dimensions, batch input |
| **Characters API** | List, filter, and use character personas |
| **Privacy Architecture** | Zero data retention, decentralized compute |
| **TEE & E2EE Models** | Attestation verification, E2EE implementation steps |
| **Prompt Caching** | Provider behavior, `prompt_cache_key`, cache stats |
| **Models Reference** | Recommended models by use case |
| **Pricing** | Text, image, audio, video pricing tables |
| **Rate Limits** | Tiers, headers, abuse protection |
| **Error Codes** | All error codes with response body examples |
| **Response Headers** | Balance, deprecation, rate limit headers |
| **Agent Frameworks** | Eliza, Coinbase AgentKit, OpenClaw, LangChain |
| **Claude Code Router** | Full setup with config.json |
| **Venice MCP Server** | Official MCP server for AI agents |

## OpenAI Compatibility Quick Reference

| Endpoint | Drop-in? | Notes |
|----------|----------|-------|
| `/chat/completions` | ✅ Yes | Tools, streaming, structured output all work |
| `/audio/speech` | ✅ Yes | Same format as OpenAI TTS |
| `/audio/transcriptions` | ✅ Yes | Same multipart format |
| `/embeddings` | ✅ Yes | Same request/response |
| `/models` | ⚠️ Partial | Defaults to text-only — must filter by `?type=` |
| `/image/generate` | ❌ No | Different path and response format |
| `/video/queue` | ❌ No | Venice-specific async pattern |

## Deployment

Hosted on Netlify. To redeploy:

```bash
netlify deploy --prod --dir=.
```

## Source

Single file: `index.html` — no build step, no dependencies.
