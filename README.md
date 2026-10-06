# Suparelay

Make international calls from your AI agent. Suparelay calls any phone number in the world from your browser, with no app to install and no SIM card. The person you call answers on their normal phone. Ask your agent to call a phone number or a country: Suparelay gives the price per minute and a Call link. The link opens the Suparelay dialer in your browser with the number ready, and you make the call on [suparelay.app](https://suparelay.app).

Setup guide: [suparelay.app/ai/mcp](https://suparelay.app/ai/mcp)

## Install in Cursor

**Marketplace:** open **Customize** in the Cursor sidebar, search for Suparelay, and select **Install**.

**Manual:**

1. Clone this repository into `~/.cursor/plugins/local/suparelay`.
2. Run **Developer: Reload Window**.
3. Open **Customize** and confirm that the `suparelay` MCP server is on.

## Install in any MCP client

Add a remote MCP server with this URL. It uses Streamable HTTP and needs no sign-in.

```text
https://suparelay.app/mcp
```

Or give your agent this prompt:

```text
Fetch and follow the instructions to set me up with Suparelay from https://suparelay.app/mcp/setup.md
```

## Tools

Both tools are read-only. The call itself happens on suparelay.app.

| Tool                      | What it returns                                                                 |
| ------------------------- | ------------------------------------------------------------------------------- |
| `get_call_price`          | The price per minute for a phone number, and a Call link to the browser dialer. |
| `get_country_call_prices` | The landline and mobile prices for a country, and a Call link.                  |

## Repository contents

| Path          | Purpose                                                              |
| ------------- | -------------------------------------------------------------------- |
| `plugin.json` | Agent Plugins manifest for Cursor.                                   |
| `mcp.json`    | MCP server for Cursor: `https://suparelay.app/mcp`.                  |
| `server.json` | Official MCP Registry entry `app.suparelay/suparelay`.               |
| `chatgpt/`    | ChatGPT plugin for the ZIP upload: `https://suparelay.app/chatgpt/mcp`. |

## Building the ChatGPT ZIP

```sh
cd chatgpt && zip -r ../suparelay-chatgpt.zip .
```

Upload `suparelay-chatgpt.zip` at [platform.openai.com/plugins](https://platform.openai.com/plugins). Git ignores the ZIP.

## Support

[suparelay.app/support](https://suparelay.app/support) · [Privacy](https://suparelay.app/privacy) · [Terms](https://suparelay.app/terms)

## License

MIT. Copyright 2026 Kollektiv LLC.
