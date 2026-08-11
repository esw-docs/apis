---
description: >-
  Connect AI clients to the ESW MCP server, configure OAuth or service tokens,
  and use approved ESW knowledge tools.
hidden: true
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: false
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# Model Context Protocol (MCP)

The ESW Model Context Protocol server provides retrieval tools against the sanctioned ESW documentation corpus, allowing assistants to ground their responses in approved material

## Connect to the ESW MCP <a href="#connect-to-the-esw-mcp" id="connect-to-the-esw-mcp"></a>

### Cursor <a href="#cursor" id="cursor"></a>

<a href="https://cursor/anysphere.cursor-deeplink/mcp/install?name=esw&#x26;config=eyJ1cmwiOiAiaHR0cHM6Ly9tY3AuZXN3LmNvbS9tY3AifQ%3D%3D" class="button secondary">Install in Cursor</a>

Open Cursor <i class="fa-cursor">:cursor:</i> and click install. Alternatively, add the following to your `~/.cursor/mcp.json` file.&#x20;

{% embed url="https://cursor.com/docs" %}
Refer to Cursor docs for more info
{% endembed %}

{% code expandable="true" %}
```json
{
  "mcpServers": {"esw": {
      "url": "https://mcp.esw.com/mcp"
    }
  }
}
```
{% endcode %}

### VS Code <a href="#vs-code" id="vs-code"></a>

<a href="https://vscode.dev/redirect/mcp/install?name=esw&#x26;config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fmcp.esw.com%2Fmcp%22%7D" class="button secondary">Install in VS Code</a>

Open VS Code <i class="fa-vscode">:vscode:</i> and click Install. Alternatively, add the following to your `.vscode/mcp.json` file in your workspace. Refer to [VS Code docs](https://code.visualstudio.com/docs/copilot/customization/mcp-servers) for more information.

{% code expandable="true" %}
```json
{
  "servers": {"esw": {
      "type": "http",
      "url": "https://mcp.esw.com/mcp"
    }
  }
}
```
{% endcode %}

### Claude Code <a href="#claude-code" id="claude-code"></a>

To add MCP to Claude Code, run the following command.

{% code expandable="true" %}
```bash
claude mcp add --transport http esw https://mcp.esw.com/mcp
```
{% endcode %}

{% embed url="https://code.claude.com/docs/en/mcp#configure-mcp-servers" %}
Refer to Claude Code docs for more info
{% endembed %}

### ChatGPT <a href="#chatgpt" id="chatgpt"></a>

You can enable MCP servers on ChatGPT <i class="fa-chatgpt">:chatgpt:</i> if you have a Pro, Plus, Business, Enterprise, or Education account. Follow the [OpenAI documentation](https://platform.openai.com/docs/guides/developer-mode) for instructions. Use the following parameters when setting up your custom connector:

* The server URL is `https://mcp.esw.com/mcp`.
* Use `OAuth` as the connection mechanism.

The ESW MCP server also works with OpenAI’s Responses API when building autonomous agents or calling tools through custom runtimes.

{% embed url="https://developers.openai.com/api/docs/guides/developer-mode" %}

### Other <a href="#other" id="other"></a>

MCP is an open protocol supported by many clients. Consult your client’s documentation for connection guidance. Use the server URL `https://mcp.esw.com/mcp` and OAuth whenever possible. If your client cannot perform OAuth, request a service API key from the ESW MCP team and pass it in the `Authorization` header as a bearer token:

{% code expandable="true" %}
```json
"esw": {
  "url": "https://mcp.esw.com/mcp",
  "headers": {
    "Authorization": "Bearer <<YOUR_SERVICE_TOKEN>>"
  }
}
```
{% endcode %}

***

## OAuth <a href="#oauth" id="oauth"></a>

The ESW MCP server supports OAuth 2.1 with PKCE, optional Dynamic Client Registration, and API key authentication for service accounts. Most clients use the authorization code + PKCE grant to request scopes, while automated systems can register dynamically at `https://mcp.esw.com/register` or supply an administrator-issued API key. Choose OAuth for human-driven sessions, Dynamic Client Registration for self-service client onboarding, and API keys for tightly scoped automation.

## Autonomous Agents <a href="#autonomous-agents" id="autonomous-agents"></a>

If you’re building agentic software or integrating with orchestration frameworks, you can pass a service token or restricted API key as a bearer token to the MCP server.

{% code expandable="true" %}
```json
curl https://mcp.esw.com/mcp \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <<YOUR_SERVICE_TOKEN>>" \
  -d '{
      "jsonrpc": "2.0",
      "method": "tools/call",
      "params": {
        "name": "kb_search",
        "arguments": {"query": "reset VPN token", "top_k": 3}
      },
      "id": 1
  }'
```
{% endcode %}

## Tools <a href="#tools" id="tools"></a>

The server exposes the following [MCP tools](https://modelcontextprotocol.io/docs/concepts/tools). Enable operator confirmation inside your MCP client, and be cautious when chaining this server with others to avoid prompt-injection attacks. To request additional tools, email [ai-support@esw.com](mailto:ai-support@esw.com)

| Resource           | Tool       | Data source / API                        |
| ------------------ | ---------- | ---------------------------------------- |
| ESW Knowledge Base | kb\_search | Internal ESW knowledge base search index |

Each tool returns a structured payload containing the normalized query, result count, and an array of documents with page titles, URLs, content snippets, and relevance scores.

***

{% embed url="https://modelcontextprotocol.io/specification/2025-11-25" %}

Contact the [ESW MCP team](mailto:ai-support@esw.com)
