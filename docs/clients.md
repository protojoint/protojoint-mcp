# Adding ProtoJoint to an AI app

Do the five steps in the [README](../README.md) first (sign in, have MCP calls, **AI connections…**, **Let AI apps control this tab**, keep the tab open). The server is `https://protojoint.ai/mcp`.

## Claude (claude.ai and Claude Desktop)

Settings › Connectors › **Add custom connector**, paste the server URL, and sign in to ProtoJoint when asked.

## Claude Code

Create an API key under **AI connections** (it is shown once, so copy it), then run:

```
claude mcp add --transport http protojoint https://protojoint.ai/mcp --header "Authorization: Bearer <API key>"
```

## Cursor

Add the server to Cursor's `mcp.json` with an API key:

```json
{
  "mcpServers": {
    "protojoint": {
      "url": "https://protojoint.ai/mcp",
      "headers": { "Authorization": "Bearer <API key>" }
    }
  }
}
```

This repository is also a Cursor plugin (`.cursor-plugin/plugin.json` and the `mcp.json` beside it), which adds the server without a key; a client that follows MCP's authorization flow signs you in itself.

## Gemini CLI

Install the extension from this repository:

```
gemini extensions install https://github.com/protojoint/protojoint-mcp
```

or add the server to Gemini CLI's `settings.json`:

```json
{
  "mcpServers": {
    "protojoint": { "httpUrl": "https://protojoint.ai/mcp" }
  }
}
```

Gemini CLI finds the OAuth sign-in from the server's 401 answer, so no key is needed.

## Any other MCP client

Add a remote server of type Streamable HTTP with the URL `https://protojoint.ai/mcp`. A client that follows MCP's authorization flow finds the sign-in itself (the 401 answer points to the server's protected-resource metadata; dynamic client registration and PKCE S256 are supported). A client that takes headers can use an API key as `Authorization: Bearer <API key>`.

## If a call fails

The error text says what went wrong: no tab open with the switch on, the tab did not answer in time, an unconfirmed email address, no MCP calls on the account (a free account gets them by sharing its designs and AI sessions), the month's calls used up, too many calls in a minute, or, among others, a tab closed while the call ran and the fair-use limit on a Max plan. The [privacy policy](https://protojoint.ai/legal/privacy.html) and the [documentation](https://protojoint.ai/docs/ai/) are the places to read more; <support@protojoint.ai> answers the rest.
