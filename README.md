# DeepSeek Web Search AI Agent — n8n

An AI-powered web-search workflow built with **n8n**, **DeepSeek**, **OpenRouter**, and **Firecrawl**.

## Workflow

```text
Chat Message
     ↓
  AI Agent
  ↙  ↓  ↘
DeepSeek  Memory  Structured Output
                 ↓
             Search Query
                 ↓
             Firecrawl
                 ↓
           HTTP Request
```

## Features

- Natural-language chat input
- DeepSeek V3.2 through OpenRouter
- Conversational memory
- Structured search-query output
- Firecrawl search
- HTTP API integration
- n8n AI Agent orchestration

## Tech Stack

- n8n
- DeepSeek V3.2
- OpenRouter
- Firecrawl
- Structured Output Parser
- HTTP APIs

## Setup

1. Import `deepseek-web-search-agent.json` into n8n.
2. Configure your own OpenRouter credential.
3. Configure your own Firecrawl credential.
4. Review the HTTP Request node before enabling it.
5. Replace `YOUR_WEBHOOK_OR_API_ENDPOINT` with an endpoint you own or have verified.
6. Test with non-sensitive queries.
7. Activate when ready.

## How It Works

The AI Agent generates an internet-search query. A structured output parser constrains the result to:

```json
{
  "search_query": "Internet search"
}
```

The query is passed to Firecrawl, and the resulting data is then sent to the configured HTTP endpoint.

### Important HTTP Endpoint Note

The original workflow contained a specific external endpoint. It has been replaced in this public version with:

`YOUR_WEBHOOK_OR_API_ENDPOINT`

Do **not** restore an endpoint unless you know and trust its owner and understand what data the workflow sends to it.

## Security

This public version excludes:

- OpenRouter credential references
- Firecrawl credential references
- n8n instance metadata
- n8n webhook IDs
- The original external HTTP endpoint

No API keys are included.

**Never commit API keys, access tokens, passwords, private webhook URLs, or sensitive user/search data to GitHub.**

## Screenshot

![DeepSeek Web Search AI Agent workflow](screenshots/workflow.png)

## Possible Improvements

- Return search results directly to the chat
- Add source citations
- Filter search results
- Restrict searchable domains
- Add error handling and rate limiting
- Authenticate the HTTP endpoint
- Validate HTTP responses
- Cache repeated searches

## License

MIT License
