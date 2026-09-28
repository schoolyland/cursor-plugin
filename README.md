# Schoolyland for Cursor and Grok Bot

Run your WordPress course business from Cursor or Grok Bot. Once connected, you can ask for things in plain language and the agent works directly on your site: pages and Elementor layouts, WooCommerce products and orders, LearnDash courses and students, FluentCRM contacts and email campaigns, forms and SEO.

The plugin connects to the Schoolyland MCP server at `https://mcp.schoolyland.com/mcp`.

## Requirements

- A Schoolyland account with the MCP service set up for your site. You can set it up at [schoolyland.com/my-mcp](https://schoolyland.com/my-mcp/).
- Which tools you get depends on your plan (Free: read-only, Basic: read and write, Pro: all tools).

## Installation

### Cursor Marketplace

In Cursor, type `/add-plugin` in chat, search for **Schoolyland**, and install it.

### Grok Bot

Open **Plugins** in Grok Bot, find **Schoolyland**, add it, and click **Authorize**.

### From source (local development)

Cursor scans `~/.cursor/plugins/local/<plugin-name>/` for local plugins:

```bash
git clone https://github.com/schoolyland/cursor-plugin.git schoolyland-cursor-plugin
mkdir -p ~/.cursor/plugins/local
rsync -a --delete --exclude='.git' schoolyland-cursor-plugin/ ~/.cursor/plugins/local/schoolyland/
```

Then reload Cursor (`Cmd-Shift-P → Developer: Reload Window`) and check that `Customize → Plugins` lists **Schoolyland** and `Customize → MCPs` shows `schoolyland`.

## Connecting your site

The first time the agent uses the connection, a sign-in window opens:

1. Sign in to your Schoolyland account. The first time, we email you a one-time code.
2. Choose your site and approve the connection.

The plugin holds no password or secret — only the public server address. Sign-in uses OAuth 2.1 with PKCE, and the connection gets its own credentials on your site.

You can see and revoke every connected app under **Connected applications** at [schoolyland.com/my-mcp](https://schoolyland.com/my-mcp/).

## Usage

Ask in chat, or use the command:

```
/schoolyland Give me a weekly summary of my site
/schoolyland Draft an email campaign announcing my new course
```

The Schoolyland server instructs the agent to confirm with you before it changes anything. Page and post edits are backed up automatically and can be restored.

## Terms and privacy

- [MCP Terms of Service](https://schoolyland.com/mcp-terms/)
- [MCP Privacy Policy](https://schoolyland.com/mcp-privacy/)

## Support

Email [info@schoolyland.com](mailto:info@schoolyland.com).

## License

MIT
