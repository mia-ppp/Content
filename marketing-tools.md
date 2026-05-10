# Composio Writing Tools

Mapping of Composio toolkits to writing and publishing use cases.

## Publishing & Editing

| Composio Toolkit | Auth | Key Writing Actions | Depth |
|-----------------|------|---------------------|-------|
| `NOTION` | OAuth 2.0 | Read/create pages, query databases, update blocks, search content | Deep |
| `GOOGLEDOCS` | OAuth 2.0 | Read documents, create documents, insert and replace text, format content | Deep |

## Communication

| Composio Toolkit | Auth | Key Writing Actions | Depth |
|-----------------|------|---------------------|-------|
| `SLACK` | OAuth 2.0 | Send messages, read channels, upload files, search messages | Deep |

---

## Coverage Depth Guide

- **Deep** — 20+ actions, covers most common operations, suitable for daily use
- **Medium** — 5-20 actions, covers core read operations and some writes
- **Shallow** — Under 5 actions, basic read-only access

---

## How the Agent Uses These Tools

| Task | Tool | What happens |
|------|------|-------------|
| Humanize a Notion draft | Notion | Agent reads the page, rewrites it, updates the blocks in place |
| Humanize a Google Doc | Google Docs | Agent reads the doc, rewrites it, inserts the clean version |
| Share a humanized draft | Slack | Agent posts the final version to a specified channel |

---

## Toolkit Reference

Each Composio toolkit name maps to its `TOOL_NAME` identifier on the Composio platform. To list available actions:

```bash
# List all actions for a toolkit
npx composio actions list --app NOTION

# Search for specific actions
npx composio actions list --app GOOGLEDOCS --search "insert"
```

For full setup instructions see `../integrations/composio.md`.
