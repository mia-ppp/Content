# Tools Registry

Index of all agent-compatible tools available in this repository. Organized by category.

All three tools connect via Composio — one setup gives the agent access to all of them. See `integrations/composio.md` for setup instructions.

---

## Publishing & Editing

| Tool | Auth | MCP via | Key Actions |
|------|------|---------|-------------|
| Notion | OAuth 2.0 | Composio | Create pages, update blocks, query databases, search, read content |
| Google Docs | OAuth 2.0 | Composio | Read documents, create documents, insert text, format content |

## Communication

| Tool | Auth | MCP via | Key Actions |
|------|------|---------|-------------|
| Slack | OAuth 2.0 | Composio | Send messages, read channels, upload files, search messages |

---

## When Skills Use Tools

| Skill | Tools it may use |
|-------|-----------------|
| `humanizer` | Notion, Google Docs — to read a draft and write back the humanized version |

---

## Adding New Tools

To add a new tool integration:
1. Add it to this registry table
2. Create `integrations/{tool-name}.md` with auth and action details
3. Update `composio/marketing-tools.md` if it's available via Composio
