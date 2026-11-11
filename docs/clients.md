# Connect an MCP client

The TeX/Java endpoint is `/tex/java/mcp/v1/streamable-http`. For the local README launch command, use `http://127.0.0.1:8080/tex/java/mcp/v1/streamable-http`. Remote clients use the endpoint exposed by your deployment.

## GitHub Copilot in VS Code

Add this server to the workspace `.vscode/mcp.json`:

```json
{
  "servers": {
    "tex-java": {
      "type": "http",
      "url": "https://YOUR_MCP_HOST/tex/java/mcp/v1/streamable-http"
    }
  }
}
```

Replace the host placeholder and configure credentials using the client's supported mechanism and the engine's authentication settings. Keep secrets out of committed files.

Start `tex-java` through **MCP: List Servers**, enable its tools in Copilot Agent mode, and ask a TeX/Java question. Inspect tool calls and citations after content has been ingested and published.

## Other clients

Use the client's HTTP MCP transport and authentication configuration. Some clients use `mcpServers` instead of VS Code's `servers` object. Consult the pinned engine's `MCP-SERVER.md` for supported transports and tools.

A successful initialization confirms protocol connectivity; it does not establish that indexes contain TeX/Java content. Verify real retrieval after publication.
