# Parallel: agent access checklist

Domain: [parallel.ai](https://parallel.ai)

Use Parallel Search MCP to search the web and fetch pages from an MCP client.
This checklist covers the Search MCP; it does not describe access to other
Parallel APIs.

1. **Choose the access level.** For exploration and light use, connect to
   `https://search.parallel.ai/mcp` anonymously with no account or API key.
   Anonymous search uses Fast mode and has lower rate limits. See the
   [Search MCP installation guide](https://docs.parallel.ai/integrations/mcp/search-mcp#installation).
2. **Add the server to your MCP client.** Use the client's HTTP MCP transport
   with `https://search.parallel.ai/mcp` and no authentication. Follow the
   [client-specific setup instructions](https://docs.parallel.ai/integrations/mcp/search-mcp#installation)
   and add this server alongside any existing servers.
3. **Confirm the tools are available.** Check the client's connected-tool list
   for `web_search` and `web_fetch`. Ask it to find a current source on a topic,
   then fetch one of the returned URLs. The
   [tool reference](https://docs.parallel.ai/integrations/mcp/search-mcp#per-call-tool-parameters)
   explains the search objective, queries, and fetch URL inputs.
4. **Authenticate if you need higher limits.** Create an account at
   [Parallel Platform](https://platform.parallel.ai), obtain an API key, and
   configure the client's secret storage to send it as an
   `Authorization: Bearer <key>` header to `/mcp`. Alternatively, use
   `https://search.parallel.ai/mcp-oauth` for the browser OAuth flow in a
   compatible client. `/mcp-oauth` requires authentication and rejects anonymous
   requests. Follow the
   [authentication instructions](https://docs.parallel.ai/integrations/mcp/search-mcp#installation)
   for your client; keep API keys out of committed configuration.

These are service-specific reference steps. OAR v0 currently generates its UI
checklist from scan signals; loading Markdown approval-path files into that
checklist is not implemented yet.
