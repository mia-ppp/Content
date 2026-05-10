# Composio Integration Guide

Composio is a single MCP server that gives your AI agent access to Notion, Google Docs, Slack, and 200+ other tools — handling all OAuth and authentication for you.

---

## Why Composio

Notion, Google Docs, and Slack don't have native MCP servers. Without Composio, your agent can write a humanized draft but can't push it back to where you actually work. With Composio, it can read your Notion page, rewrite it, and update it in place — all in one step.

---

## Setup

### Step 1 — Create a Composio account

Go to [composio.dev](https://composio.dev) and sign up.

### Step 2 — Connect your tools

In the Composio dashboard, connect:
- **Notion** — click Connect, authorize with your Notion account
- **Google Docs** — click Connect, authorize with your Google account
- **Slack** — click Connect, authorize with your Slack workspace

Each connection uses OAuth — Composio handles token storage and refresh automatically.

### Step 3 — Get your API key

In the Composio dashboard go to **Settings → API Keys** and copy your key.

### Step 4 — Add Composio as an MCP server

**Claude Desktop** — add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "composio": {
      "command": "npx",
      "args": ["@composio/mcp@latest", "start", "--api-key", "YOUR_COMPOSIO_API_KEY"]
    }
  }
}
```

**Cursor** — add to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "composio": {
      "command": "npx",
      "args": ["@composio/mcp@latest", "start", "--api-key", "YOUR_COMPOSIO_API_KEY"]
    }
  }
}
```

Replace `YOUR_COMPOSIO_API_KEY` with your actual key from Step 3.

After saving, fully quit and reopen the app.

---

## Verifying the Connection

Ask your agent: "List my Notion pages" or "What Slack channels do I have access to?"

If it returns results — Composio is working.

---

## Common Writing Workflows

**Humanize a Notion draft:**
> "Read the draft on my Notion page [page name], humanize it using the humanizer skill, and update the page with the rewritten version."

**Humanize a Google Doc:**
> "Open my Google Doc [doc name], run the humanizer on it, and replace the content with the cleaned version."

**Share to Slack after editing:**
> "Humanize this draft and post the final version to the #content channel on Slack."

---

## Available Toolkits

See `../composio/marketing-tools.md` for the full list of Composio toolkit names, auth methods, and available actions.

---

## Troubleshooting

**Agent can't find Composio tools**
- Make sure you fully quit and reopened the app after adding the MCP config
- Check your API key is correct — no extra spaces or quotes

**Authorization expired**
- Go to the Composio dashboard and reconnect the tool that's failing
- Composio usually handles token refresh automatically, but manual reconnection fixes most auth errors

**Action not available**
- Run `npx composio actions list --app NOTION` in Terminal to see all available actions for that toolkit
- Check `composio/marketing-tools.md` for the depth rating of each tool

---

## Pricing

Composio has a free tier that covers basic usage. Check [composio.dev/pricing](https://composio.dev/pricing) for current plan details as pricing may have changed.
