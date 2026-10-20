# Cactus MCP server

Cactus (heycactus.ai) learns a product from its codebase, answers its customers live, and keeps its help site and changelog current with every release. Its MCP server lets your team reach that knowledge from Claude, ChatGPT, Cursor, VS Code or any other MCP client.

This repository holds no server code. It lists Cactus's hosted MCP server: how to connect, the tools it offers, and the manifests MCP directories read.

## Connect

- Server: `https://mcp.heycactus.ai/mcp`
- Transport: Streamable HTTP
- Sign-in: OAuth 2.0 with your Cactus account (Google or GitHub). Dynamic client registration and client ID metadata documents are supported, with PKCE (S256).

Step-by-step setup for each AI client: https://heycactus.ai/docs/connect-an-ai-client

In Claude Code:

```sh
claude mcp add --transport http cactus https://mcp.heycactus.ai/mcp
```

In Cursor, add this to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "cactus": {
      "url": "https://mcp.heycactus.ai/mcp"
    }
  }
}
```

You need a Cactus team with a product built from a GitHub repository. Cactus is about to launch; its closed beta started on 16 Oct 2026. Join the waitlist at https://heycactus.ai.

## Tools

On `https://mcp.heycactus.ai/mcp`, signed in:

| Tool | What it does |
|---|---|
| `list_products` | List your team's products |
| `search_help` | Search the product's published help pages |
| `read_page` | Read a help page |
| `list_topics` | List help topics |
| `read_timeline` | Read the product's dated record of releases |
| `lookup_map` | Read the product map Cactus keeps from your code |
| `search_conversations` | Search past customer conversations |
| `read_conversation` | Read a conversation |
| `search_evidence` | Search past customer conversations and imported help articles |
| `search`, `fetch` | Search, and fetch a result |
| `ask` | Ask Cactus a question. It answers from the published pages, the product map, the product knowledge and past conversations, and cites its sources |
| `start_investigation`, `get_investigation` | Investigate a question in the product's code and knowledge, and read the finding |

Every tool carries MCP annotations. No tool edits or deletes anything. Only `ask` and `start_investigation` aren't read-only, because each runs a new answer or investigation.

## Public help-center servers

Every product's public help center has its own server, with no sign-in: `https://mcp.heycactus.ai/p/<name>/mcp`. Cactus's own help center is `https://mcp.heycactus.ai/p/cactus/mcp`. It offers `search_help`, `read_page`, `list_topics`, `read_timeline`, `ask_help`, `contact_team`, `search` and `fetch`.

`ask_help` answers the way the help center answers a visitor. It starts from the published help pages and reads the product map, the code index and the code when those fall short. `contact_team` sends the team a message they can reply to.

## Links

- Website: https://heycactus.ai
- MCP: https://heycactus.ai/mcp
- Setup: https://heycactus.ai/docs/connect-an-ai-client
- Privacy: https://heycactus.ai/privacy
- Terms: https://heycactus.ai/terms
- Support: support@heycactus.ai

The files in this repository are under the MIT license.
