# Helena

The official Cursor and Grok Bot plugin for
[Helena by Enrich Labs](https://enrichlabs.ai).

Helena is an AI marketing teammate that works with the brand, context, and
integrations in your Enrich Labs account. Use it to research opportunities,
plan campaigns, create content, analyze results, and carry marketing work from
an initial request through a finished deliverable.

## Install

### Grok Bot

1. Open **Marketplace** in Grok Bot.
2. Search for **Helena** and select **Add**.
3. Select **Authorize**, sign in to Enrich Labs, choose the brand to connect,
   and approve access.

The installed plugin is available to every Bot on the same Grok Bot account.

### Cursor

1. Open **Cursor Settings → Plugins**.
2. Search for **Helena** and select **Install**.
3. Complete the Enrich Labs sign-in and brand-selection flow.

## Requirements

- An Enrich Labs account with a paid plan that includes hosted MCP access.
- Access to the brand selected during authorization.
- Any third-party services Helena uses must already be connected in Enrich
  Labs and remain subject to their own permissions.

## How it works

The plugin connects to Enrich Labs' hosted, Streamable HTTP MCP server:

```json
{
  "mcpServers": {
    "helena": {
      "type": "http",
      "url": "https://enrichlabs.ai/mcp"
    }
  }
}
```

Authentication uses OAuth with PKCE. No Enrich Labs password, API key, or
access token is stored in this repository. The authorization screen shows the
brand being connected before access is granted.

Helena runs longer agent tasks asynchronously. A client starts a turn, checks
its progress, and receives the final response and any generated assets when
the turn completes. Available actions depend on the connected Enrich Labs
brand, plan, integrations, and the permissions of the authorizing user.

## Example requests

- "Research this week's most important conversations in our market and brief
  me on three content opportunities."
- "Turn this product announcement into a launch plan and draft the channel
  assets."
- "Analyze our recent campaign results and recommend what to test next."
- "Create an on-brand social campaign for this offer and prepare it for my
  review."

Review consequential actions and generated material before publishing or
sending. Helena cannot exceed the permissions of the connected accounts.

## Privacy and support

- [Privacy policy](https://www.enrichlabs.ai/privacy)
- [Terms of service](https://www.enrichlabs.ai/terms)
- [MCP setup](https://enrichlabs.ai/mcp)
- Support: [support@enrichlabs.ai](mailto:support@enrichlabs.ai)

## License

[MIT](LICENSE)
