# Shard Connector for Obsidian

Cursor plugin that connects agents to your [Obsidian](https://obsidian.md) vault through [Shard Connector](https://shardconnector.com), a hosted [Model Context Protocol](https://modelcontextprotocol.io/) server backed by Obsidian Sync.

Works in the Cursor editor, the Cursor CLI, and Cloud Agents without running Obsidian locally or installing the Local REST API plugin.

## Prerequisites

1. An Obsidian account with an active **Obsidian Sync** subscription.
2. A [Shard Connector](https://shardconnector.com) account connected to your vault.

## Install

1. Open **Customize** in Cursor and browse **Plugins**, or run `/add-plugin shard-connector` in chat.
2. Click **Install**.
3. Under **Customize -> MCPs**, click **Authenticate** next to the Obsidian server and sign in with the Google account you use on [shardconnector.com](https://shardconnector.com).

One sign-in connects both Local and Cloud environments in Cursor.

## MCP configuration

```json
{
  "mcpServers": {
    "Obsidian": {
      "type": "http",
      "url": "https://mcp.shardconnector.com/mcp"
    }
  }
}
```

Authentication uses OAuth 2.1 with dynamic client registration, so no API keys or secrets are stored in configuration files. Each user signs in with their own Shard Connector account and reaches their own vault.

## Capabilities

| Area | Tools |
| --- | --- |
| Search & browse | `list_files`, `search_notes` (path and full-text search across `.md`, `.canvas`, and `.base` files), `get_status` |
| Read | `read_note` (accepts vault paths and `obsidian://` URLs) |
| Create & edit | `create_note`, `create_folder`, `patch_note`, `add_to_note`, `write_note`, `edit_frontmatter` |
| Organize | `move_path` (updates wikilinks and markdown links across the vault), `trash_note`, `trash_folder`, `sync` |

## Local testing

Copy this directory into `~/.cursor/plugins/local/shard-connector` (Cursor skips symlinks that point outside `~/.cursor/plugins/local`) and run **Developer: Reload Window**.

## Links

- Homepage: https://shardconnector.com
- Cursor setup guide: https://shardconnector.com/guides/obsidian-cursor
- Support: https://shardconnector.com/support
- Privacy policy: https://shardconnector.com/privacy

Not affiliated with Obsidian.

## License

[MIT](LICENSE)
